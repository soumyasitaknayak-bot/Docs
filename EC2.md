## 📦 AWS EC2 – Elastic Compute Cloud

AWS EC2 provides resizable compute capacity in the cloud.

### EC2 sizing and configuration options:

- Operating System
- Instance Type (CPU, Memory, Storage)
- Network settings
- Security settings
- Key Pairs for SSH access
- Bootstrap scripts for initialization

### EC2 user data scripts

- Run during instance launch
- Automate setup tasks
- Used to install software, configure settings
- Runs with sudo privileges

### Types of EC2 Instances

1. On-Demand Instances
2. Reserved Instances
3. Spot Instances
4. Dedicated Hosts

We have families like General Purpose, Compute Optimized, Memory Optimized, Storage Optimized, and GPU Instances.

m5.2xlarge
m:instance type
5: generation
2:xlarge size

General Purpose: t3, m5

- daily computing needs

Compute Optimized: c5

- high performance computing
- batch processing, media transcoding

Memory Optimized: r5, x1e

- memory intensive apps
- databases, in-memory caches

Storage Optimized: i3, d2

- high storage throughput
- big data, data warehousing

https://instances.vantage.sh/

### Security Groups

- fundamental of EC2 security
- control inbound/outbound traffic
- groups only contain allow rules
- can only be refernced by ip or bu security group id
