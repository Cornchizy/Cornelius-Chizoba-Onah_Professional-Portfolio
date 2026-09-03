# Windows Event Logs Investigation

## Overview

This project is part of my cybersecurity learning journey toward an entry-level cybersecurity/SOC role.

The purpose of this project was to learn how Windows Event Viewer records system and security activity and how a cybersecurity analyst can use these logs during an investigation.

I worked with Windows Event Viewer and investigated security-related events, including successful logons, failed logons, logon types, and process creation events.

---

## Objectives

- Understand Windows Event Viewer
- Identify the major Windows event logs
- Explore the Security log
- Investigate successful logons using Event ID 4624
- Investigate failed logons using Event ID 4625
- Understand Windows logon types
- Investigate process creation using Event ID 4688
- Learn how to filter Windows events
- Perform a basic authentication investigation
- Perform a basic process investigation
- Practice thinking like a junior SOC analyst

---

## Tools Used

- Windows Event Viewer
- Local Security Policy
- Group Policy
- Command Prompt
- Windows Security Event Logs

---

## Key Event IDs

| Event ID | Description |
|---|---|
| 4624 | Successful account logon |
| 4625 | Failed account logon |
| 4688 | New process creation |

---

## Investigation Process

The investigation followed this general process:

1. Opened Windows Event Viewer.
2. Located the Windows Logs section.
3. Examined the Security log.
4. Reviewed individual security events.
5. Filtered events by Event ID.
6. Investigated successful authentication events.
7. Investigated failed authentication events.
8. Compared authentication activity.
9. Investigated logon types.
10. Enabled and examined process creation auditing.
11. Reviewed Event ID 4688.
12. Performed a basic SOC-style investigation.

---

## Authentication Investigation

Event ID 4624 was used to identify successful logons.

Event ID 4625 was used to identify failed logon attempts.

During the investigation, I examined information such as:

- Account name
- Event time
- Logon type
- Failure information
- Source network information
- Authentication details

I compared failed and successful authentication events to understand how Windows records user access.

---

## Process Creation Investigation

Event ID 4688 was investigated to understand how Windows records the creation of new processes.

Process creation auditing was enabled so that newly created processes could be observed in the Security event log.

I generated processes using normal Windows commands and then reviewed the resulting security events.

The investigation focused on information such as:

- New process name
- Creator process
- Process command line, where available
- Event time

---

## What I Learned

Through this project, I learned that Windows generates security events that can provide useful evidence during cybersecurity investigations.

I learned how to:

- Navigate Event Viewer
- Locate important Windows logs
- Filter events by Event ID
- Identify successful and failed authentication
- Understand the importance of logon types
- Investigate process creation events
- Use Windows logs as security evidence
- Approach Windows investigations from a SOC analyst perspective

---

## Skills Demonstrated

- Windows Event Viewer
- Security Event Log Analysis
- Authentication Log Analysis
- Event ID Analysis
- Log Filtering
- Basic Security Investigation
- Process Monitoring
- SOC Investigation Fundamentals

---

## Evidence

Screenshots documenting the practical work are available in the `evidence` folder.

The evidence includes screenshots of:

- Event Viewer
- Windows Logs
- Security Logs
- Security Event IDs
- Successful logons
- Failed logons
- Logon details
- Logon types
- Process creation events
- Event filtering
- Authentication investigation
- Process investigation

---

## Conclusion

This project gave me practical experience working with Windows security logs and introduced me to the type of evidence a cybersecurity analyst may use when investigating authentication and system activity.

This is one step in my continued cybersecurity learning path toward an entry-level cybersecurity/SOC position.
