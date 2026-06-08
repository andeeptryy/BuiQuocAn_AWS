---
title: "WEEK 4 WORKLOG"
date: "2026-05-14"
weight: 4
chapter: false
pre: " <b> 1.4 </b> "
---

# **WEEK 4 WORKLOG**

### **Week 4 Objectives**

* Nắm vững các khái niệm nền tảng về mạng trên AWS, trọng tâm là Amazon Virtual Private Cloud (VPC), các thành phần cốt lõi và cách quản lý địa chỉ IP.
* Khám phá và triển khai các kiến trúc chịu lỗi, có tính sẵn sàng cao thông qua việc kết hợp Elastic Load Balancing (ELB) và Auto Scaling Group (ASG).
* Củng cố toàn diện các kỹ năng đám mây cơ bản qua bài thực hành tổng hợp: từ quản trị định danh (IAM), bảo mật lưu trữ (S3), triển khai máy chủ (EC2) đến giám sát hệ thống (CloudWatch).

---

### **Tasks to be carried out this week**

| Day | Task | Start Date | Completion Date | Reference/Material |
| :--- | :--- | :--- | :--- | :--- |
| 1 (Thứ Hai) | **Tổng quan AWS Networking & VPC căn bản**: Nghiên cứu các thành phần VPC (Public/Private Subnet, Route Table, IGW, NAT Gateway). Phân biệt Security Group vs NACL và ôn tập mô hình kiến trúc 3 lớp (3-tier). | 11/05/2026 | 11/05/2026 | [Video Link](https://www.youtube.com/watch?v=uAQCm4sm_1c) |
| 2 (Thứ Ba) | **AWS Load Balancer & Auto Scaling**: Tìm hiểu các loại ELB (ALB, NLB, CLB). Thực hành mô phỏng Auto Scaling Group (ASG) bao gồm Launch Template, Scaling Policies và Health Check. | 12/05/2026 | 12/05/2026 | AWS Load Balancer & Auto Scaling (YouTube) |
| 3 (Thứ Tư) | **Thực hành Lab: AWS Cloud Fundamentals**: Tạo IAM User (nguyên tắc least privilege). Cấu hình S3 Bucket bảo mật (Versioning, Encryption). Triển khai web server trên EC2, mở port SG và quan sát CloudWatch metrics. | 13/05/2026 | 13/05/2026 | [AWS Study Group Lab](https://000004.awsstudygroup.com/) |

---

### **Week 4 Achievements**

* Hiểu rõ cấu trúc tiêu chuẩn của một VPC và nắm bắt best practice trong việc phân chia không gian mạng (Subnetting) và quản lý CIDR.
* Phân tích và thiết lập thành công định tuyến giữa các subnet qua Route Table; phân biệt rõ cách hoạt động của tường lửa trạng thái (Security Group) và tường lửa không trạng thái (NACL).
* Nắm vững nguyên lý hoạt động của các bộ cân bằng tải (ALB và NLB) trong việc phân phối lưu lượng của các kiến trúc ứng dụng hiện đại.
* Nắm bắt mô hình tự động mở rộng/thu nhỏ tài nguyên (ASG) dựa theo tải CPU và traffic thực tế, đảm bảo ứng dụng luôn đạt tính sẵn sàng cao (HA).
* Thực hành thành thạo quy trình triển khai hạ tầng từ con số 0: quản trị an toàn IAM User/Group/Policy và thiết lập S3 theo chuẩn bảo mật (Private Blocks, SSE-S3 Encryption).
* Triển khai thành công EC2 instance, thiết lập kết nối SSH, chạy ứng dụng web cơ bản và sử dụng CloudWatch để giám sát log hiệu quả.
* Hoàn thiện tư duy nền tảng vững chắc về AWS Networking, sẵn sàng tiến bước vào các chủ đề mạng nâng cao như VPC Peering, Transit Gateway hoặc ECS/EKS.