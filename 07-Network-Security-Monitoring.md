# Network Security Monitoring

**TryHackMe SOC Level 1 — Module 7**

**Status:** ✅ Completed

## Overview

This module focused on network security monitoring and the detection of network-based attacks.

The module progressed from network security fundamentals into practical detection techniques for network discovery, data exfiltration and Man-in-the-Middle attacks. It also introduced Intrusion Detection Systems (IDS) and provided hands-on experience using Snort to detect and investigate suspicious network activity.

Through the practical exercises, I developed a better understanding of how a SOC analyst can use network logs, packet captures, IDS alerts and detection rules to identify indicators of compromise and investigate potential attacks.

---

## Topics Covered

### Network Security Essentials

I learned the fundamentals of network security and the importance of protecting and monitoring the network perimeter.

The module covered:

- Network security fundamentals
- Network perimeters
- Perimeter security controls
- Firewalls
- Web Application Firewalls (WAF)
- VPN security
- Network monitoring
- Firewall and perimeter logs
- Identifying suspicious network activity

I also learned how different types of perimeter logs can provide evidence of reconnaissance, web attacks and authentication attacks.

**Skill developed:** Understanding network perimeter security and using security logs to identify suspicious activity.

---

### Network Discovery Detection

I learned how attackers perform network discovery to identify active hosts, services and potential targets.

I explored the difference between:

- External scanning
- Internal scanning
- Horizontal scanning
- Vertical scanning

External scanning involves probing systems from outside the network, while internal scanning occurs from within the network. Horizontal scanning targets the same port across multiple hosts, whereas vertical scanning targets multiple ports on a single host.

I also learned how network logs can be analysed to identify scanning behaviour and determine whether activity originated from inside or outside an environment.

**Skill developed:** Detecting network reconnaissance and identifying scanning patterns.

---

### Data Exfiltration Detection

I learned how attackers can attempt to transfer sensitive information out of a compromised environment and how different network channels can be abused for this purpose.

The module covered several potential exfiltration methods, including:

- DNS
- FTP
- HTTP
- ICMP

I learned that exfiltration can involve stages such as discovery and collection, staging, data transfer and command-and-control coordination.

I also explored indicators that can help identify suspicious transfers, such as unusual traffic volumes, repeated requests, large uploads, suspicious external destinations and abnormal protocol behaviour.

**Skill developed:** Identifying potential data exfiltration through network traffic and logs.

---

### Man-in-the-Middle Detection

I learned how Man-in-the-Middle (MITM) attacks allow an attacker to intercept or manipulate communication between legitimate endpoints.

The practical investigation focused on three MITM techniques:

- ARP spoofing
- DNS spoofing
- SSL stripping

I learned how ARP spoofing can be used to associate an attacker's MAC address with a legitimate IP address, allowing traffic to be intercepted.

I also explored how DNS spoofing can redirect victims towards an attacker-controlled destination and how SSL stripping can downgrade communication from HTTPS to HTTP, potentially exposing sensitive information.

**Skill developed:** Identifying MITM attack indicators within network traffic.

---

### IDS Fundamentals

I learned the purpose of an **Intrusion Detection System (IDS)** and how IDS technologies can provide an additional layer of detection beyond perimeter controls such as firewalls.

I explored different IDS classifications, including:

- Host-based IDS (HIDS)
- Network-based IDS (NIDS)
- Signature-based detection
- Anomaly-based detection
- Hybrid detection

I also learned the difference between IDS and IPS technologies, with IDS primarily focused on detecting and alerting on suspicious activity while IPS can actively prevent or block detected threats.

The module introduced **Snort** as an example of an open-source network intrusion detection and prevention technology.

**Skill developed:** Understanding IDS architecture, detection methods and network-based threat detection.

---

### Snort

I learned how to use **Snort** for network traffic analysis, intrusion detection and PCAP investigation.

The practical exercises introduced several Snort capabilities, including:

- Checking the Snort installation and version
- Testing Snort configuration files
- Loading and using detection rules
- Packet logger mode
- IDS/IPS mode
- PCAP investigation
- Analysing Snort output
- Filtering network traffic
- Writing custom Snort rules

