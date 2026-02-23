## Automated Ingestion & Response (IR) Lab 

The Atuomated Ingestion Response lab demonstrates a full cloud security monitoring and automated incident response pipline using **AWS** and **Splunk**. 

Instead of relying on a single telemetry source to respond to threats, the lab shows how logs across the control and data plane can be correlated to provide visibility into adversary tactics and techniques and enable effective, automated mitigation.

The scenario models a previously compromised a cloud workload operating within the same AWS account as the victim instance; a common real-world initial access scenario. The attacker will conduct MITRE-aligned techniques against a Linu EC2 instance. 

Activity will generate telemetry across AWS API logs, VPC network flow metadata, and host-based Linux logs. The sources are ingested into Splunk SIEM, where they are normalized, correlated, and analyzed to detect malicious behavior and trigger automated response actions.

<img src="aws-splunk.png" width="300" height="300" />

### Core components 
- Amazon Web Services CLI
- Amazon VPC
- VPC Flow Logs 
-	Amazon EC2 
-	AWS CloudTrail
-	S3
-	Amazon CloudWatch
-	Splunk 
-	AWS Lambda
-	Ubuntu
