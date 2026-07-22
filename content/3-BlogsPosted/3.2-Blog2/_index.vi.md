---
title: "Blog 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---


![alt text](/images/3-BlogsPosted/blog2.jpg)

Blog thứ hai tôi chọn dịch xoay quanh bài toán nền tảng trong thiết kế hệ thống trên AWS: làm thế nào để xây dựng một kiến trúc mạng an toàn, có tính bảo mật cao và dễ dàng mở rộng từ Amazon VPC. 

Bài viết từ AWS giới thiệu về tầm quan trọng của việc thiết kế kiến trúc mạng trước khi triển khai ứng dụng, phân tách các vùng mạng và hiểu rõ các cơ chế kiểm soát truy cập.

## 1. Tổng quan giải pháp về Amazon VPC

Amazon VPC (Virtual Private Cloud) cho phép tạo một mạng riêng ảo trên nền tảng AWS để triển khai và quản lý tài nguyên an toàn. Các thành phần chính bao gồm:

* **Amazon VPC:** Cung cấp dải địa chỉ IP (CIDR Block) và toàn quyền kiểm soát cấu hình mạng.
* **Public Subnet & Private Subnet:** Phân tách vùng mạng công cộng và nội bộ để tối ưu bảo mật.
* **Route Table & Internet Gateway:** Định tuyến lưu lượng và kết nối Internet.
* **NAT Gateway:** Hỗ trợ kết nối ra ngoài cho các tài nguyên trong Private Subnet.
* Bên cạnh đó còn có **Security Group** và **Network ACL** để kiểm soát truy cập ở nhiều lớp.

Việc thiết kế hạ tầng mạng từ đầu giúp hệ thống ổn định và dễ dàng mở rộng khi lưu lượng tăng cao.

## 2. Phân tách Subnet và Kiểm soát truy cập hoạt động như thế nào?

Thay vì đặt toàn bộ tài nguyên chung một chỗ, kiến trúc chia hệ thống thành các vùng mạng riêng biệt để giảm bề mặt tấn công:

* **Public Subnet:** Chứa các tài nguyên cần kết nối Internet như Application Load Balancer hoặc Bastion Host.
* **Private Subnet:** Chứa các thành phần quan trọng như Amazon EC2 xử lý nghiệp vụ hoặc Amazon RDS, không truy cập trực tiếp từ Internet.
* **Security Group:** Hoạt động ở mức tài nguyên (Instance Level), có tính **stateful** (tự động cho phép lưu lượng phản hồi).
* **Network ACL:** Hoạt động ở mức Subnet, có thể cấu hình cho phép/từ chối và là **stateless** (phải khai báo cả chiều vào và chiều ra).

Cách tiếp cận này giúp áp dụng mô hình **Defense in Depth** để bảo vệ hệ thống tối đa.

## 3. Luồng xử lý và thiết kế mạng

Từ nội dung bài viết, tôi tóm tắt luồng hoạt động của hạ tầng:

1. Người dùng gửi request từ Internet thông qua Internet Gateway.
2. Lưu lượng đi vào Application Load Balancer nằm trong Public Subnet.
3. Load Balancer chuyển tiếp request xuống Amazon EC2 nằm trong Private Subnet để xử lý nghiệp vụ.
4. EC2 kết nối với cơ sở dữ liệu Amazon RDS nội bộ.
5. Các dịch vụ trong Private Subnet sử dụng NAT Gateway khi cần truy cập Internet ra ngoài an toàn.

Mô hình này giúp hệ thống vừa đáp ứng được nhu cầu phục vụ người dùng, vừa bảo mật dữ liệu nhạy cảm bên trong.

## 4. Điều tôi học được từ bài blog

Bài viết này giúp tôi nhận ra rằng việc xây dựng ứng dụng trên Cloud không chỉ đơn thuần là khởi tạo máy chủ, mà nền tảng mạng (Networking) đóng vai trò quyết định sự ổn định và bảo mật. Với vai trò kỹ sư hạ tầng trong dự án **Smart Healthcare Appointment System**, tư duy thiết kế VPC rất hữu ích cho các cấu hình:

* Phân chia subnet cho dịch vụ web và cơ sở dữ liệu y tế.
* Cấu hình Security Group chặt chẽ để bảo vệ thông tin bệnh nhân.
* Thiết lập Route Table và Gateway an toàn.

Hiểu rõ mô hình này giúp tôi thiết kế hệ thống tuân thủ các tiêu chuẩn bảo mật khắt khe trong ngành y tế.

## 5. Liên hệ với Smart Healthcare Appointment System

* **Smart Healthcare Appointment System** cần áp dụng mô hình phân tách Public/Private Subnet để bảo vệ dữ liệu lịch hẹn và thông tin người dùng.
* Việc cấu hình Security Group và Network ACL giúp hạn chế tối đa các truy cập trái phép vào hệ thống backend.
* Nền tảng mạng VPC vững chắc sẽ tạo tiền đề để dễ dàng mở rộng quy mô khi lượng người dùng tăng lên.

## 6. Kết luận

Thiết kế mạng với Amazon VPC là bước nền tảng quan trọng nhất trước khi triển khai bất kỳ hệ thống nào trên AWS. Việc nắm vững cách vận hành của VPC, Subnet và các lớp bảo mật giúp tối ưu hóa hiệu năng, tính sẵn sàng và độ an toàn cho các ứng dụng thực tế.

Link bài đăng trong nhóm FCAJ: [https://www.facebook.com/groups/awsstudygroupfcj/permalink/2220573215374305/](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2220573215374305/)