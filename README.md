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
   <img width="1920" height="752" alt="Screenshot (116)" src="https://github.com/user-attachments/assets/327f4276-dd10-4485-9e48-4337315acff2" />
   <img width="1017" height="531" alt="Screenshot 2026-02-03 164607" src="https://github.com/user-attachments/assets/4b734615-9487-4df3-a29c-4e6d9b3f1013" />

2. Stored credentials as JSON key-value pairs
   <img width="1005" height="579" alt="image" src="https://github.com/user-attachments/assets/8d05310b-1ef6-4561-8f5d-fdcb7c03aec8" />

3. Used sample code from Secrets Manager to update our config.py file.
   <img width="1015" height="530" alt="Screenshot 2026-02-03 164738" src="https://github.com/user-attachments/assets/2ae4b036-c30c-4c5d-ac97-11a354723e31" />

4. Added code to use the get_secret() function & boto3 to retrieve our credentials securely
   <img width="1024" height="145" alt="Screenshot 2026-02-03 164852" src="https://github.com/user-attachments/assets/4540f23d-68f4-4b36-9951-486e6f7bfdc6" />
   <img width="1000" height="433" alt="Screenshot 2026-02-03 165029" src="https://github.com/user-attachments/assets/2211bd2c-7103-4437-8af0-321d5fadd3a1" />

5. Pushed code on GitHub and run the app.
   <img width="1028" height="500" alt="Screenshot 2026-02-03 170208" src="https://github.com/user-attachments/assets/310bab54-4b4f-4548-a93c-70cecc449be6" />
   <img width="1029" height="524" alt="Screenshot 2026-02-03 170120" src="https://github.com/user-attachments/assets/dc89a1a5-20fd-46c2-8145-36e7039c427d" />
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