I also learned how Snort rules can be used to identify specific characteristics within network traffic and generate alerts when matching activity is detected.

**Skill developed:** Using Snort for network intrusion detection, traffic analysis and PCAP investigation.

---

# Practical Application

This module included several practical investigations that allowed me to apply network security monitoring and threat detection concepts to simulated security scenarios.

---

## Network Security Essentials — Perimeter Log Investigation

I investigated simulated network perimeter logs to identify indicators of malicious activity.

The practical exercises involved analysing:

- Firewall logs
- WAF logs
- VPN authentication logs
- IDS-related information

### Firewall Analysis

I analysed firewall logs to identify patterns associated with network reconnaissance and port scanning.

I looked for repeated connection attempts from a source IP across multiple destination ports and used filtering and command-line tools to narrow down the relevant log entries.

This demonstrated how repeated connection attempts across multiple ports can provide an indicator of automated reconnaissance.

### WAF Log Analysis

I investigated WAF logs containing both allowed and blocked web requests.

I filtered the logs to focus on blocked requests and identified patterns associated with suspicious web activity.

This reinforced the importance of filtering large log datasets to reduce noise and isolate potentially malicious activity.

### VPN Log Analysis

I analysed VPN authentication logs to identify repeated failed authentication attempts.

I used log filtering and counting techniques to identify potential brute-force behaviour and investigated the source of the suspicious authentication attempts.

The practical investigation then involved following the activity through the logs to determine whether authentication activity resulted in successful access.

### Perimeter Breach Investigation

I completed a larger investigation involving multiple perimeter log sources.

The investigation required correlating information from:

- Firewall logs
- VPN authentication logs
- IDS alerts

I followed the activity from initial reconnaissance through attempted authentication, internal access, lateral movement, command-and-control activity and potential data exfiltration.

This demonstrated how individual alerts and log entries can be correlated to reconstruct a wider attack sequence.

**Skills applied:**

- Firewall log analysis
- WAF log analysis
- VPN log analysis
- IDS alert analysis
- Log filtering
- Command-line investigation
- Reconnaissance detection
- Brute-force detection
- Attack chain reconstruction
- Log correlation

The walkthrough I used demonstrates this progression through firewall reconnaissance, VPN authentication, SMB activity, C2 beaconing and exfiltration indicators. :contentReference[oaicite:1]{index=1}

---

## Network Discovery Detection

I completed practical exercises investigating network discovery activity using recorded log data.

The investigation involved identifying network scanning activity and determining whether the traffic represented internal or external scanning.

I also analysed scanning patterns to distinguish between:

### Horizontal Scanning

Scanning the same destination port across multiple hosts.

### Vertical Scanning

Scanning multiple ports on a single host.

I used log analysis techniques to identify the source and destination addresses involved in scanning activity and determine the nature of the reconnaissance.

**Skills applied:**

- Network reconnaissance detection
- Log analysis
- Internal vs external scanning
- Horizontal scanning detection
- Vertical scanning detection
- Source/destination IP analysis
- Command-line log analysis

The practical walkthrough specifically demonstrates identifying internal scanning through source/destination IP analysis and differentiating horizontal and vertical scanning behaviour. :contentReference[oaicite:2]{index=2}

---

## Data Exfiltration Detection

I investigated different techniques that attackers can use to transfer data out of a compromised environment.

### DNS Exfiltration

I investigated how DNS queries can be abused to transfer data by encoding information within DNS requests.

I learned to look for indicators such as:

- Unusually long DNS queries
- High volumes of DNS requests
- Repeated queries to a suspicious domain
- DNS traffic containing encoded or unusual data
- Requests without corresponding responses

I also explored how Splunk can be used to identify abnormal DNS query patterns and correlate source IP addresses and queried domains.

### FTP Exfiltration

I investigated FTP traffic for indicators associated with data transfer.

Relevant indicators included:

- FTP authentication activity
- `USER` and `PASS` commands
- File upload commands
- Large or repeated transfers
- Suspicious external destinations
- Sensitive file types

