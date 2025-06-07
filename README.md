# Cloud Security Labs & Mini Project

**GitHub:** [github.com/dkamalon/cloud-security-labs](https://github.com/dkamalon/cloud-security-labs)

---

## Table of Contents

1. [Overview](#overview)  
2. [Labs Summary](#labs-summary)  
   - [AWS](#aws)  
   - [Azure](#azure)  
   - [GCP](#gcp)  
3. [Mini Project: Secure AWS Web Application](#mini-project-secure-aws-web-application)  
4. [Example IAM Role JSON (least privilege)](#example-iam-role-json-least-privilege)  
5. [Commit Organization & Best Practices](#commit-organization--best-practices)  
   - [Organizing Commits](#organizing-commits)  
   - [Writing Commit Messages](#writing-commit-messages)  
   - [Sample Commit Messages](#sample-commit-messages)  
   - [Additional Tips](#additional-tips)  

---

## Overview

This repository contains 35+ hours of hands-on cloud security labs across **AWS**, **Azure**, and **GCP**, demonstrating practical experience with essential cloud security services. It also includes a mini project showcasing a secure AWS web application deployment.

---

## Labs Summary

### AWS
- Identity and Access Management (IAM) policies and role management  
- S3 bucket security best practices and encryption with KMS  
- CloudTrail setup for auditing  
- GuardDuty for threat detection  
- Web Application Firewall (WAF) configuration  

#### Sample AWS commands/config snippets

```bash
# Create IAM policy with least privilege
aws iam create-policy --policy-name ReadOnlyS3Access --policy-document file://readonly-s3-policy.json

# Enable CloudTrail logging
aws cloudtrail create-trail --name MyTrail --s3-bucket-name my-cloudtrail-logs

json

// Sample S3 bucket policy to restrict public access
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "DenyPublicRead",
      "Effect": "Deny",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-secure-bucket/*",
      "Condition": {
        "Bool": {
          "aws:SecureTransport": "false"
        }
      }
    }
  ]
}
Azure
Identity and Conditional Access policies

Network Security Groups (NSGs) configuration

Defender for Cloud monitoring

Azure Sentinel for security alerting and automation

Sample Azure CLI commands

bash

# Create NSG rule to allow only SSH from specific IP
az network nsg rule create --resource-group MyResourceGroup --nsg-name MyNSG --name AllowSSH --protocol Tcp --direction Inbound --priority 1000 --source-address-prefixes 203.0.113.0/24 --destination-port-ranges 22 --access Allow

# Enable Azure Defender for servers
az security pricing create --name VirtualMachines --tier 'Standard'
PowerShell example for Conditional Access policy

powershell

# Create a conditional access policy requiring MFA for admins
New-AzureADMSConditionalAccessPolicy -DisplayName "Require MFA for admins" -Conditions @{Users=@{IncludeUsers=@("All")}} -GrantControls @{BuiltInControls=@("Mfa")}
GCP
IAM permissions management

Security Command Center for risk assessment

Sample GCP commands

bash

# Assign role to user with least privilege
gcloud projects add-iam-policy-binding my-project --member=user:example@example.com --role=roles/storage.objectViewer

# Enable Security Command Center
gcloud services enable securitycenter.googleapis.com

# List findings in Security Command Center
gcloud scc findings list --organization=123456789
Mini Project: Secure AWS Web Application
Developed a secure web application using EC2 instances and S3 storage with strict IAM roles.

Enabled comprehensive logging and monitoring with CloudTrail and GuardDuty.

Configured AWS WAF to protect against common web threats.

Simulated common misconfigurations such as publicly accessible S3 buckets and overly permissive IAM roles.

Documented findings and remediation steps thoroughly.

All project files and documentation are available in this repository for review.

Example IAM Role JSON (least privilege)

json

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:ListBucket",
        "s3:GetObject"
      ],
      "Resource": [
        "arn:aws:s3:::my-secure-bucket",
        "arn:aws:s3:::my-secure-bucket/*"
      ]
    }
  ]
}
Commit Organization & Best Practices
Organizing Commits
Work in small, logical steps (e.g., IAM policy creation, CloudTrail setup, NSG rule configuration).

Commit after completing each task to keep history granular and review-friendly.

Keep commits focused and avoid mixing unrelated changes.

Writing Commit Messages
Use this structure to ensure clarity:

php-template

<type>: <short summary>

<optional detailed description>
Common types:

feat: new feature

fix: bug fix

docs: documentation changes

chore: maintenance tasks

refactor: code restructuring without behavior change

Keep summary under 50 characters and use present tense. Add details if necessary to explain the "why" or "how."

Sample Commit Messages
feat: Add IAM policies for AWS S3 access control

feat: Configure CloudTrail for AWS audit logging

docs: Update README with CloudTrail setup instructions

feat: Add Azure NSG rule script to restrict SSH access

feat: Implement Azure Conditional Access policy requiring MFA

feat: Add GCP IAM binding for least privilege access

feat: Build secure AWS web app with strict IAM roles and WAF

fix: Correct JSON syntax in S3 bucket policy

Additional Tips
Use git add -p to stage related changes per commit.

Write commit messages descriptive and helpful for reviewers.

Push commits regularly to keep the repository updated.

Thank you for reviewing my cloud security projects and contributions!



