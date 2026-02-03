# AWS Secrets Manager – Secure Credential Management

## 📌 Project Overview
This project demonstrates how to securely manage AWS credentials using **AWS Secrets Manager** instead of hardcoding sensitive information in application code.

<img width="826" height="700" alt="Screenshot 2026-01-28 160532" src="https://github.com/user-attachments/assets/cde81052-a682-4bb1-94fe-245013e02cc8" />


The goal was to follow cloud security best practices and prevent credential exposure in source control systems like GitHub.
---

## ❓ Problem Statement
Hardcoding AWS access keys in application code is insecure and can lead to:
- Credential leaks
- Unauthorized access
- Security breaches
- GitHub push protection failures

---

## ✅ Solution
Implemented **AWS Secrets Manager** to store sensitive credentials securely and retrieve them dynamically at runtime using the AWS SDK for Python (`boto3`).

No secrets are stored in code or committed to GitHub.

---

## 🏗️ Architecture / Flow
1. AWS credentials are stored securely in AWS Secrets Manager
2. Application uses IAM permissions to access the secret
3. Secrets are retrieved dynamically at runtime
4. Credentials are never hardcoded or exposed

---

## 🛠️ Technologies Used
- AWS Secrets Manager
- AWS IAM
- Python
- boto3
- Git & GitHub

---

## 🚀 Implementation Steps
1. Created a secret in AWS Secrets Manager
2. Stored credentials as JSON key-value pairs
3. Configured IAM permissions (`secretsmanager:GetSecretValue`)
4. Used boto3 to retrieve secrets securely
5. Removed all hardcoded credentials
6. Verified GitHub push protection blocked secret exposure

---

## 🔐 Security Best Practices Followed
- No hardcoded AWS credentials
- Secrets managed via AWS Secrets Manager
- IAM least-privilege access
- GitHub secret scanning respected
- Local credentials cleaned after testing

---

## ▶️ How to Run (Local Testing)
```bash
python -m venv venv
venv\Scripts\activate
pip install boto3
python app.py
