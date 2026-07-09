---
title: "WEEK 8 WORKLOG"
date: "2026-06-14"
weight: 8
chapter: false
pre: " <b> 1.8 </b> "
---

# **WEEK 8 WORKLOG**

### **Week 8 Objectives**

* Master the AWS Unified Operations framework, shifting from reactive troubleshooting to a proactive prevention mindset (Shift-Left) for mission-critical systems.
* Gain proficiency in containerizing applications using Docker Compose, managing repositories with Amazon ECR, and deploying on Amazon EC2.
* Build automated Continuous Integration and Continuous Deployment (CI/CD) pipelines for containerized applications on Amazon ECS to optimize software Quality Control (QC).
* Optimize application performance and analytical data warehousing using Amazon ElastiCache (Redis/Memcached) and Amazon Redshift.
* Extend and isolate private network communication by configuring VPC Peering connections and subnet-level Network ACLs.

---

### **Tasks to be carried out this week**

| Day | Task | Start Date | Completion Date | Reference/Material |
| :--- | :--- | :--- | :--- | :--- |
| 1 (Mon) | **AWS Unified Operations**: Studied framework methodologies for building resilient operations. Applied Shift-Left strategies to reduce MTTI/MTTR through automated incident patterns and proactive monitoring. | 08/06/2026 | 08/06/2026 | [AWS Cloud Operations Blog](https://aws.amazon.com/vi/blogs/mt/aws-unified-operations-building-resilient-operations-for-mission-critical-workloads/) |
| 2 (Tue) | **Application Deployment with Docker**: Practiced packaging applications via Docker Compose. Deployed infrastructure on Amazon EC2, integrated Amazon RDS, and pushed images to Amazon ECR. | 09/06/2026 | 09/06/2026 | [AWS Lab 000015](https://000015.awsstudygroup.com/) |
| 3 (Wed) | **Amazon Redshift & ElastiCache**: Explored Massively Parallel Processing (MPP) and Columnar storage in Redshift. Analyzed ElastiCache architecture for in-memory caching logic to offload relational databases. | 10/06/2026 | 10/06/2026 | [Video Module 06-03](https://www.youtube.com/watch?v=UvdiRW34aNI) |
| 4 (Thu) | **CI/CD for Containers on ECS**: Configured automated integration and deployment workflows using GitHub/GitLab and AWS CodeBuild. Set up Container Insights and managed log routers with Firelens. | 11/06/2026 | 11/06/2026 | [AWS Lab 000017](https://000017.awsstudygroup.com/vi/) |
| 5 (Fri) | **Network Security with VPC Peering & NACL**: Established secure VPC Peering connections between isolated VPCs. Configured stateless Network ACLs at the subnet level and enabled Cross-Peering DNS. | 12/06/2026 | 12/06/2026 | [AWS Lab 000019](https://000019.awsstudygroup.com/vi/) |
| 6 (Sat) | **AWS Community Meetup**: Participated in the "First Cloud AI Journey" meetup. Learned about real-world DevOps practices, MNC corporate culture, and AWS community growth paths. | 13/06/2026 | 13/06/2026 | [FCAJ Meetup](#) |

---

### **Week 8 Achievements**

* Successfully completed 100% of the weekly plan, transitioning from foundational security governance to modern cloud application deployment and automation.
* **Unified Operations & Shift-Left**: Grasped the core principles of adopting a proactive monitoring strategy to intercept operational anomalies before they escalate, ensuring enterprise-grade platform resiliency.
* **Containerization & CI/CD**: Mastered the complete deployment lifecycle of containerized workloads, successfully building robust CI/CD pipelines that streamline code testing and deployment, effectively eradicating human operational errors.
* **Data Optimization**: Acquired technical depth in data delivery acceleration by leveraging Redshift's columnar architecture for high-performance analytical queries and designing low-latency in-memory caching solutions using ElastiCache.
* **Key Takeaway**: Realized that a secure and highly available application must go hand-in-hand with an automated pipeline (CI/CD) and containerized isolation, ensuring that security and quality are continuously tested at every stage of the software development lifecycle.
* **Next Steps**: Apply the CI/CD and containerization concepts learned to design the architectural proposal for the final internship project, focusing on automated DevSecOps workflows.