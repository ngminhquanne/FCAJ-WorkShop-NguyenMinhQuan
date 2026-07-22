---
title : "Giới thiệu"
date : 2024-01-01 
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

## GIỚI THIỆU

### Mục tiêu

Phần này giới thiệu phạm vi của workshop và bài toán mà Smart Healthcare Appointment System đang giải quyết. Trước khi đi vào các thao tác triển khai, người đọc cần hiểu tài liệu trong hệ thống đi qua những bước nào, vì dự án phải tách frontend, backend, lưu trữ và cơ sở dữ liệu thành các thành phần riêng, đồng thời những dịch vụ AWS nào tham gia vào toàn bộ quy trình đó.

### Bối cảnh bài toán

Trong thực tế, hồ sơ y tế và lịch hẹn không chỉ cần được đặt thành công mà còn phải được quản lý theo trạng thái, kiểm duyệt trước khi xác nhận và đảm bảo khả năng truy cập ổn định cho người dùng cuối. Nếu toàn bộ file đều đi qua application server, hệ thống sẽ tốn tài nguyên xử lý, khó mở rộng và khó tối ưu chi phí khi số lượng hồ sơ tăng lên. Vì vậy, kiến trúc Smart Healthcare Appointment System được tổ chức theo hướng frontend gửi yêu cầu đến backend để lấy thông tin upload an toàn, sau đó file được đưa trực tiếp lên Amazon S3.

### Luồng tổng quát của workshop

Workshop tập trung vào một hành trình hoàn chỉnh của hồ sơ và lịch hẹn:

1. Người dùng điền metadata và chọn hồ sơ bệnh án cần tải lên từ giao diện web.
2. Backend xác thực đầu vào, sinh presigned URL và khóa lưu trữ cho file.
3. Trình duyệt upload trực tiếp lên S3 thay vì gửi toàn bộ binary qua server.
4. Metadata được ghi vào cơ sở dữ liệu với trạng thái ban đầu là `pending`.
5. Bác sĩ hoặc quản trị viên kiểm duyệt lịch hẹn và hồ sơ trong khu vực quản trị.
6. Sau khi được duyệt, lịch hẹn và hồ sơ xuất hiện trong trang tìm kiếm, quản lý, xem trước và tải xuống.

### Các nội dung tiếp theo

Ba mục con bên dưới đóng vai trò nền tảng cho toàn bộ workshop:

1. Smart Healthcare Appointment System là gì?
2. Dịch vụ sử dụng
3. Kiến trúc giải pháp
