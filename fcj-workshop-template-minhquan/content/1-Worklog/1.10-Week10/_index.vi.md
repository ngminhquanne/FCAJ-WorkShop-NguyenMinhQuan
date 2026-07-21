---
title: "Worklog Tuần 10"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---



### Mục tiêu tuần 10:

* Triển khai application layer và database layer theo kiến trúc Cloud.
* Cấu hình các dịch vụ managed database, compute, load balancing và asynchronous messaging.
* Thiết lập luồng tích hợp giữa S3 Event Notification và SQS.

### Các công việc cần triển khai trong tuần này:
| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Triển khai **RDS DB Subnet Group** và **RDS PostgreSQL** trong private subnets để cung cấp database layer cho ứng dụng. | 03/07/2026 | 03/07/2026 | |
| 2 | Triển khai các **EC2 Application Servers** trong application layer và cấu hình kết nối đến cơ sở dữ liệu PostgreSQL. | 04/07/2026 | 04/07/2026 | |
| 3 | Triển khai **Application Load Balancer** để phân phối request đến các application servers và theo dõi trạng thái của target instances. | 05/07/2026 | 05/07/2026 | |
| 4 | Tạo **SQS Queue** và **Dead-Letter Queue (DLQ)** để hỗ trợ xử lý message bất đồng bộ và lưu trữ các message không được xử lý thành công. | 06/07/2026 | 06/07/2026 | |
| 5 | Cấu hình **S3 Event Notification** để gửi sự kiện từ S3 Bucket đến **SQS Queue** khi phát sinh hoạt động upload file. | 07/07/2026 | 07/07/2026 | |


### Kết quả đạt được tuần 10:

* Triển khai RDS DB Subnet Group và RDS PostgreSQL trong private subnets.
* Triển khai EC2 Application Servers và cấu hình kết nối đến cơ sở dữ liệu PostgreSQL.
* Triển khai Application Load Balancer để phân phối request đến các application servers.
* Tạo SQS Queue và Dead-Letter Queue (DLQ) cho quá trình xử lý message bất đồng bộ.
* Cấu hình S3 Event Notification để gửi sự kiện upload file đến SQS Queue.


