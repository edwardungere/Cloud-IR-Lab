# EC2 Setup

## Create Splunk instance

Name: splunk-instance

AMI (Amazon Machine Image): **Red Hat Enterprise Linux 10**

Instance type: **t3.medium**

### Create key pair

Key pair: **Create new keypair**

Name: **splunk-key** 

Type: **RSA** 

Format: **.pem** (for OpenSSH)

### Network settings

Network: **MyVPC**

Subnet: **Public-1A** 

Auto-assign public IP: **Enable**

Select existing security group: **splunk-group**

### Advanced settings

IAM instance profile: **splunk-role**

## Create Victim EC2

Name: splunk-instance

AMI (Amazon Machine Image): **Red Hat Enterprise Linux 10**

Instance type: **t3.medium**

### Create key pair

Key pair: **Create new keypair**

Name: **splunk-key** 

Type: **RSA** 

Format: **.pem** (for OpenSSH)

### Network settings

Network: **MyVPC**

Subnet: **Public-1A** 

Auto-assign public IP: **Enable**

Select existing security group: **splunk-group**

### Advanced settings

IAM instance profile: **splunk-role**

