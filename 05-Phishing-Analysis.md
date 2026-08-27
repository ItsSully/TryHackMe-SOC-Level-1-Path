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

I completed the **Phishing Unfolding** scenario in the TryHackMe SOC Simulator, investigating a simulated phishing incident as it developed within a corporate environment.

The scenario provided practical experience with the SOC investigation workflow, including monitoring alerts, investigating suspicious activity using **Splunk**, analysing supporting log data and documenting findings in case reports.

### Investigation

The investigation began with a suspicious phishing email containing a malicious ZIP attachment. I followed the related alerts and investigated the activity occurring on the affected endpoint.

Key areas of the investigation included:

- Analysing the suspicious phishing email and attachment
- Investigating the extracted `.lnk` file
- Analysing suspicious PowerShell activity
- Investigating suspicious parent-child process relationships
- Reviewing Sysmon and endpoint logs in Splunk
- Investigating suspicious DNS activity
- Identifying indicators associated with potential data exfiltration
- Connecting multiple alerts to understand the wider attack chain
- Documenting findings through SOC case reporting

### SIEM Investigation

I used **Splunk** to investigate alerts and search relevant logs associated with the affected host.

This involved moving from individual alerts into the underlying log data to establish whether suspicious activity was connected to the original phishing event.

A key part of the investigation was analysing suspicious process activity and DNS queries, which provided additional evidence of malicious behaviour.

### Attack Chain Analysis

I applied the **Cyber Kill Chain** to help understand the incident as a sequence of related stages rather than treating each alert independently.

This helped connect the initial phishing email to subsequent execution, reconnaissance, data staging and attempted exfiltration activity.

### Case Reporting

The scenario also required documenting investigation findings through SOC case reports.

This reinforced the importance of clearly recording:

- What happened
- Which systems and users were affected
- Evidence supporting the investigation
- Why an alert should be classified or escalated
- Recommended remediation actions

### Key Takeaways

The scenario demonstrated how a SOC analyst can move from an initial phishing alert to a wider investigation by correlating multiple sources of evidence.

It reinforced the importance of:

- Alert triage
- SIEM investigation
- Log analysis
- Process analysis
- DNS analysis
- Threat intelligence
- Attack chain reconstruction
- Clear incident documentation

**Skills applied:**

- SIEM alert triage
- Splunk
- Log analysis
- Phishing investigation
- Endpoint analysis
- PowerShell analysis
- DNS analysis
- Threat intelligence
- Cyber Kill Chain
- Attack chain reconstruction
- Incident documentation
- Case reporting

### Reflection

The Phishing Unfolding scenario helped me understand how individual security alerts can form part of a much larger attack chain.

It was particularly useful for developing my ability to investigate an alert using supporting log data, identify relationships between suspicious events and document findings in a structured SOC case report.
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
