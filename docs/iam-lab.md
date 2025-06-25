# 🔐 IAM Lab – ReadOnly User: `blue-lab-user`

## ✅ Objective
Create a secure, scoped-down IAM user to explore AWS services in read-only mode. This user will be used to access GuardDuty, CloudTrail, VPC logs, and IAM data via AWS CLI.

---

## 👤 User Details
- **Username**: `blue-lab-user`
- **Access Type**: Programmatic access (Access Key & Secret Key)
- **Console Access**: ❌ Disabled
- **User Creation Date**: 25-June-2025
- [User Details Screenshot](../images/iam-user-creation.png)

---

## 🛡️ Permissions
- **Policy Attached**: `ReadOnlyAccess` (AWS managed - job function)
- **Scope**: Grants read-only access to IAM resources like users, roles, groups, and policies.
- **Why ReadOnly?**
  - No risk of resource modification
  - Ideal for audit and investigation
  - Perfect for blue team visibility without write privileges
  - [Permissions Screenshot](../images/policy-attached.png)

---

## ⚙️ AWS CLI Setup
```bash
aws configure
