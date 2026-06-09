Terraform AWS VPC Project
Project Overview

This project demonstrates how to create AWS networking infrastructure using Terraform Infrastructure as Code (IaC).

The goal of the project is to automate VPC creation instead of manually creating resources through the AWS Console.

Technologies Used
Terraform
AWS VPC
AWS Subnets
Git
GitHub
Amazon EC2 (for running Terraform)
Project Architecture
VPC (10.0.0.0/16)
│
├── Public Subnet 1 (10.0.1.0/24)
├── Public Subnet 2 (10.0.2.0/24)
│
├── Private Subnet 1 (10.0.3.0/24)
├── Private Subnet 2 (10.0.4.0/24)
│
└── Internet Gateway (Future Enhancement)
Project Objectives
Learn Terraform basics
Understand AWS networking concepts
Create AWS resources using Infrastructure as Code
Manage infrastructure through version control
Prerequisites

Before starting the project:

AWS Account
IAM User with programmatic access
AWS CLI installed
Terraform installed
Git installed
Step 1: Configure AWS Credentials

Configured AWS credentials using:

aws configure

Provided:

AWS Access Key
AWS Secret Key
Region
Output Format

Verified access:

aws sts get-caller-identity
Step 2: Create Project Structure

Created project directory:

mkdir terraform-vpc
cd terraform-vpc

Created Terraform files:

providers.tf
variables.tf
terraform.tfvars
vpc.tf
Step 3: Configure AWS Provider

Created provider configuration to allow Terraform to communicate with AWS.

File:

providers.tf

Purpose:

Connect Terraform to AWS
Specify AWS region
Step 4: Create Variables

Created variables for:

AWS Region
VPC CIDR Block

Benefits:

Reusability
Flexibility
Better code management
Step 5: Create Terraform VPC Resource

Created VPC resource using:

resource "aws_vpc" "main"

Configured:

CIDR Block
Tags

Purpose:

Create isolated AWS network environment
Step 6: Initialize Terraform

Executed:

terraform init

Purpose:

Download AWS provider plugin
Initialize Terraform working directory
Step 7: Validate Configuration

Executed:

terraform validate

Purpose:

Verify Terraform syntax
Detect configuration errors
Step 8: Generate Execution Plan

Executed:

terraform plan

Purpose:

Preview infrastructure changes
Verify resources before deployment
Step 9: Deploy Infrastructure

Executed:

terraform apply

Terraform created:

1 VPC resource

Deployment completed successfully.

Challenges Faced
AWS Credential Error

Error:

No valid credential sources found

Resolution:

Configured AWS credentials using:

aws configure

Verified credentials:

aws sts get-caller-identity
Terraform Concepts Learned
Providers
Resources
Variables
Terraform State
Terraform Plan
Terraform Apply
Outcome

Successfully provisioned AWS VPC infrastructure using Terraform and managed the project using Git and GitHub.
