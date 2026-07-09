---
title: "Bản Đề Xuất"
date: "2026-07-09"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

![Sơ Đồ Kiến Trúc](/images/Proposal/Cloud-Nexus-Architecture.png)
<span class="meta-info">*Hình 1: Sơ đồ kiến trúc tổng thể của Cloud Nexus *</span>

## 1. TÓM TẮT ĐIỀU HÀNH

### 1.1 Tổng quan dự án
**Cloud Nexus** là nền tảng mô phỏng và phân tích bảo mật mạng (Threat Modeling Platform) dành cho các chuyên gia an ninh mạng và kiến trúc sư hạ tầng. Hệ thống cho phép người dùng thiết kế sơ đồ mạng trực quan trên giao diện web, sau đó sử dụng sức mạnh của Trí tuệ nhân tạo (Google Gemini 2.0 Flash) để tự động phát hiện lỗ hổng, mô phỏng đường đi tấn công và đề xuất các biện pháp phòng thủ một cách chính xác.

### 1.2 Mục tiêu chính
- Xây dựng một nền tảng serverless 100% trên AWS giúp tự động hóa quy trình đánh giá bảo mật mạng.
- Tích hợp AI để quét topology, phân tích lỗ hổng và mô phỏng kịch bản tấn công.
- Thiết lập hệ thống cảnh báo (Alert) qua SNS khi phát hiện các chuỗi tấn công nghiêm trọng.
- Triển khai Hạ tầng dưới dạng mã (Infrastructure as Code - IaC) bằng AWS CDK để dễ dàng quản lý.

### 1.3 Tiêu chí thành công
- Web dashboard tải thành công và mượt mà từ S3 static hosting.
- API Gateway phản hồi trạng thái `{"status":"ok"}` tại endpoint `/api/health`.
- Lambda gọi thành công Google Gemini API và trả về topology định dạng JSON hợp lệ.
- Toàn bộ hạ tầng có thể deploy (`cdk deploy`) và xóa (`cdk destroy`) chỉ bằng một câu lệnh.

---

## 2. PHÁT BIỂU VẤN ĐỀ

### 2.1 Vấn đề hiện tại
Việc thiết kế và kiểm định tính an toàn của một kiến trúc mạng đang gặp nhiều rào cản:
- Phát hiện lỗ hổng mạng bằng phương pháp thủ công tốn rất nhiều thời gian.
- Thiếu các công cụ giúp hình dung rõ ràng và trực quan đường đi của một cuộc tấn công.
- Việc thiết lập một môi trường thử nghiệm (test environment) thực tế rất phức tạp và rủi ro.
- Khó khăn trong việc so sánh hiệu quả của hệ thống trước và sau khi áp dụng các biện pháp phòng thủ.

### 2.2 Đối tượng khách hàng mục tiêu
- Chuyên gia bảo mật (Security Analysts).
- Kiến trúc sư hạ tầng đám mây (Cloud Architects).
- Sinh viên chuyên ngành An toàn thông tin / An ninh mạng.

---

## 3. KIẾN TRÚC GIẢI PHÁP

Hệ thống được thiết kế theo hướng hiện đại, kết hợp giữa Serverless và Generative AI:

- **Lớp Giao diện (Frontend):** Xây dựng bằng React + Vite + ReactFlow + Tailwind CSS, lưu trữ tĩnh trên Amazon S3.
- **Lớp Xử lý (Backend):** Sử dụng Framework FastAPI chạy trên môi trường AWS Lambda (Python 3.12 ARM64) và định tuyến thông qua Amazon API Gateway.
- **Lớp Trí tuệ Nhân tạo (AI):** Tích hợp Google Gemini API (model: Gemini 2.0 Flash) làm lõi phân tích logic bảo mật.
- **Lớp Hạ tầng (Infrastructure):** Quản lý toàn bộ bằng AWS CDK (TypeScript). Tận dụng Amazon DynamoDB (lưu trữ), Amazon SQS (hàng đợi bất đồng bộ), AWS Step Functions (điều phối) và AWS Secrets Manager (bảo mật API Key).

---

## 4. LỘ TRÌNH DỰ ÁN

Dự án được triển khai theo các giai đoạn cuốn chiếu từ đầu tháng 06 đến đầu tháng 07/2026:

