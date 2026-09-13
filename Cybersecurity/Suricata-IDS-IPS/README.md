# Suricata IDS/IPS – ICMP Ping Flood Detection

## Overview

This project demonstrates the use of Suricata as an Intrusion Detection and Prevention System (IDS/IPS) to monitor network traffic and detect an ICMP ping flood.

The lab was performed in a controlled environment using Kali Linux. I created custom Suricata detection rules to identify excessive ICMP Echo Requests and then tested the rules using a Python-based ping flood simulator against my lab target.

The goal of this project was to gain practical experience with network monitoring, custom IDS rules, alert generation, and security event analysis.

---

## Tools and Technologies

- Kali Linux
- Suricata IDS/IPS
- Python
- pythonping
- ICMP
- Linux command line
- Suricata Fast Log

---

## Lab Objective

The objectives of this lab were to:

1. Install and configure Suricata.
2. Configure the network being monitored.
3. Update Suricata detection rules.
4. Create custom ICMP ping flood detection rules.
5. Test the Suricata configuration.
6. Run Suricata in live monitoring mode.
7. Generate controlled ICMP traffic from the lab.
8. Verify that Suricata detected the traffic.
9. Review the resulting security alerts.

---

## Network Configuration

The Suricata lab used the network interface configured on the Kali Linux system.

The custom rules were configured to monitor traffic directed toward the Suricata `HOME_NET` network.

The ICMP test traffic was generated against the controlled lab target:

`172.20.10.4`

---

## Custom Suricata Rules

Two custom rules were created to detect excessive ICMP Echo Requests.

### Rule 1 – Excessive ICMP Echo Requests

```text
alert icmp any any -> $HOME_NET any (msg:"PING FLOOD DETECTION - Excessive ICMP Echo Requests";itype:8;flow:to_server;threshold: type limit, track by_src, count 100, seconds 10;classtype:attempted-dos;sid:21;)

This rule generates an alert when a source sends a high number of ICMP Echo Requests toward the monitored network.

Rule 2 – Rapid ICMP Echo Requests
alert icmp any any -> $HOME_NET any (msg:"PING FLOOD DETECTION - Rapid ICMP Echo Requests";itype:8;flow:to_server;detection_filter: track by_src, count 50, seconds 1;classtype:attempted-dos;sid:122;)

This rule detects a rapid burst of ICMP Echo Requests from the same source.

Suricata Configuration Test

Before running Suricata, the configuration was tested using:

sudo suricata -T -c /etc/suricata/suricata.yaml -i eth0

A successful configuration test confirmed that Suricata could load the configuration and rules.

Running Suricata

Suricata was started in live monitoring mode using:

sudo suricata -c /etc/suricata/suricata.yaml -i eth0

The system was then monitored for generated alerts.

Traffic Generation

A Python script using the pythonping library was used to generate controlled ICMP Echo Requests against the lab target.

The test was performed only within the controlled lab environment.

The traffic generation was used to verify that the custom Suricata rules could detect the simulated ping flood.

Detection and Alert Analysis

Suricata successfully detected the generated ICMP traffic.

The resulting alerts were observed in:

/var/log/suricata/fast.log

The alerts contained the custom message:

PING FLOOD DETECTION

This confirmed that the custom ICMP detection rules were successfully loaded and triggered by the test traffic.

Evidence
Suricata Installation

Suricata Version

Network Interface

HOME_NET Configuration

Emerging Threats Rule Update

Custom Ping Flood Rules

Suricata Rule Files

Suricata Configuration Test

Suricata Running

Ping Flood Script

Ping Flood Test

Suricata Detection Alerts

Skills Demonstrated
Linux command-line administration
Network traffic monitoring
IDS/IPS configuration
Suricata rule creation
ICMP traffic analysis
Security alert investigation
Log analysis
Basic DoS detection
Security testing in a controlled lab environment
Technical documentation
