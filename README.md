# AWS EBS Snapshot Cleanup Lambda

[![Python](https://img.shields.io/badge/Python-3.9+-blue)](https://python.org) [![AWS Lambda](https://img.shields.io/badge/AWS-Lambda-orange)](https://aws.amazon.com/lambda/)

Serverless AWS Lambda function using Boto3 to automatically delete orphaned EBS snapshots—those not attached to running EC2 instances or from deleted volumes—for cost optimization.

## Features
- Scans all self-owned EBS snapshots.
- Deletes orphans (no volume, unattached volume, or stopped instance attachments).
- Handles errors (e.g., missing volumes).
- Logs actions to CloudWatch; returns deletion summary.

## Prerequisites
- AWS account with EC2/Lambda permissions.
- IAM role for Lambda: `ec2:DescribeSnapshots`, `ec2:DescribeInstances`, `ec2:DescribeVolumes`, `ec2:DeleteSnapshot`.
- Python 3.9+ runtime.

