# Networking Fundamentals — Investigation Report

## 1. Introduction

This investigation documents the networking fundamentals I practiced using Kali Linux in a VirtualBox lab environment.

The purpose of the lab was to understand how a Linux system communicates on a network and how basic networking information can be examined from a cybersecurity perspective.

My Kali Linux machine was configured with the following IPv4 address:

**10.0.2.15/24**

---

## 2. Network Configuration

I used Linux networking commands to examine my network interface, IP address, routing information, and network configuration.

The `/24` prefix indicates a subnet mask of `255.255.255.0`.

The network was configured using VirtualBox NAT networking.

---

## 3. IP Address and Routing

I examined the IP address assigned to the Kali Linux machine and inspected the routing table.

The IP address identified during the lab was:

**10.0.2.15/24**

The routing information was used to identify the default gateway and understand how traffic leaves the local network.

### Commands Used

```bash
ip addr
ip route
4. Network Interfaces and MAC Addresses

I examined the network interfaces available on the Kali Linux machine and identified the interface being used for network communication.

I also examined the associated MAC address.

Command Used
ip -br addr
5. Listening Ports and Services

I examined TCP and UDP ports that were listening on the Kali Linux system.

I also used a command that displays the processes associated with listening network sockets.

Commands Used
ss -tuln
sudo ss -tulnp

An important observation from this exercise was that a system does not necessarily have to have publicly accessible services running. If no listening ports are present, that is still a valid security observation.

6. DNS Investigation

I performed DNS lookups to understand how domain names are translated into IP addresses.

Command Used
nslookup github.com

This demonstrated the relationship between a domain name and the IP address returned by DNS.

DNS is important in cybersecurity because analysts may investigate domains contacted by systems during security incidents.

7. Network Connectivity Testing

I tested connectivity to the local default gateway and an external IP address.

Commands Used
ping -c 4 127.0.0.1
ping -c 4 8.8.8.8

I also tested connectivity using a domain name:

ping -c 4 github.com

These tests helped demonstrate the difference between testing connectivity directly to an IP address and testing connectivity using a domain name.

8. ARP and Neighbor Information

I examined the neighbor table to understand how the system tracks nearby network devices.

Command Used
ip neigh

This provided practical exposure to the relationship between IP addresses and link-layer/MAC addresses on a local network.

9. Active Network Connections

I examined active TCP and UDP network connections.

Command Used
ss -tun

This helped demonstrate how network connections can be investigated from a Linux system.

10. Traceroute

I used traceroute to examine the network path toward an external destination.

Command Used
traceroute -m 5 8.8.8.8

The results showed the network hops encountered while attempting to reach the destination.

Some hops may not respond to traceroute probes, which can appear as * * *. This does not automatically indicate a network failure.

11. Nmap

I performed a basic Nmap scan against my own Kali Linux machine.

Command Used
nmap 127.0.0.1

The purpose was to practice basic network and service discovery in a controlled environment.

Scanning my own machine provided a safe way to understand how Nmap identifies available services and ports.

12. Network Troubleshooting Process

The exercises demonstrated a basic troubleshooting workflow:

Check the IP address.
Check the routing table.
Test the default gateway.
Test external IP connectivity.
Test DNS resolution.
Examine active connections.
Examine listening services.
Investigate network paths and services when necessary.

This process can help an IT or cybersecurity analyst narrow down where a network problem may be occurring.

13. Cybersecurity Relevance

Networking fundamentals are important for cybersecurity because most security events involve communication between systems.

Understanding networking concepts allows a security analyst to investigate:

Suspicious IP addresses
Unusual ports
Unexpected network connections
DNS requests
Network routes
Exposed services
Potential unauthorized communication

These skills will also be useful in later phases involving Wireshark, SIEM platforms, threat intelligence, incident response, and threat hunting.

14. Lessons Learned

During this project, I learned that networking troubleshooting should be systematic rather than based on guessing.

I learned how to use Linux commands to examine network configuration, connectivity, ports, services, DNS, routing, and network connections.

I also learned that an unusual result does not automatically mean that a security incident has occurred. Further investigation and context are required before making a conclusion.

15. Conclusion

This project gave me practical experience with fundamental networking concepts using Kali Linux.

The knowledge gained from this phase provides a foundation for analyzing network traffic and investigating security events.

The next phase of my cybersecurity learning path will focus on:

Wireshark + PCAP Analysis

This will allow me to move from examining network configuration and connections to analyzing the actual packets traveling across a network.
