# Automated Ingestion & Response (AIR) Lab 

## 1. Introduction
The Automated Ingestion Response lab demonstrates a full cloud security monitoring and automated incident response pipline using **AWS** and **Splunk**. 

Instead of relying on a single telemetry source to respond to threats, this lab demonstrates how logs across the control and data plane can be correlated to provide expanded visibility into internal adversary tactics and techniques to enable effective automated mitigation. 

## 2. Background
As organizations continue to offload production and operations to the cloud, cloud enviroments are increasingly becoming crucial components of enterprise infrastructure. 

In traditional networks, the firewall acted as the primary enforcement point and defined the boundary between "trusted" and "untrusted" users. In cloud architecture, trust is better defined by credentials compared to network layout. Access to resources is goverened by credentials, and an external attacker with valid keys or permissions can perform actions that appear indistinguishable from authorized activity. 

Comprehensive logging and monitoring across both the control and data plane, paired with sevrless compute functions can provide active defense for these critical enviroments.

# 3. Scenario
This scenario models an internal machine launching MITRE-mapped attacks against an internal cloud workload operating within the same AWS account. The attacker will will move laterally from the its own instace to the private instance. 

Activity from the attacker will generate telemetry across AWS API logs, VPC network flow metadata, and host-based Linux logs. These sources are ingested into a Splunk instance, where they are normalized, correlated, and analyzed to detect malicious behavior and trigger automated response actions via Lambda Functions.

## 4. System Architecture

### 4.1 Overview

AIR utilizes cloud services that lie on seperate layers of the shared responsibility model. On the IaaS level, EC2 instances are used to represent internal machines and workloads they support. On the SaaS level, AWS CloudWatch and CloudTrail are logging services that enable logging of metadata such as IP data and traffic flow within the VPC to configuration changes and API calls. This means, when paired together, they monitor data across the control and data plane. 

### 4.2 Network Design Decisions

The network is intentionally designed as an internal cloud enviroment with no direct internet connectivity. This models a segmented enterprise intranet architecture and reduces the total attack surface. By eliminating public ingress and eress traffic, the system isolates internal traffic and lateral movement scenarios and allows focused evaluation of detection and response capatabilities against internal threats. 

<img src="aws-splunk.png" width="300" height="300" />

### 5. Threat Model

The threat model can be found here: [threat model](https://github.com/edwardungere/AIR/architecture/threat-model.md)

	•	3.3 IAM Model
	•	3.4 Logging Flow
	4.	Threat Model
	5.	Mitigation Mapping
	6.	Evaluation
	7.	Discussion

