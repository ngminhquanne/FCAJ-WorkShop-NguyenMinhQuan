---
title: "Blog 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---


![alt text](/images/3-BlogsPosted/blog1.jpg)

Blog thứ nhất tôi chọn dịch xoay quanh bài toán rất thực tế trong thiết kế kiến trúc phân tán: làm thế nào để xử lý các yêu cầu không đồng bộ, giảm tải cho backend và đảm bảo hệ thống không bị quá tải khi lượng truy cập tăng đột biến. Thay vì xử lý trực tiếp mọi request ngay lập tức, kiến trúc Event-Driven kết hợp với hàng đợi giúp các dịch vụ hoạt động linh hoạt, ổn định và tự động hóa quy trình xử lý.

Bài viết từ AWS giới thiệu cách kết hợp **Amazon API Gateway**, **Amazon SQS**, **AWS Lambda** và **Amazon CloudWatch** để xây dựng mô hình này. Đây là một hướng tiếp cận quan trọng giúp tối ưu hóa hiệu năng, giảm chi phí vận hành và nâng cao tính sẵn sàng cho ứng dụng trên Cloud.

## 1. Tổng quan giải pháp

Kiến trúc được mô tả trong bài sử dụng:

* **Amazon API Gateway** để tiếp nhận yêu cầu từ client và chuyển dữ liệu vào hàng đợi.
* **Amazon SQS** làm hàng đợi lưu trữ message theo thứ tự để chờ xử lý.
* **AWS Lambda** để xử lý dữ liệu tự động theo mô hình serverless.
* **Amazon DynamoDB** làm cơ sở dữ liệu lưu trữ kết quả phía backend.
* Bên cạnh đó còn có **Amazon CloudWatch** để giám sát hệ thống và **Amazon SNS** để gửi cảnh báo khi xảy ra sự cố.

Điểm đáng chú ý là hệ thống đã tách rời hoàn toàn thành phần tiếp nhận yêu cầu và thành phần xử lý nghiệp vụ, giúp ứng dụng không bị nghẽn cổ chai khi có lượng lớn request gửi đến cùng lúc.

## 2. Event-Driven Architecture hoạt động như thế nào?

Thay vì xử lý đồng bộ trực tiếp, kiến trúc hướng sự kiện cho phép các thành phần giao tiếp thông qua message:

* Người dùng gửi yêu cầu thông qua API Gateway.
* API Gateway đẩy request vào hàng đợi Amazon SQS thay vì gọi thẳng vào backend.
* SQS lưu trữ message an toàn và phân phối lần lượt cho Lambda.
* AWS Lambda tự động kích hoạt để xử lý từng message mà không cần quản lý máy chủ.
* Kết quả xử lý được lưu xuống cơ sở dữ liệu hoặc ghi nhận log trên CloudWatch.

Cách tiếp cận này giúp giảm tải trực tiếp cho backend, ngăn chặn tình trạng quá tải và đảm bảo không bị mất dữ liệu khi lưu lượng tăng đột biến.

## 3. Luồng xử lý chính

Từ nội dung bài viết, tôi tóm tắt luồng hoạt động như sau:

1. Client gửi request tới Amazon API Gateway.
2. API Gateway chuyển tiếp request vào hàng đợi Amazon SQS.
3. Amazon SQS lưu trữ message theo thứ tự và kích hoạt AWS Lambda.
4. AWS Lambda xử lý dữ liệu và lưu vào cơ sở dữ liệu backend.
5. Amazon CloudWatch thu thập log, metrics và gửi cảnh báo qua Amazon SNS nếu phát hiện lỗi hoặc bất thường.

Trong mô hình này, việc tách biệt các dịch vụ giúp tăng tính cô lập, nghĩa là nếu một thành phần gặp sự cố, các phần còn lại của hệ thống vẫn có thể hoạt động bình thường.

## 4. Điều tôi học được từ bài blog

Bài viết này làm tôi chú ý hơn tới việc thiết kế các tác vụ nền và xử lý bất đồng bộ trong hệ thống quy mô lớn. Với vai trò làm việc với hạ tầng và backend, tôi thấy kiến trúc Event-Driven với SQS và Lambda rất hữu ích trong các bài toán như:

* Xử lý các tác vụ nặng ngầm (background jobs) như gửi email, sinh báo cáo.
* Tiếp nhận lượng lớn request đăng ký lịch hẹn khám bệnh mà không làm sập server.
* Đồng bộ dữ liệu giữa các microservices một cách an toàn.

Ngay cả khi hệ thống chưa áp dụng toàn bộ mô hình phức tạp, việc hiểu tư duy hướng sự kiện giúp tôi thiết kế các luồng xử lý dữ liệu chịu tải tốt hơn.

## 5. Liên hệ với Smart Healthcare Appointment System

* **Smart Healthcare Appointment System** có thể áp dụng hàng đợi SQS để xử lý các luồng đặt lịch hẹn cao điểm, tránh tình trạng nghẽn hệ thống.
* Việc sử dụng AWS Lambda cho các tác vụ xử lý ngầm giúp tối ưu chi phí vì chỉ tính tiền khi mã nguồn chạy thực tế.
* Tích hợp CloudWatch giúp theo dõi sát sao hiệu năng và phát hiện sớm các sự cố trong quá trình vận hành hệ thống y tế.

## 6. Kết luận

Kiến trúc Event-Driven với Amazon SQS và AWS Lambda đang trở thành giải pháp cốt lõi để xây dựng các hệ thống phân tán chịu tải cao. Việc ứng dụng mô hình này giúp giảm thiểu độ trễ, tăng khả năng mở rộng và đảm bảo sự ổn định tuyệt đối cho các ứng dụng hiện đại.


Link bài đăng trong nhóm FCAJ: [https://www.facebook.com/groups/awsstudygroupfcj/permalink/2219595365472090/](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2219595365472090/)