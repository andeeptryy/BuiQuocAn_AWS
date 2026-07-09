---
title: "Blog 2: Verifiable Blockchain Key Management"
date: "2026-06-18"
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# [SECURITY/Web3] Building secure, verifiable blockchain key management on AWS Nitro Enclaves at Turnkey
<span class="meta-info">By Harshvardhan Chunawala and Jack Kearney | On June 08, 2026 | In</span> [Web3](https://aws.amazon.com/blogs/web3/), [Security](https://aws.amazon.com/blogs/web3/category/security-identity-compliance/security/), [AWS Nitro Enclaves](https://aws.amazon.com/ec2/nitro/nitro-enclaves/) | [Facebook Post](https://www.facebook.com/groups/awsstudygroupfcj/posts/2187837505314543/)

Hello AWS Study Group VN community!

The continuous string of private key compromises has made "Key Management" a massive headache for Web3/DeFi developers. 

I recently read a technical blog from the AWS Web3 Blog on how Turnkey completely resolves this issue by combining cryptography with the hardware infrastructure of **AWS Nitro Enclaves**. Here are the core highlights:

## 1. The Key Management Challenge
Traditional <span class='highlight-code'>transaction signing</span> processes often force developers into difficult tradeoffs between security and operational efficiency:
- **Do-It-Yourself (DIY) Infrastructure:** Requires massive capital expenditure and introduces high compliance risks.
- **Third-party Custodians:** Reduces direct control over assets and lacks operational transparency.
- **Standard Software Infrastructure:** <span class='highlight-code'>Raw keys</span> are highly vulnerable to extraction through <span class='highlight-code'>memory dumps</span> or <span class='highlight-code'>log files</span> if the ecosystem is compromised.

## 2. AWS Nitro Enclaves Isolation Mechanism
Turnkey implements an **Enclave-Native Key Management** model, shifting all sensitive operations—including key generation, digital signing, and policy execution—into AWS Nitro Enclaves:
- **Hardware Isolation:** The enclave environment has no persistent storage, no interactive access (no SSH), and no external internet connectivity.
- **Secure Communication:** Data is transmitted exclusively via an internal <span class='highlight-code'>VSOCK</span> channel. Configuration keys are decrypted only in RAM at the exact moment of transaction signing and are immediately purged. Neither Turnkey's system administrators nor AWS can access the raw keys.

## 3. Cryptographic Key Generation and Storage
The system utilizes a <span class='highlight-code'>Hierarchical Deterministic Wallet (HD Wallet)</span> model to manage derivative key structures:
- **Seed Generation:** Uses a highly secure random number generator provided by the hardware <span class='highlight-code'>Nitro Security Module (NSM)</span>.
- **Symmetric Encryption:** The root <span class='highlight-code'>Seed</span> string is encrypted using a master secret called the <span class='highlight-code'>Quorum Key</span> before being persisted to the database.
- **Transaction Signing:** The ciphertext is loaded into the enclave, temporarily decrypted in RAM to execute the cryptographic signing instruction, and then securely discarded. Raw keys are never written to disk.

## 4. Architecture: Separation of State and Data Flow
To simplify, Turnkey's architecture is divided into two distinct zones: The External Management Zone (untrusted) and the Internal Compute Zone (strictly trusted).

![Turnkey Architecture](/images/3-Blogs/Blog-3/image_0d024a.png)
<span class="meta-info">*Figure 1: Turnkey Infrastructure & Data Flow*</span>

- **External (AWS Cloud Infrastructure):** When a user sends a request via API Gateway, an <span class='highlight-code'>Amazon EC2</span> instance (Coordinator) processes it. State data and encrypted root keys are stored in the <span class='highlight-code'>Aurora Database</span>. Background tasks like the Async Queue, Redis, Updater, Heartbeat, and Webhook Notifiers only synchronize the system and send alerts. This zone is entirely oblivious to raw keys.
- **Internal (AWS Nitro Enclave):** The EC2 server forwards sensitive commands down to the Enclave via an internal <span class='highlight-code'>gRPC/VSOCK</span> channel. Within this isolated environment, processing is fully self-contained across 5 steps:
  1. **TLS Fetcher:** Establishes secure outbound network connections from within.
  2. **Parser:** Extracts and parses transaction data.
  3. **Policy Engine:** Verifies if the transaction complies with user-defined rules (limits, blocklists, etc.).
  4. **Notarizer:** Cryptographically authenticates valid transactions after they pass the policy engine.
  5. **Signer:** Fetches the encrypted key from the database, temporarily decrypts it in RAM to sign the transaction, and instantly wipes all traces.

## 5. Mathematical Remote Attestation
Turnkey shifts the paradigm from a *trust-based* model to a *verifiable* model based on:
- **Remote Attestation:** AWS provides a cryptographically signed attestation document verified by hardware to prove that the executing code inside the enclave hasn't been tampered with or implanted with malware.
- **Reproducible Builds:** The system operates on <span class='highlight-code'>QuorumOS</span>—a minimalist operating system. Independent third parties can compile the source code from scratch to verify the integrity of the deployed system.

## Real-world Applications
- **Embedded Wallets:** Integrating non-custodial wallets into decentralized applications with enterprise-grade security standards.
- **AI Agent Transactions:** Empowering AI agents to execute automated on-chain transactions based on pre-set policies without ever exposing the configuration keys.

## Conclusion
Turnkey's solution leverages AWS Nitro Enclaves to establish a closed-loop key processing workflow entirely in RAM, automatically freeing memory post-execution. The strict separation between state storage and the isolated hardware execution environment ensures digital assets remain protected even if the host infrastructure is breached. Simultaneously, through remote attestation and reproducible builds, the system allows users to independently verify the integrity and transparency of the entire cryptographic process.

> **Original Reference:** [Building secure, verifiable blockchain key management on AWS Nitro Enclaves at Turnkey](https://aws.amazon.com/blogs/web3/building-secure-verifiable-blockchain-key-management-on-aws-nitro-enclaves-at-turnkey/)
> **Community Discussion:** [AWS Study Group FCJ Facebook Post](https://www.facebook.com/groups/awsstudygroupfcj/posts/2187837505314543/)