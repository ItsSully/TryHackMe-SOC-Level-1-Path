# Windows Security Monitoring

**TryHackMe SOC Level 1 — Module 9**  
**Status:** ✅ Completed

## Overview

This module focused on monitoring and investigating Windows systems using native Windows Event Logs, Event Viewer, Sysmon and PowerShell.

The module covered the full lifecycle of Windows-based attacks, from initial access and post-compromise activity to persistence and command-and-control. I practised analysing authentication events, process creation, file activity, network connections and other Windows telemetry to identify suspicious behaviour and reconstruct attack chains.

---

# Topics Covered

## Windows Logging for SOC

This room introduced the fundamentals of Windows logging and how Windows Event Logs can be used by SOC analysts during detection and investigation.

### Key Areas

- Windows Event Logs and EVTX files
- Event Viewer
- Security logs
- Authentication events
- User management events
- Process creation monitoring
- Sysmon
- PowerShell logging
- Logon IDs and event correlation
- Identifying suspicious processes and activity

### Authentication Monitoring

I worked with Windows Security events used to investigate authentication activity, including:

- **4624** — Successful Logon
- **4625** — Failed Logon

I learned how these events can be used to identify:

- Brute-force attacks
- Password spraying
- Suspicious RDP logins
- Unexpected source IP addresses
- Suspicious logon types

I also learned how a **Logon ID** can be used to connect related events and follow activity after a successful login.

### User Management

I investigated Windows events related to account creation, modification, password changes and account deletion.

These events can help identify suspicious activity such as attackers creating or enabling accounts to maintain access to a compromised system.

### Sysmon

I explored Sysmon as a more detailed source of endpoint telemetry.

Particular focus was placed on **Sysmon Event ID 1 (Process Creation)** and how process information, command lines, parent processes, hashes and user context can be used to investigate suspicious execution.

### Practical Application

I analysed Windows event log datasets using Event Viewer and practised correlating Security and Sysmon events to investigate authentication and process activity.

This helped me understand how individual Windows events can be connected together to reconstruct an attack sequence rather than analysing each event in isolation.

---

# Windows Threat Detection 1

This room focused on detecting **Initial Access** techniques against Windows systems.

### Key Areas

- Initial Access
- RDP brute-force attacks
- Malicious RDP logins
- Phishing attachments
- Malicious files
- LNK attachments
- Double extensions
- Malicious downloads
- USB-based malware
- Sysmon investigation

### RDP Brute Force Detection

I investigated Windows Security logs to identify failed RDP authentication attempts.

I used Event IDs such as **4625** to identify failed logins and looked at fields including:

- Source IP
- Username
- Logon Type
- Workstation information

I then correlated failed authentication activity with successful **4624** events to determine whether an attacker gained access.

### Phishing Investigation

I investigated different phishing scenarios involving malicious files and Windows shortcuts.

This included understanding how attackers can disguise executable files using techniques such as:

- Misleading file extensions
- Double extensions
- Malicious LNK shortcuts
- PowerShell-based downloads

### Malicious Download Investigation

I used Sysmon telemetry to follow a suspicious file from download through execution and network activity.

This involved correlating different event types to understand the progression of the attack and identify indicators such as downloaded files, processes and external connections.

### USB Malware Investigation

I also investigated a simulated attack involving malicious removable media.

I analysed Sysmon process and file events to identify:

- The file executed from the USB
- Files created by the malware
- Activity involving another removable drive

### Skills Applied

- Windows Event Viewer
- Security Event Log analysis
- Sysmon investigation
- RDP attack detection
- Phishing analysis
- Malware execution tracking
- IOC identification
- Attack-chain reconstruction

---

# Windows Threat Detection 2

This room focused on what happens **after initial access**, particularly discovery, collection and data transfer activity.

### Key Areas

- Windows discovery techniques
- Process-tree analysis
- System and user discovery
- Credential access
- Sensitive file discovery
- Clipboard collection
- Data staging
- Data exfiltration
- Ingress Tool Transfer
- Sysmon investigation

### Discovery Detection

I investigated commands and processes used by attackers to understand the compromised Windows environment.

