# SOC Level 1 Capstone Challenges

**TryHackMe SOC Level 1 — Module 14**  
**Status:** ✅ Completed

## Overview

This module brought together many of the skills developed throughout the SOC Level 1 pathway through practical Digital Forensics and Incident Response (DFIR) investigations.

The module focused on investigating complete attack scenarios rather than individual techniques. I analysed phishing attacks, endpoint activity, network traffic, malicious files and attacker behaviour to reconstruct incidents and understand how different stages of an attack were connected.

The investigations required me to combine evidence from multiple sources and use a structured approach to identify the initial access method, attacker activity, progression and objectives.

---

# Topics Covered

## Tempest

Tempest was a full incident investigation involving a compromised Windows machine.

The objective was to analyse endpoint and network artefacts and reconstruct the attack from the initial compromise through to the attacker's final objective.

### Key Areas

- Digital forensics
- Incident response
- Windows Event Logs
- Sysmon
- Network traffic analysis
- Wireshark
- Brim
- Initial Access
- Discovery
- Privilege Escalation
- Actions on Objective
- Attack-chain reconstruction

### Log Analysis

I began the investigation by analysing the available endpoint and network logs.

This involved examining Windows telemetry and identifying events that could provide information about:

- User activity
- Process execution
- Authentication
- Network connections
- Suspicious files
- Attacker behaviour

I used timestamps and related indicators to establish a timeline of activity.

### Initial Access — Malicious Document

The investigation identified a malicious document as part of the initial compromise.

I analysed the available evidence to determine how the document was delivered and how it contributed to the execution of the attack.

This required correlating endpoint activity with network evidence to understand what happened after the document was opened.

### Stage 2 Execution

I investigated the subsequent execution activity and traced the processes generated after the initial compromise.

Process relationships and command execution were analysed to understand how the attacker progressed from the initial document to additional activity on the system.

### Network Traffic Analysis

I analysed captured network traffic using tools such as Wireshark and Brim.

The investigation focused on identifying suspicious connections and understanding how network activity related to the endpoint events observed earlier.

### Internal Reconnaissance

After gaining access, the attacker performed discovery activity against the compromised environment.

I investigated the available evidence to identify reconnaissance activity and understand what information the attacker was attempting to gather.

### Privilege Escalation

I investigated activity associated with the attacker attempting to obtain higher privileges on the compromised system.

This involved correlating process and endpoint evidence to determine how the attacker progressed within the environment.

### Actions on Objective

The final stage of the investigation focused on identifying what the attacker ultimately achieved after compromising the machine.

By combining endpoint and network evidence, I reconstructed the attack chain from initial access through to the final objective.

### Skills Applied

- Digital forensics
- Incident investigation
- Windows Event Log analysis
- Sysmon analysis
- Network traffic analysis
- Wireshark
- Brim
- Timeline reconstruction
- Attack-chain analysis
- Initial Access detection
- Privilege Escalation investigation

---

# Boogeyman 1

Boogeyman 1 was a practical investigation into a threat group and its Tactics, Techniques and Procedures (TTPs).

The investigation followed the attack from initial access through to the attacker's objective using phishing email, endpoint and network artefacts.

### Key Areas

- Phishing investigation
- Email analysis
- Endpoint forensics
- PowerShell analysis
- LNK files
- Windows logs
- Network traffic
- Wireshark
- Tshark
- Attack-chain reconstruction

### Email Analysis

I began by investigating a phishing email provided as part of the investigation.

I examined the email and its headers to identify information about the sender, delivery and potentially malicious content.

The email was used as the starting point for understanding how the attacker gained initial access.

### Endpoint Investigation

I then investigated the victim's workstation using the available PowerShell logs and endpoint artefacts.

This allowed me to identify activity that occurred after the malicious email was interacted with.

I analysed:

- PowerShell activity
- Processes
- Command execution
- Files
- Parent-child relationships
- Suspicious execution

### Malicious LNK Investigation

The investigation involved a malicious Windows shortcut file.

I analysed the LNK artefact to understand how it was being used to initiate malicious activity and connect the phishing stage to the subsequent endpoint activity.

### Network Traffic Analysis

I analysed the provided packet capture using Wireshark and Tshark.

This allowed me to investigate network communications generated during the attack and identify connections associated with the malicious activity.

### Attack-Chain Reconstruction

I correlated the email, endpoint and network evidence to reconstruct the attack:

**Phishing Email → Malicious File → Endpoint Execution → Network Activity → Attacker Objective**

This demonstrated how different forensic artefacts can be combined to understand an incident from beginning to end.

### Skills Applied

- Phishing analysis
- Email header analysis
- LNK file analysis
- PowerShell log analysis
- Windows endpoint investigation
- Wireshark
- Tshark
- Network traffic analysis
- IOC identification
- Attack-chain reconstruction

---

# Boogeyman 2

Boogeyman 2 continued the investigation into the threat group using a new attack scenario.

This investigation introduced additional forensic evidence, including a memory dump from the victim's workstation.

### Key Areas

- Spear phishing
- Malicious Office documents
- VBA macros
- Memory forensics
- Volatility
- Olevba
- Process investigation
- Endpoint investigation
- Threat actor TTPs

