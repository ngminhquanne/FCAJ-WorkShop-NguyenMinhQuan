---
title : "Kiến trúc giải pháp"
date : 2024-01-01 
weight : 3
chapter : false
pre : " <b> 5.1.3 </b>"
---

## Mục tiêu

Mục này đưa sơ đồ kiến trúc vào ngay trong workshop để người đọc thấy rõ mỗi bước triển khai đang bám vào thành phần nào của hệ thống AWS cho dự án Smart Healthcare Appointment System.

## Sơ đồ tham chiếu

Sơ đồ dưới đây tóm tắt định hướng triển khai Smart Healthcare Appointment System được sử dụng xuyên suốt workshop:

![alt text](/images/2-Proposal/sodo.jpg)

## Giải thích theo từng lớp

1. **CloudFront và S3 static hosting** chịu trách nhiệm phân phối giao diện web tới bệnh nhân và bác sĩ.
2. **EC2** chạy backend API để xác thực yêu cầu đặt lịch, sinh presigned URL và điều phối trạng thái lịch khám.
3. **RDS PostgreSQL** lưu trữ metadata, trạng thái kiểm duyệt lịch hẹn và dữ liệu y tế phục vụ tìm kiếm.
4. **S3 object storage** lưu file hồ sơ bệnh án, kết quả xét nghiệm tách khỏi application server để luồng truyền file dung lượng lớn được mở rộng hơn.
5. **CloudWatch** cung cấp logs, metrics và alarms để hỗ trợ quan sát vận hành hệ thống y tế.

## Ý nghĩa đối với workshop

Mỗi phần trong workshop tương ứng với một mảnh của kiến trúc này:

1. Phần điều kiện tiên quyết xác minh CloudFront, S3, EC2 và RDS đã sẵn sàng.
2. Phần upload chứng minh trình duyệt có thể gửi file hồ sơ trực tiếp lên S3 thông qua presigned URL do backend cấp.
3. Phần kiểm thử và kiểm duyệt xác nhận metadata và trạng thái lịch hẹn luôn đồng bộ với nhau.
4. Phần quan sát vận hành và cleanup cho thấy môi trường y tế không chỉ được triển khai mà còn được theo dõi và dọn dẹp có kiểm soát.