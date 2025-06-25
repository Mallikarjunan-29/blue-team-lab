# ⚙️ AWS CLI Lab – Verifying Blue-Lab-User Access

## 🎯 Objective

Use the AWS Command Line Interface (CLI) to authenticate with `blue-lab-user`, validate permissions, and prepare for detection-based workflows.

---
## 1️⃣ Pre-requisites

AWS Free Tier account
IAM user (blue-lab-user) with ReadOnlyAccess
Access keys generated and saved securely
AWS CLI installed

## 2️⃣ Configure AWS CLI

Run the following command:

```bash
aws configure
```
Enter the details from the access key created earlier:
AWS Access Key ID
AWS Secret Access Key
Region: us-east-2 (or your preferred region)
Output format: json
![Config Inputs](../images/aws-cli-configure.png)
*Screenshot: Inputs presented to the aws config command*

## 3️⃣ Validate Access

Run the following command

```bash
aws sts get-caller-identity
```
Expected Output:
ARN of the IAM user
Account ID
User ID

![Caller Identity](../images/aws-cli-caller-identity.png)
*Screenshot: Validated access related information*

## ✅ Outcome

The `blue-lab-user` was successfully created and tested for CLI access.

- Access is granted via the AWS-managed **ReadOnlyAccess** policy, which provides **view-only permissions across all AWS services**, including IAM, GuardDuty, S3, VPC, and CloudTrail.
- This ensures a **non-destructive learning environment**, perfect for hands-on cloud security labs without any risk of altering live resources.
- The access model aligns with AWS security best practices and supports safe experimentation in real-world enterprise scenarios.

## 🔒 Notes
CLI access uses programmatic credentials, not your root account — best practice ✅
Keep .aws/credentials file secured (stored in your home directory)
No destructive actions can be taken due to ReadOnly permissions