### Spear Phishing Investigation

The investigation began with a targeted phishing email.

I analysed the provided email and the associated document to understand how the attacker attempted to gain access to the victim's workstation.

### Malicious Document Analysis

I investigated a malicious Microsoft Office document and examined its contents for suspicious functionality.

I used **Olevba** to analyse the document and identify VBA macro activity.

This demonstrated how malicious documents can be used as an initial access mechanism and how embedded macros can contribute to payload execution.

### Memory Forensics

A memory dump from the victim's workstation was provided as part of the investigation.

I used **Volatility** to analyse the memory image and extract useful forensic information.

This allowed me to investigate:

- Running processes
- Process relationships
- Command execution
- Network connections
- Other artefacts present in memory

### Endpoint Investigation

I correlated the memory evidence with the phishing and document analysis to understand how the attack progressed after the malicious document was opened.

This demonstrated the value of memory forensics when investigating activity that may not be fully visible through traditional log files.

### Skills Applied

- Spear-phishing analysis
- Office document analysis
- VBA macro analysis
- Olevba
- Memory forensics
- Volatility
- Process investigation
- Endpoint investigation
- IOC extraction
- Threat actor TTP analysis

---

# Boogeyman 3

Boogeyman 3 continued the investigation of the threat group and focused on the later stages of the attack.

The investigation required analysing how the attacker progressed from the phishing payload to activity within the victim's environment and ultimately toward the domain.

### Key Areas

- Phishing payload analysis
- Endpoint investigation
- Domain activity
- Windows investigation
- Credential activity
- Network evidence
- Lateral movement
- Attack-chain reconstruction
- Threat actor TTPs

### Phishing Payload

I investigated the malicious phishing payload and examined the activity generated after the victim interacted with it.

This allowed me to connect the initial phishing stage with the subsequent attacker activity.

### Endpoint Investigation

I analysed endpoint evidence to identify processes, commands and other activity associated with the compromise.

The investigation focused on understanding how the attacker moved through the environment after establishing an initial foothold.

### Domain Activity

The investigation progressed into activity involving the Windows domain environment.

I analysed the available evidence to understand how the attacker interacted with domain resources and progressed beyond the original compromised endpoint.

### Attack Progression

I reconstructed the attack by correlating evidence from different stages of the incident.

The investigation demonstrated how an attacker can progress from:

**Phishing → Payload Execution → Endpoint Compromise → Internal Activity → Domain-Level Activity**

### Threat Actor TTPs

Throughout the investigation, I identified attacker behaviours and techniques used during the compromise.

This reinforced the importance of understanding TTPs rather than focusing only on individual indicators.

### Skills Applied

- Phishing payload analysis
- Endpoint investigation
- Windows investigation
- Domain activity analysis
- Network investigation
- Lateral movement analysis
- IOC identification
- TTP identification
- Attack-chain reconstruction

---

# Key Takeaways

- Digital forensics allows analysts to investigate incidents using evidence left behind on compromised systems.
- A complete incident investigation often requires combining endpoint, network, email and memory evidence.
- Phishing can be investigated through email headers, malicious documents, files and endpoint activity.
- Windows Event Logs and Sysmon provide valuable evidence during endpoint investigations.
- Wireshark and Tshark can be used to analyse network traffic and identify suspicious communications.
- Memory forensics can reveal information that may not be available through traditional logs.
- Tools such as Volatility and Olevba can provide valuable evidence during forensic investigations.
- Attack-chain reconstruction helps analysts understand how an incident progressed from initial access to the attacker's objective.
- Understanding attacker TTPs makes it easier to connect individual pieces of evidence into a wider investigation.
- Effective DFIR investigations rely on correlating evidence rather than analysing individual artefacts in isolation.

---

# Skills Developed

- Digital Forensics
- Incident Response
- DFIR Investigation
- Phishing Analysis
- Email Header Analysis
- Malicious Document Analysis
- VBA Macro Analysis
- LNK Analysis
- Windows Event Log Analysis
- Sysmon
- PowerShell Log Analysis
- Memory Forensics
- Volatility
- Olevba
- Wireshark
- Tshark
- Brim
- Network Traffic Analysis
- IOC Identification
- TTP Identification
- Timeline Reconstruction
- Attack-Chain Reconstruction
- Endpoint Investigation
- Threat Actor Analysis

---

# Reflection

This module was a strong way to finish the SOC Level 1 pathway because it brought together many of the skills I developed throughout the previous modules.

Earlier modules focused on individual areas such as phishing, Windows and Linux logging, network traffic, threat intelligence and SIEM analysis. These investigations required me to combine those skills and apply them to complete incidents.

The biggest takeaway for me was the importance of **correlating evidence**. A single email, process, network connection or log event may not provide enough context on its own, but combining multiple artefacts can reveal the full progression of an attack.

I also gained more experience with practical DFIR tools including Wireshark, Tshark, Brim, Volatility and Olevba.

Overall, this module strengthened my ability to investigate incidents from initial access through to the attacker's objective and gave me practical experience applying SOC investigation techniques across multiple evidence sources.
