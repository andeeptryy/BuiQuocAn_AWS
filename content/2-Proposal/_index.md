---
title: "Proposal"
date: "2026-07-09"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

![Architecture Diagram](/images/Proposal/Cloud-Nexus-Architecture.png)
<span class="meta-info">*Figure 1: Cloud Nexus Overall Architecture *</span>

## 1. EXECUTIVE SUMMARY

### 1.1 Project Overview
**Cloud Nexus** is a GenAI-powered Threat Modeling Platform built for cybersecurity professionals and infrastructure architects. The system enables users to visually design network topologies and leverages Google Gemini 2.0 Flash to automatically detect vulnerabilities, simulate attack paths, and recommend precise defensive measures.

### 1.2 Main Objectives
- Build a 100% serverless platform on AWS to automate the network security assessment workflow.
- Integrate AI to scan topologies, analyze vulnerabilities, and simulate attack scenarios.
- Establish an Alerting system via SNS for critical attack chain detections.
- Deploy Infrastructure as Code (IaC) using AWS CDK for automated provisioning and teardown.

### 1.3 Success Criteria
- Web dashboard successfully loads from S3 static hosting.
- API Gateway returns a `{"status":"ok"}` response at the `/api/health` endpoint.
- Lambda functions successfully invoke the Google Gemini API, returning valid JSON topologies.
- The entire infrastructure can be deployed (`cdk deploy`) and destroyed (`cdk destroy`) with a single command.

---

## 2. PROBLEM STATEMENT

### 2.1 Current Challenges
Designing and validating secure network architectures involves significant hurdles:
- Manual vulnerability detection is extremely time-consuming.
- It is difficult to visualize and quantify complex attack paths.
- Setting up realistic testing environments is complex, expensive, and risky.
- There is a lack of tools to visually compare an architecture's resilience before and after applying defenses.

### 2.2 Target Audience
- Security Analysts
- Cloud Architects
- Cybersecurity Students

---

## 3. SOLUTION ARCHITECTURE

The system is built on a modern, event-driven Serverless and Generative AI foundation:

- **Frontend:** Built with React + Vite + ReactFlow + Tailwind CSS, statically hosted on Amazon S3.
- **Backend:** Powered by FastAPI running on AWS Lambda (Python 3.12 ARM64) and routed via Amazon API Gateway.
- **AI Core:** Integrates Google Gemini API (Gemini 2.0 Flash model) for security logic and reasoning.
- **Infrastructure:** Fully managed via AWS CDK (TypeScript), utilizing Amazon DynamoDB (storage), Amazon SQS (async queues), AWS Step Functions (orchestration), and AWS Secrets Manager (credential security).

---

## 4. PROJECT TIMELINE

The project is executed in rolling phases from early June to early July 2026:

| Phase | Tasks | Duration |
| :--- | :--- | :--- |
| **Kick-off** | Environment setup, IAM policy configuration, AWS CLI. | 01/06 → 04/06 |
| **Frontend** | Build drag-and-drop UI with React + ReactFlow. | 05/06 → 09/06 |
| **Backend** | Develop FastAPI + Integrate AI service (Gemini 2.0 Flash). | 10/06 → 14/06 |
| **Infrastructure**| Write AWS CDK stacks (Simulation, API, Frontend, Auth). | 15/06 → 19/06 |
| **Deployment** | Build Lambda Layers, deploy all stacks to AWS. | 20/06 → 23/06 |
| **Integration** | Connect Frontend-Backend flows, secure API keys. | 24/06 → 27/06 |
| **Testing** | End-to-End system testing, QA, and bug fixing. | 28/06 → 30/06 |
| **Finalization** | Documentation, workshop reports, and resource cleanup. | 01/07 → 04/07 |

---

## 5. BUDGET ESTIMATION

The Serverless architecture maximizes cost efficiency, bringing the idle running cost to near zero.

| AWS Service / Partner | Estimated Cost / Month | Notes |
| :--- | :--- | :--- |
| **Amazon S3** (Static Hosting) | ~$0.01 | Storage cost for static UI assets |
| **Amazon API Gateway** | $0.00 | Covered by AWS Free Tier |
| **AWS Lambda** | $0.00 | Covered by AWS Free Tier |
| **Amazon Cognito** | $0.00 | Covered by AWS Free Tier |
| **Amazon DynamoDB** | $0.00 | Covered by AWS Free Tier |
| **Amazon SQS & SNS** | $0.00 | Covered by AWS Free Tier |
| **AWS Step Functions** | $0.00 | Covered by AWS Free Tier |
| **AWS Secrets Manager** | ~$0.40 | Cost for storing 1 fixed Secret Key |
| **Google Gemini API** | $0.00 | Utilizing Gemini 2.0 Flash Free Tier |
| **Total Estimated Cost** | **~$0.41/month** | Highly cost-effective system |

---

## 6. RISK ASSESSMENT

| Risk | Description | Impact | Mitigation Strategy |
| :--- | :--- | :--- | :--- |
| **API Key Exposure** | Google API key accidentally committed to Git. | High | Utilize AWS Secrets Manager and strict `.gitignore` rules. |
| **Unexpected Costs** | Continuous Lambda invocations due to bugs or DDoS. | Medium | Configure CloudWatch Alarms and AWS Budget alerts. |
| **AI Parsing Errors** | Gemini returns invalid JSON causing logic failures. | Medium | Implement Retry logic (2x) and a safe fallback mechanism. |
| **Lambda Timeouts** | AI inference takes longer than 30 seconds. | Low | Increase timeout limits and offload to SQS for async processing. |
| **CDK Deploy Failures** | Version conflicts in the AWS CDK environment. | Low | Pin package versions and pre-validate templates before deploying. |
| **CORS Issues** | Browsers block cross-origin requests from the Frontend. | Low | Pre-configure robust CORS middleware at the FastAPI layer. |
| **Data Loss** | Accidental deletion of DynamoDB tables during cleanup. | Medium | Enable Backups and Point-in-Time Recovery (PITR). |

---

## 7. CONCLUSION
**Cloud Nexus** is a highly practical solution that transforms the traditional, dry Threat Modeling process into an intuitive, automated, and secure visual experience. By strictly adhering to an AWS Serverless architecture combined with the core capabilities of Google Gemini 2.0 Flash, the project not only fulfills all technical criteria flawlessly but also demonstrates high commercial viability with near-zero operational costs.