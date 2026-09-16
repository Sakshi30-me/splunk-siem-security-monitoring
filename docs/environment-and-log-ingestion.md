# Environment and Log Ingestion


## Environment

- **SIEM:** Splunk Enterprise
- **Dataset:** Windows security event logs
- **Index:** `windowslogs`
- **Event Volume:** Approximately 12,000 events

## Log Analysis

The Windows security dataset was used to practice centralized security monitoring and log analysis in Splunk.

The dataset contains different types of Windows security activity, including authentication and system/process events.

The initial search was:

```spl
index=windowslogs
```

This returned approximately 12,000 events and provided the dataset used for the investigation.

---

## Authentication Events

Windows authentication activity was analyzed using Event ID 4624.

```spl
index=windowslogs EventID=4624
```

Relevant fields were then extracted to investigate usernames, IP addresses, logon types, workstations, and processes.

---

## System Activity

Windows process creation activity was analyzed using Event ID ```1```.

```spl
index=windowslogs EventID=1
```

This provided system activity that could be correlated with authentication events during the investigation.

---

## Evidence

01 — [Splunk Events](screenshots/01_Splunk_events.png)

02 — [Authentication Events](screenshots/02_authentication_events.png)

03 — [System Activity](screenshots/03_system_activity.png)
