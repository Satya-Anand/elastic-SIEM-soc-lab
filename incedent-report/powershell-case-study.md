# Incident Case Study: Suspicious PowerShell Activity

## Incident Overview

Elastic SIEM generated an alert indicating suspicious PowerShell execution on a monitored Windows endpoint.

PowerShell is frequently abused by attackers to execute scripts, download malware, or perform lateral movement within a network.

---

## Detection

The alert was triggered using the detection query:


process.name:powershell.exe


This rule monitors execution of PowerShell processes on the endpoint.

---

## Attack Simulation

The following commands were executed to simulate attacker activity:

PowerShell execution:


powershell -ExecutionPolicy Bypass


Encoded PowerShell command:


powershell -EncodedCommand aQBlAHgA


These commands generated process execution logs collected by Elastic Agent.

---

## Investigation Process

The following investigation steps were performed:

1. Alert reviewed in Elastic SIEM dashboard.
2. Process execution logs examined.
3. Command activity correlated with endpoint events.
4. Associated telemetry reviewed in SIEM logs.

---

## Findings

The SIEM logs confirmed the following:

- PowerShell process execution occurred on the endpoint
- Encoded PowerShell command was executed
- Activity matched the simulated attack commands

---

## MITRE ATT&CK Mapping

| Technique ID | Technique |
|---------------|-----------|
| T1059.001 | PowerShell |
| T1027 | Obfuscated / Encoded Commands |

---

## Conclusion

The detection rule successfully identified suspicious PowerShell activity and generated an alert