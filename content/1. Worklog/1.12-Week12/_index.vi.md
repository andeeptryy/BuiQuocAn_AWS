---
title: "BÁO CÁO TUẦN 12"
date: "2026-07-12"
weight: 12
chapter: false
pre: " <b> 1.12 </b> "
---

# **BÁO CÁO TUẦN 12**

### **Mục tiêu trong tuần**

* Triển khai giao diện Web (Drag-Drop UI) lên AWS Amplify và cấu hình định tuyến tên miền bằng Amazon Route 53.
* Bảo vệ ứng dụng Frontend khỏi các lỗ hổng web phổ biến (như DDoS, Injection) bằng việc cấu hình AWS WAF.
* Hoàn thiện tích hợp hệ thống End-to-End, đảm bảo luồng hoạt động mượt mà từ xác thực Cognito đến lưu trữ DynamoDB.
* Rà soát và tinh chỉnh lại toàn bộ quyền IAM của các dịch vụ để tuân thủ tuyệt đối nguyên tắc Đặc quyền tối thiểu (Least Privilege).
* Viết tài liệu và script hướng dẫn dọn dẹp tài nguyên (Clean-up) để xóa hạ tầng AWS, đáp ứng yêu cầu quản trị chi phí của dự án.

---

### **Lịch trình công việc chi tiết**

| Ngày | Nội dung công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu / Lab |
| :--- | :--- | :--- | :--- | :--- |
| Thứ Hai (06/07) | **Triển khai Frontend**: Host giao diện người dùng lên AWS Amplify. Cấu hình phân giải DNS và liên kết tên miền tùy chỉnh thông qua Route 53. | 06/07/2026 | 06/07/2026 | [AWS Amplify Docs](https://docs.aws.amazon.com/amplify/) |
| Thứ Ba (07/07) | **Cấu hình AWS WAF**: Triển khai tường lửa AWS WAF với các tập luật cơ bản để bảo vệ ứng dụng Amplify khỏi các cuộc tấn công web và giới hạn truy cập. | 07/07/2026 | 07/07/2026 | [AWS WAF Documentation](https://docs.aws.amazon.com/waf/) |
| Thứ Tư, Năm (08-09/07) | **Tích hợp End-to-End**: Kiểm thử toàn bộ hệ thống. Đảm bảo luồng chạy chuẩn từ xác thực Cognito JWT -> API Gateway -> Lambda -> DynamoDB/S3. | 08/07/2026 | 09/07/2026 | System Architecture Diagram |
| Thứ Sáu (10/07) | **Tinh chỉnh Quyền IAM**: Audit toàn bộ các IAM Roles của Lambda, Step Functions. Gỡ bỏ các quyền thừa để tuân thủ nguyên tắc Least Privilege. | 10/07/2026 | 10/07/2026 | [AWS IAM Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) |
| Thứ 7 - CN (11-12/07) | **Tài liệu Clean-up**: Viết hướng dẫn từng bước để xóa bảng DynamoDB, S3 Bucket, và Lambda an toàn, tránh phát sinh chi phí khi không sử dụng. | 11/07/2026 | 12/07/2026 | AWS Cost Optimization Guidelines |

---

### **Kết quả đạt được (Week 12 Achievements)**

* Đưa thành công đồ án Hệ thống mô phỏng GenAI đi vào hoạt động toàn diện, đảm bảo tính bảo mật vòng ngoài và tối ưu chi phí vận hành.
* **Thiết lập Bảo mật Vòng ngoài**: Củng cố tuyến phòng thủ đầu tiên của hệ thống bằng cách định tuyến qua Route 53 và lọc request độc hại bằng AWS WAF, tạo ra môi trường an toàn cho người sử dụng.
* **Củng cố Nền tảng Bảo mật**: Hoàn tất việc rà soát IAM, đảm bảo mọi microservice chỉ giao tiếp với quyền hạn vừa đủ. Điều này thể hiện tư duy DevSecOps trưởng thành trong môi trường doanh nghiệp.
* **Sẵn sàng Vận hành & Dọn dẹp**: Hoàn thiện tài liệu "Clean-up" bắt buộc. Đảm bảo hạ tầng Serverless khổng lồ có thể được gỡ bỏ an toàn sau khi demo, loại trừ hoàn toàn rủi ro bị tính phí AWS ngoài ý muốn.
* **Tổng kết Thực tập**: Đã chuẩn bị đầy đủ log, metric, sơ đồ kiến trúc và code mẫu (snippet) để tiến hành viết báo cáo thực tập tổng hợp cuối kỳ.