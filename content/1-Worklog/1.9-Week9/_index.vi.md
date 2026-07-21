---
title: "Worklog Tuần 9"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---


### Mục tiêu tuần 9:

* Phân tích yêu cầu dự án và thiết kế kiến trúc Cloud 3 lớp.
* Xác định và lựa chọn các dịch vụ AWS phù hợp cho từng lớp kiến trúc.
* Xây dựng, kiểm tra và hoàn thiện sơ đồ kiến trúc Cloud dựa trên nhận xét của các anh chị trong group FCAJ.
* Tính toán tổng chi phí dự kiến của kiến trúc hạ tầng.
* Triển khai các thành phần networking và storage nền tảng cần thiết cho dự án.
* Cấu hình kết nối mạng, kiểm soát traffic, kết nối riêng tư đến Amazon S3 và các tài nguyên lưu trữ.

### Các công việc cần triển khai trong tuần này:
| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Hoàn thành thiết kế sơ đồ kiến trúc Cloud theo mô hình kiến trúc 3 lớp cho dự án. | 27/06/2026 | 27/06/2026 | |
| 2 | Phân tích yêu cầu dự án và xác định các thành phần trong kiến trúc Cloud 3 lớp, gồm presentation layer, application layer và data layer. | 28/06/2026 | 28/06/2026 | |
| 3 | Lựa chọn các dịch vụ AWS phù hợp cho từng lớp kiến trúc và xây dựng sơ đồ kiến trúc Cloud ban đầu, bao gồm luồng dữ liệu chính giữa các thành phần. | 29/06/2026 | 29/06/2026 | |
| 4 | Hoàn thiện sơ đồ kiến trúc Cloud dựa trên nhận xét, góp ý của các anh chị trong group FCAJ Tính tổng chi phí hạ tầng. | 30/06/2026 | 30/06/2026 | |
| 5 | Triển khai các thành phần cốt lõi của **hạ tầng mạng AWS** cho dự án. Tạo và cấu hình **Amazon VPC**, bao gồm các **public subnet, private subnet** và **route table** cần thiết. Gắn **Internet Gateway** để cung cấp kết nối Internet cho các thành phần thuộc mạng public. Cấu hình **Security Groups** nhằm kiểm soát traffic inbound và outbound giữa các tài nguyên theo kiến trúc 3 lớp đã đề xuất. | 01/07/2026 | 01/07/2026 | |
| 6 | Triển khai các thành phần networking và storage bổ sung theo kiến trúc Cloud đã thiết kế. Cấu hình **NAT Instance** bằng một **EC2 instance** được triển khai trong public subnet nhằm cung cấp kết nối Internet outbound cho các tài nguyên trong private subnet. Tạo **S3 Gateway Endpoint** để cho phép VPC kết nối riêng tư đến Amazon S3 mà không cần định tuyến traffic S3 qua Internet công cộng. Cấu hình các **S3 Buckets** riêng biệt cho static website hosting và file upload, giúp quản lý độc lập nội dung website và dữ liệu được tải lên. | 02/07/2026 | 02/07/2026 | |


### Kết quả đạt được tuần 9:

* Hoàn thành thiết kế sơ đồ kiến trúc Cloud theo mô hình kiến trúc 3 lớp cho dự án.
* Phân tích yêu cầu dự án và xác định các thành phần trong kiến trúc Cloud 3 lớp.
* Lựa chọn các dịch vụ AWS phù hợp cho từng lớp kiến trúc và xây dựng sơ đồ kiến trúc Cloud ban đầu.
* Hoàn thiện sơ đồ kiến trúc dựa trên nhận xét, góp ý của các anh chị trong group FCAJ và tính toán tổng chi phí dự kiến của hạ tầng Cloud.
* Hoàn thành triển khai các thành phần hạ tầng mạng cốt lõi, gồm Amazon VPC, public subnet, private subnet, route table, Internet Gateway và Security Groups.
* Triển khai NAT Instance bằng một EC2 instance trong public subnet để cung cấp kết nối Internet outbound cho các tài nguyên trong private subnet.
* Tạo S3 Gateway Endpoint để VPC kết nối riêng tư đến Amazon S3 mà không cần định tuyến traffic S3 qua Internet công cộng.
* Cấu hình các S3 Buckets riêng biệt cho static website hosting và file upload nhằm quản lý độc lập nội dung website và dữ liệu được tải lên.


