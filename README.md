# AWS-EC2-Linux--Server-Launch
Launching an AWS EC2 Linux server means creating a virtual machine (VM) running a Linux-based operating system using Amazon Web Services' Elastic Compute Cloud (EC2). This virtual server provides a scalable and flexible environment to deploy applications, host websites, or run development workloads.  

# 🚀 Launching an EC2 Linux Server on AWS

This guide outlines the steps to launch, configure, and access a Linux-based EC2 instance on AWS.

---

## ✅ Prerequisites

- AWS account
- Basic knowledge of AWS Management Console
- Key pair (.pem) file for SSH access

---

## 📌 Steps to Launch an EC2 Linux Instance

### Step 1: Navigate to EC2 Dashboard
- Go to **EC2** under the AWS Management Console.
- Click **Launch instance**.

### Step 2: Configure Instance Basics
- **Name**: Enter a name for your instance (e.g., `Server-linux`)
- **Amazon Machine Image (AMI)**: Select **Amazon Linux 2023** or preferred Linux AMI.
- **Instance Type**: Choose `t2.micro` (Free Tier eligible).

### Step 3: Key Pair
- Select an existing key pair or create a new one.
- Download the `.pem` file if a new key is created.

### Step 4: Configure Network Settings
- Create a new security group or use an existing one.
- Allow:
  - **SSH (port 22)** — for remote login
  - **HTTP (port 80)** — for web traffic
  - **HTTPS (port 443)** — for secure web traffic (optional)

> 🔒 **Security Tip**: Use `My IP` instead of `Anywhere (0.0.0.0/0)` for SSH access in production.

### Step 5: Configure Storage
- Default 8 GiB root volume (gp3). Adjust as needed.

### Step 6: Launch Instance
- Click **Launch instance**.

---

## 🔗 Connect to EC2 Instance

1. Go to **EC2 > Instances**, select your running instance.
2. Click **Connect > EC2 Instance Connect (browser-based SSH)** or use:

```bash
ssh -i /path/to/key.pem ec2-user@<your-public-ip>

