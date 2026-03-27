---
name: "AWS CLI"
description: "Manage AWS services — EC2, S3, Lambda, IAM, and more. Use when an agent needs to provision cloud infrastructure, manage S3 buckets, invoke Lambda functions, or configure AWS resources."
---

# AWS CLI

Manage all AWS services from the terminal.

- **Repo**: https://github.com/aws/aws-cli
- **Docs**: https://docs.aws.amazon.com/cli/

## Installation

```bash
brew install awscli
aws configure
```

## Key Commands

```bash
aws s3 ls
aws s3 cp file.txt s3://bucket/file.txt
aws ec2 describe-instances --output json
aws lambda invoke --function-name myFunc output.json
aws iam list-users --output json
aws sts get-caller-identity
```

## Agent-Friendly Features

- `--output json` for structured output (also `text`, `table`)
- Profile-based auth (`--profile`)
- Environment variable auth (`AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`)
- `--query` for JMESPath filtering
- `--no-cli-pager` to disable interactive paging
