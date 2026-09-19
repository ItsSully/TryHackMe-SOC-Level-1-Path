# Threat Analysis Tools

**TryHackMe SOC Level 1 — Module 12**  
**Status:** ✅ Completed

## Overview

This module focused on using Cyber Threat Intelligence (CTI) and threat intelligence tools to investigate and enrich suspicious indicators.

I learned how SOC analysts can take raw indicators such as files, hashes, IP addresses and domains and enrich them with additional context to determine whether they are associated with malicious activity.

The module also introduced threat intelligence frameworks and practical investigation workflows for turning raw data into actionable intelligence.

---

# Topics Covered

## Intro to Cyber Threat Intel

This room introduced the fundamentals of Cyber Threat Intelligence and how it can support SOC investigations.

### Key Areas

- Cyber Threat Intelligence (CTI)
- Threat intelligence classifications
- CTI lifecycle
- Intelligence collection
- Intelligence analysis
- Intelligence dissemination
- MITRE ATT&CK
- TAXII
- STIX
- Cyber Kill Chain
- Diamond Model
- Practical threat profiling

### Cyber Threat Intelligence

I learned that Cyber Threat Intelligence provides evidence-based knowledge about adversaries, including their:

- Indicators
- Tactics
- Techniques
- Motivations
- Behaviour
- Recommended defensive actions

I also learned the difference between **data, information and intelligence**, and how raw indicators can be enriched and analysed to provide useful context during an investigation.

### CTI Lifecycle

I studied the main stages of the threat intelligence lifecycle:

1. **Direction**
2. **Collection**
3. **Processing**
4. **Analysis**
5. **Dissemination**
6. **Feedback**

This demonstrated how threat intelligence is gathered, processed and turned into information that can support security decisions.

### Threat Intelligence Frameworks

I was introduced to several frameworks and standards used within threat intelligence, including:

- **MITRE ATT&CK** — mapping adversary tactics and techniques
- **STIX** — representing and sharing structured threat intelligence
- **TAXII** — exchanging threat intelligence over a standardised protocol
- **Cyber Kill Chain** — understanding stages of an attack
- **Diamond Model** — analysing relationships between adversaries, capabilities, infrastructure and victims

### Practical Application — Threat Profiling

I completed a practical investigation where I analysed multiple pieces of information from a simulated security incident.

I correlated information such as:

- Suspicious IP addresses
- Email addresses
- Downloaded files
- User activity
- Threat indicators

I then used the collected information to build a threat profile and understand how the different indicators were connected.

### Skills Applied

- CTI fundamentals
- Threat intelligence lifecycle
- Threat profiling
- Indicator correlation
- MITRE ATT&CK
- STIX and TAXII
- Attack-chain analysis
- Intelligence reporting

---

# File and Hash Threat Intel

This room focused on using threat intelligence to investigate suspicious files and file hashes.

### Key Areas

- File-based indicators
- File hashes
- MD5
- SHA-1
- SHA-256
- File-path analysis
- VirusTotal
- MalwareBazaar
- Malware behaviour
- Sandbox analysis
- MITRE ATT&CK mapping

### File and Hash Investigation

I learned how file hashes can act as unique identifiers for files and can be used to search threat intelligence databases.

I worked with different hashing algorithms including:

- MD5
- SHA-1
- SHA-256

Hashes can be used to determine whether a suspicious file has previously been identified as malicious.

### File Path and Filename Analysis

I also learned that the location and naming of a file can provide useful context during an investigation.

Suspicious file paths, unusual filenames and unexpected executable files can all contribute to determining whether an artefact requires further investigation.

### Threat Intelligence Enrichment

I explored how platforms such as **VirusTotal** and **MalwareBazaar** can be used to enrich file indicators.

This can provide information such as:

- Detection results
- Malware family information
- File reputation
- Related samples
- Observed behaviour
- Associated indicators

### Sandbox and Behavioural Analysis

I learned how sandbox telemetry can provide additional information about what a suspicious file does when executed in a controlled environment.

This can reveal behaviours such as:

- Process creation
- File modifications
- Registry activity
- Network connections
- Command execution

I also learned how observed behaviour can be mapped to **MITRE ATT&CK techniques**.

### Practical Application

I completed file and hash enrichment exercises where I investigated suspicious file indicators and used threat intelligence sources to gather additional context.

The investigation demonstrated how a SOC analyst can move from a single suspicious file or hash to a broader understanding of its reputation and behaviour.

### Skills Applied

- File hash analysis
- MD5/SHA-1/SHA-256
- IOC enrichment
- VirusTotal investigation
- MalwareBazaar investigation
- Sandbox analysis
- Malware behaviour analysis
- MITRE ATT&CK mapping

---

# IP and Domain Threat Intel

This room focused on enriching IP addresses and domains to determine whether network indicators are associated with malicious infrastructure.

### Key Areas

- IP enrichment
- Domain enrichment
- DNS
- WHOIS
- Autonomous Systems (ASNs)
- Geolocation
- Shodan
- Censys
- TLS certificates
- VPN detection
- Proxy detection
- Tor infrastructure
- Threat intelligence correlation

