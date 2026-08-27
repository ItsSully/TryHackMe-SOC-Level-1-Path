# Network Traffic Analysis

**TryHackMe SOC Level 1 — Module 6**

**Status:** ✅ Completed

## Overview

This module introduced network traffic analysis and provided hands-on experience with tools and techniques used to investigate network activity.

The module progressed from understanding network traffic and common network flows to analysing packet captures with **Wireshark** and performing network forensic investigations with **NetworkMiner**.

I developed an understanding of how network traffic can be used to identify suspicious activity, investigate anomalies and support security investigations.

---

## Topics Covered

### Network Traffic Basics

I learned the fundamentals of **Network Traffic Analysis (NTA)** and why it is important within a SOC environment.

Network traffic analysis involves capturing, inspecting and analysing communications across a network to understand normal activity and identify deviations from expected behaviour.

I explored:

- What network traffic analysis is used for
- Information available within network traffic
- Network traffic sources
- North-South and East-West traffic
- Network logs
- Full packet capture
- Network statistics
- Network taps
- Port mirroring
- Common network protocols and flows

I also explored how network traffic analysis can help analysts detect suspicious activity, reconstruct attacks and validate security alerts.

**Skill developed:** Understanding the role of network traffic analysis within security monitoring and investigations.

---

### Wireshark: The Basics

I learned the fundamentals of **Wireshark**, a network packet analyser used to inspect live traffic and packet capture files (PCAP/PCAPNG).

I practised:

- Loading packet capture files
- Navigating the Wireshark interface
- Understanding packet details
- Packet dissection
- Navigating packet numbers
- Finding and marking packets
- Adding packet comments
- Exporting packets and objects
- Using Expert Information
- Applying packet filters
- Following network conversations and streams

This provided the foundation for using Wireshark to investigate network traffic at packet level.

**Skill developed:** Basic packet capture analysis and navigation using Wireshark.

---

### Wireshark: Packet Operations

I progressed from basic packet inspection into more detailed packet analysis using Wireshark's statistics and filtering capabilities.

I explored:

- Protocol hierarchy
- Conversations
- Endpoints
- IPv4 and IPv6 statistics
- DNS statistics
- HTTP statistics
- Name resolution
- Packet filtering
- Capture filters
- Display filters
- Logical expressions
- Protocol-specific filtering

These features helped me understand how analysts can narrow large packet captures down to the traffic relevant to an investigation.

I also practised using statistical views to identify communication patterns, endpoints and protocol activity.

**Skill developed:** Using Wireshark statistics and filters to investigate specific network events.

---

### Wireshark: Traffic Analysis

I applied the Wireshark skills developed in the previous lessons to investigate suspicious network activity and identify attack patterns.

The practical analysis covered several types of network activity, including:

- Nmap scanning
- TCP Connect scans
- SYN scans
- UDP scans
- ARP poisoning and Man-in-the-Middle activity
- DHCP analysis
- NetBIOS analysis
- Kerberos analysis
- DNS tunnelling
- ICMP tunnelling
- Suspicious network behaviour

I learned how different network attacks create recognisable traffic patterns and how Wireshark filters can be used to isolate those patterns within a packet capture.

### Network Scanning

I analysed different Nmap scanning behaviours and learned how to distinguish between:

- TCP Connect scans
- SYN scans
- UDP scans

This involved analysing TCP flags, handshakes, packet behaviour and ICMP responses.

### ARP Poisoning

I investigated ARP traffic to identify signs of **ARP spoofing and Man-in-the-Middle activity**.

This involved examining ARP requests and responses and correlating MAC addresses with network traffic.

### Host Identification

I explored how network protocols such as:

- DHCP
- NetBIOS (NBNS)
- Kerberos

can provide information about hosts, usernames and network identities.

### Network Tunnelling

I investigated how attackers can abuse protocols such as **DNS and ICMP** to create covert communication channels.

This demonstrated how unusual traffic patterns can provide indicators of command-and-control activity or potential data exfiltration.

**Skill developed:** Detecting and investigating suspicious network activity using packet-level evidence.

---

### NetworkMiner

I learned how **NetworkMiner** can be used for network forensic analysis of recorded traffic.

I explored how NetworkMiner can extract information from packet captures, including:

- Hosts
- IP and MAC addresses
- Operating systems
- Hostnames
- Network services
- Web server information
- Files and other extracted artefacts
- Credentials and authentication-related information
- DNS information
- Email-related information

I also investigated recorded traffic captures to identify information about hosts, services, files and network activity.

**Skill developed:** Network forensic analysis using NetworkMiner.

---

# Practical Application

The module provided hands-on experience analysing packet captures using **Wireshark** and **NetworkMiner**.

## Wireshark Investigation

