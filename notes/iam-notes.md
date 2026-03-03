# Identity Access Management (IAM) Notes

Controls and guards access to resources within AWS

Resources are entities created within AWS:
- EC2 instance
- S3 bucket or object
- Lambda function
- DynamoDB table

Users/Roles attempt to perform Actions on resources

Actions can be made through the:
- AWS CLI
- AWS Console (GUI)
- SDKs (Python, Java, etc.)
  
All are calling the **same** backend APIs

Clicking "Create bucket" in the console = `aws mb s3://my-bucket` in the command line

## Policy
Policy is a JSON document that specificies what a user or role can or cannot do.

AWS implicitly denies everything
Policies are used for explicility allowing and implicitly denying access

## Access Key & Secret Access Key

Keys are used to interact with AWS, used with CLI and SDKs. GUI uses username and password

## Best practices

- Never use root account.
- **Explicit** Effect: 'Deny' takes precedence over Effect: 'Allow'
- Use Least Privelege model