I also explored how packet captures can be examined using Wireshark and TCP stream analysis.

### HTTP Exfiltration

I investigated how HTTP can be abused to transfer data while blending into normal web traffic.

The investigation focused on suspicious HTTP POST requests, unusual upload volumes and large request payloads.

I also explored how analysts can use packet captures and HTTP streams to investigate the content being transferred.

### ICMP Exfiltration

I investigated how ICMP traffic can be abused as a covert communication channel.

This demonstrated how attackers can potentially hide encoded or encrypted information within ICMP traffic.

**Skills applied:**

- DNS analysis
- FTP analysis
- HTTP analysis
- ICMP analysis
- Splunk investigation
- Wireshark analysis
- Data exfiltration detection
- Network anomaly detection
- Packet stream analysis
- Suspicious traffic identification

The practical material I used covers DNS, FTP, HTTP and ICMP exfiltration, including Splunk and Wireshark-based investigation techniques. :contentReference[oaicite:3]{index=3}

---

## Man-in-the-Middle Detection

I completed a practical investigation into a simulated MITM attack using packet captures and network evidence.

The investigation covered three stages of the attack.

### ARP Spoofing

I analysed ARP traffic to identify evidence of ARP spoofing.

I investigated:

- ARP replies
- MAC addresses
- IP-to-MAC mappings
- Repeated ARP responses
- Multiple MAC addresses claiming the same IP address

This demonstrated how an attacker can impersonate a legitimate network device, such as a gateway, to intercept traffic.

### DNS Spoofing

I investigated DNS responses to identify evidence of DNS spoofing.

I compared DNS requests and responses and looked for unexpected responses associated with the domain being investigated.

This demonstrated how an attacker positioned within the network can manipulate DNS resolution and redirect victims to an attacker-controlled destination.

### SSL Stripping

I investigated a simulated SSL stripping attack where HTTPS communication was downgraded to HTTP.

I examined the traffic to identify indicators such as:

- HTTP communication following an HTTPS request
- Redirect behaviour
- Modified responses
- Plaintext HTTP requests
- Sensitive information appearing within unencrypted traffic

This demonstrated how SSL stripping can allow an attacker positioned between a victim and a legitimate service to capture information that would otherwise be protected by TLS.

**Skills applied:**

- ARP analysis
- MAC address analysis
- DNS analysis
- DNS spoofing detection
- SSL/TLS analysis
- HTTP analysis
- Packet capture investigation
- MITM detection
- Wireshark filtering

The practical scenario specifically links ARP spoofing, DNS spoofing and SSL stripping as a chained MITM investigation. :contentReference[oaicite:4]{index=4}

---

# IDS & Snort Practical Investigation

## IDS Investigation

I investigated the fundamentals of Intrusion Detection Systems and how they can be used to detect malicious network activity.

I learned how IDS solutions can be classified based on where they operate and how they detect threats.

I also explored how signature-based detection can identify known patterns of malicious traffic, while anomaly-based detection can identify deviations from expected behaviour.

The practical exercises introduced Snort as a network-based detection technology and demonstrated how detection rules can be used to identify suspicious traffic.

**Skills applied:**

- IDS concepts
- HIDS vs NIDS
- Signature-based detection
- Anomaly-based detection
- Hybrid detection
- Network threat detection
- Snort fundamentals

The IDS material specifically covers IDS types, Snort, default and custom rules and practical PCAP investigation. :contentReference[oaicite:5]{index=5}

---

## Snort Practical

I completed hands-on exercises using Snort to investigate network traffic and PCAP files.

### Snort Configuration

I used Snort commands to:

- Check the installed version
- Test configuration files
- Identify loaded rules
- Validate Snort configurations

### Packet Logger Mode

I used Snort in packet logging mode to capture and inspect network traffic.

This involved generating traffic within the lab environment and analysing the resulting Snort logs.

I also investigated packet-level information such as ports and packet fields.

### IDS/IPS Mode

I used Snort in IDS mode to monitor traffic and generate alerts based on its configured rules.

This demonstrated how Snort can identify specific network activity and provide alerts for potentially suspicious traffic.

