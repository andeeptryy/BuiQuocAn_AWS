---
title: "WEEK 9 WORKLOG"
date: "2026-06-21"
weight: 9
chapter: false
pre: " <b> 1.9 </b> "
---

# **WEEK 9 WORKLOG**

### **Week 9 Objectives**

* Research and complete the in-depth translation of the AWS technical blog on cloud networking and Generative AI.
* Analyze requirements, finalize the user flow, and kick-off the GenAI Network Architecture Simulator project.
* Design a Serverless architecture (Amazon API Gateway & AWS Lambda) to fulfill the Cost Optimization requirement.
* Establish a secure team collaboration environment by configuring access control through AWS IAM.
* Optimize the storage of network states by utilizing a NoSQL database (Amazon DynamoDB) instead of a traditional relational database.

---

### **Tasks to be carried out this week**

| Day | Task | Start Date | Completion Date | Reference/Material |
| :--- | :--- | :--- | :--- | :--- |
| 1 (Mon) | **AWS Technical Research**: Read and deeply researched the 2nd AWS technical blog covering cloud networking and GenAI applications. Extracted core concepts. | 15/06/2026 | 15/06/2026 | [AWS Networking Blog](#) |
| 2 (Tue) | **Technical Translation**: Translated the blog content into Vietnamese, formatted in Markdown, and aligned technical terminologies to ensure academic accuracy. | 16/06/2026 | 16/06/2026 | [AWS Networking Blog](#) |
| 3 (Wed) | **GenAI Project Kick-off**: Kicked off the group project focusing on building a GenAI-based Network Architecture Simulator. Defined the core user flow. | 17/06/2026 | 17/06/2026 | Project Requirements |
| 4 (Thu) | **Serverless Architecture Design**: Designed the AWS Cloud Architecture. Transitioned from EC2 instances to a Serverless model (API Gateway & Lambda) to minimize costs. | 18/06/2026 | 18/06/2026 | [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/) |
| 5 (Fri) | **AWS IAM Configuration**: Set up foundational AWS Identity and Access Management roles and policies for the 5 team members to collaborate securely. | 19/06/2026 | 19/06/2026 | [AWS IAM Documentation](https://docs.aws.amazon.com/iam/) |
| 6-7 (Sat-Sun) | **System Documentation**: Documented the system design and researched Amazon Bedrock as a potential managed service to power the GenAI engine safely. | 20/06/2026 | 21/06/2026 | [Amazon Bedrock Docs](https://docs.aws.amazon.com/bedrock/) |

---

### **Week 9 Achievements**

* Successfully completed 100% of the weekly plan, establishing the foundational architecture and team workflow for the new GenAI project.
* **Completed Project Blueprint**: Successfully finalized the core user flow and cloud architecture for the GenAI Network Simulator project.
* **Optimized Infrastructure Costs**: Solved the challenge of storing dynamic user-edited network models (JSON format) without incurring high relational database costs by integrating Amazon DynamoDB.
* **Key Takeaway**: Realized that making critical architectural decisions early, such as choosing NoSQL over relational databases for dynamic states, practically applies the "Cost Optimization" pillar of the AWS Well-Architected Framework and prevents future technical debt.
* **Next Steps**: Begin writing code to deploy the foundational Serverless infrastructure and initialize the core AWS Lambda functions.