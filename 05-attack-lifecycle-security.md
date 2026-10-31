# Attack lifecycle and security frameworks

Notes from the TryHackMe SOC Level 1 path, written in my own words. [Back to the main README](./README.md)

## Contents

- [Reconnaissance](#reconnaissance)
- [Malware, exploits, and payloads](#malware-exploits-and-payloads)
- [Signs of exploitation](#signs-of-exploitation)
- [Persistence and defense evasion](#persistence-and-defense-evasion)
- [Command and control (C2)](#command-and-control-c2)
- [Shadow copies](#shadow-copies)
- [Kill chains](#kill-chains)
- [Frameworks and tools](#frameworks-and-tools)

---

## Reconnaissance

Reconnaissance is the research and planning phase of an attack.

- **Passive recon:** no direct contact with the target. Examples: WHOIS lookups, social media research, reviewing leaked data.
- **Active recon:** direct contact with the target. Examples: social engineering, port scanning, banner grabbing, probing for open services.
- **Email harvesting:** collecting email addresses from public, free, or paid sources.

## Malware, exploits, and payloads

- **Malware:** software designed to damage, disrupt, or gain unauthorized access to a computer.
- **Exploit:** code that takes advantage of a vulnerability or flaw in an application or system.
- **Payload:** the malicious code the attacker runs on the system after exploiting it.

Office **macros** are automated scripts embedded in documents. Attackers can abuse them to run malicious code.

## Signs of exploitation

- Unexpected process spawns
- Registry changes or newly created services
- Suspicious command-line arguments in system logs

## Persistence and defense evasion

**Malicious services (ATT&CK T1543.003).** Attackers can use `sc.exe` (create, start, stop, query, or delete Windows services) and `reg.exe` to change service settings. They may also give a malicious service a name that looks like a legitimate Windows or software service, so it blends in.

**Timestomping (ATT&CK T1070.006).** The attacker changes a file's timestamps (modified, accessed, created, and changed) so that the malware looks like part of a legitimate program and is harder for a forensic investigator to spot.

*I will check the technique IDs on attack.mitre.org.*

## Command and control (C2)

C2 is how the attacker communicates with an infected machine. Common channels:

- **HTTP (port 80) and HTTPS (port 443):** the traffic blends in with normal web traffic, which can help it get past firewalls. Infected machines often check in at regular intervals, called **beaconing**.
- **DNS:** the infected machine sends constant DNS requests to a DNS server controlled by the attacker. This is called **DNS tunneling**.

## Shadow copies

Shadow Copy is a Microsoft technology that creates backup snapshots of files or volumes. Ransomware often deletes shadow copies to stop victims from restoring their files, so shadow copy deletion is a useful thing to detect.

## Kill chains

The **kill chain** describes the path attackers follow to break into a target.

The **Unified Kill Chain (UKC)** is a more detailed model with 18 phases. It supports threat modelling by helping identify attack surfaces and how systems might be exploited.

Two example phases:

- **Weaponization:** preparing the infrastructure and tools needed to carry out the attack.
- **Defense evasion:** the techniques an attacker uses to avoid the defenses in a system or network.

Threat modelling uses frameworks such as **STRIDE** and **DREAD**. **CVSS** is related, but it scores the severity of vulnerabilities.

## Frameworks and tools

| Name | What it is |
|---|---|
| **MITRE CAR** (Cyber Analytics Repository) | A knowledge base of detection analytics built on the ATT&CK model, with explanations and implementations for tools like Splunk and EQL. |
| **MITRE D3FEND** | A framework of defensive techniques with a common language for describing how security controls work. Its matrix has seven tactics. |
| **MITRE Caldera** | An automated adversary emulation tool that simulates attacker behavior using ATT&CK, so teams can test their defenses. |
| **MITRE ATLAS** | A knowledge base and matrix of threats against AI and machine learning systems. |
