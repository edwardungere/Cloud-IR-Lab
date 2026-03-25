# Adversary Profile

## Motivation

Financially motivated external actor targeting confidential business data.

Adversary's goals are:

1. Data exfiltration -  Access and steal confidential data (credentials, records, config files) from the private subnet.
2. Privilege escalation - Obtain admin privileges on EC2 instances and escalate via AWS IAM to broaden access to cloud resources.
   
## Starting position

External. Originating from the internet. Initial access gained by exploiting a public-facing EC2
instance, then pivoting into the private subnet containing a database.

## Tools available

Living-off-the-land only. SSH, FTP, AWS CLI, cURL, cron, find/grep,
and other pre-installed OS/cloud-native utilities.

