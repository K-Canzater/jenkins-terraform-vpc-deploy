# jenkins-terraform-vpc-deploy
Infrastructure automation project that deploys an AWS VPC using Terraform and Jenkins CI/CD pipeline.
# jenkins-terraform-vpc-deploy 🚀

Automated deployment of AWS VPC infrastructure using **Terraform** and **Jenkins CI/CD pipeline**.

## 📌 Overview

This project sets up a complete AWS Virtual Private Cloud (VPC) environment using **Infrastructure as Code (IaC)** principles. A **Jenkins pipeline** is used to automate Terraform workflows, making the provisioning process repeatable, consistent, and hands-free.

## 🔧 Tools & Technologies

- **Terraform** – Infrastructure as Code
- **Jenkins** – CI/CD pipeline automation
- **AWS** – Cloud infrastructure (VPC, Subnets, Route Tables, etc.)
- **S3 + DynamoDB** – Remote backend for Terraform state management
- **GitHub** – Source control and integration with Jenkins

## 🏗️ Infrastructure Components

- VPC
- Public and Private Subnets
- Route Tables and Associations
- Internet Gateway
- Security Groups

## 🔁 CI/CD Flow

1. **Code pushed to GitHub**
2. **Jenkins** pulls the repo and runs:
   - `terraform init`
   - `terraform plan`
   - `terraform apply`
3. Infrastructure is deployed to AWS automatically

## 🛡️ IAM & State Management

- **IAM Role/User** created for Jenkins with least privilege permissions
- **Remote Terraform State** stored securely in S3
- **State Locking** handled via DynamoDB to prevent conflicts

## 📁 Project Structure

.
├── modules/
│ └── vpc/ # Reusable VPC module (main.tf, variables.tf, outputs.tf)
├── environments/
│ └── dev/ # Dev environment using the VPC module
│ ├── main.tf
│ ├── variables.tf
│ └── backend.tf
├── Jenkinsfile # Jenkins pipeline definition
├── README.md

## 🚀 Getting Started

To run this project:

1. Set up AWS credentials in Jenkins securely
2. Configure your remote backend (S3 + DynamoDB)
3. Push changes to GitHub
4. Jenkins will detect changes and deploy infra using Terraform

## ✅ Future Enhancements

- Add EC2, RDS, or EKS modules
- Add Slack notifications to Jenkins
- Add dev/staging/prod environment separation

---
