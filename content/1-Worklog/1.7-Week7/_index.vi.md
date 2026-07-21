---
title: "Worklog Tuần 7"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---



### Mục tiêu tuần 7:

* Cấu hình DNS và HTTPS cho các ứng dụng được triển khai trên AWS.
* Cải thiện khả năng monitoring, auditing và governance bằng các dịch vụ vận hành AWS.
* Tìm hiểu mô hình tích hợp serverless theo hướng event-driven.
* Tìm hiểu backup, disaster recovery và tối ưu chi phí.
* Đánh giá kiến trúc AWS bằng AWS Well-Architected Framework.

### Các công việc cần triển khai trong tuần này:
| Ngày | Nội dung thực hiện | Ngày bắt đầu | Ngày kết thúc | Tài liệu tham khảo |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **Tìm hiểu DNS và HTTPS trên AWS**<br>- Tìm hiểu hosted zone, record, routing policy và health check trong **Amazon Route 53**.<br>- Request và validate certificate bằng **AWS Certificate Manager**.<br>- Cấu hình custom domain và HTTPS cho CloudFront Distribution.<br>- Kiểm tra DNS resolution và truy cập bảo mật. | 16/06/2026 | 16/06/2026 | [Amazon Route 53](https://aws.amazon.com/route53/)<br>[AWS Certificate Manager](https://aws.amazon.com/certificate-manager/) |
| 2 | **Tìm hiểu Monitoring và Governance**<br>- Tìm hiểu CloudTrail events, trails và audit history.<br>- Tìm hiểu AWS Config rules, resources và compliance status.<br>- Kiểm tra CloudWatch Logs, Metrics và Alarms.<br>- So sánh vai trò của CloudTrail, Config và CloudWatch. | 17/06/2026 | 17/06/2026 | [AWS CloudTrail](https://aws.amazon.com/cloudtrail/)<br>[AWS Config](https://aws.amazon.com/config/)<br>[Amazon CloudWatch](https://aws.amazon.com/cloudwatch/) |
| 3 | **Tìm hiểu kiến trúc Serverless theo hướng Event-driven**<br>- Tìm hiểu event, event bus, rule và target với **Amazon EventBridge**.<br>- Tìm hiểu state, execution và error handling với **AWS Step Functions**.<br>- Kết nối EventBridge với Lambda và SQS/SNS.<br>- So sánh xử lý synchronous và asynchronous. | 18/06/2026 | 18/06/2026 | [Amazon EventBridge](https://aws.amazon.com/eventbridge/)<br>[AWS Step Functions](https://aws.amazon.com/step-functions/) |
| 4 | **Tìm hiểu Backup, Disaster Recovery và Cost Optimization**<br>- Tìm hiểu backup plan, recovery point và vault với **AWS Backup**.<br>- Ôn lại RDS snapshot, Multi-AZ và các chiến lược khôi phục.<br>- Tìm hiểu Cost Explorer, AWS Budgets và Trusted Advisor.<br>- So sánh backup, high availability và disaster recovery objectives. | 19/06/2026 | 19/06/2026 | [AWS Backup](https://aws.amazon.com/backup/)<br>[AWS Cost Explorer](https://aws.amazon.com/aws-cost-management/aws-cost-explorer/)<br>[AWS Trusted Advisor](https://aws.amazon.com/premiumsupport/technology/trusted-advisor/) |
| 5 | **Tìm hiểu Cloud Concepts và AWS Well-Architected Framework**<br>- Ôn lại các khái niệm điện toán đám mây và các mô hình dịch vụ: IaaS, PaaS và SaaS.<br>- Tìm hiểu AWS Region, Availability Zone, scalability, elasticity và mô hình shared responsibility.<br>- Tìm hiểu sáu pillars của Well-Architected Framework: Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimization và Sustainability.<br>- Hiểu cách framework hỗ trợ ra quyết định kiến trúc và cải tiến liên tục. | 20/06/2026 | 20/06/2026 | [AWS Cloud Practitioner Essentials](https://aws.amazon.com/training/course-offerings/aws-cloud-practitioner-essentials/)<br>[AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)<br>[AWS Well-Architected Tool](https://aws.amazon.com/well-architected-tool/) |


### Kết quả đạt được tuần 7:

* Cấu hình DNS và hiểu quy trình xác thực chứng chỉ HTTPS cho ứng dụng trên AWS.
* Sử dụng CloudTrail, AWS Config và CloudWatch để auditing, kiểm tra compliance và giám sát vận hành.
* Hiểu cơ chế xử lý event-driven với EventBridge, Step Functions, Lambda và SQS/SNS.
* Tìm hiểu các phương pháp backup, disaster recovery, high availability và tối ưu chi phí AWS.
* Hiểu các cloud concepts cơ bản, AWS global infrastructure, mô hình shared responsibility và sáu pillars của AWS Well-Architected Framework.


