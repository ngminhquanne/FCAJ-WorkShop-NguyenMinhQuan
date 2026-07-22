---
title : "Dịch vụ sử dụng"
date : 2024-01-01 
weight : 1
chapter : false
pre : " <b> 5.1.2 </b> "
---



## Các thành phần chính

Workshop Smart Healthcare Appointment System sử dụng các dịch vụ chính sau:

* **Amazon S3** để lưu trữ hồ sơ bệnh án, kết quả xét nghiệm, hình ảnh y tế và lưu static assets của frontend.
* **Amazon CloudFront** để phân phối giao diện web ổn định tới người dùng cuối.
* **Amazon EC2** để chạy backend API của Smart Healthcare Appointment System.
* **Amazon RDS PostgreSQL** để lưu metadata lịch hẹn, trạng thái hồ sơ, thông tin bệnh nhân và bác sĩ.
* **Amazon CloudWatch** để thu thập log, metric và alarm phục vụ giám sát vận hành hệ thống y tế.

## Vai trò của từng dịch vụ

Mỗi dịch vụ đảm nhiệm một nhiệm vụ riêng trong kiến trúc:

1. S3 tách phần lưu trữ file y tế ra khỏi application server, giúp giảm tải cho backend.
2. EC2 xử lý logic nghiệp vụ như xác thực đầu vào, sinh presigned URL đặt lịch và cập nhật metadata y tế.
3. RDS lưu dữ liệu có cấu trúc để phục vụ moderation, tìm kiếm lịch khám và đồng bộ trạng thái.
4. CloudFront hỗ trợ phân phối frontend nhanh hơn và phù hợp cho kịch bản truy cập qua trình duyệt của người bệnh/bác sĩ.
5. CloudWatch cho phép nhóm quan sát log backend, theo dõi metric và tạo alarm cho các tình huống bất thường.

## Ghi chú về bảo mật và vận hành

Trong báo cáo, kiến trúc này cũng cần nhấn mạnh hai điểm kỹ thuật quan trọng. Thứ nhất là nguyên tắc **least privilege**, nghĩa là mỗi thành phần chỉ nên được cấp đúng quyền cần thiết thay vì dùng quyền quá rộng hoặc hard-code access key vào source code. Thứ hai là khả năng vận hành, trong đó CloudWatch logs, metrics và alarm đóng vai trò chứng minh hệ thống y tế có được theo dõi chủ động chứ không chỉ triển khai xong là kết thúc.