Sysmon logs were used to identify the processes responsible for executing commands and to trace activity back through the process tree.

### Collection and Credential Access

The investigation covered different types of information attackers may target after gaining access, including:

- Browser credentials
- SSH keys
- Sensitive documents
- Clipboard contents
- Other files of interest

I learned how endpoint telemetry can help identify suspicious access to these resources.

### Data Staging and Exfiltration

I investigated how collected information can be gathered into a staging directory before being transferred out of the system.

This demonstrated how a SOC analyst can use file creation, process execution and network activity to trace the movement of data through an attack.

### Ingress Tool Transfer

I also investigated different ways attackers can transfer tools or files onto a compromised Windows machine.

The room demonstrated how legitimate Windows utilities and built-in functionality can be abused to download files.

### Skills Applied

- Windows threat hunting
- Sysmon analysis
- Process-tree reconstruction
- Discovery detection
- Credential-access investigation
- File-system investigation
- Data staging detection
- Exfiltration analysis
- Detection of tool transfer

---

# Windows Threat Detection 3

The final room focused on **Command and Control, Persistence and Impact**.

The objective was to investigate how attackers maintain access to a compromised Windows machine and continue operating after the initial compromise.

### Key Areas

- Command and Control (C2)
- Persistence
- Backdoor accounts
- Windows services
- Scheduled tasks
- Registry Run Keys
- Startup persistence
- Malware execution
- Impact

### Command and Control

I investigated Windows telemetry to identify suspicious communication between the compromised host and external infrastructure.

Sysmon events were used to correlate processes with network activity and identify potential C2 behaviour.

### Persistence

The room introduced several Windows persistence mechanisms, including:

- Creating backdoor accounts
- Modifying account privileges
- Malicious Windows services
- Scheduled tasks
- Registry Run Keys
- Startup-folder execution

I learned how attackers can use legitimate Windows functionality to maintain access while attempting to blend into normal system activity.

### Practical Investigation

I used Windows Event Logs and Sysmon telemetry to investigate suspicious activity and connect different events together.

This involved looking at processes, authentication activity, files and persistence mechanisms to build a clearer picture of how an attacker maintained access to the system.

### Skills Applied

- Persistence detection
- C2 investigation
- Windows Event Log analysis
- Sysmon analysis
- Account activity investigation
- Service and scheduled-task investigation
- Registry persistence detection
- Attack-chain reconstruction

---

# Key Takeaways

- Windows Event Logs provide valuable visibility into authentication, account activity and system behaviour.
- Sysmon provides additional endpoint telemetry that can help identify suspicious processes, files and network activity.
- Event IDs such as **4624, 4625 and Sysmon Event ID 1** are useful when investigating Windows activity.
- Correlating events is more effective than analysing individual logs in isolation.
- Attackers can abuse legitimate Windows functionality for execution, discovery, persistence and data transfer.
- Process trees, Logon IDs and timestamps can help reconstruct an attacker's activity.
- Initial access, post-compromise activity, persistence and C2 can leave different traces across Windows telemetry.

---

# Skills Developed

- Windows Event Log Analysis
- Event Viewer
- Sysmon
- Security Log Analysis
- Authentication Monitoring
- RDP Attack Detection
- Phishing Detection
- Malware Investigation
- Process Tree Analysis
- File-System Investigation
- Network Activity Analysis
- Persistence Detection
- Command-and-Control Investigation
- IOC Identification
- Attack-Chain Reconstruction
- Windows Threat Hunting

---

# Reflection

This module significantly improved my understanding of endpoint monitoring and how Windows systems can be investigated from a SOC perspective.

Instead of only looking for individual indicators, I learned how to correlate authentication events, processes, files and network activity to understand what happened on a compromised machine.

The biggest takeaway for me was the importance of understanding **Windows telemetry and knowing what normal activity looks like**. This provides the foundation for identifying unusual behaviour and investigating incidents effectively.

Overall, this module strengthened my practical understanding of Windows security monitoring and gave me more experience with the type of endpoint investigation that can be involved in a SOC environment.
