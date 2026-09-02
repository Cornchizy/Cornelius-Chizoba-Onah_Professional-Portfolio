# Wireshark + PCAP Analysis

## Overview

This project documents my hands-on learning and practical experience with Wireshark and PCAP analysis using Kali Linux.

The purpose of this project was to build practical skills in capturing, filtering, examining, and interpreting network traffic from a cybersecurity perspective.

This project builds on the Networking Fundamentals phase of my cybersecurity learning path.

## Learning Objectives

During this project, I practiced:

- Capturing network traffic
- Identifying network interfaces
- Understanding packet structure
- Examining IPv4 packets
- Analyzing TCP traffic
- Understanding TCP handshakes
- Investigating DNS traffic
- Examining HTTP and HTTPS/TLS traffic
- Using Wireshark display filters
- Following TCP streams
- Investigating PCAP traffic
- Performing a basic network traffic security investigation

## Lab Environment

- Operating System: Kali Linux
- Network Interface: eth0
- Virtualization Platform: VirtualBox
- Network Configuration: VirtualBox networking
- Kali Linux IPv4 Address: Dynamic/24
- Primary Tool: Wireshark

## Project Labs

### Lab 1 — Wireshark Introduction

I verified that Wireshark was installed and identified the network interface used by my Kali Linux machine.

I then opened Wireshark and performed my first packet capture using the eth0 interface.

### Lab 2 — Understanding Packets

I examined the three main sections of the Wireshark interface:

- Packet List
- Packet Details
- Packet Bytes

I selected individual packets and expanded protocol information to understand how packet data is structured.

### Lab 3 — IP Packet Analysis

I used Wireshark filters to identify IPv4 traffic and examined:

- Source IP address
- Destination IP address
- Protocol
- Time To Live
- IPv4 packet information

My Kali Linux IP address during this project was:

**10.226.139.40/24**

### Lab 4 — TCP Analysis

I examined TCP packets and investigated TCP header information, including:

- Source port
- Destination port
- Sequence number
- Acknowledgment number
- TCP flags
- Window information

I also examined TCP communication and the three-way handshake.

### Lab 5 — DNS Analysis

I generated DNS traffic and used Wireshark to investigate DNS queries and responses.

I examined DNS information such as:

- Query
- Response
- Domain name
- Record information
- Source and destination information

DNS analysis is useful in cybersecurity investigations because suspicious or malicious activity may involve unusual domain lookups.

### Lab 6 — HTTP and HTTPS/TLS Traffic

I generated HTTP and HTTPS traffic and examined the resulting packets.

The exercise demonstrated the difference between unencrypted HTTP communication and encrypted HTTPS/TLS communication.

I also observed that encrypted traffic does not normally expose the application contents directly without appropriate decryption information.

### Lab 7 — Wireshark Display Filters

I practiced using Wireshark display filters to isolate specific types of traffic.

Examples included:

```text
ip
tcp
udp
dns
icmp
ip.addr == 10.226.139.40
tcp.port == 443
dns && ip.addr == 10.226.139.40

Lab 8 — Follow TCP Stream

I used Wireshark's Follow TCP Stream functionality to examine a TCP conversation as a communication session instead of analyzing individual packets separately.

This demonstrated how analysts can reconstruct and investigate network conversations.

Lab 9 — Basic PCAP Investigation

I created a packet capture containing normal network traffic generated through:

ICMP
DNS
HTTPS/TLS

I then investigated the captured traffic using Wireshark filters and packet details.

Lab 10 — Mini Security Investigation

The final practical exercise simulated a basic network traffic investigation.

I generated normal network traffic and investigated:

Source and destination addresses
ICMP communication
DNS requests
TLS traffic
TCP information
HTTPS-related traffic
Port 443

The purpose was to practice moving from simply viewing packets to investigating network activity from a security analyst perspective.

Cybersecurity Relevance

Wireshark is an important tool for understanding network traffic and investigating potential security incidents.

The skills practiced in this project can support activities such as:

Network troubleshooting
Incident investigation
Malware traffic analysis
Suspicious connection analysis
DNS investigation
Protocol analysis
Network-based threat detection
Incident response
Threat hunting

Understanding packets also provides a foundation for analyzing suspicious network behavior in a Security Operations Center (SOC) environment.

Key Skills Demonstrated
Wireshark
PCAP analysis
Packet capture
Network protocol analysis
TCP/IP analysis
DNS analysis
TCP analysis
TLS traffic analysis
Wireshark display filters
TCP stream analysis
Network traffic investigation
Basic security investigation
Evidence

The evidence directory contains screenshots documenting the practical exercises completed during this project.

Lessons Learned

This project helped me understand that network traffic can be investigated at a much deeper level than simply looking at IP addresses and open ports.

I learned how individual packets contain multiple layers of information and how Wireshark can be used to examine those layers.

I also learned that filters are essential when working with large packet captures because they allow analysts to focus on specific protocols, addresses, ports, and types of communication.
