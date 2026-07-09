---
title: "Blog 1: Software Supply Chain Security"
date: "2026-06-01"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# [SECURITY] SOFTWARE SUPPLY CHAIN SECURITY BASED ON AWS WELL-ARCHITECTED FRAMEWORK
<span class="meta-info">By Trevor Schiavone and Desiree Brunner | On May 26, 2026 | In</span> [Security](https://aws.amazon.com/blogs/security/), [Best Practices](https://aws.amazon.com/blogs/security/category/best-practices/), [AWS Well-Architected](https://aws.amazon.com/architecture/well-architected/) | [Facebook Post](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2179514172813543/)

Hello AWS Study Group VN community!

Recently, software supply chain attacks leveraging public repositories like <span class='highlight-code'>npm Registry</span> (such as the Shai-Hulud, tea.xyz, and axios incidents) have been on a massive rise. Attackers typically compromise maintainer accounts or exploit misconfigurations within CI/CD environments to inject malicious payloads.

Based on the **AWS Well-Architected Framework (Security Pillar)**, here are 5 core best practices from the AWS Security Blog to help you harden your defense mechanisms:

## 1. Eliminate Long-term Credentials & Implement Least Privilege
Malware constantly searches for exposed secrets, such as <span class='highlight-code'>npm tokens</span> or <span class='highlight-code'>IAM Access Keys</span>, inadvertently left on developer machines or embedded within CI/CD configurations.
- **For Developers:** Always use the <span class='highlight-code'>aws login</span> command to obtain short-lived credentials instead of hardcoding static access keys in local configuration files.
- **For CI/CD Pipelines:** Implement <span class='highlight-code'>OIDC (OpenID Connect)</span> authentication with GitHub Actions or GitLab CI to provision temporary, scoped IAM roles per job execution. If third-party integration is strictly required, store credentials securely in **AWS Secrets Manager** and configure automatic key rotation.

## 2. Enforce Defense in Depth & Artifact Signing
A single compromised account should never result in a total system breach.
- Enforce mandatory **Multi-Factor Authentication (MFA)** and establish multi-approval gates before any deployment to the Production environment.
- Leverage **AWS Signer** to cryptographically sign software artifacts. Combine this with **Amazon ECR** managed signing to automatically sign container images, and deploy an admission controller (such as Kyverno) on Amazon EKS to block unsigned or untrusted images from running.

## 3. Centralize Dependency Management
Instead of pulling packages directly from the public internet every time, utilize **AWS CodeArtifact** to manage internal dependencies and define secure upstream repositories. This effectively mitigates the risk of *Typosquatting* attacks.
- Verify <span class='highlight-code'>npm provenance attestations</span> to cryptographically validate that a package was genuinely built from the original source repository and via the author's authorized CI/CD workflow.

## 4. Automate Continuous Security Scanning
Traditional CVE scanners often fall short when dealing with unpublicized Zero-day exploits.
- Integrate **Amazon Inspector** directly into your CI/CD pipelines. Inspector leverages behavioral analysis to detect "sleeper packages" (latent malware) long before they are formally cataloged under a <span class='highlight-code'>MAL-ID</span> identifier.
- Consistently generate and store a <span class='highlight-code'>SBOM (Software Bill of Materials)</span> for every release to ensure complete visibility and enable rapid blast-radius isolation in the event of an incident.

## 5. Enhance Logging & Proactive Monitoring
Enable **AWS CloudTrail** to continuously audit all API calls. Set up real-time monitoring for anomalous operations, such as an unauthorized <span class='highlight-code'>sts:AssumeRole</span> request originating from an unknown IP address, or an explicit <span class='highlight-code'>ecr:PutImage</span> action pushed directly from a developer workstation bypassing the designated CI/CD pipeline.
- Pair **Amazon GuardDuty** with **Amazon EventBridge** to detect threat intelligence patterns and trigger automated incident response workflows instantly.

## Conclusion
Securing the software supply chain on the cloud goes beyond writing secure application code. It demands a **comprehensive strategy**: establishing a multi-layered defense-in-depth architecture, eradicating long-term privileged credentials, and maintaining absolute visibility and governance over every artifact before it enters the production lifecycle.

> **Original Reference:** [Well-Architected best practices for software supply chain security](https://aws.amazon.com/vi/blogs/security/well-architected-best-practices-for-software-supply-chain-security/)
> **Community Discussion:** [AWS Study Group FCJ Facebook Post](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2179514172813543/)