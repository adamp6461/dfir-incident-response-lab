# MITRE ATT&CK Mapping

## Overview

This lab demonstrates how endpoint telemetry and network traffic can be correlated during a simulated phishing investigation. The observed activity has been mapped to the MITRE ATT&CK Framework to illustrate how common attacker behaviors align with defensive monitoring.

---

## ATT&CK Mapping

| Tactic              | Technique                    | ID        | Evidence                                                        |
| ------------------- | ---------------------------- | --------- | --------------------------------------------------------------- |
| Initial Access      | Phishing                     | T1566     | Simulated phishing email used as the investigation scenario.    |
| Execution           | PowerShell                   | T1059.001 | Windows Event Logs reviewed for PowerShell activity.            |
| Discovery           | System Information Discovery | T1082     | Windows system information and endpoint telemetry collected.    |
| Credential Access   | Brute Force                  | T1110     | Failed authentication events reviewed during the investigation. |
| Command and Control | Application Layer Protocol   | T1071     | TCP/TLS communications inspected using Wireshark.               |

---

## Defensive Data Sources

The following data sources were used throughout the investigation:

* Windows Security Event Logs
* Windows System Event Logs
* Windows Application Event Logs
* Splunk Cloud SIEM
* Splunk Universal Forwarder
* Wireshark Packet Captures

---

## Detection Opportunities

Potential detections that could be implemented include:

* Alert on excessive failed logon attempts.
* Monitor PowerShell execution from unusual parent processes.
* Detect unusual outbound TCP/TLS connections.
* Identify suspicious authentication patterns.
* Correlate endpoint events with network traffic.

---

## Skills Demonstrated

* MITRE ATT&CK Mapping
* Endpoint Telemetry Analysis
* Windows Event Log Analysis
* Splunk Search Processing Language (SPL)
* Network Traffic Analysis
* Digital Forensics & Incident Response (DFIR)
