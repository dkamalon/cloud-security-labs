# Cloud Security Labs & Mini Project

**GitHub:** [github.com/dkamalon/cloud-security-labs](https://github.com/dkamalon/cloud-security-labs)

---

## Overview

Completed 35+ hours of hands-on cloud security labs across AWS, Azure, and GCP. This repository showcases practical experience with core cloud security services and a secure AWS web application project.

---

## Labs Summary

### AWS
- Identity and Access Management (IAM) policies and role management  
- S3 bucket security best practices and encryption with KMS  
- CloudTrail setup for auditing  
- GuardDuty for threat detection  
- Web Application Firewall (WAF) configuration  

#### Sample AWS commands/config snippets:

```bash
# Create IAM policy with least privilege
aws iam create-policy --policy-name ReadOnlyS3Access --policy-document file://readonly-s3-policy.json

# Enable CloudTrail logging
aws cloudtrail create-trail --name MyTrail --s3-bucket-name my-cloudtrail-logs

# Sample S3 bucket policy to restrict public access
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
Sample Azure CLI commands:
# Create NSG rule to allow only SSH from specific IP
az network nsg rule create --resource-group MyResourceGroup --nsg-name MyNSG --name AllowSSH --protocol Tcp --direction Inbound --priority 1000 --source-address-prefixes 203.0.113.0/24 --destination-port-ranges 22 --access Allow

# Enable Azure Defender for servers
az security pricing create --name VirtualMachines --tier 'Standard'

# Create a conditional access policy (PowerShell)
New-AzureADMSConditionalAccessPolicy -DisplayName "Require MFA for admins" -Conditions @{Users=@{IncludeUsers=@("All")} } -GrantControls @{BuiltInControls=@("Mfa")}

GCP
IAM permissions management

Security Command Center for risk assessment

Sample GCP commands:
# Assign role to user with least privilege
gcloud projects add-iam-policy-binding my-project --member=user:example@example.com --role=roles/storage.objectViewer

# Enable Security Command Center
gcloud services enable securitycenter.googleapis.com

# List findings in Security Command Center
gcloud scc findings list --organization=123456789

Mini Project: Secure AWS Web Application
Built a secure web app using EC2 instances and S3 storage with strict IAM roles.

Enabled comprehensive logging and monitoring with CloudTrail and GuardDuty.

Configured AWS WAF to protect against common web threats.

Simulated common misconfigurations like publicly accessible S3 buckets and over-permissive IAM roles.

Documented findings and remediation steps.

All project files and documentation are published here for review.

Example IAM Role JSON (least privilege):
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

