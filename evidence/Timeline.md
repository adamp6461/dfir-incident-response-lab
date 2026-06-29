# Incident Timeline

## Overview

This timeline documents the sequence of events during the investigation of a suspected phishing-related endpoint compromise at AP Technology Group.

The timeline follows the incident from initial user report through containment and recovery.

---

| Time | Event | Analyst Action | Outcome |
|------|-------|----------------|---------|
| **09:18** | Employee reports workstation is unusually slow after opening an email attachment. | Incident ticket opened and investigation initiated. | Investigation begins. |
| **09:22** | Splunk generates security alerts. | Reviewed endpoint logs and security events. | Suspicious PowerShell activity identified. |
| **09:27** | PowerShell execution observed. | Correlated execution time with user activity. | Potential malicious script execution suspected. |
| **09:31** | Multiple failed authentication attempts detected. | Reviewed authentication logs for abnormal login behavior. | No successful unauthorized authentication confirmed. |
| **09:37** | Network traffic reviewed in Wireshark. | Inspected outbound connections from affected workstation. | Unrecognized external IP address identified. |
| **09:42** | Indicators of Compromise collected. | Documented suspicious processes, user account, filename, and external IP. | IOC list created for future monitoring. |
| **09:50** | Workstation isolated. | Removed endpoint from the network to prevent further communication. | Potential spread contained. |
| **10:08** | Investigation findings documented. | Prepared incident report and supporting evidence. | Findings preserved for review. |
| **10:30** | Incident closed. | Recommended remediation and monitoring actions. | Incident marked as contained. |

---

## Investigation Summary

The investigation determined that the incident most likely originated from a phishing email containing a malicious attachment.

Following execution of the attachment, suspicious PowerShell activity, repeated failed authentication attempts, and outbound network traffic were observed.

Although no evidence of lateral movement or confirmed data exfiltration was identified, the workstation was isolated as a precaution while the investigation was completed.

---

## Key Milestones

- User reported suspicious workstation behavior.
- Splunk detected abnormal activity.
- PowerShell execution investigated.
- Authentication logs reviewed.
- Network traffic analyzed with Wireshark.
- Indicators of Compromise documented.
- Endpoint isolated.
- Incident successfully contained.
