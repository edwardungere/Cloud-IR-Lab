# System Threat Modeling

## 1. Security Objectives, Component Breakdown, and Scope

### 1.1 System Description

#### 1.1.1 System Information
- Automated Ingestion Response Lab (AIR) contains an internal threat actor, another internal workload that is located in the same private subnet, and a third internal instance with Splunk Enterprise.
- The internal attacker machine is monitored and its information is collected by numerous services across AWS.
- AIR is a system that generates logs these across the control and data plane and correlates for a full-system view and optimized log collection.
- Any attacks are responded to with automated response techniques that follow well-known standards and frameworks.

#### 1.1.2 Technology 
- AIR uses Splunk Enterprise as an internal SIEM the private instances send logs to.
- The victim instance is used for internal workloads that represent an enterprise system, while the threat instance is used for launching attacks against the cloud enviroment which is not directly accessible by the internet. 
- Splunk Universal Forwarder (SUF) is installed on the both private instances and forwards system logs to Splunk.
- VPC flow logs capture network traffic and metadata, these are sent to CloudWatch logs. CloudTrail logs api and IAM activity and stores them in S3 buckets.
- The Splunk SIEM assumes an IAM role and periodically pulls these logs and sends generated alerts to Amazon API gateway, which then invokes Lambda functions to execute automated mitigation.

### 1.2 Data Flow Diagram
![dfd](dfd.png)

## 2. Security Objectives 

### 2.1 STRIDE
#### Spoofing:
- SSH login via stolen credentials
- Assuming IAM role with stolen credentials
- Using instance metadata to retrieve IAM role credentials
#### Tampering:
- System file deletion or modification on instances
- Changing role security group or NACL rules
- Altering configuration of CloudTrail
- Modifying IAM policies
- Modifyng log objects in S3
#### Repudiation:
- Deleting logs 
- Disabling logging
- Clearing shell history
- Deleting log objects in S3
#### Information Disclosure:
- Accessing S3 buckets without authorization
- Reading EC2 instance metadata credentials
- Exfiltrating logs and data
#### Denial of Service:
- Exhuasting system resources via traffic flooding
- Intentionally misconfigured security group causing lockout
- Deleting or stopping EC2 instances
#### Elevation of Privilege:
- Creating IAM users with admin priveleges
- Exploiting overly permissive IAM policies
- Adding unauthorized users to sudoers group
- Adding IAM policy to compromised role
  
### 2.2 Out of Scope
- Physical access
- Zero-day kernel exploits
- Multi-account compromise

## 3. Components
| Component Name | Description | Function |
|----------|----------|----------|
| Splunk Enterprise    | System Information Event Manager   | Pulls, indexes, correlates, and generates alers from logs  | 
| Amazon S3    | Storage service that stores data and retrieves data within buckets  | CloudTrail storage destination   |
| CloudWatch | Data 3   | Data 4   |   
| CloudTrail | SaaS component that tracks and logs control plane data | Data 4   |   
| Lambda     | Severless compute service that runs code in managed enviroment| Short, quick lived functions that mediate attacks |   
| Splunk Universal Forwarder    | Application installed on machines that sends operating system logs to SIEM | Sends auth.log/syslog files to Splunk |   
| Row 2    | Data 3   | Data 4   |   

Threat Actor
- Compromised internal machine


Assumptions
- Single AWS account
- No internal malicious users
- Limited lateral movement


#### Reducing false positives
- Correlating multiple signals
- Detecting sequences (e.g., API change → SSH → privilege escalation)
- Making detections defendable