### Domain Enrichment

I investigated how DNS information can provide additional context about suspicious domains.

This included looking at:

- DNS records
- Domain information
- WHOIS data
- Domain age
- TLS certificates
- Associated infrastructure

I learned that domain information can help analysts determine whether an indicator is likely to be legitimate or requires further investigation.

### IP Enrichment

I learned how to investigate IP addresses using several types of information.

This included:

- Geolocation
- Autonomous System Numbers (ASNs)
- Reputation
- Hosting information
- Associated services

This can help determine where an IP address is located, who controls the network and what infrastructure is exposed.

### Service Exposure

I explored how tools such as **Shodan** and **Censys** can provide information about publicly exposed services.

This can help analysts identify:

- Open ports
- Services
- Service banners
- TLS information
- Potentially suspicious infrastructure

### VPN and Proxy Detection

I also learned how SOC analysts can identify whether an IP address is associated with:

- VPN services
- Proxies
- Tor exit nodes
- Other anonymisation infrastructure

This can provide additional context when investigating suspicious network connections.

### Practical Application

I completed practical IP and domain enrichment exercises where I investigated network indicators and combined information from multiple intelligence sources.

Rather than relying on a single reputation score, I learned to correlate multiple signals before drawing conclusions about an indicator.

### Skills Applied

- IP investigation
- Domain investigation
- DNS analysis
- WHOIS analysis
- ASN investigation
- GeoIP analysis
- Shodan
- Censys
- TLS certificate analysis
- VPN/proxy detection
- IOC enrichment

---

# Invite Only

This room was a practical threat intelligence challenge designed to bring together the techniques covered throughout the module.

The objective was to investigate a set of flagged indicators and turn the available information into useful threat intelligence.

### Key Areas

- Threat intelligence investigation
- IOC enrichment
- Indicator correlation
- File analysis
- Hash analysis
- IP investigation
- Domain investigation
- Threat actor context
- Intelligence reporting

### Practical Investigation

I investigated a collection of suspicious artefacts and used threat intelligence techniques to enrich the available indicators.

This involved analysing different types of indicators and connecting information between them rather than investigating each artefact independently.

I used the information gathered during the investigation to identify relationships between indicators and build a clearer picture of the activity.

### Threat Intelligence Workflow

The investigation reinforced a practical SOC workflow:

**Verify → Enrich → Correlate → Analyse → Report**

I learned that a single indicator may not provide enough information on its own. Combining multiple sources can reveal additional context and relationships that would otherwise be missed.

### Skills Applied

- Threat intelligence enrichment
- IOC investigation
- Indicator correlation
- File and hash analysis
- IP and domain investigation
- Threat profiling
- Intelligence analysis
- Investigation reporting

---

# Key Takeaways

- Threat Intelligence provides context that helps SOC analysts investigate and prioritise suspicious activity.
- Raw indicators such as hashes, IP addresses and domains become more useful when enriched with additional intelligence.
- The CTI lifecycle provides a structured approach to collecting, processing, analysing and sharing intelligence.
- MITRE ATT&CK can be used to map observed adversary behaviour to known tactics and techniques.
- STIX and TAXII support the structured representation and sharing of threat intelligence.
- File hashes can be investigated using platforms such as VirusTotal and MalwareBazaar.
- IP and domain indicators can be enriched using DNS, WHOIS, ASN, geolocation and infrastructure information.
- Tools such as Shodan and Censys can provide additional information about exposed services.
- Multiple intelligence sources should be correlated rather than relying on a single reputation result.
- Threat intelligence can help turn individual indicators into a wider understanding of an attack.

---

# Skills Developed

- Cyber Threat Intelligence
- CTI Lifecycle
- IOC Enrichment
- File Hash Analysis
- MD5 / SHA-1 / SHA-256
- VirusTotal
- MalwareBazaar
- IP Investigation
- Domain Investigation
- DNS Analysis
- WHOIS
- ASN Analysis
- GeoIP
- Shodan
- Censys
- TLS Certificate Analysis
- VPN/Proxy Detection
- MITRE ATT&CK
- STIX
- TAXII
- Threat Profiling
- Indicator Correlation
- Intelligence Analysis
- SOC Investigation

---

# Reflection

This module helped me understand how threat intelligence fits into the wider SOC investigation process.

Previously, I mainly focused on analysing logs, processes, network traffic and endpoint activity. This module showed me how threat intelligence can provide additional context around the indicators discovered during those investigations.

I particularly found the enrichment process useful because a single IP address, domain or file hash may not reveal much by itself. By investigating the indicator across multiple intelligence sources, it is possible to build a much clearer picture of its reputation, infrastructure and associated behaviour.

The practical investigations also reinforced the importance of correlation. Rather than relying on one tool or one detection result, I learned to combine multiple sources of evidence before reaching a conclusion.

Overall, this module strengthened my understanding of CTI and gave me practical experience with the enrichment and investigation workflows used by SOC analysts.
