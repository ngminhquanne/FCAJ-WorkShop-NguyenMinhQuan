---
title: "Worklog Tuần 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---



### Mục tiêu tuần 2:

* Tìm hiểu chuyên sâu về mô hình máy ảo (Virtual Machine) trên AWS thông qua Amazon EC2.
* Hiểu các thành phần của EC2 Instance như AMI, Instance Type, Key Pair và Security Group.
* Thực hành kết nối và quản lý máy chủ bằng SSH và AWS Systems Manager Session Manager.
* Tìm hiểu cơ chế tự động mở rộng với EC2 Auto Scaling.
* Làm quen với dịch vụ máy chủ đơn giản Amazon Lightsail.
* Tìm hiểu các dịch vụ lưu trữ trên AWS gồm Amazon EBS, Amazon S3 và Amazon EFS.
* Thực hành tạo, gắn, quản lý và sao lưu tài nguyên lưu trữ trên AWS.

### Các công việc cần triển khai trong tuần này:
| Ngày | Nội dung thực hiện | Ngày bắt đầu | Ngày kết thúc | Tài liệu tham khảo |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **Tìm hiểu Amazon EC2 và Compute VM**<br>- Tìm hiểu khái niệm **Virtual Machine** và **EC2 Instance**.<br>- Tìm hiểu **AMI, Instance Type, Key Pair** và **Security Group**.<br>- Tìm hiểu vòng đời của EC2 Instance.<br>- Phân biệt **Public IP, Private IP** và **Elastic IP**. | 20/05/2026 | 20/05/2026 | [Amazon EC2](https://aws.amazon.com/ec2/)<br>[Giới thiệu về Amazon EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) |
| 2 | **Triển khai và truy cập EC2 Instance**<br>- Tạo **EC2 Instance** từ một **AMI**.<br>- Cấu hình **Instance Type, Key Pair** và **Security Group**.<br>- Kết nối đến EC2 bằng **SSH**.<br>- Tạo **IAM Role** dành cho EC2.<br>- Gắn quyền **AmazonSSMManagedInstanceCore** cho Role.<br>- Gắn **IAM Role** vào EC2 Instance.<br>- Kiểm tra trạng thái **SSM Agent**.<br>- Truy cập và quản trị EC2 thông qua **AWS Systems Manager Session Manager**.<br>- So sánh phương thức truy cập bằng **SSH** và **SSM**. | 21/05/2026 | 21/05/2026 | [Amazon EC2](https://aws.amazon.com/ec2/)<br>[AWS Systems Manager](https://aws.amazon.com/systems-manager/)<br>[Giới thiệu về Amazon EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) |
| 3 | **Tìm hiểu EC2 Auto Scaling và Amazon Lightsail**<br>- Tìm hiểu **Launch Template** và **Auto Scaling Group**.<br>- Phân biệt **Minimum Capacity, Desired Capacity** và **Maximum Capacity**.<br>- Tìm hiểu **Scaling Policy** và **Health Check**.<br>- Tạo một **Amazon Lightsail Instance**.<br>- Cấu hình **Static IP** và **Firewall Rules** trên Lightsail. | 22/05/2026 | 22/05/2026 | [EC2 Auto Scaling](https://aws.amazon.com/ec2/autoscaling/)<br>[Amazon Lightsail](https://aws.amazon.com/lightsail/)<br>[Triển khai ứng dụng FCJ Management với Auto Scaling Group](https://github.com)<br>[Amazon Lightsail Workshop - Cost Optimization on AWS](https://github.com) |
| 4 | **Nền tảng lưu trữ AWS (Amazon S3)**<br>- Tìm hiểu mô hình **Object Storage** và kiến trúc của **Amazon S3**.<br>- Tìm hiểu **Bucket, Object, Object Key** và **Region**.<br>- Tạo và cấu hình **S3 Bucket**.<br>- Thực hành upload, download, copy và delete **Object**.<br>- Cấu hình **Static Website Hosting** trên **Amazon S3**.<br>- Tìm hiểu **Cross-Origin Resource Sharing (CORS)** và cấu hình **CORS Policy** cho frontend truy cập S3.<br>- Tìm hiểu **Storage Class, Versioning, Lifecycle Rule** và **Server-Side Encryption**.<br>- Tìm hiểu **Block Public Access, Bucket Policy** và quyền truy cập bằng **IAM Policy**.<br>- Thực hành quản lý S3 bằng **AWS Management Console** và **AWS CLI**. | 23/05/2026 | 23/05/2026 | [Amazon S3](https://aws.amazon.com/s3/)<br>[Hosting website tĩnh với Amazon S3](https://docs.aws.amazon.com/de_de/AmazonS3/latest/userguide/WebsiteHosting.html)<br>[S3 Static Website Hosting](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html)<br>[S3 CORS](https://docs.aws.amazon.com/AmazonS3/latest/userguide/cors.html) |
| 5 | **Tìm hiểu S3 Access Point, các lớp lưu trữ và vòng đời dữ liệu**<br>- Tìm hiểu **S3 Access Point** và cách tạo các điểm truy cập riêng cho từng ứng dụng hoặc nhóm người dùng.<br>- Tìm hiểu các **S3 Storage Class** và tiêu chí lựa chọn dựa trên tần suất truy cập dữ liệu.<br>- Tìm hiểu **S3 Lifecycle Rule** để tự động chuyển đổi hoặc xóa Object theo thời gian.<br>- Tìm hiểu các dịch vụ lưu trữ lạnh (**Cold Storage**) như **S3 Glacier Instant Retrieval, S3 Glacier Flexible Retrieval** và **S3 Glacier Deep Archive**.<br>- So sánh thời gian truy xuất, thời gian lưu trữ tối thiểu và chi phí giữa các lớp **S3 Glacier Storage Class**.<br>- Thực hành cấu hình **S3 Access Point, Lifecycle Rule** và kiểm tra quá trình chuyển đổi Storage Class. | 24/05/2026 | 24/05/2026 | [Amazon S3 Access Points](https://aws.amazon.com/s3/features/access-points/)<br>[S3 Storage Classes](https://aws.amazon.com/s3/storage-classes/)<br>[S3 Lifecycle](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html) |
| 6 | **Tìm hiểu Amazon EFS và tổng hợp thực hành**<br>- Tìm hiểu mô hình **File Storage** của **Amazon EFS**.<br>- Tạo **EFS File System** và **Mount Target**.<br>- Kết nối EFS với EC2 Instance.<br>- Kiểm tra khả năng đọc và ghi dữ liệu trên EFS.<br>- So sánh **EBS, S3** và **EFS**.<br>- Xóa các tài nguyên không còn sử dụng sau khi thực hành. | 25/05/2026 | 25/05/2026 | [Amazon EFS](https://aws.amazon.com/efs/) |


### Kết quả đạt được tuần 2:

* Triển khai và quản lý được EC2 Instance, IAM Role, SSH và SSM.
* Hiểu và thực hành được EC2 Auto Scaling và Amazon Lightsail.
* Tạo, gắn và sao lưu được EBS Volume.
* Quản lý được S3 Bucket, Object, Static Website Hosting và CORS.
* Hiểu S3 Access Point, Storage Class, Lifecycle Rule và Cold Storage.
* Kết nối và sử dụng được Amazon EFS với EC2.
* Phân biệt được Block Storage, Object Storage và File Storage.

