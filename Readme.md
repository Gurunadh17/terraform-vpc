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

terraform statefile
{
  "version": 4,
  "terraform_version": "1.15.5",
  "serial": 1,
  "lineage": "d4933bd6-a9fc-aabd-be26-f907d91cf293",
  "outputs": {},
  "resources": [
    {
      "mode": "managed",
      "type": "aws_vpc",
      "name": "main",
      "provider": "provider[\"registry.terraform.io/hashicorp/aws\"]",
      "instances": [
        {
          "schema_version": 1,
          "attributes": {
            "arn": "arn:aws:ec2:us-east-1:547361936227:vpc/vpc-012f7bb0590f1e337",
            "assign_generated_ipv6_cidr_block": false,
            "cidr_block": "10.0.0.0/16",
            "default_network_acl_id": "acl-0b6147e5943aeba0c",
            "default_route_table_id": "rtb-01bbf7ca7a9815f46",
            "default_security_group_id": "sg-08b0c220f1fe84c99",
            "dhcp_options_id": "dopt-0ed0711a34ed550b0",
            "enable_dns_hostnames": false,
            "enable_dns_support": true,
            "enable_network_address_usage_metrics": false,
            "id": "vpc-012f7bb0590f1e337",
            "instance_tenancy": "default",
            "ipv4_ipam_pool_id": null,
            "ipv4_netmask_length": null,
            "ipv6_association_id": "",
            "ipv6_cidr_block": "",
            "ipv6_cidr_block_network_border_group": "",
            "ipv6_ipam_pool_id": "",
            "ipv6_netmask_length": 0,
            "main_route_table_id": "rtb-01bbf7ca7a9815f46",
            "owner_id": "547361936227",
            "tags": {
              "Name": "terraform-vpc"
            },
            "tags_all": {
              "Name": "terraform-vpc"
            }
          },
          "sensitive_attributes": [],
          "identity_schema_version": 0,
          "private": "eyJzY2hlbWFfdmVyc2lvbiI6IjEifQ=="
        }
      ]
    }
  ],
  "check_results": null
}
Successfully provisioned AWS VPC infrastructure using Terraform and managed the project using Git and GitHub.
