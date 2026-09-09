# Web Security Monitoring

**TryHackMe SOC Level 1 — Module 8**

**Status:** ✅ Completed

## Overview

This module focused on understanding how web applications and services work, how they can be attacked, and how SOC analysts can detect and investigate malicious web activity.

The module progressed from the fundamentals of web security into practical detection scenarios involving web attacks, web shells and web-based denial-of-service attacks.

I developed an understanding of web infrastructure, common security controls, web server logging, attack detection techniques, WAFs, SIEM-based investigation and the indicators that can help identify malicious activity against web services.

---

# Topics Covered

## Web Security Essentials

I learned the fundamentals of web security and how the different components of a web service interact.

### Web Infrastructure

I learned that a web service can be broken down into three main components:

- Web Application
- Web Server
- Host Machine

The web application contains the code and resources that provide the functionality of the website.

The web server receives and processes requests before returning responses to users.

The host machine provides the underlying operating system and environment in which the web server and application run.

Understanding these components helped me understand where different security controls can be applied.

### Web Requests and Logging

I learned how browsers communicate with web servers through HTTP requests and responses.

I also learned about common HTTP request methods such as:

- `GET` — used to retrieve resources
- `POST` — used to submit information to a server

Web server access logs can provide valuable information during security investigations, including:

- Client IP address
- Timestamp
- Requested resource
- HTTP method
- Response status
- User-Agent
- Referrer
- Response size

These logs can allow analysts to reconstruct user activity and identify suspicious patterns.

### Web Security Controls

I learned how security controls can be applied across the application, web server and host machine.

Application-level protections include:

- Secure coding
- Input validation and sanitisation
- Access control
- Strong authentication

Web server protections include:

- Access logging
- Web Application Firewalls (WAFs)
- Content Delivery Networks (CDNs)

Host-level protections include:

- Least privilege
- System hardening
- Antivirus
- Patch management

I also learned the importance of defence in depth, where multiple security controls are used together rather than relying on a single defensive mechanism.

### CDN and WAF Security

I learned how Content Delivery Networks can provide both performance and security benefits.

CDNs can:

- Mask the origin server IP
- Reduce direct exposure of the origin server
- Absorb large amounts of traffic during DDoS attacks
- Enforce HTTPS/TLS
- Integrate with WAFs

I also learned how WAFs inspect HTTP requests and can identify and block potentially malicious traffic.

Different WAF deployment models include:

- Cloud-based / reverse proxy
- Host-based
- Network-based

Common WAF detection techniques include:

- Signature-based detection
- Heuristic-based detection
- Behavioural and anomaly detection
- IP reputation and location filtering

### Practical Application — Secure-A-Site

I completed the practical Secure-A-Site scenario, applying the security principles covered throughout the room.

The scenario required securing three layers of a web service:

- Web Application
- Web Server
- Host Machine

This allowed me to apply security controls in a practical environment rather than only learning them theoretically.

**Skills applied:**

- Web security hardening
- Security control selection
- Application security
- Web server security
- Host security
- WAF awareness
- CDN security
- Patch management
- Defence in depth

The practical reinforced how security needs to be considered across the entire web infrastructure rather than focusing on only the application itself.

---

# Detecting Web Attacks

I learned how SOC analysts can identify common web attacks using logs, network traffic and security controls.

The room covered both client-side and server-side attacks, as well as network-based detection and WAF monitoring. :contentReference[oaicite:1]{index=1}

## Client-Side Attacks

I learned about attacks that target the user or their browser rather than directly attacking the server.

One of the main examples was Cross-Site Scripting (XSS).

I learned that XSS can involve malicious content being executed within a user's browser and that understanding the difference between client-side and server-side attacks is important when investigating web incidents.

## Server-Side Attack Detection

I investigated web server access logs to identify indicators of malicious activity.

The practical investigation involved identifying:

- Automated directory fuzzing
- Brute-force activity
- Suspicious User-Agent strings
- SQL injection attempts
- Suspicious requests to web application endpoints

I learned how attacker tooling can leave identifiable patterns in web logs.

For example, directory fuzzing activity could be associated with the User-Agent:

`FFUF v2.1.0`

I also investigated brute-force activity against a login endpoint and analysed a SQL injection payload found within the logs.

This demonstrated how seemingly individual web requests can provide evidence of an ongoing attack when viewed together.

