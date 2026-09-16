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

<img width="1897" height="859" alt="01_Splunk_events" src="https://github.com/user-attachments/assets/7806ee60-bdac-42ba-921f-446095214797" />

---

<img width="1891" height="902" alt="02_authentication_events" src="https://github.com/user-attachments/assets/b1eb53ed-b7a9-4da6-98e7-24446d45a6d0" />

---

<img width="1902" height="877" alt="03_system_activity" src="https://github.com/user-attachments/assets/5f98d1d3-8f12-45c5-bf44-c294e9abf292" />

