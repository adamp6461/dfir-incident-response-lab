# Indicators of Compromise (IOCs)

## Overview

This document lists the Indicators of Compromise (IOCs) identified during the investigation of a suspected phishing-related endpoint compromise at AP Technology Group.

These indicators can be used for future monitoring, detection engineering, and incident response activities.

---

## Endpoint Indicators

| Indicator | Value | Description |
|-----------|-------|-------------|
| Hostname | AP-WKS-014 | Affected Windows workstation |
| User Account | j.smith | User assigned to affected workstation |
| Process | powershell.exe | Suspicious PowerShell execution observed |
| Attachment | invoice_update.docm | Email attachment opened by user |

---

## Network Indicators

| Indicator | Value | Description |
|-----------|-------|-------------|
| External IP Address | 185.199.108.153 | Destination observed during outbound network communication |
| Protocol | HTTPS | Encrypted outbound connection identified |
| Network Tool | Wireshark | Used to inspect captured traffic |

---

## Authentication Indicators

| Indicator | Value | Description |
|-----------|-------|-------------|
| Failed Login Attempts | Multiple | Repeated authentication failures observed following initial activity |
| Log Source | Windows Security Logs | Authentication events reviewed in Splunk |

---

## Security Events

- Suspicious PowerShell execution
- Multiple failed authentication attempts
- Outbound connection to an unfamiliar external IP address
- User reported degraded workstation performance

---

## Detection Opportunities

The following activities should be monitored in future investigations:

- Unusual PowerShell execution
- Multiple failed authentication attempts
- Office documents containing macros
- Unexpected outbound HTTPS connections
- Suspicious process creation events

---

## Recommended Monitoring

- Create Splunk alerts for abnormal PowerShell execution.
- Monitor repeated failed authentication attempts.
- Review outbound network traffic for unfamiliar destinations.
- Enable enhanced PowerShell logging.
- Deploy Sysmon for improved endpoint visibility.

---

## MITRE ATT&CK References

| Technique | Description |
|-----------|-------------|
| T1566 | Phishing |
| T1059.001 | PowerShell |
| T1110 | Brute Force |
| T1071 | Application Layer Protocol |
| T1105 | Ingress Tool Transfer |