## Network-Based Detection

I also analysed network traffic using a packet capture.

This involved using Wireshark to investigate HTTP traffic and identify evidence of malicious activity.

I learned how filtering traffic and following HTTP streams can help reconstruct attacker activity.

The investigation included:

- Identifying successful brute-force authentication
- Investigating HTTP responses
- Identifying SQL injection activity
- Following network streams
- Examining User-Agent information
- Recovering evidence from network traffic

This reinforced the importance of correlating network traffic with other sources of evidence during an investigation.

## Web Application Firewall

I learned how WAFs can be used to detect and block malicious web requests.

I investigated how WAF rules can be created to identify suspicious traffic based on characteristics such as User-Agent values.

I also learned that WAFs inspect web requests and can apply rules to allow, block or otherwise respond to suspicious traffic.

**Skills applied:**

- Web log analysis
- HTTP investigation
- Attack detection
- SQL injection detection
- Brute-force detection
- Network traffic analysis
- Wireshark
- User-Agent analysis
- WAF rule creation
- Incident investigation

The practical exercises demonstrated how a SOC analyst can move from individual suspicious requests to identifying a wider attack pattern.

---

# Detecting Web Shells

I learned how web shells can be used by attackers to maintain remote access to a compromised web server.

Web shells are particularly important from a SOC perspective because they can provide attackers with a way to execute commands remotely after gaining access to a web server. TryHackMe specifically focuses on detecting web-shell activity through log, file-system and network analysis. :contentReference[oaicite:2]{index=2}

## Web Shell Detection

I learned that detecting web shells requires analysing multiple sources of evidence rather than relying on a single indicator.

The investigation covered:

- Web server logs
- File-system activity
- Network traffic
- HTTP requests
- Suspicious files
- Command execution
- Attacker interaction with the web shell

I learned that unusual requests to web-accessible files can be an important indicator of web-shell activity.

I also developed an understanding of how attackers can upload or interact with malicious server-side files and subsequently use them to execute commands.

## Web Shell Investigation

The practical work involved investigating suspicious web-shell activity and examining the evidence left behind by the attacker.

I analysed the relationship between:

- Suspicious web requests
- Web-accessible files
- Command execution
- Network communication
- Server-side activity

This helped demonstrate how a SOC analyst can move from an initial suspicious web request to determining whether a server has potentially been compromised.

## Detection Approach

A key takeaway from this room was that web-shell detection should combine multiple sources of evidence.

For example, a suspicious request becomes more significant when it can be correlated with:

- A recently created or modified server-side file
- Unusual HTTP requests
- Command execution
- Unexpected network activity
- Other indicators of compromise

**Skills applied:**

- Web shell detection
- Web log analysis
- File-system analysis
- Network analysis
- HTTP investigation
- Command execution analysis
- Indicator identification
- Incident investigation

This practical helped me understand how web shells can fit into a larger attack chain and why correlating different evidence sources is important during an investigation.

---

# Detecting Web DDoS

I learned how Denial-of-Service (DoS) and Distributed Denial-of-Service (DDoS) attacks can target web services by overwhelming them with traffic or resource-intensive requests.

The room focused on detecting application-layer DoS/DDoS attacks through log analysis and SIEM investigation, as well as understanding defensive techniques. :contentReference[oaicite:3]{index=3}

## DoS and DDoS Attacks

I learned the difference between DoS and DDoS attacks.

A DoS attack attempts to disrupt the availability of a service, while a DDoS attack can use a network of compromised devices, known as a botnet, to generate traffic from multiple sources.

I also learned about different application-layer techniques, including:

- HTTP floods
- Slowloris
- Cache bypass
- Oversized queries
- Login or form abuse
- Input validation abuse

## Attack Motives

I learned that DDoS attacks can be carried out for different reasons, including:

- Financial loss
- Extortion
- Hacktivism
- Distraction
- Competition
- Denial of wallet
- Reputational damage

Understanding attacker motivation can provide useful context during an investigation.

## Log-Based Detection

I analysed web logs to identify indicators of a possible DoS/DDoS attack.

Important indicators included:

- Unusually high request rates
- Repeated requests to the same endpoint
- Unusual User-Agent values
- Geographic anomalies
- Bursts of requests within a short period
- Large numbers of `503 Service Unavailable` responses
- Resource-intensive requests

I learned that endpoints such as:

