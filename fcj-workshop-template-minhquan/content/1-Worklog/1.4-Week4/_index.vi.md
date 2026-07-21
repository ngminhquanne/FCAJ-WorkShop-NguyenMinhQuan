---
title: "Worklog Tuần 4"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---



### Mục tiêu tuần 4:

* Tìm hiểu mô hình điện toán serverless với AWS Lambda.
* Xây dựng HTTP API bằng Amazon API Gateway.
* Tìm hiểu cơ chế tích hợp bất đồng bộ với Amazon SQS và Amazon SNS.
* Giám sát ứng dụng serverless bằng Amazon CloudWatch.
* Xây dựng và kiểm tra serverless API sử dụng API Gateway, Lambda, DynamoDB và CloudWatch.

### Các công việc cần triển khai trong tuần này:
| Ngày | Nội dung thực hiện | Ngày bắt đầu | Ngày kết thúc | Tài liệu tham khảo |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **Tìm hiểu AWS Lambda**<br>- Tìm hiểu điện toán serverless, Function, Runtime, Handler, Trigger và Execution Role.<br>- Tạo và invoke một Lambda Function.<br>- Kiểm tra execution log và cấu hình tài nguyên của Lambda. | 31/05/2026 | 31/05/2026 | [AWS Lambda](https://aws.amazon.com/lambda/)<br>[AWS Lambda là gì?](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |
| 2 | **Tìm hiểu Amazon API Gateway**<br>- Tìm hiểu API, Resource, Route, Method, Stage và Integration.<br>- Tạo HTTP API và kết nối với Lambda Function.<br>- Gửi request kiểm tra API và kiểm tra response status code. | 01/06/2026 | 01/06/2026 | [Amazon API Gateway](https://aws.amazon.com/api-gateway/)<br>[HTTP APIs](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api.html) |
| 3 | **Tìm hiểu Amazon SQS và Amazon SNS**<br>- Tìm hiểu message queue, topic, publisher và subscriber.<br>- Tạo SQS Queue và SNS Topic.<br>- Gửi message và tìm hiểu cơ chế xử lý bất đồng bộ.<br>- So sánh trường hợp sử dụng của SQS và SNS. | 02/06/2026 | 02/06/2026 | [Amazon SQS](https://aws.amazon.com/sqs/)<br>[Amazon SNS](https://aws.amazon.com/sns/)<br>[Workshop AWS SQS và SNS](https://github.com) |
| 4 | **Tìm hiểu Amazon CloudWatch**<br>- Tìm hiểu Metrics, Logs, Log Groups, Dashboards và Alarms.<br>- Kiểm tra log của Lambda và API Gateway.<br>- Tạo alarm cơ bản và sử dụng CloudWatch để giám sát hoạt động ứng dụng. | 03/06/2026 | 03/06/2026 | [Amazon CloudWatch](https://aws.amazon.com/cloudwatch/)<br>[Giám sát Lambda functions](https://docs.aws.amazon.com/lambda/latest/dg/monitoring-functions.html)<br>[Workshop AWS CloudWatch](https://github.com) |
| 5 | **Thực hiện Serverless Hands-on Lab**<br>- Xây dựng API sử dụng **API Gateway -> Lambda -> DynamoDB**.<br>- Kiểm tra các thao tác create, read, update và delete.<br>- Cấu hình CloudWatch logging và kiểm tra luồng request.<br>- Kiểm tra IAM permissions và xóa các tài nguyên không còn sử dụng. | 04/06/2026 | 04/06/2026 | [AWS Serverless Workshops](https://catalog.workshops.aws/)<br>[Amazon DynamoDB](https://aws.amazon.com/dynamodb/) |


### Kết quả đạt được tuần 4:

* Tạo và invoke được AWS Lambda Function với runtime và execution role phù hợp.
* Xây dựng được HTTP API bằng Amazon API Gateway và tích hợp với Lambda.
* Hiểu sự khác nhau giữa message queue của Amazon SQS và cơ chế pub/sub notification của Amazon SNS.
* Cấu hình được CloudWatch Logs, Metrics và Alarms để giám sát tài nguyên serverless.
* Hoàn thành Hands-on Lab serverless sử dụng API Gateway, Lambda, DynamoDB và CloudWatch.
* Thực hành kiểm tra IAM permissions, xác minh luồng request và dọn dẹp tài nguyên AWS.


