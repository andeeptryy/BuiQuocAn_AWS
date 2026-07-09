---
title: "BÁO CÁO TUẦN 8"
date: "2026-06-14"
weight: 8
chapter: false
pre: " <b> 1.8 </b> "
---

# **BÁO CÁO TUẦN 8**

### **Mục tiêu trong tuần**

* Nắm bắt phương pháp luận AWS Unified Operations, dịch chuyển từ tư duy xử lý sự cố thụ động sang phòng ngừa chủ động (Shift-Left) cho các hệ thống trọng yếu.
* Thành thạo quy trình đóng gói và triển khai ứng dụng độc lập bằng Docker, kết hợp quản lý kho lưu trữ Amazon ECR và máy chủ Amazon EC2.
* Xây dựng luồng tự động hóa tích hợp và kiểm thử liên tục (CI/CD Pipeline) cho ứng dụng chạy trên Amazon Elastic Container Service (ECS), phục vụ mục tiêu đảm bảo chất lượng phần mềm (QC).
* Tối ưu hóa hiệu suất ứng dụng và kho dữ liệu với Amazon ElastiCache (Redis/Memcached) và kiến trúc lưu trữ dạng cột của Amazon Redshift.
* Mở rộng và bảo mật kết nối mạng nội bộ thông qua việc thiết lập VPC Peering và tường lửa cấp mạng con (Network ACLs).

---

### **Lịch trình công việc chi tiết**

| Ngày | Nội dung công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu / Lab |
| :--- | :--- | :--- | :--- | :--- |
| Thứ Hai (08/06) | **Nghiên cứu AWS Unified Operations**: Học cách xây dựng hệ thống bền vững cho mission-critical workloads. Áp dụng tư duy Shift-Left, giảm thiểu MTTI/MTTR bằng giám sát chủ động và tự động hóa. | 08/06/2026 | 08/06/2026 | [AWS Cloud Operations Blog](https://aws.amazon.com/vi/blogs/mt/aws-unified-operations-building-resilient-operations-for-mission-critical-workloads/) |
| Thứ Ba (09/06) | **Triển khai ứng dụng với Docker**: Thực hành đóng gói ứng dụng qua Docker Compose ở local. Triển khai lên Amazon EC2, kết nối Amazon RDS và đẩy container image lên kho lưu trữ tập trung Amazon ECR. | 09/06/2026 | 09/06/2026 | [AWS Lab 000015](https://000015.awsstudygroup.com/) |
| Thứ Tư (10/06) | **Amazon Redshift & ElastiCache**: Phân biệt kiến trúc lưu trữ cột (Columnar) của Redshift và hàng (Row-based). Tìm hiểu cơ chế caching ứng dụng bằng ElastiCache để giảm tải xử lý cho Database. | 10/06/2026 | 10/06/2026 | [Video Module 06-03](https://www.youtube.com/watch?v=UvdiRW34aNI) |
| Thứ Năm (11/06) | **CI/CD cho Container trên ECS**: Thiết lập luồng CI/CD tự động bằng GitHub/GitLab và AWS CodeBuild. Theo dõi hệ thống bằng Container Insights và quản lý luồng logs ứng dụng qua cấu hình Firelens. | 11/06/2026 | 11/06/2026 | [AWS Lab 000017](https://000017.awsstudygroup.com/vi/) |
| Thứ Sáu (12/06) | **Bảo mật mạng với VPC Peering & NACL**: Cấu hình VPC Peering để liên kết trực tiếp 2 VPC riêng biệt. Thiết lập Network ACL (stateless firewall) bảo vệ cấp subnet và kích hoạt phân giải Cross-Peering DNS. | 12/06/2026 | 12/06/2026 | [AWS Lab 000019](https://000019.awsstudygroup.com/vi/) |
| Thứ Bảy (13/06) | **Sự kiện AWS Meetup**: Tham dự chương trình "First Cloud AI Journey". Học hỏi kinh nghiệm thực chiến về DevOps, văn hóa doanh nghiệp đa quốc gia (MNCs) và lộ trình phát triển cùng cộng đồng AWS. | 13/06/2026 | 13/06/2026 | [FCAJ Meetup](#) |

---

### **Kết quả đạt được (Week 8 Achievements)**

* Hoàn thành xuất sắc 100% kế hoạch tuần, đánh dấu bước chuyển mình từ việc quản trị bảo mật nền tảng sang tư duy triển khai ứng dụng đám mây hiện đại.
* **Tư duy Vận hành Chủ động (Shift-Left)**: Hiểu rõ phương pháp tiếp cận chủ động trong vận hành hệ thống, giúp ngăn ngừa lỗi phần mềm trước khi phát sinh thay vì chỉ "chữa cháy", đảm bảo độ tin cậy tuyệt đối cho ứng dụng.
* **Container hóa & CI/CD**: Làm chủ toàn diện vòng đời phát triển của một ứng dụng: từ bước lập trình môi trường Local, viết Dockerfile, quản lý trên Amazon ECR đến khi thiết lập luồng CI/CD hoàn toàn tự động, loại bỏ rủi ro do thao tác thủ công.
* **Tối ưu hóa Dữ liệu (Data Optimization)**: Củng cố kiến thức về tối ưu hóa truy xuất dữ liệu: Ứng dụng xử lý song song trong Amazon Redshift và tự thiết kế logic bộ nhớ đệm với Amazon ElastiCache.
* **Kinh nghiệm rút ra**: Nhận thức sâu sắc rằng một ứng dụng bảo mật và có tính sẵn sàng cao phải đi liền với một luồng kiểm thử tự động (CI/CD) và sự cô lập của Container. Điều này giúp các tiêu chuẩn an toàn luôn được rà soát liên tục trong mọi vòng đời phần mềm.
* **Định hướng tuần tới**: Áp dụng trực tiếp kiến thức về CI/CD, Container và Bảo mật tự động hóa để phác thảo Đề cương dự án thực tập cuối kỳ (Proposal) mang tính thực chiến cao.