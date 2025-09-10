# Module 02 - Dịch vụ mạng trên AWS

## Module 02-01 - AWS Virtual Private Cloud (VPC)

### Khái niệm cơ bản
- **Amazon VPC**: Cho phép bạn khởi chạy tài nguyên AWS trong một mạng ảo mà bạn định nghĩa.  
- **VPC thuộc một Region**: Khi tạo VPC, cần khai báo CIDR IPv4 (bắt buộc) và IPv6 (tùy chọn).  
- **Giới hạn**: Mỗi AWS Account có thể tạo tối đa **5 VPC trong 1 Region**.  
- **Mục đích**: Dùng để phân tách môi trường (Production / Dev / Test / Staging).  
  > Lưu ý: Nếu muốn tách biệt hoàn toàn tài nguyên giữa người dùng, cần **tách AWS Account**, vì chỉ nhiều VPC không đủ.  

### Subnet
- VPC có thể chia thành nhiều **Subnet** (mạng con).  
- Mỗi **Subnet chỉ thuộc một Availability Zone**.  
- CIDR Subnet là tập con của CIDR VPC.  
- AWS giữ lại **5 địa chỉ IP** trong mỗi Subnet:  
  - `10.10.1.0` → Network address  
  - `10.10.1.255` → Broadcast  
  - `10.10.1.1` → Router  
  - `10.10.1.2` → DNS  
  - `10.10.1.3` → Reserved cho tính năng tương lai  

### Route Table (Bảng định tuyến)
- Tập hợp các **Route** để xác định đường đi cho mạng.  
- AWS tạo sẵn **Default Route Table** khi khởi tạo VPC (không xóa được).  
- Default Route Table chứa 1 Route duy nhất: cho phép các Subnet trong cùng VPC liên lạc với nhau.  
- Có thể tạo **Custom Route Table**, nhưng không thể xóa Route mặc định (local).  

### Elastic Network Interface (ENI)
- **ENI** là một card mạng ảo gắn vào EC2.  
- Khi chuyển sang máy chủ khác, ENI vẫn giữ:  
  - Private IP  
  - Elastic IP  
  - MAC Address  

### Elastic IP Address (EIP)
- Địa chỉ IPv4 Public tĩnh, có thể gắn vào ENI.  
- **Có phí khi không sử dụng** (để tránh lãng phí).  

### VPC Endpoint
- Cho phép kết nối tài nguyên trong VPC với dịch vụ AWS **qua mạng private** (không qua Internet).  
- 2 loại:  
  - **Interface Endpoint**: Dùng ENI trong VPC với Private IP để kết nối dịch vụ.  
  - **Gateway Endpoint**: Dùng Route Table để định tuyến (chỉ hỗ trợ **S3** và **DynamoDB**).  

### Internet Gateway (IGW)
- Cổng để EC2 trong VPC có thể kết nối Internet.  
- Tự động **scale out**, **HA** do AWS quản lý (không cần cấu hình).  

### NAT Gateway
- Cho phép EC2 trong **Private Subnet** ra Internet/dịch vụ AWS khác.  
- **Chỉ outbound**, không nhận inbound.  

---

## Giải thích sơ đồ mô hình

![VPC Diagram](image.png)

- **Region**: Singapore (ap-southeast-1).  
- **VPC CIDR**: `10.10.0.0/16`.  

### Subnet
- **Public Subnets**:  
  - `10.10.1.0/24` (chứa NAT Gateway).  
  - `10.10.2.0/24`.  
- **Private Subnets**:  
  - `10.10.3.0/24` (chứa EC2 với ENI: `10.10.3.6`).  
  - `10.10.4.0/24`, `10.10.5.0/24`, `10.10.6.0/24`.  

### Gateway
- **Internet Gateway (IGW)**: cho Public Subnet kết nối trực tiếp Internet.  
- **NAT Gateway**: nằm trong Public Subnet, cho phép EC2 ở Private Subnet truy cập Internet (chỉ outbound).  

### Route Table
- **Public Route Table**:  
  - `10.10.0.0/16 → local`  
  - `0.0.0.0/0 → IGW`  
