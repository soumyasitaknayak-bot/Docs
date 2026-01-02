## IAM Policy Inheritance

- **Group Policies** → inherited by users
- **Inline Policies** → attached directly to users
  (works even if user is not in any group)

---

## IAM Policy Structure (Reference)

```json
{
  "Version": "2012-10-17",
  "Id": "optional-policy-id",
  "Statement": [
    {
      "Sid": "optional-statement-id",
      "Effect": "Allow",
      "Principal": { "AWS": "arn:aws:iam::123456789012:user/username" },
      "Action": ["s3:GetObject", "s3:PutObject"],
      "Resource": ["arn:aws:s3:::bucket-name/*"],
      "Condition": {
        "StringEquals": {
          "aws:RequestedRegion": "us-east-1"
        }
      }
    }
  ]
}
```

### Key Components

- **Version** _(required)_ – `2012-10-17`
- **Statement** _(required)_ – permission rules
- **Effect** – Allow / Deny
- **Action** – AWS service actions
- **Resource** – ARNs
- **Condition** – optional constraints

---

## IAM Password Policy

- Minimum password length
- Complexity rules
- Password expiration
- Prevent password reuse

---

## User Access to AWS

1. **AWS Management Console**
2. **AWS CLI**
3. **AWS API / SDK**

### AWS CLI

- Command-line interaction with AWS services

### AWS SDK

- APIs for programming languages (Python, Java, etc.)

---

## IAM Roles

- Used by **AWS services**, not humans
- Example:

  - EC2 instance accessing S3

- No long-term credentials
- Temporary permissions

---
