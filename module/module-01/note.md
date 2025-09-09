# Module 01 - Tổng Quan Về AWS

## Module 01-01 - Điện Toán Đám Mây Là Gì?
- **Điện toán đám mây**: Việc phân phối tài nguyên CNTT theo nhu cầu qua Internet (có phí).
- **Lợi ích**:
  - Tối ưu hóa chi phí
  - Tăng tốc độ phát triển nhờ tự động hóa và quản trị
  - Linh hoạt, dễ dàng thêm/bớt tài nguyên
  - Mở rộng quy mô toàn cầu

---

## Module 01-02 - Điều Gì Tạo Nên Sự Khác Biệt?
- AWS dẫn đầu về Cloud **13 năm liên tiếp** (tính đến 2023)
- Khác biệt về **tầm nhìn** và **văn hóa**
- Nguyên tắc: *“Khách hàng sẽ ngày càng trả ít tiền hơn cho cùng dịch vụ sử dụng”*
- Luôn ưu tiên **giá trị khách hàng** trong Leadership Principles

---

## Module 01-03 - Bắt Đầu Hành Trình Lên Mây
- Nhiều khóa học từ cơ bản đến nâng cao
- Có thể **tự học**, kết nối bạn bè để học hỏi
- Đăng ký AWS sớm để trải nghiệm qua **Free Tier**
- Nhà cung cấp uy tín: **Udemy, A Cloud Guru**

---

## Module 01-04 - Hạ Tầng Toàn Cầu Của AWS
- Một **Data Center** có thể chứa hàng chục nghìn máy chủ
- AWS sử dụng **thiết bị tối ưu hóa chuyên biệt**
- **Availability Zone (AZ)**:
  - Bao gồm 1+ Data Center
  - Được thiết kế **fault isolation** (không hỏng đồng thời)
  - Kết nối bằng đường riêng tốc độ cao
- AWS khuyến nghị triển khai ứng dụng trên **tối thiểu 2 AZ**
- **AWS Region**:
  - Tối thiểu 3 AZ
  - Hiện có hơn 25 Region toàn cầu
  - Các Region kết nối với nhau bằng **AWS Backbone Network**
  - Dữ liệu và dịch vụ **độc lập giữa các Region**
- **Edge Locations (POP)**: Cung cấp dịch vụ với **độ trễ thấp**
  - Dịch vụ đi kèm: **CloudFront (CDN), WAF, Route 53 (DNS)**

---

## Module 01-05 - Công Cụ Quản Lý AWS Services
- **AWS Management Console**: 
  - Login bằng **Root** hoặc **IAM User**
- **Support Center**: Tạo support case
- **AWS CLI**: Công cụ mã nguồn mở để quản lý dịch vụ bằng **command line**
- **AWS SDK**: Bộ thư viện hỗ trợ lập trình, quản lý vòng đời API

---

## Module 01-06 - Tối Ưu Hóa Chi Phí & AWS Support
- **Tối ưu chi phí**:
  - Chọn cấu hình và nơi lưu trữ phù hợp
  - Tận dụng giảm giá: **Reserved Instance, Savings Plan, Spot**
  - Xóa tài nguyên không dùng, bật/tắt tự động tài nguyên không cần 24/7
  - Sử dụng dịch vụ **Serverless**
  - Thiết kế kiến trúc tối ưu
  - Dùng **AWS Budgets** để theo dõi chi phí
  - Quản lý chi phí theo phòng ban/app bằng **Cost Allocation Tag**
  - Công cụ hỗ trợ: [AWS Pricing Calculator](https://calculator.aws)
- **Gói AWS Support**:
  - **Basic**
  - **Developer**
  - **Business**
  - **Enterprise**
  - Có thể nâng cấp nhanh chóng khi cần
