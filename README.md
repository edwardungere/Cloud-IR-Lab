# Automated Ingestion & Response (AIR) Lab 

## 1. Introduction
The Atuomated Ingestion Response lab demonstrates a full cloud security monitoring and automated incident response pipline using **AWS** and **Splunk**. 

Instead of relying on a single telemetry source to respond to threats, the lab shows how logs across the control and data plane can be correlated to provide expanded visibility into adversary tactics and techniques and enable effective, automated mitigation.

## 2. Background
This scenario models an internal machine launching MITRE-mapped attacks against an internal cloud workload operating within the same AWS account. The attacker will will move laterally from the its own instace to the private instance. 

Activity from the attacker will generate telemetry across AWS API logs, VPC network flow metadata, and host-based Linux logs. These sources are ingested into a Splunk instance, where they are normalized, correlated, and analyzed to detect malicious behavior and trigger automated response actions via Lambda Functions.

## 3. System Architecture

### 3.1 Overview

<img src="aws-splunk.png" width="300" height="300" />


	3.	System Architecture
	•	3.1 Overview
	•	3.2 Network Design Decisions
	•	3.3 IAM Model
	•	3.4 Logging Flow
	4.	Threat Model
	5.	Mitigation Mapping
	6.	Evaluation
	7.	Discussion

