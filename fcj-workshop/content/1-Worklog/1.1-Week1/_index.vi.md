---
title: "Worklog Tuần 1"
date: "2025-09-14"
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---
### Mục tiêu tuần 1:

- Làm quen thành viên FCJ, nắm nội quy và quy trình làm việc.
- Chuẩn bị môi trường làm workshop: VS Code, Hugo, Git, AWS CLI, SSH.
- Thiết lập tài khoản và bảo mật cơ bản: bật MFA, tạo Admin Group/User, cấu hình Console và Support cases.
- Nắm vững nền tảng Networking trên AWS: VPC, Subnet, Route Table, IGW, NAT GW, Security Group, NACL, Route 53.
- Thực hành Compute & kết nối: tạo EC2, kết nối SSH, lab Site‑to‑Site VPN.
- Thiết lập Hybrid DNS với Route 53 Resolver (AD, forwarders, resolver rules) cho tra cứu hai chiều.

### Các công việc cần triển khai trong tuần này:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 1 | - Làm quen thành viên FCJ <br> - Đọc và lưu ý nội quy/quy định <br> - Chuẩn bị công cụ làm workshop (VS Code, Hugo, ...) <br> - Giới thiệu về AWS & các khái niệm cơ bản | 08/09/2025 | 08/09/2025 | <https://van-hoang-kha.github.io/vi/> |
| 2 | - Tạo mới tài khoản AWS <br> - Kích hoạt MFA cho Tài khoản AWS <br> - Tạo Admin Group và Admin User <br> - Hỗ trợ Xác thực Tài khoản <br> - Khám phá và cấu hình AWS Management Console <br> - Tạo và Quản Lý Các Trường Hợp Hỗ Trợ trong AWS | 09/09/2025 | 09/09/2025 | <https://000001.awsstudygroup.com/vi/> |
| 3 | - Các dịch vụ mạng trên AWS: <br>&emsp; + VPC, Subnet, Route Table <br>&emsp; + Internet Gateway, NAT Gateway <br>&emsp; + Security Group & NACL <br>&emsp; + VPC Peering, Transit Gateway (khái niệm) <br>&emsp; + Elastic Load Balancing, Route 53 (DNS)| 10/09/2025 | 10/09/2025 | <https://github.com/tuanvu250/AWS-FCJ/blob/main/module/module-02/note.md> |
| 4 | - Thực hành EC2: <br>&emsp; + Tạo EC2 instance <br>&emsp; + Kết nối SSH <br>&emsp; + Cấu hình Site to Site VPN | 11/09/2025 | 11/09/2025 | <https://000003.awsstudygroup.com/> |
| 5 | - Thiết lập Hybrid DNS với Route 53 Resolver: <br>&emsp; + Kết nối đến RDGW <br>&emsp; + Triển khai Microsoft AD <br>&emsp; + Thiết lập DNS | 12/09/2025 | 12/09/2025 | <https://000010.awsstudygroup.com/> |
| 6 | - Thiết lập VPC Peering <br>&emsp; + Tạo kết nối Peering giữa VPCs <br>&emsp; + Cập nhật Route tables và kiểm thử kết nối | 13/09/2025 | 13/09/2025 | <https://000019.awsstudygroup.com/> |

### Kết quả đạt được tuần 1:

- Chuẩn bị môi trường làm việc; nắm các khái niệm AWS cơ bản (account, region, AZ, nhóm dịch vụ).
- Thiết lập tài khoản và bảo mật: tạo AWS account, bật MFA, tạo Admin Group/User, xác thực tài khoản, cấu hình Console và quản lý Support cases.
- Kiến thức Networking nền tảng trên AWS: VPC, Subnet, Route Table, Internet Gateway, NAT Gateway, Security Group, NACL, Elastic Load Balancing, Route 53; khái niệm về Peering, VPN, Transit Gateway.
- Thực hành Compute & kết nối: triển khai EC2 instance, kết nối SSH, cấu hình Site‑to‑Site VPN ở mức lab.
- Thiết lập Hybrid DNS với Route 53 Resolver: kết nối RDGW, triển khai Microsoft AD, cấu hình DNS/forwarders và Resolver rules cho tra cứu hai chiều.
- Hoàn thiện worklog tuần 1 và rà soát/dọn dẹp các tài nguyên không còn sử dụng.
