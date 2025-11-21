# Secure AWS Foundation Project  
**Author:** Armon Jackson  
**Project Type:** Cloud Architecture + Security Hardening  
**AWS Services:** VPC, Subnets, IGW, EC2, IAM, S3, CloudTrail, Billing Alarm  
**Tools:** draw.io, AWS Console, Hostinger Horizon

---

## 📌 Project Overview
This project builds a secure, least-privilege AWS environment that demonstrates cloud architecture fundamentals, security best practices, and cost governance.  
It serves as the foundational project in my Cloud PM + Cloud Engineering portfolio.

The environment includes:
- A custom VPC with public and private subnets  
- A reachable EC2 instance secured behind a controlled Security Group  
- A locked-down S3 bucket with encryption and blocked public access  
- IAM role for least-privilege access to S3  
- CloudTrail for governance and audit logging  
- AWS Budgets + Billing Alarm for cost control  

This project demonstrates my ability to design, deploy, validate, and document an AWS environment that is **secure, organized, cost-aware, and production-aligned**.

---

## 🏗️ Architecture Diagram
![Architecture Diagram](./ARCHITECTURE%20DIAGRAM%20LAYOUT.png)

---

## 🔐 Key Security Controls
| Control | Description |
|---------|-------------|
| **Least-Privilege IAM Role** | EC2 instance can only read from one S3 bucket |
| **SG: web-sg** | Only HTTP/HTTPS inbound allowed; SSH restricted to my IP |
| **S3 Block Public Access** | All public ACLs and policies blocked |
| **S3 Encryption** | Default encryption = AES256 |
| **CloudTrail Logging** | All management events logged to S3 |
| **Budget Alarm** | Alerts if monthly cost exceeds $15 |

---

## 🌐 VPC & Networking Details
**VPC:** `secure-foundation-vpc (10.0.0.0/16)`  
**Subnets:**
- public-a (10.0.1.0/24) – EC2 lives here  
- public-b (10.0.2.0/24)  
- private-a (10.0.11.0/24)  
- private-b (10.0.12.0/24)

**Routing:**  
- Public route table → `0.0.0.0/0` → Internet Gateway (IGW)  
- Private subnets have no direct internet route  

**EC2 Instance:**  
- Name: `sf-web-1`  
- AMI: Amazon Linux 2023  
- App: Nginx  
- SG: HTTP/HTTPS inbound (SSH restricted), all outbound allowed  

---

## 📦 S3 Secure Bucket
**Bucket:** `sf-secure-artifacts`  
**Security Settings:**
- Block Public Access: **ON**  
- Default Encryption: **SSE-S3 (AES256)**  
- Optional policy denies public access & unencrypted uploads  

EC2 instance uses an IAM role (`ec2-s3-readonly`) to safely access specific S3 paths.

---

## 🧾 Project Artifacts
All project documentation is included in the **/docs** folder.

- **[Docs Folder](./docs/Project-Charter.md)**

---

## 📸 Screenshots
All screenshots proving setup and validation are stored in:

- **[Screenshots Folder](./screenshots/README.md)**
  
AWS-config-rule.png
Cloudtrail.png
CLoudwatch-billing-backup.png
EC2-IAM-role-public-IPV4.png
EC2-connect-terminal.png
S3-bucket-block-public-access.png
S3-bucket-encryption.png
Security-groups.png
VPC-subnets-routetable-IGW.png
budgets.png
nginx-browser.png

These confirm correct configuration and environment functionality.

---

## 🧪 Validation Summary
- EC2 reachable via public IP (`http://x.x.x.x`)  
- Nginx returns default page  
- EC2 Instance Connect works  
- EC2 can read from S3 via IAM role  
- No public access to S3 allowed  
- CloudTrail delivered logs to S3  
- Budget alarm created successfully  

---

## 🎯 Purpose of This Project
This project demonstrates:
- Real AWS hands-on capability  
- Ability to design secure cloud environments  
- Practical understanding of IAM, networking, and cost control  
- Documentation aligned with Cloud PM and Cloud Engineer roles  

This is the first project in my portfolio sprint.

---

## 🌐 Portfolio Link
You can view this project and others at:

**https://jacksoncloudsolutions.org**

---

## 📬 Contact
If you'd like to connect, feel free to reach out on LinkedIn:  
**[https://www.linkedin.com/in/armonjackson/]**

