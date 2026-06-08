---
title: "WEEK 5 WORKLOG"
date: "2026-06-08"
weight: 5
chapter: false
pre: " <b> 1.5 </b> "
---

# **WEEK 5 WORKLOG**

### **Week 5 Objectives**

* Làm chủ khả năng giám sát toàn diện (observability) thông qua Amazon CloudWatch (Logs, Metrics, Events, Alarms) và công cụ giám sát vi dịch vụ CloudWatch Container Insights.
* Xây dựng chiến lược tối ưu hóa chi phí EC2 bằng cách kết hợp kịch bản tự động hóa (AWS Lambda) cho các môi trường linh hoạt và cam kết dài hạn (Savings Plans) cho hệ thống ổn định.
* Khám phá hệ sinh thái Generative AI trên AWS, trọng tâm là dịch vụ Amazon Bedrock, Foundation Models (FMs) và kiến trúc tích hợp AI vào ứng dụng.
* Mở rộng mạng lưới kết nối chuyên gia và cập nhật xu hướng AI thực chiến thông qua sự kiện FCAJ Community Day.

---

### **Tasks to be carried out this week**

| Day | Task | Start Date | Completion Date | Reference/Material |
| :--- | :--- | :--- | :--- | :--- |
| 1 (Thứ Hai) | **Thực hành AWS CloudWatch**: Nghiên cứu kiến trúc CloudWatch để hợp nhất Logs, Metrics và Events. Tìm hiểu cơ chế cảnh báo tự động (Alarms) và Container Insights dành cho môi trường EKS/ECS. | 18/05/2026 | 18/05/2026 | [AWS Study Group Lab](https://000008.awsstudygroup.com/) |
| 2 (Thứ Ba) | **Tối ưu chi phí EC2 bằng Lambda**: Tìm hiểu cách sử dụng CloudWatch Events kích hoạt AWS Lambda (dùng SDK boto3) để tự động bật/tắt máy chủ EC2 theo lịch trình cho các môi trường Dev/Test. | 19/05/2026 | 19/05/2026 | [Cost Optimization Guide](https://000022.awsstudygroup.com/) |
| 3 (Thứ Tư) | **Tối ưu chi phí EC2 bằng Savings Plans**: Phân biệt Compute Savings Plan và EC2 Instance Savings Plan. Phân tích use-case để áp dụng Savings Plan cho các hệ thống Production chạy 24/7 so với dùng Lambda. | 20/05/2026 | 20/05/2026 | [Cost Optimization Guide](https://000022.awsstudygroup.com/) |
| 4 (Thứ Sáu) | **Gen AI trên AWS (AWS Kiro)**: Nghiên cứu khái niệm Gen AI, dịch vụ Amazon Bedrock (Anthropic Claude, Llama, Titan), cơ chế Guardrails và cách thiết kế ứng dụng tích hợp AI dùng Lambda, API Gateway, DynamoDB. | 22/05/2026 | 22/05/2026 | [Video Link](https://www.youtube.com/watch?v=uAQCm4sm_1c) |
| 5 (Thứ Bảy) | **Sự kiện FCAJ Community Day**: Tham dự phiên hội thảo "Context Is Everything". Nắm bắt sự tiến hóa của AI từ việc dựa vào prompt sang mô hình xử lý ngữ cảnh/bộ nhớ dài hạn và định hướng nghề nghiệp AI. | 23/05/2026 | 23/05/2026 | Tòa nhà Bitexco |

---

### **Week 5 Achievements**

* Hiểu rõ kiến trúc tổng thể của Amazon CloudWatch, biết cách phân tách và sử dụng Logs, Metrics, Events để xây dựng bảng điều khiển giám sát (Dashboard) tập trung, tránh tình trạng theo dõi rời rạc.
* Nắm vững kỹ thuật lập trình AWS Lambda (boto3) để can thiệp vào vòng đời hoạt động của EC2, giúp tự động hóa việc tắt/mở máy chủ nhằm giảm thiểu chi phí vận hành.
* Xây dựng thành công tư duy tối ưu chi phí EC2 toàn diện: áp dụng tự động hóa (Automation) cho các workload biến động và sử dụng Savings Plans cho các workload production chạy liên tục.
* Khai phá kiến thức nền tảng về hệ sinh thái Gen AI trên AWS, hiểu rõ vai trò trung tâm của Amazon Bedrock trong việc quản lý Foundation Models và kiến trúc tích hợp hệ thống backend.
* Rút ra được bài học thực tiễn về tầm quan trọng của "Ngữ cảnh" (Context) trong việc giảm thiểu lỗi hallucination và tăng độ chính xác cho AI từ buổi hội thảo FCAJ Community Day.
* Tham gia networking hiệu quả, kết nối với cộng đồng kỹ sư Cloud và sinh viên IT đam mê AWS tại khu vực TP. Hồ Chí Minh.