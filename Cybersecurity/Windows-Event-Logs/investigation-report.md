# Windows Event Logs Investigation Report

## 1. Investigation Overview

This investigation focused on learning how Windows records security-related activity through Event Viewer.

The goal was to investigate authentication activity and process creation events using Windows Security logs.

---

## 2. Environment

### Operating System

Windows

### Tools

- Windows Event Viewer
- Local Security Policy
- Group Policy
- Command Prompt

---

## 3. Authentication Investigation

### Event ID 4624 — Successful Logon

Event ID 4624 was examined to identify successful authentication events.

The investigation reviewed:

- Account name
- Event time
- Logon type
- Source information
- Authentication information

Successful logon events were compared with failed authentication events to understand the sequence of activity.

---

### Event ID 4625 — Failed Logon

Event ID 4625 was used to identify failed authentication attempts.

The investigation reviewed:

- Account name
- Event time
- Logon type
- Failure information
- Source network information

The failed events were compared with successful logons to determine whether authentication activity appeared unusual.

---

## 4. Logon Type Analysis

Logon types were reviewed to understand how authentication occurred.

Logon type information can help an analyst distinguish between different forms of access, such as interactive, network, service, and remote interactive logons.

---

## 5. Process Creation Investigation

### Event ID 4688

Process creation auditing was enabled to allow Windows to record newly created processes.

Normal Windows commands were executed to generate process activity.

The resulting Event ID 4688 records were reviewed for information including:

- New process name
- Creator process
- Process command line, where available
- Event timestamp

---

## 6. Investigation Findings

The investigation demonstrated how Windows Security logs can be used to reconstruct user authentication and system activity.

The authentication investigation successfully identified both successful and failed logon events.

The process creation investigation demonstrated how Windows can record newly created processes when the appropriate auditing is enabled.

No malicious activity was intentionally generated during this lab. The purpose was to learn the investigation methodology using normal system activity.

---

## 7. Analyst Perspective

From a SOC analyst perspective, authentication events can be useful when investigating:

- Repeated failed logons
- Suspicious account activity
- Unusual login times
- Unexpected source addresses
- Remote access
- Possible password attacks

Process creation events can also help analysts investigate potentially suspicious programs or commands executed on a system.

---

## 8. Lessons Learned

This project improved my understanding of:

- Windows Event Viewer
- Windows Security logs
- Event IDs
- Authentication events
- Logon types
- Process creation
- Event filtering
- Basic security investigation

It also helped me understand how raw system logs can be turned into useful security information.

---

## 9. Conclusion

The Windows Event Logs project provided practical experience analyzing Windows security events.

The skills learned here will be useful in later cybersecurity projects involving SIEM platforms such as Splunk, Microsoft Sentinel, and Elastic Security.
