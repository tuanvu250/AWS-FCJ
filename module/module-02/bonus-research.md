# AWS Well-Architected Framework

## Khái niệm
AWS Well-Architected Framework là tập hợp các **nguyên tắc thiết kế**, **best practices** và **câu hỏi tự đánh giá** giúp bạn kiểm tra kiến trúc hệ thống có tuân thủ tiêu chuẩn vận hành và tối ưu trong môi trường điện toán đám mây hay không.

Framework đóng vai trò như một **bộ tự đánh giá (self-assessment)**. Sau khi trả lời, bạn sẽ nhận được báo cáo về:
- Mức độ tuân thủ với best practices
- Các điểm yếu trong kiến trúc
- Khuyến nghị cải thiện kèm theo tài liệu hướng dẫn chi tiết

## Các trụ cột chính
1. **Operational Excellence (Vận hành xuất sắc)**  
   - Khả năng giám sát, tự động hóa, và cải tiến liên tục trong vận hành.  
   - *Ví dụ*: Tự động rollback khi deploy thất bại.

2. **Security (Bảo mật)**  
   - Bảo vệ dữ liệu, hệ thống và tài sản số bằng cơ chế bảo mật đa lớp.  
   - *Ví dụ*: Sử dụng IAM roles thay vì hardcode credentials.

3. **Reliability (Độ tin cậy)**  
   - Đảm bảo hệ thống có thể phục hồi sau sự cố và đáp ứng nhu cầu thay đổi.  
   - *Ví dụ*: Dùng Multi-AZ cho RDS để dự phòng khi có sự cố.

4. **Performance Efficiency (Hiệu năng)**  
   - Sử dụng tài nguyên tối ưu để đáp ứng nhu cầu thay đổi về tải và công nghệ.  
   - *Ví dụ*: Dùng Auto Scaling cho EC2 khi lưu lượng tăng.

5. **Cost Optimization (Tối ưu chi phí)**  
   - Tránh lãng phí tài nguyên, chọn giải pháp chi phí hợp lý.  
   - *Ví dụ*: Dùng S3 Glacier để lưu trữ dữ liệu ít truy cập thay vì S3 Standard.

6. **Sustainability (Tính bền vững)** *(mới)*  
   - Giảm thiểu tác động môi trường thông qua sử dụng tài nguyên hiệu quả.  
   - *Ví dụ*: Tắt instance không cần thiết vào ban đêm.

## Ứng dụng thực tế
- Được dùng để đánh giá kiến trúc hệ thống trước khi triển khai hoặc trong quá trình vận hành.  
- Hỗ trợ tạo **báo cáo khuyến nghị chi tiết** ngay trong AWS Management Console.  
- Giúp định hướng cải tiến hệ thống theo **best practices chuẩn của AWS**.

---
