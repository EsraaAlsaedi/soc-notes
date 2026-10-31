# Alert reporting, escalation, and communication

Notes from the TryHackMe SOC Level 1 path, written in my own words. [Back to the main README](../README.md)

## Contents

- [Why Level 1 analysts write good reports](#why-level-1-analysts-write-good-reports)
- [Report format](#report-format)
- [When to escalate](#when-to-escalate)
- [How to escalate](#how-to-escalate)
- [Crisis communication](#crisis-communication)
- [Inventories and playbooks](#inventories-and-playbooks)
- [SOC metrics](#soc-metrics)

---

## Why Level 1 analysts write good reports

1. **Context for escalation:** a clear report helps Level 2 understand what happened quickly.
2. **A record of findings:** the report is saved for future reference.
3. **Better investigation skills:** writing forces me to explain my reasoning clearly.

## Report format

- **Who:** the user or account involved
- **What:** the action that took place
- **When:** when the action started and ended
- **Where:** which device or system
- **Why:** the most important part. Why this is (or is not) malicious.

## When to escalate

1. The alert indicates a major cyberattack.
2. Remediation is needed, such as a password reset.
3. Communication with customers or partners is required.
4. I am unsure what the alert means and need a senior analyst's help.

## How to escalate

Reassign the alert to the Level 2 team and notify them.

Dashboard steps:

1. Move the alert to **In progress** and investigate.
2. Write the alert report and make my verdict.
3. Assign the alert to the Level 2 analyst on shift.
4. Level 2 receives a notification and starts from my report.

## Crisis communication

Each SOC has its own crisis communication procedures.

Example: I receive an overwhelming number of alerts in a short time, and some are critical. I still prioritize them using the normal workflow (severity first, then oldest first), but I **inform the Level 2 analyst on shift** about the situation.

## Inventories and playbooks

Identity and asset inventories are essential for alert investigations:

- **Identity inventory:** information about users, such as role and department.
- **Asset inventory:** information about devices, such as owner, operating system, and how critical they are.

Example playbook stages for a suspicious login:

1. **Enrichment:** use threat intelligence and the identity inventory to learn about the affected user.
2. **Investigation:** use the gathered data and SIEM logs to decide whether the login was expected.
3. **Escalation:** escalate to Level 2, or contact the user, if necessary.

## SOC metrics

**Time-based metrics**

- **MTTD (mean time to detect):** how long it takes to detect a threat.
- **MTTA (mean time to acknowledge):** how long it takes an analyst to start working on an alert.
- **MTTR (mean time to respond):** how long it takes to respond to the threat. Some teams use R for recover or resolve, so I state which one I mean.

**Four metrics for the SOC**

| Metric | Formula | What it shows | Target |
|---|---|---|---|
| Alert count (AC) | Total alerts in a period | The SOC analysts' overall workload | Depends on company size; about 5 to 30 per day is reasonable |
| False positive rate | False positives / AC | How noisy the alerts are | Lower is better |
| Alert escalation rate | Escalated alerts / AC | The experience of Level 1 analysts | Below 50%, ideally below 20% |
| Threat detection rate | Detected threats / all threats | How reliable the SOC is | Should be as close to 100% as possible |

Targets differ between organizations, so I treat these numbers as rough guides.
