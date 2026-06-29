# Digital Forensics & Incident Response (DFIR) Lab

## Overview

This project documents a simulated Digital Forensics and Incident Response (DFIR) investigation for a suspected phishing attack within a fictional organization, **AP Technology Group**.

The objective of this investigation was to identify suspicious activity, collect evidence, analyze system and network artifacts, map attacker behavior to the MITRE ATT&CK framework, and document the complete incident response lifecycle from detection through recovery.

This repository demonstrates practical security operations skills using industry-standard tools including Splunk Enterprise, Wireshark, PowerShell, and MITRE ATT&CK.

---

## Scenario

An employee reported that their Windows workstation became noticeably slow after opening an email attachment that appeared to come from a trusted vendor.

Shortly after the report:

- Suspicious PowerShell execution was detected.
- Multiple failed authentication attempts were observed.
- Splunk generated security alerts.
- Unusual outbound network traffic was identified.
- Security Operations initiated an incident response investigation.

The goal was to determine the scope of the incident, identify indicators of compromise (IOCs), contain the affected system, and document the findings.

---

## Objectives

- Simulate a real-world security incident
- Investigate endpoint activity
- Analyze SIEM logs using Splunk
- Review network traffic with Wireshark
- Identify Indicators of Compromise (IOCs)
- Map attacker techniques using MITRE ATT&CK
- Document the complete incident response process
- Produce a professional incident report

---

## Tools & Technologies

- Splunk Enterprise
- Wireshark
- Windows PowerShell
- Windows Event Logs
- MITRE ATT&CK Framework
- GitHub

---

## Investigation Workflow

1. Receive Security Alert
2. Review Initial Evidence
3. Analyze Windows Event Logs
4. Investigate Splunk Alerts
5. Capture & Analyze Network Traffic
6. Identify Indicators of Compromise
7. Map Activity to MITRE ATT&CK
8. Contain the Incident
9. Recover the System
10. Document Findings

---

## MITRE ATT&CK Techniques

| Technique | Description |
|------------|-------------|
| T1566 | Phishing |
| T1059.001 | PowerShell |
| T1078 | Valid Accounts |
| T1071 | Application Layer Protocol |
| T1105 | Ingress Tool Transfer |

---

## Indicators of Compromise (IOCs)

Example artifacts identified during the investigation include:

- Suspicious PowerShell execution
- Multiple failed authentication attempts
- Unexpected outbound network connections
- Unrecognized IP addresses
- Potential phishing attachment

---

## Screenshots

### Step 1
Initial Security Alert

![Step 1](screenshots/step-1.png)

---

### Step 2
Splunk Investigation

![Step 2](screenshots/step-2.png)

---

### Step 3
Wireshark Network Analysis

![Step 3](screenshots/step-3.png)

---

### Step 4
MITRE ATT&CK Mapping

![Step 4](screenshots/step-4.png)

---

### Step 5
Incident Summary

![Step 5](screenshots/step-5.png)

---

## Skills Demonstrated

- Digital Forensics
- Incident Response
- Threat Detection
- SIEM Log Analysis
- Network Traffic Analysis
- MITRE ATT&CK Mapping
- Security Documentation
- Root Cause Analysis
- Technical Reporting

---

## Lessons Learned

This project reinforced the importance of correlating endpoint, log, and network evidence to accurately identify malicious activity and reduce incident response time.

The investigation also emphasized the value of structured documentation, repeatable investigation processes, and standardized threat frameworks such as MITRE ATT&CK when responding to security incidents.

---

## Future Improvements

Future enhancements may include:

- Sysmon log analysis
- Windows Event ID correlation
- YARA rule development
- Sigma detection rules
- Memory forensics
- Disk image analysis
- Malware reverse engineering
- Automated IOC detection

---
