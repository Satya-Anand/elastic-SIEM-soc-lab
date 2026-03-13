# Detection Rule: Suspicious PowerShell Execution

## Overview

PowerShell is a powerful command-line tool commonly used by system administrators. However, attackers frequently abuse PowerShell to execute malicious scripts, download payloads, or perform lateral movement.

This detection rule monitors PowerShell execution on a Windows endpoint and generates an alert in Elastic SIEM when PowerShell is executed.

---

## Detection Query


process.name:powershell.exe


This query detects events where the PowerShell process is executed on the monitored endpoint.

---

## Attack Simulation

The following commands were used to simulate suspicious activity in the lab environment.

### PowerShell Execution


powershell -ExecutionPolicy Bypass


### Encoded PowerShell Command


powershell -EncodedCommand aQBlAHgA


These commands generated process execution logs that were collected by Elastic Agent and analyzed in Elastic SIEM.

---

## Alert Generation

A detection rule was created in Elastic SIEM using the query:


process.name:powershell.exe


When PowerShell was executed on the endpoint, the rule triggered an alert in the SIEM dashboard.

---

## Investigation Steps

When the alert was generated, the following investigation steps were performed:

1. Opened the alert in Elastic SIEM.
2. Reviewed the process execution logs.
3. Verified the command executed on the Windows endpoint.
4. Checked related events and process activity.
5. Confirmed the activity was part of the simulated lab attack.

---

## MITRE ATT&CK Mapping

| Technique ID | Technique |
|---------------|-----------|
| T1059.001 | PowerShell |
| T1027 | Obfuscated / Encoded Commands |

---

## Conclusion

This detection rule successfully identified PowerShell execution activity and generated alert