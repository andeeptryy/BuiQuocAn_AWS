---
title: "WEEK 11 WORKLOG"
date: "2026-07-05"
weight: 11
chapter: false
pre: " <b> 1.11 </b> "
---

# **WEEK 11 WORKLOG**

### **Week 11 Objectives**

* Implement asynchronous processing for the "Attack Simulation" module to prevent API Gateway timeouts.
* Configure Amazon SQS and AWS Step Functions to orchestrate complex, long-running AI simulation tasks.
* Establish a robust Observability pipeline using Amazon CloudWatch for logging and metrics tracking.
* Set up automated alert notifications via Amazon SNS to instantly report critical network vulnerabilities detected by the AI.
* Conduct comprehensive API testing and record request/response logs for final reporting evidence.

---

### **Tasks to be carried out this week**

| Day | Task | Start Date | Completion Date | Reference/Material |
| :--- | :--- | :--- | :--- | :--- |
| 1 (Mon) | **Amazon SQS Configuration**: Set up Amazon SQS queues to receive and decouple "Scan Attack" payloads from the API Gateway. | 29/06/2026 | 29/06/2026 | [Amazon SQS Docs](https://docs.aws.amazon.com/sqs/) |
| 2 (Tue) | **AWS Step Functions Setup**: Built a state machine in Step Functions to orchestrate multiple Lambda functions running the attack simulation workflows asynchronously. | 30/06/2026 | 30/06/2026 | [AWS Step Functions Docs](https://docs.aws.amazon.com/step-functions/) |
| 3-4 (Wed-Thu) | **CloudWatch Integration**: Configured CloudWatch Log Groups for Lambda functions. Created dashboards to monitor API Gateway latency and AI execution metrics. | 01/07/2026 | 02/07/2026 | [Amazon CloudWatch Docs](https://docs.aws.amazon.com/cloudwatch/) |
| 5 (Fri) | **Amazon SNS Alerting**: Set up an SNS Topic and configured a Lambda trigger to send immediate email alerts when the system detects severe architectural flaws. | 03/07/2026 | 03/07/2026 | [Amazon SNS Docs](https://docs.aws.amazon.com/sns/) |
| 6-7 (Sat-Sun) | **API Testing & Log Collection**: Used Postman to simulate heavy traffic and prompt inputs. Collected CloudWatch logs and SNS email screenshots as evidence. | 04/07/2026 | 05/07/2026 | API Testing Tools |

---

### **Week 11 Achievements**

* Successfully completed 100% of the weekly plan, fulfilling the critical "Logging & Monitoring" requirement of the project.
* **Asynchronous Mastery**: Successfully decoupled the heavy AI simulation process from the main user request thread using Amazon SQS and Step Functions. This guarantees the API Gateway will not time out, significantly improving user experience.
* **Proactive Observability**: Built a complete monitoring and alerting loop. The integration of CloudWatch and SNS ensures that any system errors or detected network vulnerabilities are immediately pushed to administrators, shifting the operational mindset from reactive to proactive.
* **Next Steps**: Focus on securing the frontend layer using AWS WAF, finalizing the end-to-end integration, and preparing the mandatory Clean-up scripts.