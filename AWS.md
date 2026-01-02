1. what is cloud computing?
   1. on demand delivery
   2. pay as you go
2. Deployment model :
   1. private
   2. public
   3. hybrid
3. Five character:
   1. on demand self service
   2. broad network access
   3. multiple-tenency and resource pooling
   4. rapid elasticity and scalability
   5. measured service
4. Six Advantages
5. Problems solved by cloud
6. Types of cloud computing
   1. Infrastructure as a service (IAAS)
   2. Platform as a service (PAAS)
   3. Software as a service (SAAS)
7. AWS pricing [3 pricing fundamentals]
   1. compute
   2. storage
   3. data transfer out of the cloud
8. History
9. aws availibity zone
   1. min 3 max 6
   2. isolated from disatster
   3. high bandwidth and less latency
   4. combined zones create region

services amazon - features

respossibility model:
customer - security in the cloud
aws- security for the cloud

---

## IAM (Identity and Access Management)

IAM : Users and Groups
IAM : Identity and Access Management, Global service
root -created by dafault
users and can be groupeed,
groups -can only contain users not groups
users - part of multiple groups
IAM permission:can be assigned json documents called policies
least orivilege permissiion

policy inheritance:
Group level : we have added policies here
Inline : attached to user , doesn't matter user is in group or not

### policy structure :

IAM policy structure

```yaml
{
  "Version": "2012-10-17",
  "Id": "optional-policy-id",
  "Statement":
    [
      {
        "Sid": "optional-statement-id",
        "Effect": "Allow",
        "Principal": { "AWS": "arn:aws:iam::123456789012:user/username" },
        "Action": ["s3:GetObject", "s3:PutObject"],
        "Resource": ["arn:aws:s3:::bucket-name/*"],
        "Condition": { "StringEquals": { "aws:RequestedRegion": "us-east-1" } },
      },
    ],
}
```

Key Components:
Version (required): Use "2012-10-17" (current policy language version)
Id (optional): Unique identifier for the policy
Statement (required): Array of policy statements
Sid (optional): Statement identifier
Effect (required): "Allow" or "Deny"
Principal (required for resource-based policies): Who the policy applies to
Action (required): List of actions (e.g., "s3:GetObject")
Resource (required): ARNs the policy applies to
Condition (optional): Conditions for when the policy applies
Note: Resource belongs inside each Statement object, not at the root level.

IAM Password Policy

Users access AWS.

1.  AWS Management Console
2.  AWS CLI
3.  AWS API/SDK

aws cli : interact with aws services using commands in your command-line shell
aws sdk : software development kits (sdks) provide apis to interact with aws services  
using popular programming languages

## IAM Roles

some AWS services need to interact with other AWS services on your behalf.
for example, an EC2 instance might need to read objects from an S3 bucket.
: to do so , we will assign a role to the EC2 instance that grants it permission to access the S3 bucket.

## IAM Security Tools

1. IAM Access Advisor
   - shows the service permissions granted to a user and when those services were last accessed.
2. IAM Credential Report
   - provides a snapshot of all your IAM users and the status of their various credentials.

## IAM Best Practices

1.  Enable MFA for privileged users
2.  Create individual IAM users
3.  Use groups to assign permissions
4.  Apply the principle of least privilege
5.  Use roles for applications that run on Amazon EC2 instances
6.  Rotate credentials regularly
7.  Use IAM Access Analyzer to monitor policies
8.  Delete unnecessary credentials and users
9.  Use AWS Organizations to manage multiple AWS accounts
10. Regularly review IAM policies and permissions

## Summary

users
groups
roles : for ec2 instance on aws services
policies : json document
security : mfa + password policy
aws cli
access keys
audit : iam access advisor and credential report
