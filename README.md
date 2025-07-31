# 🎓 ORITM Graduation Surprise — Serverless Micro CRM

This project delivers a fully automated, branded graduation email surprise using a **serverless, event-driven architecture** on AWS — with *zero manual steps* and *zero SaaS cost*.  
It shows how smart **cloud primitives**, **secure transport**, and **system design principles** can replace heavy CRM tools.

## ✅ Key Features

- **📅 Event-driven**: `EventBridge Scheduler` triggers `AWS Lambda` at the exact graduation time (cron).
- **🧩 Dynamic content**: `Lambda` (Python) generates branded HTML with an inline header image.
- **📨 Secure delivery**: `Gmail SMTP` (Port 465, SSL/TLS) delivers the email via App Password — ensuring end-to-end encryption, no SES required.
- **📢 Delivery status**: `SNS` (Simple Notification Service) publishes success/failure notifications to an admin email.
- **🔒 Secured pipeline**: `IAM Roles` enforce least privilege. Secrets handled via environment variables (could extend to `Secrets Manager`).
- **📊 Observability**: `CloudWatch Logs` track execution, errors, and performance.

## ✅ System Design Highlights

- **Serverless by default**: No server management — fully managed AWS services.
- **Scalable**: Lambda auto-scales on demand.
- **Consistent**: Exactly-once cron, idempotent Lambda → no duplicate sends.
- **Fault Tolerant**: SNS notifications + CloudWatch monitoring ensure reliability.
- **Secure**: SMTP over SSL/TLS (Port 465), IAM Roles, App Passwords scoped to Lambda.
- **Infrastructure as Code**: Could be provisioned with `CloudFormation` or `Terraform`.
- **Extendable**: Easily plug in `DynamoDB` (recipient lists), `S3` (asset hosting), `SES` (bulk mail), `API Gateway` (CRM front end).


## ✅ Architecture Diagram

<img width="494" height="491" alt="micro-crm-architecture" src="https://github.com/user-attachments/assets/ad92dcee-c6ba-46e3-9540-ac01adaa11bb" />


## ✅ How It Works

1️⃣ **Scheduled Trigger**:  
`EventBridge Scheduler` runs at 3:45 AM IST on graduation day.

2️⃣ **Processing & Delivery**:  
`Lambda` generates the HTML email and connects to `Gmail SMTP` (Port 465, SSL/TLS) using a secure App Password.

3️⃣ **Monitoring & Notifications**:  
`Lambda` publishes success/failure to `SNS`, which pushes an alert to the admin’s inbox.  
Logs & metrics flow to `CloudWatch` for observability.

## ✅ Tools & Skills Demonstrated

- **AWS Lambda**
- **EventBridge Scheduler**
- **SNS (Simple Notification Service)**
- **Gmail SMTP (Port 465, SSL/TLS)**
- **IAM Roles & Secrets**
- **Python (Serverless runtime)**
- **CloudWatch Logs**
- **Event-driven serverless design**
- **Idempotent & exactly-once cron logic**
- **Secure email automation**


## ✅ If Scaled

The same pattern could scale to a **micro CRM**:
- `DynamoDB`: Store dynamic user lists & personalization data.
- `S3`: Host branded HTML templates.
- `SES`: High-volume email delivery at low cost.
- `API Gateway`: Expose endpoints for campaign creation or dashboarding.
- `Secrets Manager`: Manage SMTP/App Passwords securely at scale.

## ✅ Getting Started

> 📌 *Note:* This example uses a Gmail App Password for SMTP. Always store secrets in environment variables or `AWS Secrets Manager` for production.

1. Clone this repo:
   ```bash
   git clone https://github.com/YOUR_USERNAME/oritm-graduation-crm.git
   ```
   

## 📑 License

This project is open source under the [MIT License](./LICENSE).  
Feel free to fork, adapt, and build on it for learning or real use cases.

## 🤝 Let's Connect

Thanks for checking out this project!  
I love designing secure, serverless, event-driven solutions that create real impact.

📌 *If you're exploring Cloud, DevOps, System Design, or Automation — or just want to brainstorm cool ideas — I'd love to connect.*

- [🔗 Connect on LinkedIn](https://www.linkedin.com/in/ghaayathri-devi-k-21089b231/)
- [📧 Reach me by Email](mailto:kgd.careers@gmail.com)

🚀✨ *Let's build smart cloud solutions together!*

— **Ghaayathri Devi K**
