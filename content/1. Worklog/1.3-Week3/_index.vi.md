---
title: "WEEK 3 WORKLOG"
date: "2026-05-09"
weight: 3
chapter: false
pre: " <b> 1.3 </b> "
---

# **WEEK 3 WORKLOG**

### **Week 3 Objectives**

* Làm chủ các tài nguyên điện toán cốt lõi trên AWS, phân biệt rõ ứng dụng thực tế giữa môi trường tùy biến cao (Amazon EC2) và môi trường triển khai nhanh (Amazon Lightsail).
* Nghiên cứu chuyên sâu các hệ thống lưu trữ AWS, phân biệt chính xác giữa Lưu trữ khối (EBS), Lưu trữ tệp (EFS, FSx) và Lưu trữ đối tượng (S3).
* Tìm hiểu quy trình dịch chuyển máy chủ toàn diện lên nền tảng đám mây thông qua dịch vụ AWS Application Migration Service (MGN).
* Hiểu rõ kiến trúc của Amazon S3, tập trung vào khả năng mở rộng vô hạn, độ bền dữ liệu và cách quản lý vòng đời thông qua các lớp lưu trữ (Storage Classes).

---

### **Tasks to be carried out this week**

| Day | Task | Start Date | Completion Date | Reference/Material |
| :--- | :--- | :--- | :--- | :--- |
| 1 (Thứ Ba) | **Amazon EC2, EBS và Lightsail**: Học về các loại EC2 instance và tính năng của EBS (Volume, Snapshot). So sánh sự linh hoạt của EC2 với giải pháp chi phí thấp của Lightsail. | 05/05/2026 | 05/05/2026 | [Video Link](https://youtu.be/e7XeKdOVq40) |
| 2 (Thứ Tư) | **Amazon EFS / FSx & AWS MGN**: Nghiên cứu EFS và các tùy chọn FSx (Windows/Lustre). Tìm hiểu quy trình chuyển đổi MGN: cài đặt agent, replicate dữ liệu máy nguồn và cutover. | 06/05/2026 | 06/05/2026 | [Video Link](https://youtu.be/hFVYG8WqfU0) |
| 3 (Thứ Sáu) | **Dịch vụ lưu trữ AWS: Amazon S3**: Khám phá khái niệm Object Storage. Nghiên cứu độ bền 99.999999999% (11 số 9), khả năng mở rộng và các lớp lưu trữ (Standard, IA, Glacier). | 08/05/2026 | 08/05/2026 | [Video Link](https://youtu.be/_yunukwcAwc) |

---

### **Week 3 Achievements**

* Hoàn thành 100% tiến độ nghiên cứu lý thuyết và thực hành, nắm vững hệ sinh thái điện toán và lưu trữ toàn diện trên AWS.
* Phân biệt rõ rệt Amazon EC2 và Amazon Lightsail, có khả năng lựa chọn đúng dịch vụ điện toán dựa trên độ phức tạp và ngân sách của dự án.
* Phân loại và nhận biết chính xác tình huống sử dụng tối ưu (Use cases) cho các loại hình lưu trữ: EBS (Block), EFS/FSx (File) và S3 (Object).
* Thực hành thành thạo các thao tác cốt lõi: khởi tạo EC2, gắn kết EBS Volume, tạo S3 Bucket, tải dữ liệu lên lưu trữ và quản lý phân quyền an toàn.
* Nắm bắt được tư duy chuyển đổi hệ thống (Cloud Migration) qua AWS MGN, hiểu rõ quy trình kỹ thuật từ lúc sao chép máy nguồn cho đến khi chính thức chạy trên AWS (cutover).
* Tiếp tục củng cố kỹ năng vận hành thực tế thông qua việc thao tác trực tiếp trên giao diện AWS Console.