- **Private Route Table**:  
  - `10.10.0.0/16 → local`  
  - `0.0.0.0/0 → NAT Gateway`  

### Ý nghĩa
- EC2 trong **Private Subnet** (`10.10.3.6`) không ra Internet trực tiếp, mà đi qua **NAT Gateway**.  
- Public Subnet có thể truy cập Internet trực tiếp thông qua **IGW**.  
- Đây là mô hình **2-tier VPC**:  
  - Public Layer: Internet Gateway, NAT Gateway.  
  - Private Layer: EC2, Database, dịch vụ backend.  

---
## Module 02-02 - VPC Security and Multi-VPC Features

### 1. Security Group (SG)
- **Firewall ảo stateful** (có lưu trạng thái).
- Kiểm soát lưu lượng **inbound** (đến) và **outbound** (đi) của tài nguyên AWS.
- Rule giới hạn theo: **protocol, source, port, hoặc SG khác**.
- Chỉ hỗ trợ **allow rule** (không có deny).
- Áp dụng trực tiếp lên **Elastic Network Interface**.
- Mặc định:
  - Chặn tất cả **inbound**.
  - Cho phép tất cả **outbound**.

---

### 2. Network Access Control List (NACL)
- **Firewall ảo stateless** (không lưu trạng thái).
- Kiểm soát inbound và outbound ở mức **Subnet**.
- Rule giới hạn theo: **protocol, source, port**.
- Áp dụng trên **VPC Subnet**.
- Mặc định:
  - Cho phép tất cả inbound và outbound.
- Rule được đọc **từ trên xuống dưới**, match rule nào thì áp dụng rule đó.
- Hỗ trợ cả **allow** và **deny**.

---

### 3. VPC Flow Logs
- Cho phép **ghi lại metadata** của traffic đến/đi từ các ENI trong VPC.
- Export log sang **CloudWatch Logs** hoặc **S3**.
- Không ghi nội dung gói tin, chỉ log header (IP nguồn, IP đích, port, action).

---

### 4. VPC Peering
- Kết nối trực tiếp **2 VPC** để tài nguyên có thể liên lạc mà không qua Internet.
- **Tăng bảo mật**: traffic đi trong nội bộ AWS.
- Đặc điểm:
  - **Kết nối 1:1** (không có transitive routing).
  - Không hỗ trợ nếu 2 VPC bị **overlap CIDR**.
- Ứng dụng: kết nối VPC Dev ↔ VPC Analytics.

### Sơ đồ VPC Peering
![VPC Peering](image-1.png)

- **VPC 10.10.0.0/16** ↔ **VPC 10.11.0.0/16** qua Peering Connection.  
- Route Table:
  - VPC A: `10.11.0.0/16 → Peering Connection`
  - VPC B: `10.10.0.0/16 → Peering Connection`
- EC2 ở VPC A ↔ EC2 ở VPC B có thể giao tiếp trực tiếp.

---

### 5. Transit Gateway (TGW)
- **Hub trung tâm** để kết nối nhiều VPC và mạng On-premises.
- Giúp **đơn giản hóa mạng** và loại bỏ cấu hình peering phức tạp.
- **Transit Gateway Attachment (TGA)**: liên kết một Subnet trong AZ với TGW.
- Khi một subnet trong AZ kết nối TGW, các subnet khác cùng AZ cũng có thể sử dụng TGW.

### Sơ đồ Transit Gateway
![Transit Gateway](image-2.png)

- **Production VPC (10.10.0.0/16)**  
- **Staging VPC (10.11.0.0/16)**  
- **Dev VPC (10.12.0.0/16)**  
- **Test VPC (10.13.0.0/16)**  

→ Tất cả gắn vào **Transit Gateway**.  

- Route Table của TGW:
  - `10.10.0.0/16 → Attachment-1`
  - `10.11.0.0/16 → Attachment-2`
  - `10.12.0.0/16 → Attachment-3`
  - `10.13.0.0/16 → Attachment-4`

Các VPC có thể liên lạc chéo qua TGW (**hỗ trợ transitive routing**).

---
