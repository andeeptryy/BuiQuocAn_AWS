---
title: "BÁO CÁO TUẦN 11"
date: "2026-07-05"
weight: 11
chapter: false
pre: " <b> 1.11 </b> "
---

# **BÁO CÁO TUẦN 11**

### **Mục tiêu trong tuần**

* Triển khai kiến trúc xử lý bất đồng bộ (asynchronous) cho module "Mô phỏng tấn công" để tránh lỗi timeout của API Gateway.
* Cấu hình Amazon SQS và AWS Step Functions để điều phối các tác vụ mô phỏng AI phức tạp, chạy ngầm.
* Xây dựng hệ thống giám sát (Observability) toàn diện bằng Amazon CloudWatch để ghi log và theo dõi chỉ số.
* Thiết lập hệ thống cảnh báo tự động qua Amazon SNS để gửi thông báo tức thời khi AI phát hiện lỗ hổng mạng nghiêm trọng.
* Tiến hành kiểm thử API (API Testing) toàn diện và trích xuất log để làm minh chứng cho báo cáo cuối kỳ.

---

### **Lịch trình công việc chi tiết**

| Ngày | Nội dung công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu / Lab |
| :--- | :--- | :--- | :--- | :--- |
| Thứ Hai (29/06) | **Cấu hình Amazon SQS**: Thiết lập hàng đợi SQS để tiếp nhận và tách rời (decouple) các yêu cầu "Scan Attack" khỏi API Gateway. | 29/06/2026 | 29/06/2026 | [Amazon SQS Docs](https://docs.aws.amazon.com/sqs/) |
| Thứ Ba (30/06) | **Thiết lập AWS Step Functions**: Xây dựng state machine điều phối nhiều hàm Lambda để chạy luồng mô phỏng tấn công ngầm một cách tuần tự. | 30/06/2026 | 30/06/2026 | [AWS Step Functions Docs](https://docs.aws.amazon.com/step-functions/) |
| Thứ Tư, Năm (01-02/07) | **Tích hợp CloudWatch**: Cấu hình CloudWatch Logs cho các hàm Lambda. Tạo Dashboard theo dõi độ trễ API và hiệu suất chạy AI. | 01/07/2026 | 02/07/2026 | [Amazon CloudWatch Docs](https://docs.aws.amazon.com/cloudwatch/) |
| Thứ Sáu (03/07) | **Cảnh báo qua Amazon SNS**: Tạo SNS Topic và cấu hình Lambda trigger để gửi email cảnh báo tức thì khi phát hiện lỗi thiết kế kiến trúc mạng. | 03/07/2026 | 03/07/2026 | [Amazon SNS Docs](https://docs.aws.amazon.com/sns/) |
| Thứ 7 - CN (04-05/07) | **Kiểm thử API & Thu thập Log**: Dùng Postman để giả lập tải và gửi prompt. Thu thập log CloudWatch và ảnh chụp màn hình email SNS làm minh chứng. | 04/07/2026 | 05/07/2026 | API Testing Tools |

---

### **Kết quả đạt được (Week 11 Achievements)**

* Hoàn thành xuất sắc 100% kế hoạch, đáp ứng hoàn hảo tiêu chí đánh giá bắt buộc về "Logging & Monitoring" của công ty.
* **Làm chủ Xử lý Bất đồng bộ**: Tách rời thành công tác vụ chạy AI nặng khỏi luồng request chính bằng Amazon SQS và Step Functions. Điều này giải quyết triệt để rủi ro API Gateway bị timeout, tăng cường độ ổn định cho trải nghiệm người dùng.
* **Giám sát Chủ động**: Xây dựng thành công vòng lặp giám sát và cảnh báo. Việc kết hợp CloudWatch và SNS đảm bảo mọi lỗi hệ thống hoặc lỗ hổng bảo mật do AI quét được đều báo cáo ngay lập tức cho quản trị viên, thể hiện tư duy vận hành chủ động.
* **Định hướng tuần tới**: Tập trung bảo mật lớp giao diện (Frontend) với AWS WAF, hoàn thiện tích hợp toàn bộ hệ thống (end-to-end) và chuẩn bị các script dọn dẹp tài nguyên (Clean-up).