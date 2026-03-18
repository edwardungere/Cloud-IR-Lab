# MITRE ATT&CK-Mapped Tactics

| Tactic | Description | 
| ----------- | ----------- | 
| Reconnaissance | Scanning cloud instances, finding open ports, banner grabbing |
| Initial Access | Exploiting exposed SSH/FTP services |
| Execution | Running commands via SSH sessions |
| Persistence | Adding SSH keys, creating accounts |
| Privilege Escalation | Abusing misconfigurations/least privelege to gain root |
| Defense Evasion | Using legitimate tools to avoid detection |
| Credential Access | Stealing stored credentials, keys |
| Lateral Movement | SSH from one instance to another |
| Collection | Gathering files/data of interest |
| Exfiltration | Transferring data out via FTP, SCP, etc. |

Map each detection to an ATT&CK technique:
	•	SSH brute-force - T1110
	•	IAM privilege escalation - T1098
	•	CloudTrail modification - T1562.008
	•	Port scanning - T1046

   

