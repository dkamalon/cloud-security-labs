
# ☁️ Cloud Security Labs & Mini Project  
Hands-on labs and a mini project focused on **cloud security** across **AWS, Azure, and GCP**.  
Built to gain practical experience in identifying and remediating misconfigurations and securing cloud environments.

## 🔗 Live Repository  
[github.com/deepakkamalon/cloud-security-labs](https://github.com/deepakkamalon/cloud-security-labs)

---

## 📚 Summary

- 35+ hours of guided and self-designed cloud security labs  
- Focus on Identity & Access Management, threat detection, encryption, and misconfiguration analysis  
- Includes a full mini-project: Secure AWS web app deployment with real-world attack simulations  

---

## 🔐 Cloud Platforms & Labs

### 🚀 AWS

- IAM Roles, Policies & Least Privilege Access  
- S3 Bucket Security: Public Access, Encryption, and Bucket Policies  
- KMS Encryption for storage and data protection  
- CloudTrail for auditing and logging  
- GuardDuty for threat detection  
- WAF for application-level protection

### ☁️ Azure

- Azure AD Identity & Conditional Access  
- NSGs (Network Security Groups)  
- Microsoft Defender for Cloud configuration  
- Azure Sentinel (SIEM)

### 🌐 GCP

- IAM Permissions and Roles  
- Security Command Center for threat detection and misconfigurations  

---

## 🛠️ Mini Project: Secure AWS Web Application

### 📌 Description  
Deployed a simple web application on AWS using EC2, S3, IAM, and security services.  
Intentionally simulated misconfigurations to demonstrate security risks and their remediation.

### ✅ Features

- EC2 Instance hosting web app with secure IAM role  
- S3 Bucket with public access simulation and then restriction  
- Logging with CloudTrail & Monitoring  
- WAF configuration to prevent common attacks  
- IAM misconfig simulation (e.g., full admin privileges) and secure policy rewrite  
- Documentation with before/after screenshots and JSON policy files  

### 📂 Project Structure

```
/aws-secure-webapp
├── architecture-diagram.png
├── EC2-setup.md
├── S3-security.md
├── IAM-policy-misconfigs.md
├── WAF-setup.md
├── CloudTrail-logs.md
└── remediation-notes.md
```

---

## 🎯 TryHackMe: Cloud Path Labs

- IAM Exploitation  
- Metadata Service Abuse  
- S3 Bucket Enumeration and Misconfiguration  
- Completed all Cloud Path modules: [TryHackMe Profile](https://tryhackme.com/p/deepakkamalon)

---

## 📸 Screenshots

_Add key screenshots from labs and project output here._

---

## 📁 How to Use

1. Clone the repo:  
   ```bash
   git clone https://github.com/deepakkamalon/cloud-security-labs.git
   ```
2. Explore each cloud platform’s folder for step-by-step lab walkthroughs  
3. Check the `aws-secure-webapp/` directory for the mini project

---

## 🧠 Skills Demonstrated

- Cloud security fundamentals  
- Hands-on configuration of IAM, encryption, logging, SIEM, and firewalls  
- Cloud-native tools (CloudTrail, Sentinel, Security Command Center)  
- Real-world misconfiguration simulation and remediation  
- Documentation & GitHub project structure

---

## 📫 Contact

Feel free to connect on [LinkedIn](https://linkedin.com/in/deepakkamalon) or drop an issue if you have any questions!
