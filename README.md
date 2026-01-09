# 🚀 Deploy EC2 Using Terraform

This repository contains Terraform infrastructure-as-code to **provision an AWS EC2 instance** in your AWS account.  
The goal is to automate the creation of compute resources using Terraform so that infrastructure is reproducible, version-controlled, and scalable. :contentReference[oaicite:0]{index=0}

---

## 🧱 Project Overview

With this Terraform configuration you will:

✔ Configure the **AWS provider**  
✔ Create a **security group** for EC2 access  
✔ Deploy an **EC2 instance** with your selected AMI and instance type  
✔ Output the *public IP / DNS* of the EC2 instance after creation :contentReference[oaicite:1]{index=1}

This is a foundational IaC example to help automate cloud infrastructure deployments. :contentReference[oaicite:2]{index=2}

---

## 🛠 Tools & Technologies

- **Terraform (>= 1.0)**
- **AWS Provider**
- **Amazon EC2**
- **AWS IAM credentials**
- (Optional) **SSH keypair** for login

---

## 📁 Repository Structure

.
├── main.tf # AWS provider & EC2 instance resource
├── variables.tf # Input variables for key configuration
├── output.tf # Outputs (public IP / DNS)
├── terraform.tfstate # Terraform state (auto-generated)
├── .terraform.lock.hcl # Dependency lock
└── README.md # This documentation

---

## 🚀 Usage Instructions

### 1️⃣ Install Terraform

Download and install Terraform from the official HashiCorp site, then verify with:

```sh
terraform --version

```
2️⃣ Configure AWS Credentials

Before running Terraform, set your AWS credentials:

```
export AWS_ACCESS_KEY_ID="YOUR_ACCESS_KEY"
export AWS_SECRET_ACCESS_KEY="YOUR_SECRET_KEY"
export AWS_DEFAULT_REGION="ap-south-1"

```
(You can also use aws configure with the AWS CLI)
3️⃣ Initialize Terraform
```
terraform init
```
4️⃣ Preview Deployment
```
terraform plan

```
This shows what resources Terraform will create.
5️⃣ Deploy Infrastructure
```
terraform apply
```
6️⃣ View Outputs

After successful deployment, Terraform will show outputs such as the EC2 instance public IP or DNS.
```
terraform output
```
📌 AWS Provider

The Terraform AWS provider tells Terraform where and how to provision AWS resources.

📌 EC2 Instance

A typical EC2 resource in Terraform might look like this:
```
resource "aws_instance" "web_server" {
  ami           = var.ami
  instance_type = var.instance_type
  tags = {
    Name = "Terraform-EC2"
  }
}

```
This snippet deploys an EC2 VM using your chosen AMI and instance type.


📌 Outputs
- Output Name	Description
- public_ip	  Public IP of the deployed EC2 instance
- public_dns	Public DNS of the EC2 instance

Outputs help you quickly connect to the deployed server after creation.
## 📬 About the Author

Abhi Pal
- Cloud & DevOps enthusiast building automated infrastructure using Terraform.
- GitHub: https://github.com/abhi2330
