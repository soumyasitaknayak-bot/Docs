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

IAM : Users and Groups
IAM : Identity and Access Management, Global service
root -created by dafault
users and can be groupeed,
groups -can only contain users not groups
users - part of multiple groups
IAM permission:can be assigned json documents called policies
least orivilege permissiion




IAM (Identity and Access Management)

policy inheritance:
Group level : we have added policies here 
Inline : attached to user , doesn't matter user is in group or not

policy structure :
IAM policy structure

{
    "Version": "2012-10-17",
    "Id": "optional-policy-id",
    "Statement": [
        {
            "Sid": "optional-statement-id",
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::123456789012:user/username"
            },
            "Action": [
                "s3:GetObject",
                "s3:PutObject"
            ],
            "Resource": [
                "arn:aws:s3:::bucket-name/*"
            ],
            "Condition": {
                "StringEquals": {
                    "aws:RequestedRegion": "us-east-1"
                }
            }
        }
    ]
}


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
