---
title: "BÁO CÁO TUẦN 10"
date: "2026-06-28"
weight: 10
chapter: false
pre: " <b> 1.10 </b> "
---

# **BÁO CÁO TUẦN 10**

### **Mục tiêu trong tuần**

* Triển khai thực tế hạ tầng Serverless trên AWS dựa trên bản thiết kế hệ thống.
* Phát triển thành công các hàm AWS Lambda và API Gateway để kết nối giao diện người dùng với DynamoDB.
* Phác thảo logic và xây dựng bộ khung cho module "Validation Engine" nhằm kiểm duyệt tính an toàn của kiến trúc mạng.
* Tham gia sự kiện FCAJ Community Day để cập nhật kiến thức về tự động hóa vận hành và bảo mật AI trong môi trường doanh nghiệp lớn.
* Nghiên cứu Giao thức MCP (Model Context Protocol) nhằm xử lý chuẩn xác "ngữ cảnh" cho hệ thống AI, giảm thiểu lỗi ảo giác.

---

### **Lịch trình công việc chi tiết**

| Ngày | Nội dung công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu / Lab |
| :--- | :--- | :--- | :--- | :--- |
| Thứ Hai (22/06) | **Triển khai Hạ tầng Serverless**: Cấu hình hạ tầng trên AWS dựa trên thiết kế. Thiết lập môi trường lập trình cục bộ (Local) và kết nối với tài khoản AWS. | 22/06/2026 | 22/06/2026 | AWS Console |
| Thứ Ba (23/06) | **Khởi tạo AWS Lambda**: Lập trình và khởi tạo các hàm AWS Lambda cốt lõi xử lý việc tiếp nhận Prompt và chuẩn bị dữ liệu cho khâu AI tạo mô hình. | 23/06/2026 | 23/06/2026 | [AWS Lambda Documentation](https://docs.aws.amazon.com/lambda/) |
| Thứ Tư, Năm (24-25/06) | **Tích hợp API & Validation Engine**: Xây dựng API endpoints qua API Gateway kết nối frontend với DynamoDB. Lên khung logic cho Validation Engine. | 24/06/2026 | 25/06/2026 | [Amazon API Gateway Docs](https://docs.aws.amazon.com/apigateway/) |
| Thứ Sáu (26/06) | **Đóng gói Mã nguồn**: Hoàn tất module code, đóng gói mã nguồn dự án. Chuẩn bị tài liệu và câu hỏi chuyên sâu tham gia sự kiện công nghệ. | 26/06/2026 | 26/06/2026 | Project Source Code |
| Thứ Bảy (27/06) | **Sự kiện FCAJ Community Day**: Tham dự sự kiện "Data Driven, AI Risen". Tập trung nghiên cứu Deep Response Engine và cách xử lý ngữ cảnh AI cấp doanh nghiệp. | 27/06/2026 | 27/06/2026 | [FCAJ Event](#) |
| Chủ nhật (28/06) | **Nghiên cứu MCP & Báo cáo**: Viết báo cáo tổng kết sự kiện, đề xuất tích hợp Giao thức MCP (Model Context Protocol) vào khâu AI Validation của dự án. | 28/06/2026 | 28/06/2026 | [Model Context Protocol Docs](#) |

---

### **Kết quả đạt được (Week 10 Achievements)**

* Hoàn thành xuất sắc 100% kế hoạch tuần, tiến bước từ thiết kế lý thuyết sang thực hành mã hóa và trau dồi kiến thức từ môi trường doanh nghiệp thực tế.
* **Tích hợp API thành công**: Triển khai thông suốt hạ tầng Serverless nền tảng, đảm bảo luồng giao tiếp mượt mà giữa Frontend, AWS Lambda và Amazon DynamoDB thông qua API Gateway.
* **Đột phá trong xử lý Ngữ cảnh AI (Context Engineering)**: Giải quyết vấn đề AI bị ảo giác (hallucination) bằng cách thiết lập cấu trúc định dạng JSON từ DynamoDB thành một bộ ngữ cảnh chặt chẽ.
* **Kinh nghiệm rút ra**: Nhận ra rằng "Ngữ cảnh là tất cả" đối với việc kiểm tra kiến trúc mạng bằng AI. Cung cấp bộ bối cảnh chặt chẽ là chìa khóa để AI đưa ra các cảnh báo bảo mật chính xác tuyệt đối dựa trên bản vẽ thực tế.
* **Định hướng tuần tới**: Hoàn thiện khâu AI Validation, tích hợp chính thức giao thức MCP, và chuẩn bị dữ liệu nền tảng cho kịch bản mô phỏng tấn công mạng.