# 🛡️ SOC2 Automated Compliance Gates

**Continuous Compliance and Zero-Trust CI/CD Pipeline for B2B SaaS.**

This repository demonstrates a production-grade DevSecOps pipeline designed to automatically enforce SOC2 and ISO27001 security controls before any code reaches production. By shifting security left, we eliminate compliance bottlenecks and prevent costly misconfigurations.

## 🏗️ Architecture & SOC2 Mapping

This pipeline integrates three crucial security gates, directly mapping to SOC2 Common Criteria (CC):

1. **Secrets Detection (Semgrep)** - **SOC2 Control:** CC6.1 (Logical Access Security)
   - **Action:** Scans source code for hardcoded API keys, passwords, and tokens, preventing unauthorized access vectors.

2. **Infrastructure-as-Code Scanning (Checkov)**
   - **SOC2 Control:** CC6.6 (Boundary Protection) & CC6.7 (Data Transmission)
   - **Action:** Validates Terraform/OpenTofu configurations to ensure databases are encrypted at rest, storage buckets are private, and least-privilege policies are enforced.

3. **Container & Dependency Scanning (Trivy)**
   - **SOC2 Control:** CC7.1 (Vulnerability Management)
   - **Action:** Inspects open-source dependencies and container images for known CVEs (CRITICAL and HIGH severity), ensuring a secure software supply chain.

## ⚙️ How It Works

This GitHub Actions workflow is triggered automatically on every `push` and `pull_request` to the `main` branch. If any security policy is violated, the pipeline fails, blocking the merge and generating an auditable log for compliance reporting.

---

### 📬 Let's Automate Your Compliance
Are you a B2B SaaS startup preparing for a SOC2 audit to close enterprise deals? Let's integrate these automated guardrails into your infrastructure.

🔗 **Contact me:** [linkedin.com/in/trustascode](https://www.linkedin.com/in/trustascode)
