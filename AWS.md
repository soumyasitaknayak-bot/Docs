# ☁️ Cloud Computing & AWS

---

## 1️⃣ What is Cloud Computing?

Cloud computing is the **on-demand delivery** of IT resources over the internet with **pay-as-you-go pricing**.

### Key Points

- **On-demand delivery** – resources available instantly
- **Pay as you go** – pay only for what you use

---

## 2️⃣ Cloud Deployment Models

1. **Private Cloud**

   - Dedicated to a single organization
   - More control and security

2. **Public Cloud**

   - Shared infrastructure
   - Managed by providers like **Amazon Web Services**

3. **Hybrid Cloud**

   - Combination of private + public cloud
   - Flexible and scalable

---

## 3️⃣ Five Essential Characteristics of Cloud Computing

1. **On-demand self-service**
2. **Broad network access**
3. **Multi-tenancy & resource pooling**
4. **Rapid elasticity & scalability**
5. **Measured service**

---

## 4️⃣ Six Advantages of Cloud Computing

1. No upfront hardware cost
2. High scalability
3. High availability
4. Cost efficiency
5. Faster deployment
6. Global reach

---

## 5️⃣ Problems Solved by Cloud Computing

- Hardware procurement delays
- High infrastructure cost
- Scalability limitations
- Disaster recovery complexity
- Global accessibility issues
- Maintenance overhead

---

## 6️⃣ Types of Cloud Computing (Service Models)

1. **IaaS – Infrastructure as a Service**

   - Virtual machines, networking, storage
   - Example: EC2

2. **PaaS – Platform as a Service**

   - Runtime, OS, development platform
   - Example: Elastic Beanstalk

3. **SaaS – Software as a Service**

   - Fully managed applications
   - Example: Gmail, Salesforce

---

## 7️⃣ AWS Pricing – 3 Fundamentals

1. **Compute**
2. **Storage**
3. **Data transfer (OUT of the cloud)**

---

## 8️⃣ Brief History of Cloud Computing

- Concept evolved from virtualization
- Popularized after AWS launched EC2 in **2006**
- Enabled scalable, global infrastructure

---

## 9️⃣ AWS Availability Zones (AZ)

- Minimum **3**, maximum **6** per region
- Physically isolated from disasters
- Connected via **high bandwidth, low latency**
- Multiple AZs together form an **AWS Region**

---

## 🔐 AWS Shared Responsibility Model

### AWS – _Security **OF** the Cloud_

- Physical data centers
- Hardware
- Network infrastructure
- Managed services security

### Customer – _Security **IN** the Cloud_

- OS patching
- IAM configuration
- Data encryption
- Application security

---

# 👤 IAM – Identity and Access Management

**IAM** is a **global service** used to manage **users, groups, roles, and permissions**.

---

## IAM Core Concepts

### Root User

- Created by default
- Full access
- Should be locked and protected with MFA

### Users

- Individual identities
- Can belong to **multiple groups**

### Groups

- Collection of users
- **Cannot contain other groups**

### Permissions

- Defined using **JSON policies**
- Follow **least privilege principle**

---

## IAM Security Tools

1. **IAM Access Advisor**

   - Shows when services were last accessed

2. **IAM Credential Report**

   - Snapshot of all IAM users and credentials

---

## IAM Best Practices

1. Enable MFA for privileged users
2. Create individual IAM users
3. Use groups for permissions
4. Apply least privilege
5. Use roles for EC2 applications
6. Rotate credentials regularly
7. Use IAM Access Analyzer
8. Remove unused users/keys
9. Use AWS Organizations
10. Review permissions regularly

---

## ✅ Final Summary (Quick Revision)

- **Users** – individual identities
- **Groups** – permission containers
- **Roles** – for AWS services (EC2 → S3)
- **Policies** – JSON permission documents
- **Security** – MFA + password policy
- **Access** – Console, CLI, SDK
- **Audit** – Access Advisor, Credential Report

---
