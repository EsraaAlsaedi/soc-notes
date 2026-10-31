# SOC challenges and SOAR

Notes from the TryHackMe SOC Level 1 path, written in my own words. [Back to the main README](./README.md)

## Contents

- [Challenges SOCs face](#challenges-socs-face)
- [SOAR](#soar)

---

## Challenges SOCs face

1. **Alert fatigue:** too many alerts, many of them false positives, make it hard to notice the real ones.
2. **Too many disconnected tools:** analysts switch between separate tools, which slows investigations.
3. **Manual processes:** investigation steps are often undocumented. Teams depend on the knowledge of experienced analysts ("tribal knowledge"), which slows investigations and increases response times.

## SOAR

Security Orchestration, Automation, and Response (SOAR) is a platform that brings the SOC's security tools together.

- **Orchestration:** makes the different tools work together.
- **Automation:** runs predefined actions automatically. These actions are written as **playbooks**.
- **Response:** takes action across different tools from one interface, and can automate that response too.

SOAR often uses **threat intelligence feeds**: real-time streams of information about threats and attacks, such as malicious IPs and domains.
