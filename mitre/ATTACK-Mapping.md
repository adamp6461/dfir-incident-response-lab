# MITRE ATT&CK Mapping

## Overview

This document maps the observed attacker behaviors from the simulated incident to the MITRE ATT&CK framework.

The objective is to identify adversary tactics and techniques that align with the activity observed during the investigation.

---

## MITRE ATT&CK Mapping

| ATT&CK Tactic | Technique ID | Technique | Evidence |
|--------------|--------------|-----------|----------|
| Initial Access | T1566 | Phishing | User opened a suspicious email attachment. |
| Execution | T1059.001 | PowerShell | Suspicious PowerShell activity observed shortly after the attachment was opened. |
| Credential Access | T1110 | Brute Force | Multiple failed authentication attempts identified during log review. |
| Command and Control | T1071 | Application Layer Protocol | Outbound HTTPS communication observed to an unfamiliar external IP address. |
| Command and Control | T1105 | Ingress Tool Transfer | PowerShell activity suggested possible download of an additional payload. |

---

## ATT&CK Matrix Summary

| Tactic | Status |
|---------|--------|
| Initial Access | Identified |
| Execution | Identified |
| Credential Access | Suspected |
| Command and Control | Identified |

---

## Investigation Notes

### Initial Access

The investigation determined that the incident most likely began when a user opened a phishing email attachment disguised as a legitimate vendor document.

---

### Execution

Immediately following the attachment execution, PowerShell activity was observed that was inconsistent with normal workstation behavior.

This activity was considered suspicious due to its timing and relationship to the reported phishing email.

---

### Credential Access

Following the PowerShell activity, several failed authentication attempts were identified.

Although no successful unauthorized login was confirmed, the activity warranted additional monitoring.

---

### Command and Control

Wireshark analysis identified outbound HTTPS traffic from the affected workstation to an unfamiliar external IP address.

While encrypted traffic is common, the timing and destination aligned with the suspected compromise.

---

## Defensive Recommendations

To improve future detection and response capabilities, the following controls are recommended:

- Implement enhanced PowerShell logging.
- Enable Sysmon for endpoint telemetry.
- Configure Splunk detections for suspicious PowerShell execution.
- Monitor repeated failed authentication attempts.
- Review outbound HTTPS traffic to unfamiliar destinations.
- Continue user phishing awareness training.

---

## References

- MITRE ATT&CK Framework
- Splunk Enterprise
- Wireshark
- Windows Event Logs
