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
Kiến trúc dưới đây mô tả định hướng triển khai Smart Healthcare Appointment System trên AWS với lớp phân phối nội dung, lớp VPC mạng an toàn, lớp ứng dụng, lớp dữ liệu và lớp giám sát vận hành:

![alt text](/images/2-Proposal/duan.jpg)

**Mô tả các thành phần chính**

* **Amazon Route 53, Amazon CloudFront, AWS WAF và AWS Certificate Manager:** Đóng vai trò lớp bảo mật biên toàn cầu (Global Edge Security & CDN), phân phối nội dung tĩnh, quản lý tên miền, chứng chỉ SSL tự động và ngăn chặn các mối đe dọa web.
* **Internet Gateway và Application Load Balancer:** Tiếp nhận request từ người dùng, định tuyến lưu lượng vào các Public Subnet và phân phối tải tới hệ thống backend.
* **Amazon EC2 (trong Private Subnet):** Chạy backend xử lý logic nghiệp vụ đặt lịch khám, xác thực và điều phối dữ liệu y tế.
* **Amazon RDS PostgreSQL (Multi-AZ) và Amazon ElastiCache for Redis:** Lưu trữ metadata lịch hẹn, thông tin bệnh nhân, tài khoản, trạng thái khám chữa bệnh và caching dữ liệu để tăng tốc độ truy vấn.
* **Amazon S3 (Upload):** Lưu trữ hồ sơ bệnh án, kết quả xét nghiệm và hình ảnh y tế với cơ chế Presigned URL cho phép upload trực tiếp từ phía client.
* **Event-Driven Execution Bus (SQS FIFO Queue, AWS Lambda, SNS & SES):** Xử lý bất đồng bộ các tác vụ đặt lịch cao điểm, gửi thông báo lịch hẹn và email xác nhận tự động.
* **Amazon CloudWatch:** Hỗ trợ logging, monitoring, cảnh báo tự động (CloudWatch Alarm) khi hệ thống có sự cố hoặc quá tải CPU.

**Ý nghĩa kiến trúc đối với Smart Healthcare Appointment System**

Kiến trúc này cho thấy Smart Healthcare Appointment System không chỉ là một ứng dụng web đơn thuần, mà là một hệ thống có lớp biên bảo mật, lớp phân phối nội dung, hạ tầng mạng VPC phân tách rõ ràng (Public/Private Subnet), hệ thống xử lý bất đồng bộ quy mô lớn và cơ chế giám sát vận hành chặt chẽ. Đây là nền tảng vững chắc để đảm bảo tính an toàn dữ liệu y tế, khả năng chịu tải cao và sẵn sàng mở rộng trong thực tế.

## 4. Triển khai kỹ thuật

Trong kỳ thực tập, nhóm tập trung vào những phần khả thi và bám sát codebase hiện có:

* Xây dựng frontend cho Trang chủ, Tìm kiếm, Đặt lịch khám, Hồ sơ bệnh nhân và Bảng điều khiển quản trị.
* Thiết kế luồng đăng nhập mô phỏng, phân quyền bệnh nhân, bác sĩ và quản trị viên.
* Chuẩn hóa cấu trúc metadata lịch hẹn phục vụ tìm kiếm, quản lý và điều phối.
* Chuẩn bị luồng upload hồ sơ bệnh án và hình ảnh y tế theo mô hình presigned URL.
* Hỗ trợ tích hợp backend Express với PostgreSQL và S3 ở mức phù hợp cho demo.

Điều này cũng có nghĩa là không phải mọi thành phần trong sơ đồ kiến trúc đều đã được triển khai đầy đủ 100%. Một số dịch vụ như SQS, CloudWatch, SNS hiện đóng vai trò định hướng mở rộng hợp lý hơn là phần đã hoàn thiện hoàn toàn. Việc trình bày rõ như vậy giúp báo cáo trung thực hơn với phạm vi thực tế.

## 5. Lộ trình và mốc triển khai

**Giai đoạn 1: Hoàn thiện sản phẩm lõi**

* Ổn định trải nghiệm tìm kiếm, đặt lịch, xem trước hồ sơ và điều hướng người dùng.
* Chuẩn hóa metadata và quy trình phê duyệt lịch hẹn.
* Ho hoàn thiện bảng điều khiển quản trị và thống kê cơ bản.

**Giai đoạn 2: Tích hợp cloud thực tế**

* Kết nối ổn định hơn giữa frontend, backend Express và PostgreSQL.
* Hoàn thiện upload trực tiếp lên S3 bằng presigned URL cho hồ sơ bệnh án.
* Chuẩn hóa môi trường cấu hình và kiểm thử end-to-end.

**Giai đoạn 3: Mở rộng hệ thống**

* Bổ sung background processing cho các tác vụ nặng hoặc bất đồng bộ.
* Thêm monitoring, alerting và logging cho môi trường sẵn sàng triển khai.
* Tối ưu chi phí bằng lifecycle policy và phân tầng dữ liệu lưu trữ lâu năm.

