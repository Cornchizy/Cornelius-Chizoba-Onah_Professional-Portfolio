# Wireshark + PCAP Analysis — Investigation Report

## 1. Introduction

This investigation documents my practical work with Wireshark and PCAP analysis using Kali Linux.

The objective was to learn how to capture network traffic, identify protocols, examine packet information, apply filters, and investigate network communication from a cybersecurity perspective.

This project follows my Networking Fundamentals project and builds on my understanding of IP addresses, ports, protocols, DNS, TCP/IP, and network communication.

---

## 2. Lab Environment

The investigation was performed using:

- Operating System: Kali Linux
- Network Interface: eth0
- IPv4 Address: 10.226.139.40/24
- Virtualization Platform: VirtualBox
- Network Analysis Tool: Wireshark

The network interface used for packet capture was `eth0`.

---

## 3. Wireshark Installation Verification

I first verified that Wireshark was installed and available on the Kali Linux system.

### Command Used

```bash
wireshark --version

4. Network Interface Identification

I identified the network interface used by the Kali Linux system.

Command Used
ip -br addr

The active interface was:

eth0

The IPv4 address assigned to the interface during this project was:

10.226.139.40/24

Identifying the correct interface was necessary before beginning packet capture.

5. First Packet Capture

I opened Wireshark and selected the eth0 interface.

A short packet capture was performed to observe live network traffic.

The capture demonstrated that network communication consists of individual packets containing information about the communication between systems.

6. Understanding Packet Structure

Wireshark provides three major areas for examining packets:

Packet List
Packet Details
Packet Bytes

The Packet List provides an overview of captured traffic.

The Packet Details section provides a structured breakdown of the selected packet and its protocols.

The Packet Bytes section provides the raw packet representation in hexadecimal and ASCII form.

Understanding these sections is important when investigating network traffic.

7. IPv4 Packet Analysis

I used the following Wireshark display filter:

ip

This filter displayed IPv4 traffic.

I examined packet information including:

Source address
Destination address
Protocol
Time To Live
IPv4 header information

My Kali Linux system used:

10.226.139.40/24

Understanding source and destination addresses is important when investigating communication between systems.

8. TCP Analysis

I filtered traffic using:

tcp

I examined TCP packet information including:

Source port
Destination port
Sequence number
Acknowledgment number
TCP flags
Window information

TCP uses a connection-oriented communication process.

I also examined the TCP three-way handshake.

The basic process is:

Client → SYN → Server
Client ← SYN/ACK ← Server
Client → ACK → Server

This process establishes a TCP connection before normal data exchange occurs.

9. DNS Analysis

I generated DNS traffic using:

nslookup github.com

I then used the following Wireshark display filter:

dns

I examined DNS packets and looked at the query and response information.

DNS analysis can be useful during security investigations because systems frequently communicate with domains before connecting to external services.

Investigating DNS activity can therefore help analysts identify unusual or suspicious domain communication.

10. HTTP and HTTPS/TLS Analysis

I generated HTTPS traffic using:

curl -I https://example.com

I then examined TLS traffic using:

tls

I also generated HTTP traffic using:

curl -I http://example.com

The exercise demonstrated an important difference between HTTP and HTTPS.

HTTP communication can expose application-level information when transmitted without encryption.

HTTPS uses TLS to encrypt application data during communication.

As a result, an analyst may still observe metadata such as:

Source IP
Destination IP
Port
Protocol
Timing
Packet size

However, the encrypted application contents are not normally readable directly from the packet capture without appropriate decryption information.

11. Wireshark Display Filters

I practiced using several Wireshark display filters.

IPv4
ip
TCP
tcp
UDP
udp
DNS
dns
ICMP
icmp
Traffic involving my Kali IP
ip.addr == 10.226.139.40
TCP port 443
tcp.port == 443
DNS traffic involving my Kali system
dns && ip.addr == 10.226.139.40

Display filters are important because packet captures can contain large amounts of traffic. Filtering allows an analyst to focus on relevant communication.

12. Following a TCP Stream

I used Wireshark's Follow TCP Stream feature to examine a TCP conversation.

This allowed the communication associated with a TCP stream to be viewed as a conversation rather than as isolated packets.

This is useful when investigating network communication because analysts often need to understand the overall session instead of examining packets individually.

13. Basic PCAP Investigation

I created a new packet capture containing normal traffic.

The traffic included:

ping -c 4 1.1.1.1
nslookup github.com
curl -I https://example.com

The resulting capture contained different types of traffic, including ICMP, DNS, TCP, and TLS-related traffic.

I then used Wireshark filters to isolate and examine the traffic.

14. ICMP Investigation

I filtered the capture using:

icmp

This allowed me to examine the packets generated by the ping command.

The expected communication included my Kali Linux system:

Source: 10.226.139.40

and the destination:

1.1.1.1

I examined the IPv4 information contained in the packets.

15. DNS Investigation

I filtered the traffic using:

dns

I selected a DNS packet and expanded the Domain Name System information.

This allowed me to examine DNS query information and understand how DNS traffic appears inside a packet capture.

16. TLS Investigation

I filtered traffic using:

tls

I selected a TLS packet and examined the IPv4 and TCP information.

For HTTPS communication, TCP port:

443

is commonly used.

The investigation demonstrated that encrypted traffic can still provide useful network metadata even when the application contents cannot be directly read.

17. Mini Security Investigation

The final exercise simulated a basic security investigation.

I generated normal traffic and examined the resulting packets.

The investigation focused on:

Source IP addresses
Destination IP addresses
Protocols
DNS queries
ICMP traffic
TCP communication
TLS traffic
HTTPS port information

The objective was not to identify malicious activity but to practice the investigation process used by a security analyst.

18. Investigation Findings

The practical exercises demonstrated that Wireshark can provide detailed visibility into network communication.

The investigation allowed me to identify:

Which systems were communicating
Which protocols were being used
Which ports were involved
DNS requests
TCP communication
ICMP traffic
TLS traffic

I also learned that seeing a particular protocol or connection does not automatically mean that the activity is malicious.

Security analysts must consider context, destination, frequency, behavior, and other evidence before determining whether traffic is suspicious.

19. Cybersecurity Relevance

Wireshark and PCAP analysis are valuable skills for cybersecurity because network traffic can provide evidence during security investigations.

These skills can be applied to:

Incident response
Network troubleshooting
Malware traffic analysis
Suspicious communication investigation
DNS investigation
Threat hunting
Network monitoring
Security Operations Center activities

Packet analysis can help an analyst understand what happened during a network event and provide evidence for further investigation.

20. Lessons Learned

The major lesson from this project was that understanding networking fundamentals makes packet analysis much easier.

I learned how to move from simply identifying an IP address or port to examining the actual packets associated with network communication.

I also learned how Wireshark filters can significantly reduce the amount of information an analyst needs to examine.

Another important lesson was that encrypted traffic does not make all network information invisible. Even when application contents are protected by TLS, network metadata can still provide useful information for investigation.

21. Conclusion

This project provided practical experience with Wireshark, packet capture, protocol analysis, display filters, TCP streams, DNS traffic, ICMP traffic, and TLS traffic.

The experience strengthened my understanding of network communication and provided a foundation for future cybersecurity activities involving security monitoring, incident response, and threat hunting.
