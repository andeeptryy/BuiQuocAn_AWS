---
title: "WEEK 7 WORKLOG"
date: "2026-06-08"
weight: 7
chapter: false
pre: " <b> 1.7 </b> "
---

# **WEEK 7 WORKLOG**

### **Week 7 Objectives**

* Nghiên cứu các phương pháp bảo mật chuỗi cung ứng phần mềm và chia sẻ kiến thức với cộng đồng.
* Thực hành trực quan hóa kiến trúc bảo mật và mô phỏng kịch bản phản ứng sự cố mạng (Incident Response) trên AWS.
* Triển khai tự động hóa quy trình sao lưu và kiểm thử phục hồi dữ liệu bằng sự kết hợp giữa AWS Backup, Lambda và SNS.
* Nắm vững các phương pháp quản trị hệ thống qua AWS Management Console, bảo mật định danh và tương tác hệ thống an toàn (CLI, SDK).

---

### **Tasks to be carried out this week**

| Day | Task | Start Date | Completion Date | Reference/Material |
| :--- | :--- | :--- | :--- | :--- |
| 1 (Thứ Hai) | **Bảo mật chuỗi cung ứng phần mềm**: Nghiên cứu AWS Well-Architected cho vòng đời SDLC (CI/CD, dependencies). Biên soạn và đăng tải bài viết chia sẻ kiến thức trên cộng đồng Facebook AWS Vietnam. | 01/06/2026 | 01/06/2026 | [AWS Security Blog](https://aws.amazon.com/vi/blogs/security/well-architected-best-practices-for-software-supply-chain-security/) |
| 2 (Thứ Ba) | **Mô phỏng kịch bản bảo mật AWS**: Sử dụng Draw.io thiết kế sơ đồ VPC. Trực quan hóa kịch bản tấn công (SSH Brute Force/Nmap), luồng logs tới CloudWatch và phản ứng sự cố chặn IP Hacker qua Subnet ACL. | 02/06/2026 | 02/06/2026 | [Draw.io Diagram](https://app.diagrams.net/) |
| 3 (Thứ Tư) | **Tự động hóa sao lưu & khôi phục**: Cấu hình AWS Backup Plan tự động. Tích hợp Lambda để chạy thử nghiệm khôi phục, kiểm tra tính toàn vẹn và dọn dẹp tài nguyên; cấu hình SNS gửi thông báo tiến trình. | 03/06/2026 | 03/06/2026 | [AWS Study Group](https://000013.awsstudygroup.com/) |
| 4 (Thứ Năm) | **Quản trị AWS Management Console**: Phân biệt Root User và IAM User, thiết lập MFA. Thực hành tương tác AWS CLI và SDK an toàn, hiểu rõ nguyên tắc bảo mật tuyệt đối Access Key/Secret Access Key. | 04/06/2026 | 04/06/2026 | [Video Link](https://www.youtube.com/watch?v=95quNuhvMT0&t=51s) |

---

### **Week 7 Achievements**

* Hoàn thành xuất sắc 100% kế hoạch nghiên cứu tài liệu, chia sẻ bài viết cộng đồng, vẽ sơ đồ kiến trúc nâng cao và thực hành các bài lab tự động hóa hệ thống theo đúng tiến độ được giao.
* **Trực quan hóa kiến trúc (Architecture Diagramming)**: Làm chủ công cụ thiết kế sơ đồ hạ tầng để mô tả chi tiết và sinh động luồng xử lý sự cố an ninh mạng (Incident Response) một cách tường minh và chuyên nghiệp.
* **Tư duy Tự động hóa & Khôi phục thảm họa (Disaster Recovery)**: Nâng cao năng lực triển khai hạ tầng tự động hóa quy trình backup/restore thông qua việc kết hợp các dịch vụ AWS Backup, Lambda và SNS, đảm bảo dữ liệu hệ thống luôn có khả năng phục hồi an toàn.
* **Quản trị hạ tầng và Truyền thông kỹ thuật (Technical Governance)**: Rèn luyện khả năng chuyển dịch thông tin từ tài liệu kỹ thuật phức tạp thành bài viết cộng đồng dễ hiểu, đồng thời củng cố vững chắc quy trình phân quyền và tương tác hệ thống an toàn (Console, CLI, SDK).
* **Kinh nghiệm rút ra**: Một hạ tầng công nghệ toàn diện không chỉ cần đảm bảo vận hành ổn định ngày qua ngày, mà quan trọng hơn là phải thiết lập được cơ chế bảo mật chuỗi cung ứng nghiêm ngặt kết hợp với quy trình kiểm thử dự phòng tự động hóa được thực hiện liên tục.
* **Định hướng tuần tới**: Tiếp tục đào sâu nghiên cứu các giải pháp tự động hóa quản trị nâng cao, tối ưu hóa các quy trình triển khai ứng dụng an toàn theo mô hình phát triển hiện đại.