## 6. ước tính ngân sách
Ảnh dưới đây là bản ước lượng chi phí tháng cho kiến trúc Smart Healthcare Appointment System tổng hợp từ AWS Pricing Calculator và xuất vào ngày 20/6/2026:

![alt text](/images/2-Proposal/uoctinh.png)


| Hạng mục | Chi phí ước tính / tháng (USD) | Ghi chú |
| :--- | :---: | :--- |
| **RDS PostgreSQL Multi-AZ** | **85.50** | Thành phần chiếm tỷ trọng lớn nhất vì ưu tiên tính sẵn sàng |
| **EC2 Server (t4g.micro x2)** | **19.51** | Hai máy ứng dụng ở hai AZ |
| **Application Load Balancer** | **18.98** | Phân phối tải và đảm bảo điểm vào thống nhất |
| **NAT Instance (t4g.nano)** | **4.64** | Hỗ trợ outbound traffic cho private subnet |
| **ElastiCache for Redis** | **7.50** | Caching dữ liệu và tối ưu tốc độ truy vấn |
| **Khác (CloudWatch, SQS, SNS)** | **5.07** | Chi phí cho monitoring, log và xử lý bất đồng bộ |
| **Tổng cộng** | **141.20** | Mức chi phí tham chiếu cho kiến trúc định hướng |

Mức chi phí trên phù hợp hơn với một kiến trúc định hướng production hoặc demo hoàn chỉnh, không phải cấu hình tối thiểu cho môi trường học tập. Đối với giai đoạn thực tập hoặc thử nghiệm, nhóm có thể giảm chi phí bằng các cách sau:

* Dùng cấu hình đơn AZ cho môi trường dev/test trước khi cần mức sẵn sàng cao hơn.
* Tắt hoặc thu nhỏ EC2 khi không cần chạy liên tục.
* Tận dụng S3 lifecycle để chuyển dữ liệu ít dùng sang Glacier.
* Chỉ bật CloudWatch log chi tiết cho các thành phần thật sự cần theo dõi.
* Tận dụng IAM Role và S3 Gateway Endpoint để giảm rủi ro cấu hình sai thay vì hard-code access key.

## 7. Đánh giá rủi ro

| Rủi ro | Tác động | Cách giảm thiểu |
| :--- | :--- | :--- |
| **Sai lệch giữa frontend, backend và luồng presigned URL** | Upload lỗi, dữ liệu hồ sơ bệnh án không đồng bộ | Chuẩn hóa API contract, test từng bước và test end-to-end trước khi demo |
| **Metadata lịch hẹn và bệnh nhân không nhất quán** | Tìm kiếm kém hiệu quả, quản lý lịch khám lộn xộn | Định nghĩa metadata bắt buộc, thêm trạng thái duyệt và quy trình admin/doctor review |
| **Cấu hình quyền truy cập AWS chưa chặt chẽ** | Rò rỉ dữ liệu y tế hoặc thao tác vượt quyền | Áp dụng IAM Role, Principle of Least Privilege và tránh hard-code key trong source code |
| **Chi phí tăng cao nếu giữ kiến trúc lớn cho môi trường dev** | Lãng phí ngân sách khi hệ thống chưa có tải thật | Phân tách môi trường dev/demo, giảm tải nguyên và theo dõi cost định kỳ |
| **Thiếu quan sát vận hành khi hệ thống lỗi** | Khó phát hiện và xử lý sự cố đặt lịch kịp thời | Thiết lập metric, log, CloudWatch Alarm và SNS notification cho các điểm quan trọng |
| **Phạm vi thực tập không đủ để hoàn thiện toàn bộ kiến trúc** | Báo cáo dễ bị hiểu là overclaim | Ghi rõ phần nào đã làm, phần nào là định hướng và minh họa bằng roadmap |

## 8. Kết quả kỳ vọng

Smart Healthcare Appointment System mang lại giá trị ở cả ba góc độ:

* **Đối với người dùng cuối:** Bệnh nhân và bác sĩ có một nền tảng tập trung để đặt lịch khám, quản lý hồ sơ bệnh án nhanh hơn, trực quan và đáng tin cậy hơn.
* **Đối với nhóm phát triển:** Dự án kết nối chặt chẽ giữa frontend, backend, metadata design và tư duy kiến trúc cloud trong cùng một sản phẩm hoàn chỉnh.
* **Đối vối định hướng học tập:** Dự án là cầu nối giữa UI/UX, nghiệp vụ y tế thực tế và triển khai hệ thống an toàn trên AWS.

Từ góc nhìn cá nhân, bản đề xuất này cũng phản ánh quá trình tôi chuyển từ suy nghĩ làm giao diện cho đẹp sang thiết kế trải nghiệm phải đi cùng luồng dữ liệu, bảo mật, chi phí và vận hành hệ thống. Đó là giá trị học tập lớn nhất mà Smart Healthcare Appointment System mang lại cho tôi trong kỳ thực tập này.