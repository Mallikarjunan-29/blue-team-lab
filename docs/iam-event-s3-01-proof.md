#  CloudTrail Detection of IAM Privilege Escalation via S3 Logs

## Scenario

As part of our cloud blue team lab, we simulated a suspicious activity where the scoped user `blue-team-lab` attempted to escalate privileges by attaching a new IAM policy using the AWS CLI.

---

## Objective

Detect and verify unauthorized IAM API activity that **was not visible in CloudTrail Console** but **was logged in the S3 bucket** configured for CloudTrail.

---

##  Action Simulated

```bash
aws iam attach-user-policy \
    --user-name blue-team-lab \
    --policy-arn arn:aws:iam::aws:policy/AdministratorAccess
```
![Simulated attack](../images/aws-cli-attack-simulation-01.png)
*Screenshot: Command used for simulation*

![View Detailed Report](../reports/s3-simulation01-finding-26-06-2025-01.json)
*Log captured from S3 bucket — not seen in CloudTrail console!*

## Why This Matters

1.Helps detect stealthy IAM activities that bypass real-time console visibility

2.Shows the importance of S3 log monitoring in addition to Event History

3.Forms the baseline for alerting in Splunk/Wazuh-based detections
