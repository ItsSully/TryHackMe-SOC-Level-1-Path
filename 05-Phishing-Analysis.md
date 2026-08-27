# Phishing Analysis

**TryHackMe SOC Level 1 — Module 5**

**Status:** ✅ Completed

## Overview

This module focused on analysing and defending against phishing attacks, progressing from the fundamentals of email analysis to investigating phishing campaigns and a simulated phishing incident within a corporate environment.

I developed an understanding of email structure, phishing indicators, investigation tools, defensive measures and practical phishing analysis techniques.

---

## Topics Covered

### Phishing Analysis Fundamentals

I learned the fundamentals of email communication and how to analyse email headers and bodies when investigating potentially malicious messages.

Key areas included:

- Email addresses and domains
- Email headers
- Email bodies
- Email source code
- Attachments
- Embedded links
- Base64-encoded content
- Common phishing characteristics

I also learned how attackers can use techniques such as sender impersonation, urgent language, malicious attachments, suspicious hyperlinks and misleading content to make phishing emails appear legitimate.

**Skill developed:** Email analysis and identification of common phishing indicators.

### Phishing Emails in Action

I examined examples of phishing emails to identify indicators and techniques used by attackers.

This included analysing suspicious email content and recognising characteristics such as social engineering, manipulated links, tracking elements, credential harvesting and malicious attachments.

**Skill developed:** Phishing email identification and social engineering analysis.

### Phishing Analysis Tools

I learned about tools and techniques that can support phishing investigations, including the analysis of:

- Email headers
- Email bodies
- IP addresses
- URLs
- Attachments
- File reputation
- Malware

I also explored how analysts can use reputation and analysis tools to gather additional information about suspicious email artefacts.

**Skill developed:** Using security tools and external intelligence to support phishing investigations.

### Phishing Prevention

I learned about defensive measures that can reduce the risk posed by phishing attacks.

This reinforced the importance of combining technical controls with user awareness and secure email practices.

**Skill developed:** Understanding phishing prevention and defensive controls.

---

# Practical Application

The module included several practical exercises that allowed me to apply phishing analysis techniques to realistic scenarios.

## The Greenholt Phish

I completed **The Greenholt Phish** challenge, where I investigated a suspicious email that had been escalated to the SOC for analysis.

The investigation involved examining the email and identifying information such as:

- Sender and recipient details
- Email headers
- Originating IP address
- SPF and DMARC information
- Attachment details
- File hash
- File type

This required analysing the email beyond its visible contents and using technical information from the message to determine whether it was legitimate.

**Skills applied:**

- Email header analysis
- Email metadata analysis
- SPF and DMARC awareness
- IP investigation
- Attachment analysis
- File hashing
- Phishing detection

The challenge reinforced the importance of analysing multiple indicators rather than relying solely on the appearance or content of an email.

---

## Snapped Phish-ing Line

I completed the **Snapped Phish-ing Line** challenge, which involved investigating a phishing campaign affecting multiple employees.

The investigation involved analysing phishing emails and suspicious URLs and gathering information about the phishing infrastructure.

The scenario provided practical experience with:

- Analysing multiple phishing emails
- Investigating suspicious URLs
- Identifying phishing infrastructure
- Using command-line tools to examine email artefacts
- Gathering information about the phishing campaign

**Skills applied:**

- Phishing campaign analysis
- Email investigation
- URL analysis
- Command-line investigation
- Threat intelligence
- Identifying phishing infrastructure

The challenge demonstrated how individual phishing emails can be connected to a wider campaign rather than treated as isolated incidents.
---

## Phishing Unfolding — SOC Simulator

I completed the **Phishing Unfolding** SOC Simulator scenario, investigating a simulated phishing attack as it progressed through a corporate environment.

The scenario involved monitoring real-time alerts, identifying suspicious activity and documenting the attack chain.

### Investigation

The investigation began with a suspicious phishing email containing a malicious ZIP attachment.

I analysed the subsequent activity and followed the attack through multiple stages, including:

