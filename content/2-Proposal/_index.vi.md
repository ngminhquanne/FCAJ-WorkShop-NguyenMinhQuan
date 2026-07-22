---
title: "Bản đề xuất"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---



## Smart Healthcare Appointment System theo định hướng triển khai trên AWS

## 1. Tóm tắt điều hành

Smart Healthcare Appointment System là nền tảng hỗ trợ bệnh nhân đặt lịch khám chữa bệnh, quản lý thông tin y tế và kết nối với các cơ sở y tế một cách nhanh chóng, minh bạch. Bài toán mà hệ thống hướng đến không chỉ là một trang web đặt lịch đơn thuần, mà là xây dựng một hệ thống y tế số có cấu trúc, bảo mật thông tin tuyệt đối và có khả năng mở rộng lâu dài để chịu tải cao trong giờ cao điểm.

Trong phạm vi thực tập, tôi tham gia chính ở mảng backend và hạ tầng, đồng thời hỗ trợ nhóm kết nối luồng giao diện với hệ thống xử lý ngầm và các dịch vụ AWS. Vì vậy, bản đề xuất này vừa phản ánh góc nhìn sản phẩm, vừa phản ánh tư duy kỹ thuật để đưa hệ thống từ một đồ án học tập thành một nền tảng y tế số có thể triển khai trên cloud.

Điểm quan trọng của hệ thống là không được thiết kế như một ứng dụng đơn khối thông thường. Thay vào đó, kiến trúc được tách lớp rõ ràng giữa giao diện, logic nghiệp vụ, hàng đợi xử lý bất đồng bộ và cơ sở dữ liệu. Cách tiếp cận này giúp hệ thống đảm bảo tính sẵn sàng cao, bảo mật dữ liệu bệnh nhân và vận hành ổn định.

## 2. Tuyên bố vấn đề

Trong môi trường y tế hiện nay, quy trình đặt lịch và quản lý hồ sơ thường gặp nhiều bất cập do phân tán hoặc vận hành thủ công. Điều này dẫn đến nhiều vấn đề:

* Bệnh nhân tốn nhiều thời gian chờ đợi tại quầy hoặc gặp tình trạng nghẽn hệ thống vào các khung giờ cao điểm đăng ký khám.
* Dữ liệu lịch hẹn và thông tin y tế cá nhân nếu không được phân tách và bảo vệ chặt chẽ sẽ đối mặt với rủi ro lộ lọt thông tin.
* Hệ thống dễ bị quá tải (bottleneck) khi lượng truy cập tăng đột biến, gây gián đoạn dịch vụ khám chữa bệnh.
* Khó khăn trong việc đồng bộ trạng thái lịch hẹn giữa bệnh nhân, bác sĩ và các phòng ban trong cơ sở y tế.

**Vấn đề hiện tại**

Nếu xây dựng hệ thống theo mô hình đơn giản, nghĩa là toàn bộ lượng request đặt lịch đều đổ trực tiếp vào một server duy nhất, hệ thống sẽ nhanh chóng sập nguồn khi số lượng người dùng truy cập đồng thời tăng cao. Ngoài ra, việc thiếu các cơ chế xử lý bất đồng bộ hay phân vùng mạng an toàn sẽ làm giảm khả năng mở rộng và độ an toàn của dữ liệu y tế.

Một vấn đề khác là nhiều hệ thống chỉ giải quyết được việc lưu trữ dữ liệu cơ bản nhưng chưa tối ưu hóa được khía cạnh chịu tải, giám sát lỗi thời gian thực và bảo mật theo tiêu chuẩn ngành y tế.

**Giải pháp đề xuất**

Smart Healthcare Appointment System được đề xuất theo cấu trúc sau:

* Frontend cung cấp trải nghiệm tìm kiếm, đặt lịch, quản lý hồ sơ y tế và thông tin bác sĩ.
* Backend Node.js/Express xử lý logic nghiệp vụ, xác thực, phân quyền và điều phối lịch hẹn.
* PostgreSQL lưu metadata lịch hẹn, thông tin bệnh nhân, bác sĩ và trạng thái khám chữa bệnh.
* Amazon S3 lưu trữ hồ sơ bệnh án, kết quả xét nghiệm và hình ảnh y tế để giảm tải cho backend và phù hợp với mô hình object storage.
* Các dịch vụ mở rộng như CloudFront, SQS, CloudWatch, SNS được đưa vào định hướng để tăng hiệu năng, xử lý hàng đợi đặt lịch cao điểm, giám sát và tối ưu chi phí.

Mẫu chốt của giải pháp là sử dụng kiến trúc phân tầng kết hợp hàng đợi xử lý bất đồng bộ cho các luồng đặt lịch cao điểm, trong khi backend tập trung vào metadata và nghiệp vụ y tế. Kiến trúc này phù hợp hơn cho một nền tảng y tế số có xu hướng tăng trưởng cả về dung lượng dữ liệu lẫn số lượng người dùng đồng thời.

## 3. Kiến trúc giải pháp