I worked through multiple packet capture exercises and used Wireshark to investigate network activity at different levels.

### Network Reconnaissance

I analysed packet captures containing network scanning activity and learned to identify patterns associated with Nmap scans.

This included distinguishing between:

- TCP Connect scans
- SYN scans
- UDP scans

I used packet behaviour, TCP flags, handshake patterns and ICMP responses to identify scanning activity.

**Skills applied:**

- Packet analysis
- Nmap scan detection
- TCP analysis
- UDP analysis
- TCP flag analysis
- Wireshark filtering

### ARP Spoofing and Man-in-the-Middle Activity

I investigated ARP traffic to identify suspicious behaviour associated with ARP poisoning.

By examining MAC addresses and ARP requests, I learned how an analyst can identify signs that a device may be attempting to impersonate another host on the network.

I also examined related HTTP traffic to understand how intercepted traffic could provide additional evidence of a potential Man-in-the-Middle attack.

**Skills applied:**

- ARP analysis
- MAC address analysis
- Man-in-the-Middle detection
- HTTP traffic analysis
- Packet correlation

### Host Identification

I investigated network traffic generated by protocols including **DHCP, NetBIOS and Kerberos**.

These protocols can provide useful information for identifying hosts, usernames and network identities during an investigation.

**Skills applied:**

- DHCP analysis
- NetBIOS analysis
- Kerberos traffic analysis
- Host identification
- Network enumeration

### DNS and ICMP Tunnelling

I investigated how DNS and ICMP can be abused as covert communication channels.

This reinforced the importance of looking for abnormal traffic patterns rather than relying only on traditional indicators.

Examples of suspicious characteristics included:

- Unusual DNS query patterns
- High volumes of DNS traffic
- Suspicious or encoded data
- Unusual ICMP traffic
- Communication patterns that differ from the expected baseline

**Skills applied:**

- DNS analysis
- ICMP analysis
- Covert channel detection
- Network anomaly detection
- Potential command-and-control identification

---

## NetworkMiner Investigation

I used **NetworkMiner** to investigate recorded packet captures and identify information that could be extracted from network traffic.

The exercises involved examining hosts, network addresses, operating system information, services, web server information, files and other artefacts contained within the captures.

This demonstrated how network forensic tools can help analysts extract useful information from a PCAP without manually inspecting every individual packet.

**Skills applied:**

- Network forensics
- PCAP analysis
- Host identification
- OS fingerprinting
- Service identification
- Artefact extraction
- Network evidence analysis

---

# Key Takeaways

- Network Traffic Analysis provides visibility into communications that may not be fully represented in standard logs.
- Understanding normal network behaviour helps analysts identify anomalies.
- Wireshark allows analysts to inspect packet-level information and investigate suspicious communications.
- Wireshark statistics can help analysts understand protocols, conversations and endpoints within a capture.
- Filtering allows large packet captures to be narrowed down to relevant events.
- Different scanning techniques produce different network patterns that can be identified through packet analysis.
- ARP traffic can provide evidence of spoofing and potential Man-in-the-Middle activity.
- DHCP, NetBIOS and Kerberos traffic can help identify hosts and users within a network.
- DNS and ICMP can be abused to create covert communication channels.
- NetworkMiner can assist with extracting useful forensic information from recorded network traffic.
- Network traffic analysis can support alert validation, incident investigation and attack reconstruction.

## Skills Developed

- Network Traffic Analysis
- Wireshark
- PCAP/PCAPNG analysis
- Packet analysis
- Packet filtering
- Display filters
- Capture filters
- Protocol analysis
- Network reconnaissance detection
- Nmap scan detection
- TCP analysis
- UDP analysis
- ARP analysis
- Man-in-the-Middle detection
- DHCP analysis
- NetBIOS analysis
- Kerberos analysis
- DNS analysis
- ICMP analysis
- Network anomaly detection
- Network forensics
- NetworkMiner
- Host identification
- PCAP artefact analysis

## Reflection

This module significantly developed my understanding of how network traffic can be used as evidence during a security investigation.

The progression from basic network traffic concepts to packet-level analysis with Wireshark helped me understand how analysts can move from a broad network view into individual packets and conversations.

The practical exercises were particularly useful because they demonstrated that different types of malicious activity can produce recognisable network patterns. Investigating scanning activity, ARP poisoning, host discovery and network tunnelling helped me understand how packet-level evidence can be used to identify suspicious behaviour.

Learning NetworkMiner also showed me how dedicated network forensic tools can extract useful information from recorded traffic and support investigations without requiring every packet to be manually analysed.

Overall, this module strengthened my ability to approach network activity from a defensive perspective and provided a foundation for further development in network monitoring, threat detection and SOC investigations.
