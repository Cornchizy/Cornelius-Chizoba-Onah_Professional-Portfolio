# Linux Security Investigation Report

## 1. Investigation Overview

This report documents a basic security review performed in my Kali Linux lab environment after completing my Linux Fundamentals training.

The purpose of this investigation was to practice reviewing system information, users, privileges, processes, services, network connections, logs, and files.

---

## 2. Environment

- Operating System: Kali Linux
- Platform: VirtualBox
- Environment: Personal Lab
- Investigation Type: Basic Linux Security Review

---

## 3. User and Privilege Review

The following commands were used to identify the current user and review account information:

`whoami`

`id`

`groups`

`sudo -l`

The purpose of this review was to identify the active user, review group membership, and understand available elevated privileges.

---

## 4. Process Review

The following command was used to review running processes:

`ps aux`

Processes were reviewed based on the user running them, process ID, resource usage, and command information.

An unfamiliar process was not automatically considered malicious. Additional investigation and context would be required before making a conclusion.

---

## 5. Service Review

The following command was used to review active services:

`systemctl --type=service --state=running`

This review helped identify background services currently running on the system.

---

## 6. Network Review

The following commands were used to review network information and listening ports:

`ip addr`

`ip route`

`ss -tuln`

`ss -tulnp`

This review helped identify network interfaces, IP addressing, routing information, and services listening for network connections.

---

## 7. Log Review

Recent system events were reviewed using:

`journalctl -n 20`

Failed events were searched using:

`journalctl | grep -i "failed" | tail -n 20`

The purpose of the log review was to practice identifying events that may require further investigation.

A failed event alone was not treated as proof of malicious activity. Events require additional context, including the affected service, timing, frequency, and related system activity.

---

## 8. File Investigation

Files were investigated using:

`ls -la`

`file FILENAME`

`stat FILENAME`

`sha256sum FILENAME`

The investigation included reviewing file type, permissions, ownership, metadata, timestamps, and SHA-256 hashes.

I also practiced identifying misleading file extensions by checking the actual file content and type rather than trusting the filename alone.

---

## 9. Investigation Workflow

The following investigation process was used:

IDENTITY  
↓  
PRIVILEGES  
↓  
PROCESSES  
↓  
SERVICES  
↓  
NETWORK  
↓  
LOGS  
↓  
FILES  
↓  
FINDINGS  

This workflow demonstrated how multiple sources of information can be used together during a basic security investigation.

For example:

Unexpected Service  
↓  
Check Running Process  
↓  
Identify Listening Port  
↓  
Review Related Logs  
↓  
Investigate Associated Files  
↓  
Collect Additional Evidence  

---

## 10. Key Learning Outcome

This investigation demonstrated how Linux administration and cybersecurity concepts connect during a security review.

I practiced using Linux commands to investigate users, privileges, processes, services, network connections, logs, files, metadata, and file integrity.

---

## 11. Conclusion

Completing this project provided me with hands-on experience using fundamental Linux commands for basic system and security investigation.

The skills developed in this project provide a foundation for my continued cybersecurity training in Networking Fundamentals, Wireshark and PCAP analysis, SIEM tools, incident response, and threat hunting.

---

## Disclaimer

All commands and activities documented in this report were performed in my personal lab environment for educational purposes. No unauthorized systems were targeted or accessed.
