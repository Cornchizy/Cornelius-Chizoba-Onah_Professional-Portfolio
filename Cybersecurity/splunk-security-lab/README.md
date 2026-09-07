# Splunk Authentication Security Investigation

## Overview

This project demonstrates the use of Splunk and Splunk Processing Language (SPL) to investigate authentication events and identify potentially suspicious login activity.

The lab was completed in a controlled environment using Kali Linux and a simulated authentication dataset.

## Objectives

The objectives of this project were to:

- Install and verify Splunk
- Configure Splunk for security log analysis
- Import authentication data
- Learn basic SPL searches
- Identify failed login attempts
- Analyze suspicious source IP addresses
- Identify targeted user accounts
- Correlate authentication events
- Detect repeated failed login attempts
- Visualize authentication activity
- Build a basic SOC-style security dashboard
- Document the investigation findings

## Environment

| Component | Details |
|---|---|
| Operating System | Kali Linux 2026.3 |
| Architecture | x86_64 |
| Splunk Version | 10.4.3 |
| Data Type | Authentication Logs |
| Dataset | Controlled/Synthetic Security Dataset |
| Primary Language | SPL |

## Dataset

A controlled authentication dataset was created for this investigation.

The dataset contained fields including:

- `_time` - Date and time of the event
- `user` - Username involved in the authentication attempt
- `src_ip` - Source IP address
- `event_type` - Type of event
- `status` - Authentication result

The dataset contained both successful and failed authentication events.

## Investigation Process

### 1. Splunk Verification

Splunk was verified as installed and running on the Kali Linux system.

### 2. Data Preparation

A controlled authentication dataset was created and prepared for ingestion into Splunk.

### 3. Data Ingestion

The authentication dataset was imported into Splunk and stored in the `security` index.

### 4. Initial SPL Search

The following SPL query was used to search the security index:

```spl
index=security

5. Field Analysis

Important authentication fields were displayed using:

index=security
| table _time user src_ip event_type status
6. Failed Login Investigation

Failed authentication attempts were identified using:

index=security status=failure
7. Failed Logins by Source IP

The number of failed attempts from each source IP was calculated using:

index=security status=failure
| stats count by src_ip
| sort - count
8. Failed Logins by User

Failed authentication attempts were also grouped by username:

index=security status=failure
| stats count by user
| sort - count
9. Source IP and User Correlation

The relationship between source IP addresses and targeted accounts was investigated using:

index=security status=failure
| stats count by src_ip user
| sort - count
10. Suspicious Source Investigation

The source IP generating the highest number of failures was investigated further by reviewing all authentication activity associated with that IP.

index=security src_ip=SUSPICIOUS_IP
| sort _time
| table _time user status

SUSPICIOUS_IP was replaced with the IP identified during the investigation.

11. High-Volume Failed Login Detection

A basic detection query was created to identify IP/user combinations with three or more failed login attempts:

index=security status=failure
| stats count by src_ip user
| where count >= 3
| sort - count
12. Authentication Timeline

Authentication activity was visualized over time using:

index=security
| timechart count by status
Security Finding

The investigation identified repeated failed authentication attempts associated with a particular source IP and user account.

The suspicious activity was investigated by:

Identifying failed authentication events.
Ranking source IP addresses by the number of failures.
Identifying accounts receiving repeated failures.
Correlating source IP addresses with usernames.
Reviewing the authentication timeline.
Checking whether successful authentication occurred after repeated failures.

Repeated authentication failures can be an indicator of password guessing or brute-force activity. A successful authentication following multiple failures should receive additional investigation to determine whether the login was legitimate or potentially unauthorized.

SOC Relevance

This investigation demonstrates several activities commonly performed by entry-level SOC analysts:

Log analysis
Event filtering
Authentication monitoring
IP address analysis
User activity analysis
Event correlation
Detection development
Timeline analysis
Security visualization
Incident documentation
Skills Demonstrated
Splunk
SPL
Linux
Log Analysis
Authentication Monitoring
Security Investigation
Threat Detection
Event Correlation
Basic SOC Analysis
Security Dashboard Development
Technical Documentation
Evidence

Screenshots documenting the practical work are stored in the screenshots directory.

The evidence includes:

Splunk installation verification
Splunk service status
Splunk Web interface
Search & Reporting
Dataset creation
Data ingestion
SPL searches
Failed-login analysis
Source IP analysis
User analysis
Authentication correlation
Suspicious activity investigation
Detection query
Authentication timeline
SOC dashboard
Final investigation
Conclusion

This project provided practical experience using Splunk to investigate authentication logs and identify potentially suspicious login patterns.

The investigation demonstrated how security analysts can use centralized log data and SPL queries to identify failed authentication attempts, investigate suspicious sources, correlate events, and create basic security detections.

This project forms part of my cybersecurity portfolio and demonstrates practical experience with security monitoring and SIEM technologies.