1. **Phishing Delivery** — a malicious attachment was delivered through email.
2. **Execution** — the attachment resulted in a malicious `.lnk` file being executed.
3. **PowerShell Activity** — PowerShell was used to execute malicious commands and establish a foothold.
4. **Reconnaissance** — the attacker gathered information about the compromised system and environment.
5. **Active Directory Reconnaissance** — PowerView was used to enumerate information about the environment.
6. **Data Access & Staging** — a network share containing financial records was accessed and data was copied to a local staging directory.
7. **Defence Evasion** — the network share was disconnected after the data was staged.
8. **Data Exfiltration** — the staged data was exfiltrated through DNS tunnelling using encoded data within DNS queries.
9. **Persistence / Continued Access** — further PowerShell and reverse-shell activity indicated attempts to maintain access.

The investigation demonstrated how individual SIEM alerts can be correlated to reconstruct a wider attack chain. 

### Tools & Techniques

During the scenario, I worked with:

- **Splunk SIEM**
- SIEM alert triage
- Sysmon logs
- PowerShell analysis
- File and process analysis
- Network activity analysis
- Threat intelligence
- DNS analysis
- Incident documentation
- Cyber Kill Chain analysis

The scenario required analysing alerts and logs to identify the progression of the attack and understand the relationship between different events.

### Key Findings

Several important indicators helped demonstrate the progression of the attack:

- Malicious phishing attachment
- `.lnk` file execution
- Suspicious PowerShell activity
- PowerView activity
- Network share access
- Robocopy-based data staging
- Network share removal
- DNS tunnelling
- Encoded data within DNS queries

The combination of these indicators provided evidence of a wider compromise rather than isolated suspicious events. 

### Attack Chain Analysis

I also applied the **Cyber Kill Chain** to understand the incident as a sequence of stages rather than individual alerts.

This helped connect the phishing email to execution, reconnaissance, command and control, data staging and eventual exfiltration.

### Incident Response

The scenario also introduced the importance of considering appropriate remediation following an incident.

Potential response actions included:

- Isolating the compromised host
- Blocking malicious infrastructure
- Resetting compromised credentials
- Removing persistence mechanisms
- Performing malware/antivirus scanning
- Applying security patches
- Increasing monitoring
- Improving email security controls
- Providing phishing awareness training

The scenario demonstrated that investigation does not end when malicious activity is identified; analysts also need to consider containment, eradication and prevention of recurrence. 

**Skills applied:**

- SIEM alert triage
- Log analysis
- Phishing investigation
- Threat intelligence
- Endpoint analysis
- PowerShell analysis
- Network analysis
- DNS tunnelling detection
- Attack chain reconstruction
- Incident response
- Cyber Kill Chain analysis
- Security documentation

---

# Key Takeaways

- Phishing investigations require analysis of both the visible email and underlying technical artefacts.
- Email headers can provide valuable information about the origin and legitimacy of a message.
- Attachments, URLs, domains, IP addresses and hashes can all provide useful indicators during an investigation.
- Phishing attacks can be part of a larger attack chain rather than isolated events.
- SIEM platforms can help analysts correlate multiple events and reconstruct an incident.
- Legitimate tools such as PowerShell, Robocopy and nslookup can be abused by attackers, making process context important during investigations.
- DNS can be abused as a covert channel for data exfiltration.
- Effective phishing defence combines technical controls, monitoring, user awareness and incident response.
- Analysts need to communicate findings clearly and document evidence throughout an investigation.

## Skills Developed

- Phishing analysis
- Email header analysis
- Email metadata investigation
- URL and IP investigation
- Threat intelligence
- Attachment analysis
- SIEM alert triage
- Splunk
- Log analysis
- Sysmon analysis
- PowerShell analysis
- Network analysis
- DNS analysis
- Incident response
- Cyber Kill Chain
- Attack chain reconstruction
- Security documentation

## Reflection

This module significantly developed my understanding of phishing from both an analytical and defensive perspective.

The earlier lessons helped me understand how to identify phishing indicators and investigate email artefacts, while the practical challenges allowed me to apply these techniques to individual phishing emails and campaigns.

The **Phishing Unfolding** scenario was particularly valuable because it demonstrated how a SOC analyst can move from an initial phishing alert to reconstructing an entire attack chain using SIEM alerts and endpoint/network evidence.

It reinforced the importance of **correlating individual events, understanding attacker behaviour and documenting evidence** when investigating a security incident.
