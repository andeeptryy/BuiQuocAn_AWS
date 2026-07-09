---
title: "Blog 1: Software Supply Chain Security"
date: "2026-06-01"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# [SECURITY] BẢO MẬT CHUỖI CUNG ỨNG PHẦN MỀM THEO CHUẨN AWS WELL-ARCHITECTED
<span class="meta-info">Tác giả: Trevor Schiavone and Desiree Brunner | ngày: 26 tháng 05, 2026 | in</span> [Security](https://aws.amazon.com/blogs/security/), [Best Practices](https://aws.amazon.com/blogs/security/category/best-practices/), [AWS Well-Architected](https://aws.amazon.com/architecture/well-architected/) | [Facebook Post](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2179514172813543/)

Chào anh em AWS Study Group VN!

Thời gian gần đây, các cuộc tấn công chuỗi cung ứng (Software Supply Chain Attacks) qua <span class='highlight-code'>npm Registry</span> (như vụ Shai-Hulud, tea.xyz, axios...) đang bùng nổ. Kẻ tấn công thường chiếm quyền tài khoản maintainer hoặc lợi dụng lỗ hổng cấu hình trong môi trường CI/CD để chèn mã độc.

Dựa trên **AWS Well-Architected (Security Pillar)**, dưới đây là 5 Best Practices cốt lõi từ AWS Security Blog giúp anh em siết chặt phòng thủ:

## 1. Loại bỏ Long-term Credentials và Áp dụng Least Privilege
Mã độc luôn tìm cách quét các secret (<span class='highlight-code'>npm token</span>, <span class='highlight-code'>IAM Access Keys</span>) bị bỏ quên trên máy dev và môi trường CI/CD.
- **Với Developer:** Nên sử dụng lệnh <span class='highlight-code'>aws login</span> để lấy short-lived credentials thay vì lưu cứng key trong file config.
- **Với CI/CD:** Sử dụng <span class='highlight-code'>OIDC (OpenID Connect)</span> với GitHub Actions/GitLab CI để cấp quyền tạm thời theo từng job. Nếu bắt buộc phải dùng công cụ của bên thứ ba, hãy lưu trữ an toàn qua **AWS Secrets Manager** và thiết lập cơ chế tự động rotate key.

## 2. Phòng thủ nhiều lớp (Defense in Depth) & Ký xác thực
Một tài khoản bị lộ không nên là "dấu chấm hết" cho toàn bộ hệ thống.
- Bắt buộc kích hoạt **MFA** và áp dụng cơ chế multi-approval (phê duyệt nhiều bước) trước khi deploy lên môi trường Production.
- Sử dụng **AWS Signer** để ký xác thực artifact. Kết hợp **Amazon ECR** managed signing (tự động ký container image) và admission controller trên cụm EKS (như Kyverno) để đánh chặn các image không rõ nguồn gốc.

## 3. Quản lý Dependency tập trung
Thay vì pull trực tiếp các gói thư viện từ internet, hãy sử dụng **AWS CodeArtifact** để quản lý package nội bộ và định nghĩa upstream an toàn. Điều này giúp chặn đứng nguy cơ *Typosquatting*.
- Kiểm tra <span class='highlight-code'>npm provenance attestation</span> để xác minh package thực sự được build từ đúng mã nguồn gốc và luồng CI/CD chuẩn của tác giả.

## 4. Quét (Scanning) tự động và liên tục
Công cụ quét CVE truyền thống sẽ trở nên bất lực trước các mã độc Zero-day chưa từng được công bố.
- Tích hợp **Amazon Inspector** trực tiếp vào luồng CI/CD. Inspector sử dụng khả năng phân tích hành vi để phát hiện sớm các "sleeper packages" (mã độc ngủ đông) ngay cả trước khi chúng bị gán mã <span class='highlight-code'>MAL-ID</span>.
- Luôn xuất và lưu trữ định dạng <span class='highlight-code'>SBOMs (Software Bills of Materials)</span> để nắm quyền kiểm soát và cô lập thiệt hại nhanh nhất có thể khi xảy ra sự cố.

## 5. Tăng cường Logging & Monitoring
Bật **AWS CloudTrail** để audit toàn bộ các lời gọi API (API Calls). Cần giám sát đặc biệt các hành vi lạ, ví dụ như <span class='highlight-code'>sts:AssumeRole</span> từ một địa chỉ IP lạ, hoặc lệnh <span class='highlight-code'>ecr:PutImage</span> đẩy image trực tiếp từ máy dev mà không thông qua luồng CI/CD.
- Kết hợp **Amazon GuardDuty** và **Amazon EventBridge** để phát hiện các mối đe dọa và kích hoạt luồng phản hồi tự động (Automated Incident Response).

## Tổng kết
Bảo mật chuỗi cung ứng phần mềm trên Cloud không chỉ dừng lại ở việc viết code an toàn, mà nó là một **chiến lược toàn diện**: Xây dựng kiến trúc nhiều lớp (Defense in depth), triệt tiêu đặc quyền dài hạn và duy trì sự kiểm soát, giám sát tuyệt đối đối với mọi artifact trước khi đưa vào hệ thống vận hành.

> **Nguồn bài viết / Tài liệu tham khảo:** [Well-Architected best practices for software supply chain security](https://aws.amazon.com/vi/blogs/security/well-architected-best-practices-for-software-supply-chain-security/)
> **Bài viết trên cộng đồng:** [AWS Study Group FCJ Facebook Post](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2179514172813543/)