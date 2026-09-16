# Alert Investigation

## Investigation Objective

The authentication detection results were investigated to identify repeated Windows authentication activity and review the related user, host, logon type, and IP address information.

## Investigation SPL

```spl
index=windowslogs EventID=4624
| stats count by TargetUserName Hostname LogonType IpAddress
| sort - count
```
---

## Investigation Results

The search returned **26 authentication events** and grouped the activity by username, hostname, logon type, and IP address.

Repeated authentication activity was observed in the results and reviewed as part of the investigation.


## Findings

The investigation demonstrated how Splunk can be used to:

* Identify authentication activity.
* Group repeated authentication events.
* Review associated users, hosts, and IP addresses.
* Support investigation of security alerts.

The observed activity should be compared with expected organizational behavior before determining whether it is suspicious.

## Response Recommendation

For a production environment, investigate authentication activity that is unexpected for the user, host, logon type, or source IP address. Correlate it with other available security events before taking response actions.

## Evidence

06 — [Authentication Investigation Findings](screenshots/06_authentication_investigation_findings.png)