- `/login`
- `/search`
- `/api`
- `/register`
- `/contact`
- `/cart`
- `/checkout`

can become attractive targets because they may require additional server-side processing.

## SIEM Investigation

I used SIEM-based analysis to investigate traffic patterns associated with a DDoS scenario.

This involved analysing fields such as:

- URI paths
- Client IP addresses
- User-Agent values
- HTTP status codes
- Request counts
- Request timestamps

I learned how filtering and statistical analysis can make it easier to identify patterns within large volumes of web logs.

I also used time-based analysis to visualise request activity and identify traffic spikes.

This demonstrated how SIEM platforms can help SOC analysts move from large volumes of raw log data towards meaningful indicators of an attack.

## DDoS Defence

I learned about several defensive mechanisms that can reduce the impact of web-based DDoS attacks.

These included:

- Secure application design
- Rate limiting
- CAPTCHA challenges
- CDN protection
- Load balancing
- WAF rules
- Traffic filtering

CDNs can distribute traffic across multiple servers and reduce the amount of traffic reaching the origin server.

WAFs can also apply rules to suspicious traffic and help identify or block malicious requests.

**Skills applied:**

- DDoS detection
- Web log analysis
- SIEM investigation
- Traffic analysis
- User-Agent analysis
- IP address investigation
- HTTP status code analysis
- Time-series analysis
- WAF awareness
- CDN security
- DDoS mitigation

The practical investigation demonstrated how a SOC analyst can identify abnormal traffic patterns and determine whether they are consistent with a denial-of-service attack.

---

# Key Takeaways

- Web applications are an important attack surface because they are publicly accessible and often interact with sensitive systems and data.
- Web security requires protection across the application, web server and host machine.
- Web server access logs provide valuable evidence for reconstructing user and attacker activity.
- HTTP methods, status codes, User-Agent values and requested resources can all provide useful investigation indicators.
- Client-side and server-side attacks require different detection approaches.
- Network traffic can provide additional evidence that may not be visible from web logs alone.
- WAFs can inspect HTTP requests and apply rules to detect or block malicious traffic.
- Web shells can provide attackers with remote access to compromised web servers and require investigation across logs, files and network activity.
- DDoS attacks can be detected through abnormal request rates, traffic patterns, User-Agent values and HTTP response codes.
- SIEM platforms can help analysts filter and correlate large volumes of web security data.
- CDN and WAF technologies can provide additional layers of protection against web-based attacks.
- Effective web security relies on defence in depth rather than a single security control.

---

# Skills Developed

- Web security monitoring
- Web application security
- Web server security
- HTTP analysis
- Web log analysis
- Client-side attack detection
- Server-side attack detection
- SQL injection detection
- Brute-force detection
- Web shell detection
- File-system analysis
- Network traffic analysis
- Wireshark
- SIEM investigation
- DDoS detection
- User-Agent analysis
- IP address investigation
- WAF analysis
- CDN security
- Incident investigation
- Threat detection
- Security monitoring
- Incident documentation

---

# Reflection

This module significantly developed my understanding of how web-based attacks can be detected from a SOC perspective.

The first room helped me understand the security fundamentals behind web applications and the different layers that need to be protected. The practical Secure-A-Site scenario was particularly useful because it allowed me to apply these concepts across the web application, web server and host machine rather than only learning the theory.

The Detecting Web Attacks room then allowed me to apply these concepts to realistic attack activity. I investigated web logs and network traffic to identify suspicious behaviour such as directory fuzzing, brute-force activity and SQL injection. Using both log analysis and Wireshark helped me understand why multiple sources of evidence are important during an investigation.

The Detecting Web Shells room further developed my understanding of how attackers can maintain access to compromised web servers and how SOC analysts can detect this activity through logs, file-system evidence and network activity.

Finally, the Detecting Web DDoS room helped me understand how abnormal traffic patterns can be identified using web logs and SIEM analysis. It reinforced the importance of looking at request rates, targeted resources, IP addresses, User-Agent values and HTTP response codes when investigating availability-related attacks.

Overall, this module helped me understand how a SOC analyst can monitor web infrastructure, identify suspicious activity, investigate multiple sources of evidence and determine whether individual events form part of a wider attack.

It reinforced the importance of **log analysis, network visibility, correlation and understanding normal behaviour** when detecting threats against web services.
