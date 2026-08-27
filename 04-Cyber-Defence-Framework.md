# Cyber Defence Frameworks

**TryHackMe SOC Level 1 — Module 4**

**Status:** ✅ Completed

## Overview

This module introduced defensive security frameworks used to understand adversary behaviour, analyse attacks and support detection and response.

The module covered the **Pyramid of Pain, Cyber Kill Chain, Unified Kill Chain and MITRE ATT&CK**, alongside two practical scenarios, **Summit** and **Eviction**, which allowed me to apply these concepts in simulated environments.

---

## Topics Covered

### Pyramid of Pain

The **Pyramid of Pain** ranks different types of indicators based on how difficult and disruptive they are for an adversary to change.

Understanding the Pyramid of Pain helps defenders consider the relative value of different indicators when developing detections.

**Key concept:** Detection can become more resilient when it moves beyond easily changed indicators towards behavioural indicators and attacker techniques.

### Cyber Kill Chain

The **Cyber Kill Chain** provides a framework for understanding the different stages an adversary may go through during a network intrusion.

Understanding these stages can help defenders identify opportunities to detect and disrupt malicious activity.

**Skill developed:** Analysing adversary activity across different stages of an attack.

### Unified Kill Chain

The **Unified Kill Chain** provides a framework for understanding the phases of an attack and identifying opportunities to detect and mitigate threats to IT assets.

**Skill developed:** Understanding attack progression and defensive opportunities.

### MITRE ATT&CK

I explored **MITRE ATT&CK** as a resource for understanding and categorising adversary behaviour.

MITRE ATT&CK provides structured information about attacker tactics and techniques that can be used to support threat analysis and defensive security activities.

**Skill developed:** Understanding MITRE ATT&CK and adversary behaviour classification.

---

# Practical Application

This module included two practical scenarios that allowed me to apply the defensive frameworks and adversary behaviour concepts covered throughout the module.

## Summit — Pyramid of Pain

I completed the **Summit** scenario, a simulated detection and response exercise based on the Pyramid of Pain.

The scenario involved progressively identifying and blocking malicious activity as the simulated adversary adapted their approach.

### Detection Progression

The investigation progressed through increasingly difficult indicators:

1. **File Hash** — identified a malicious file using its hash.
2. **IP Address** — identified malicious network infrastructure and applied a block.
3. **Domain** — identified malicious domain infrastructure and applied DNS filtering.
4. **Host Artifacts** — investigated changes made to the Windows host and developed a detection for suspicious registry activity.
5. **Network Behaviour** — analysed network connection patterns and identified recurring beaconing behaviour.
6. **TTPs / Behaviour** — analysed adversary activity and developed detection based on observed behaviour.

### Tools & Techniques

During the scenario, I worked with:

* Malware sandbox analysis
* Firewall rules
* DNS filtering
* Sysmon event logs
* Windows registry activity
* Network connection analysis
* Sigma detection rules
* MITRE ATT&CK concepts

### Key Takeaway

The Summit exercise demonstrated how detection can progress from simple indicators, such as hashes and IP addresses, towards behavioural indicators and **Tactics, Techniques and Procedures (TTPs)**.

This showed why relying solely on easily changed indicators can make detections easier for an adversary to evade, while behavioural detections can provide a more resilient approach.

**Skills applied:**

* Indicator of Compromise (IoC) analysis
* Malware analysis
* Network behaviour analysis
* Host-based detection
* Windows event analysis
* Sigma rule development
* Behavioural detection
* Applying the Pyramid of Pain

---

## Eviction — MITRE ATT&CK

I also completed the **Eviction** scenario, which involved investigating the behaviour of a simulated APT and identifying techniques associated with different stages of its activity.

The scenario required identifying adversary techniques across different stages of an attack, including:

* Initial access
* User execution
* Command and scripting
* Persistence
* Defence evasion
* Discovery
* Lateral movement
* Data collection
* Potential exfiltration

The scenario reinforced how **MITRE ATT&CK can be used to categorise adversary behaviour and understand an attack across multiple stages.**

**Skills applied:**

* MITRE ATT&CK technique identification
* Adversary behaviour analysis
* Attack lifecycle analysis
* Threat detection
* Persistence identification
* Network discovery analysis
* Lateral movement analysis
* Data collection and exfiltration awareness

---

## Key Takeaways

* Defensive frameworks provide structured methods for understanding adversary behaviour.
* The Pyramid of Pain helps defenders understand the relative difficulty of changing different indicators.
* The Cyber Kill Chain provides a way to understand the stages of a network intrusion.
* The Unified Kill Chain provides another approach to understanding attack phases and defensive opportunities.
* MITRE ATT&CK can be used to categorise and analyse adversary tactics and techniques.
* Detection can become more resilient when it moves beyond simple indicators towards behavioural patterns and TTPs.
* Defenders need to adapt their detection strategies as adversaries change their methods.
* Combining threat intelligence, security telemetry and defensive frameworks can support more effective investigation and response.

## Skills Developed

* Threat detection concepts
* Indicator of Compromise (IoC) analysis
* Adversary behaviour analysis
* Pyramid of Pain
* Cyber Kill Chain
* Unified Kill Chain
* MITRE ATT&CK
* Network behaviour analysis
* Host-based detection
* Windows event analysis
* Sigma rule development
* Attack lifecycle analysis
* Defensive security analysis

## Reflection

This module helped me understand how security frameworks can be used to analyse adversary behaviour and support defensive decision-making.

The **Summit** scenario allowed me to apply the Pyramid of Pain through a progressive detection exercise, while **Eviction** reinforced the use of MITRE ATT&CK to identify and categorise adversary techniques across different stages of an attack.

Together, these scenarios helped me understand that effective detection requires defenders to look beyond individual indicators and consider the wider behaviour and techniques used by an adversary.
