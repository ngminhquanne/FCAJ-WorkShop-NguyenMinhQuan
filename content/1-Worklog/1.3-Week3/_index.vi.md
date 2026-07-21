---
title: "Worklog Tuần 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---


### Mục tiêu tuần 3:

* Tìm hiểu cách tăng tốc website tĩnh trên Amazon S3 bằng Amazon CloudFront.
* Hiểu networking nâng cao trên AWS với Public Subnet, Private Subnet, NAT Gateway, Route Table, Security Group và Network ACL.
* Tìm hiểu cách phân phối traffic ứng dụng bằng Application Load Balancer.
* Tìm hiểu cơ sở dữ liệu quan hệ được quản lý và khả năng sẵn sàng cao với Amazon RDS.
* Tìm hiểu mô hình lưu trữ NoSQL với Amazon DynamoDB.
* Tìm hiểu cách Amazon ElastiCache cải thiện hiệu năng ứng dụng bằng cách giảm tải cho database.

### Các công việc cần triển khai trong tuần này:
| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **Tìm hiểu Amazon CloudFront và CDN**<br>- Tìm hiểu các khái niệm **CDN, Distribution, Origin, Behavior, Edge Location** và **Cache**.<br>- Tạo CloudFront Distribution với **Amazon S3** làm Origin.<br>- Truy cập website tĩnh S3 thông qua CloudFront.<br>- Thực hành **Cache Invalidation** sau khi cập nhật nội dung website.<br>- So sánh truy cập trực tiếp S3 với truy cập qua CloudFront. | 26/05/2026 | 26/05/2026 | [Amazon CloudFront](https://aws.amazon.com/cloudfront/)<br>[CloudFront với Amazon S3](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/GettingStarted.html)<br>[Workshop AWS CloudFront](https://catalog.workshops.aws/) |
| 2 | **Tìm hiểu AWS Networking nâng cao**<br>- Ôn lại **Public Subnet** và **Private Subnet**.<br>- Tìm hiểu **NAT Gateway, Route Table, Internet Gateway, Security Group** và **Network ACL**.<br>- So sánh luồng lưu lượng giữa Public Subnet và Private Subnet.<br>- Tạo NAT Gateway để cho phép Private Subnet truy cập Internet chiều outbound.<br>- Cấu hình routing và kiểm tra khả năng kết nối.<br>- Phân biệt **Security Group** và **Network ACL**. | 27/05/2026 | 27/05/2026 | [Amazon VPC](https://aws.amazon.com/vpc/)<br>[NAT Gateway](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html) |
| 3 | **Tìm hiểu Application Load Balancer**<br>- Tìm hiểu vai trò của **Load Balancer** trong việc phân phối request.<br>- Tìm hiểu **Application Load Balancer, Listener, Listener Rule, Target Group** và **Health Check**.<br>- Tạo hai EC2 Instance làm application target.<br>- Tạo Target Group và đăng ký các EC2 Instance.<br>- Tạo Application Load Balancer trong các Public Subnet.<br>- Cấu hình Listener để chuyển tiếp traffic đến Target Group.<br>- Kiểm tra khả năng phân phối traffic và trạng thái của các instance.<br>- So sánh truy cập trực tiếp EC2 với truy cập thông qua Load Balancer. | 28/05/2026 | 28/05/2026 | [Elastic Load Balancing](https://aws.amazon.com/elasticloadbalancing/)<br>[Application Load Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html) |
| 4 | **Tìm hiểu nâng cao về Amazon RDS**<br>- Ôn lại vai trò của **Amazon RDS** trong việc quản lý cơ sở dữ liệu quan hệ.<br>- Tìm hiểu **DB Instance, DB Subnet Group, Security Group, Backup, Snapshot** và **Multi-AZ Deployment**.<br>- Tạo cơ sở dữ liệu RDS trong Private Subnet.<br>- Cấu hình DB Subnet Group và giới hạn quyền truy cập bằng Security Group.<br>- Kết nối ứng dụng trên EC2 với cơ sở dữ liệu RDS.<br>- Tạo manual snapshot và khôi phục cơ sở dữ liệu từ snapshot.<br>- So sánh mô hình Single-AZ và Multi-AZ.<br>- Kiểm tra kết nối cơ sở dữ liệu và dọn dẹp tài nguyên không sử dụng. | 29/05/2026 | 29/05/2026 | [Amazon RDS](https://aws.amazon.com/rds/)<br>[Amazon RDS Multi-AZ deployments](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html)<br>[Working with DB subnet groups](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_VPC.WorkingWithRDSInstanceInVPC.html) |
| 5 | **Tìm hiểu Amazon DynamoDB và Amazon ElastiCache**<br>- Tìm hiểu mô hình NoSQL của **Amazon DynamoDB**.<br>- Tìm hiểu **Table, Item, Attribute, Partition Key** và **Sort Key**.<br>- Tạo DynamoDB Table và thực hiện các thao tác **Create, Read, Update, Delete (CRUD)** cơ bản.<br>- So sánh DynamoDB với cơ sở dữ liệu quan hệ như Amazon RDS.<br>- Tìm hiểu vai trò của **Amazon ElastiCache** trong việc lưu trữ dữ liệu tạm thời trên bộ nhớ.<br>- Tìm hiểu hai engine **Redis** và **Memcached**.<br>- Tìm hiểu cách caching giảm tải cho database và cải thiện thời gian phản hồi.<br>- So sánh khả năng hoạt động của ứng dụng khi có và không có caching layer. | 30/05/2026 | 30/05/2026 | [Amazon DynamoDB](https://aws.amazon.com/dynamodb/)<br>[Các thành phần cốt lõi của DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html)<br>[Amazon ElastiCache](https://aws.amazon.com/elasticache/)<br>[Amazon ElastiCache là gì?](https://docs.aws.amazon.com/AmazonElastiCache/latest/mem-ug/WhatIs.html)<br>[AWS Workshop 000060](https://github.com)<br>[AWS Workshop 000061](https://github.com) |

### Kết quả đạt được tuần 3:

* Tạo được CloudFront Distribution sử dụng Amazon S3 làm Origin và thực hiện cache invalidation.
* Cấu hình được VPC networking nâng cao và hiểu luồng traffic giữa Public Subnet và Private Subnet.
* Tạo được Application Load Balancer, cấu hình Target Group, Listener và kiểm tra trạng thái target.
* Tạo được cơ sở dữ liệu Amazon RDS trong Private Subnet và thực hành phân quyền truy cập, snapshot, cùng khái niệm Multi-AZ.
* Tạo được DynamoDB Table và thực hiện các thao tác CRUD cơ bản theo mô hình dữ liệu NoSQL.
* Hiểu cách Amazon ElastiCache, Redis và Memcached giúp giảm tải database và cải thiện thời gian phản hồi.
* Phân biệt được cơ sở dữ liệu quan hệ, cơ sở dữ liệu NoSQL và bộ nhớ cache trong các trường hợp sử dụng khác nhau.