| Giai đoạn | Nội dung công việc | Thời gian |
| :--- | :--- | :--- |
| **Khởi động** | Thiết lập môi trường, cấu hình IAM policy, AWS CLI. | 01/06 → 04/06 |
| **Frontend** | Xây dựng UI thao tác kéo thả với React + ReactFlow. | 05/06 → 09/06 |
| **Backend** | Phát triển FastAPI + Tích hợp AI service (Gemini 2.0 Flash). | 10/06 → 14/06 |
| **Infrastructure**| Viết mã AWS CDK stacks (Simulation, API, Frontend, Auth). | 15/06 → 19/06 |
| **Triển khai** | Đóng gói Lambda Layer, deploy toàn bộ stacks lên AWS. | 20/06 → 23/06 |
| **Tích hợp** | Kết nối luồng Frontend-Backend, cấu hình bảo mật API key. | 24/06 → 27/06 |
| **Kiểm thử** | Kiểm tra toàn bộ hệ thống (End-to-End), rà soát và fix bug. | 28/06 → 30/06 |
| **Hoàn thiện** | Viết báo cáo, tài liệu kỹ thuật và dọn dẹp tài nguyên. | 01/07 → 04/07 |

---

## 5. ƯỚC TÍNH NGÂN SÁCH

Thiết kế Serverless giúp tối ưu hóa chi phí đến mức tối đa, đưa ngân sách duy trì hệ thống nhàn rỗi về mức gần như bằng 0.

| Dịch vụ AWS / Đối tác | Chi phí ước tính / Tháng | Ghi chú |
| :--- | :--- | :--- |
| **Amazon S3** (Static Hosting) | ~$0.01 | Chi phí lưu trữ file tĩnh giao diện |
| **Amazon API Gateway** | $0.00 | Nằm trong giới hạn Free Tier |
| **AWS Lambda** | $0.00 | Nằm trong giới hạn Free Tier |
| **Amazon Cognito** | $0.00 | Nằm trong giới hạn Free Tier |
| **Amazon DynamoDB** | $0.00 | Nằm trong giới hạn Free Tier |
| **Amazon SQS & SNS** | $0.00 | Nằm trong giới hạn Free Tier |
| **AWS Step Functions** | $0.00 | Nằm trong giới hạn Free Tier |
| **AWS Secrets Manager** | ~$0.40 | Chi phí lưu 1 Secret Key cố định |
| **Google Gemini API** | $0.00 | Sử dụng gói Free Tier của Gemini 2.0 Flash |
| **Tổng chi phí ước tính** | **~$0.41/tháng** | Hệ thống cực kỳ tiết kiệm |

---

## 6. ĐÁNH GIÁ RỦI RO VÀ PHÒNG NGỪA

| Rủi ro | Mô tả chi tiết | Mức độ | Biện pháp giảm thiểu |
| :--- | :--- | :--- | :--- |
| **Lộ API Key** | Google API key vô tình bị commit lên GitHub. | Cao | Sử dụng AWS Secrets Manager và kiểm soát chặt `.gitignore`. |
| **Vượt chi phí ngoài ý muốn** | Hàm Lambda bị gọi liên tục do lỗi code hoặc bị tấn công DDoS. | Trung bình | Cấu hình CloudWatch Alarm và AWS Budget alert. |
| **Lỗi phản hồi AI** | Mô hình Gemini trả về định dạng JSON không hợp lệ gây sập logic. | Trung bình | Xây dựng cơ chế Retry logic (2 lần) và luồng Fallback an toàn. |
| **Lambda Timeout** | Quá trình AI suy luận mô phỏng mất quá 30 giây. | Thấp | Nâng cấu hình timeout và sử dụng xử lý bất đồng bộ qua SQS. |
| **Lỗi Deploy CDK** | Xung đột phiên bản môi trường AWS CDK. | Thấp | Cố định (Pin) phiên bản package và kiểm tra kỹ trước khi deploy. |
| **Lỗi CORS** | Trình duyệt chặn các request cross-origin từ Frontend. | Thấp | Đã cấu hình sẵn CORS middleware tại lớp FastAPI. |
| **Mất dữ liệu trạng thái** | Bảng DynamoDB bị xóa nhầm trong quá trình dọn dẹp. | Trung bình | Thiết lập cơ chế Backup và Point-in-Time Recovery. |

---

## 7. KẾT LUẬN
**Cloud Nexus** là một giải pháp thiết thực, chuyển đổi quy trình Threat Modeling khô khan thành một trải nghiệm trực quan, tự động và an toàn. Bằng việc bám sát kiến trúc Serverless trên AWS kết hợp năng lực cốt lõi của Google Gemini 2.0 Flash, dự án không chỉ đáp ứng hoàn hảo các tiêu chí kỹ thuật mà còn chứng minh được tính khả thi cao với mức chi phí vận hành gần như bằng không.