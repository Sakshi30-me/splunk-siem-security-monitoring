# Detection Rule

## Objective

The detection rule identifies repeated Windows authentication activity by grouping successful authentication events by username and hostname.

## Detection SPL

```spl
index=windowslogs EventID=4624
| stats count by TargetUserName Hostname
| where count >= 2
| sort - count
```
---

## Alert Configuration

* **Alert Name:** Windows Authentication Activity Detection
* **Alert Type:** Scheduled
* **Schedule:** Daily
* **Trigger Condition:** Number of events > 0
* **Trigger:** Once
* **Action:** Add to Triggered Alerts
* **Status:** Enabled

---

## Purpose

This detection provides a basic security monitoring use case for identifying repeated authentication activity that can be reviewed by a security analyst.

The results should be investigated in context to determine whether the observed activity is expected or requires further investigation.

## Evidence

<img width="1473" height="654" alt="05_windows_authentication_detection" src="https://github.com/user-attachments/assets/2e7ebfed-92ea-4d46-8c36-343fcef746d6" />


