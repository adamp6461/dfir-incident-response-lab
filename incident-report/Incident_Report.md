# Incident Report: Suspected Phishing Compromise

## Incident Summary

**Incident ID:** IR-2026-001  
**Organization:** AP Technology Group  
**Incident Type:** Suspected Phishing / Endpoint Compromise  
**Severity:** Medium  
**Status:** Contained  
**Date:** June 2026  

## Executive Summary

AP Technology Group investigated a suspected phishing-related endpoint compromise after an employee reported unusual workstation behavior shortly after opening an email attachment.

The investigation identified suspicious PowerShell activity, multiple failed authentication attempts, and outbound network connections to an unrecognized external IP address. Evidence was reviewed through Splunk log analysis, Windows event data, and Wireshark network traffic inspection.

The affected workstation was isolated from the network, suspicious activity was documented, and indicators of compromise were collected for further monitoring.

## Incident Background

An employee reported that their Windows workstation became slow and unstable after opening an attachment from what appeared to be a trusted vendor email.

Security monitoring later identified suspicious activity associated with the workstation, including:

- PowerShell execution
- Failed login attempts
- Unusual outbound network traffic
- Possible command-and-control behavior

## Scope

The investigation focused on:

- One affected Windows workstation
- One employee user account
- Windows event activity
- Splunk security alerts
- Network traffic captured in Wireshark

At the time of investigation, there was no evidence of lateral movement or confirmed data exfiltration.

## Tools Used

- Splunk Enterprise
- Wireshark
- Windows PowerShell
- Windows Event Logs
- MITRE ATT&CK Framework
- GitHub Documentation

## Investigation Timeline

| Time | Event |
|------|-------|
| 09:18 | Employee reports slow workstation after opening attachment |
| 09:22 | Security alert reviewed in Splunk |
| 09:27 | Suspicious PowerShell activity identified |
| 09:31 | Failed authentication attempts observed |
| 09:37 | Outbound network traffic reviewed in Wireshark |
| 09:42 | External IP address flagged as suspicious |
| 09:50 | Workstation isolated from the network |
| 10:08 | Indicators of compromise documented |
| 10:30 | Incident marked as contained |

## Detection

The incident was initially detected through a combination of user reporting and security monitoring.

Splunk alerts indicated suspicious endpoint activity, including PowerShell execution and repeated authentication failures. These alerts were reviewed alongside network traffic to determine whether the workstation was communicating with an unknown external destination.

## Analysis

### PowerShell Activity

PowerShell activity was considered suspicious because it occurred shortly after the user opened the attachment and did not align with normal user behavior.

The activity suggested possible script execution used to download or execute additional commands.

### Authentication Activity

Multiple failed authentication attempts were observed after the suspected phishing event. This raised concern that credentials may have been tested or abused.

No successful unauthorized login was confirmed during the investigation.

### Network Traffic

Wireshark analysis showed outbound traffic from the affected workstation to an unfamiliar external IP address.

The destination was treated as suspicious due to the timing of the traffic and its relationship to the endpoint behavior observed in Splunk.

## Findings

The investigation found:

- The incident likely began with a phishing email attachment.
- Suspicious PowerShell execution occurred after the attachment was opened.
- Multiple failed login attempts were observed.
- Outbound traffic was identified to an unrecognized external IP address.
- No confirmed lateral movement was identified.
- No confirmed data exfiltration was identified.

## Indicators of Compromise

| Indicator Type | Value |
|----------------|-------|
| Hostname | AP-WKS-014 |
| User Account | j.smith |
| Suspicious Process | powershell.exe |
| File Name | invoice_update.docm |
| External IP | 185.199.108.153 |
| Event Type | Failed Login Attempts |

## MITRE ATT&CK Mapping

| Tactic | Technique | Description |
|--------|-----------|-------------|
| Initial Access | T1566 - Phishing | User opened suspicious attachment |
| Execution | T1059.001 - PowerShell | Suspicious PowerShell activity observed |
| Credential Access | T1110 - Brute Force | Multiple failed authentication attempts |
| Command and Control | T1071 - Application Layer Protocol | Outbound traffic to unknown external IP |
| Ingress Tool Transfer | T1105 | Possible external payload retrieval |

## Containment

The affected workstation was isolated from the network to prevent further communication with external systems and reduce the risk of lateral movement.

The user account was reviewed for suspicious authentication activity, and identified indicators were documented for continued monitoring.

## Eradication

Recommended eradication actions included:

- Remove the suspicious email and attachment
- Review endpoint for unauthorized scripts or files
- Reset the affected user's password
- Run endpoint malware scan
- Review startup items and scheduled tasks
- Validate that no persistence mechanisms remain

## Recovery

Recovery actions included:

- Reconnect workstation only after validation
- Confirm endpoint health
- Monitor for recurring suspicious traffic
- Review Splunk alerts for repeated activity
- Educate the user on phishing indicators

## Recommendations

- Enable stronger phishing email filtering
- Increase PowerShell logging
- Implement Sysmon for deeper endpoint visibility
- Enforce multi-factor authentication
- Create Splunk alerts for suspicious PowerShell usage
- Review failed login thresholds
- Continue user security awareness training

## Conclusion

This incident demonstrated the importance of correlating user reports, endpoint activity, SIEM alerts, and network traffic during an investigation.

Although no confirmed data exfiltration or lateral movement was identified, the suspicious PowerShell execution and outbound network traffic justified containment and further monitoring.

The incident was contained successfully, and documented indicators were preserved for future detection and investigation.
