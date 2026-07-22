---
title: "Workshop"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---




# XÂY DỰNG HỆ THỐNG SMART HEALTHCARE APPOINTMENT SYSTEM TRÊN AWS

## Tổng quan workshop

Smart Healthcare Appointment System là dự án đặt lịch khám chữa bệnh và quản lý hồ sơ y tế dành cho bệnh nhân và cơ sở y tế. Trong hệ thống này, người dùng có thể đặt lịch và tải lên hồ sơ bệnh án từ giao diện web, backend tiếp nhận yêu cầu nghiệp vụ, Amazon S3 chịu trách nhiệm lưu trữ file, cơ sở dữ liệu lưu metadata, còn bác sĩ hoặc quản trị viên thực hiện kiểm duyệt lịch hẹn và hồ sơ trước khi xác nhận. Tài liệu này được viết theo dạng workshop end-to-end để người đọc có thể theo dõi trọn vẹn một vòng đời đặt lịch khám thay vì chỉ xem rời rạc từng dịch vụ AWS.

Điểm trọng tâm của workshop là trình bày một luồng kỹ thuật hoàn chỉnh: chuẩn bị môi trường, upload hồ sơ bệnh án, xác nhận file đã được lưu đúng trên AWS, kiểm thử bước kiểm duyệt, đồng bộ dữ liệu hiển thị ra giao diện và cuối cùng là dọn dẹp tài nguyên để tránh phát sinh chi phí không cần thiết. Cách trình bày này giúp bài báo cáo thể hiện được cả phần thiết kế kiến trúc lẫn phần triển khai thực tế, kiểm thử và vận hành.

## Mục tiêu

Sau khi đọc xong mục này, người xem có thể:

* hiểu vai trò của từng thành phần trong hệ thống Smart Healthcare Appointment System,
* theo dõi được luồng upload và phê duyệt lịch hẹn, hồ sơ y tế từ đầu đến cuối,
* đối chiếu ảnh AWS Console với từng bước triển khai trong workshop,
* xem code snippet đại diện cho phần tích hợp frontend và backend,
* và nhận thấy nhóm có thực hiện cả monitoring, validation lẫn clean-up tài nguyên.

## Kết quả mong đợi

Kết quả cuối cùng của workshop là một hệ thống trong đó người dùng đặt lịch và tải hồ sơ lên thành công, quản trị viên hoặc bác sĩ duyệt lịch khám trong khu vực quản trị, lịch hẹn và hồ sơ đã duyệt xuất hiện tại trang tìm kiếm/quản lý, người dùng có thể xem trước hoặc tải xuống, đồng thời hệ thống được theo dõi bằng CloudWatch logs, metrics và alarm.


## Video demo

Người chấm có thể xem video demo Smart Healthcare Appointment System tại đây: [Video demo Smart Healthcare Appointment System](https://drive.google.com/drive/u/0/folders/1_nQH3pVoNAph2W7E95p7tp1dXqVrkS-v).

## Cấu trúc workshop

1. Giới thiệu
2. Điều kiện tiên quyết
3. Triển khai luồng upload hồ sơ và lưu trữ y tế
4. Kiểm thử hệ thống end-to-end
5. Tích hợp ứng dụng khách và quan sát hệ thống
6. Cập nhật dữ liệu
7. Dọn dẹp tài nguyên