### PCAP Investigation

I used Snort to investigate recorded PCAP files.

This involved:

- Loading PCAP files into Snort
- Applying Snort configuration files
- Reviewing generated alerts
- Examining traffic statistics
- Investigating packet information
- Comparing results produced by different configurations

### Custom Snort Rules

I also explored the structure of Snort rules and created a custom rule to identify a specific characteristic within network traffic.

This demonstrated how analysts can move beyond default detection rules and create rules tailored to a particular investigation.

**Skills applied:**

- Snort configuration
- Snort CLI
- Packet logging
- IDS monitoring
- PCAP investigation
- Alert analysis
- Rule analysis
- Custom Snort rules
- Network traffic detection

The practical Snort walkthrough covers packet logger mode, IDS/IPS mode, PCAP investigation and custom rule creation, including analysing Snort output against supplied captures. :contentReference[oaicite:6]{index=6}

---

# Key Takeaways

- Network security monitoring provides visibility into activity occurring across an environment.
- Firewall, WAF, VPN and IDS logs can provide valuable evidence during security investigations.
- Repeated connection attempts across multiple ports can indicate network reconnaissance.
- Horizontal and vertical scanning produce different patterns that can be identified through log analysis.
- Data exfiltration can occur through legitimate protocols such as DNS, HTTP, FTP and ICMP.
- Large transfers, unusual request patterns and suspicious destinations can provide indicators of potential exfiltration.
- MITM attacks can involve multiple techniques, including ARP spoofing, DNS spoofing and SSL stripping.
- IDS technologies provide an additional detection layer for identifying suspicious network activity.
- Snort can be used for packet logging, IDS monitoring, PCAP investigation and custom rule-based detection.
- Correlating multiple sources of network evidence can help analysts reconstruct an attack rather than investigating individual alerts in isolation.
- Effective network monitoring requires understanding both normal traffic behaviour and indicators of malicious activity.

---

# Skills Developed

- Network Security Monitoring
- Network Perimeter Monitoring
- Firewall Log Analysis
- WAF Log Analysis
- VPN Log Analysis
- IDS Alert Analysis
- Network Reconnaissance Detection
- Horizontal Scanning Detection
- Vertical Scanning Detection
- Data Exfiltration Detection
- DNS Analysis
- HTTP Analysis
- FTP Analysis
- ICMP Analysis
- ARP Analysis
- DNS Spoofing Detection
- SSL/TLS Analysis
- Man-in-the-Middle Detection
- Intrusion Detection Systems
- Snort
- PCAP Investigation
- Packet Analysis
- Log Filtering
- Command-Line Investigation
- Threat Detection
- Attack Chain Reconstruction
- Security Monitoring

---

# Reflection

This module significantly developed my understanding of how network security monitoring supports a SOC analyst during the detection and investigation of security incidents.

The practical exercises helped me move beyond understanding individual attack techniques and showed me how those techniques can leave identifiable footprints within logs and network traffic.

The Network Discovery and Network Security Essentials exercises helped me understand how reconnaissance and authentication attacks can be identified through patterns within security logs. I also gained experience correlating different sources of evidence to follow an attack from initial reconnaissance through later stages of compromise.

The Data Exfiltration Detection exercises demonstrated how legitimate network protocols can be abused to move information out of an environment. This reinforced the importance of analysing traffic behaviour rather than assuming that a protocol is safe simply because it is commonly used.

The Man-in-the-Middle investigation was particularly useful because it demonstrated how multiple techniques can form part of the same attack. Analysing ARP spoofing, DNS spoofing and SSL stripping helped me understand how network evidence can be used to identify interception and manipulation of communications.

Finally, working with Snort gave me practical exposure to network-based intrusion detection. Using Snort for packet logging, IDS monitoring, PCAP investigation and custom rules helped me understand how detection technologies can turn suspicious network behaviour into actionable alerts.

Overall, this module strengthened my ability to approach network activity from a defensive perspective and improved my understanding of how a SOC analyst can use logs, packet captures, detection rules and multiple sources of evidence to identify and investigate threats.
