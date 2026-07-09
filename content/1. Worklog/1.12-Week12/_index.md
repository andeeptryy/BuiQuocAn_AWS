---
title: "WEEK 12 WORKLOG"
date: "2026-07-09"
weight: 12
chapter: false
pre: " <b> 1.12 </b> "
---

# **WEEK 12 WORKLOG**

### **Week 12 Objectives**

* Deploy the Drag-Drop UI frontend on AWS Amplify and configure domain routing using Amazon Route 53.
* Secure the frontend application against web exploits (e.g., DDoS, Injection) by deploying AWS WAF (Web Application Firewall).
* Finalize the end-to-end system integration, ensuring seamless communication from Amazon Cognito authentication to DynamoDB storage.
* Review and refine all AWS IAM policies across the architecture to strictly enforce the Principle of Least Privilege.
* Develop detailed Clean-up scripts and documentation to tear down AWS resources, fulfilling project cost-management requirements.

---

### **Tasks to be carried out this week**

| Day | Task | Start Date | Completion Date | Reference/Material |
| :--- | :--- | :--- | :--- | :--- |
| 1 (Mon) | **Frontend Deployment**: Hosted the user interface on AWS Amplify. Configured DNS resolution and custom domain linking via Route 53. | 06/07/2026 | 06/07/2026 | [AWS Amplify Docs](https://docs.aws.amazon.com/amplify/) |
| 2 (Tue) | **AWS WAF Configuration**: Deployed AWS WAF with basic managed rule groups to protect the Amplify application from common web attacks and rate limiting. | 07/07/2026 | 07/07/2026 | [AWS WAF Documentation](https://docs.aws.amazon.com/waf/) |
| 3-4 (Wed-Thu) | **End-to-End Integration**: Conducted full system testing. Verified the flow from Cognito JWT authentication -> API Gateway -> Lambda -> DynamoDB/S3. | 08/07/2026 | 09/07/2026 | System Architecture Diagram |
| 5 (Fri) | **IAM Policy Refinement**: Audited all IAM roles used by Lambda, Step Functions, and API Gateway. Removed overly permissive policies to enforce Least Privilege. | 10/07/2026 | 10/07/2026 | [AWS IAM Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) |
| 6-7 (Sat-Sun) | **Clean-up Documentation**: Created a step-by-step guide and scripts to systematically delete DynamoDB tables, S3 buckets, and Lambda functions to avoid idle charges. | 11/07/2026 | 12/07/2026 | AWS Cost Optimization Guidelines |

---

### **Week 12 Achievements**

* Successfully brought the GenAI Network Architecture Simulator project to full functionality, securing the perimeter and ensuring cost efficiency.
* **Perimeter Security Established**: Strengthened the system's frontline defense by successfully routing traffic through Route 53 and filtering malicious requests with AWS WAF, guaranteeing a secure environment for end-users.
* **Robust Security Posture**: Conducted a thorough IAM audit, ensuring every microservice interacts strictly on a "need-to-know" basis, highlighting a mature DevSecOps mindset.
* **Operational Readiness**: Completed the mandatory "Clean-up" documentation. This ensures that the massive Serverless infrastructure can be reliably torn down after demonstrations, completely mitigating the risk of unexpected AWS billing.
* **Finalizing Internship**: Ready to consolidate the logs, metrics, architecture diagrams, and code snippets into the final comprehensive internship report.