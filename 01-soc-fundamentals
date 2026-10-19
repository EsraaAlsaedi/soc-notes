# SOC Notes

My study notes from the TryHackMe SOC Level 1 path and my own lab work, written in my own words. I update this as I go.

## Contents

- [SOC components](#soc-components)
- [The Level 1 analyst's job: alert triage](#the-level-1-analysts-job-alert-triage)
- [Social engineering](#social-engineering)
- [Alert prioritization](#alert-prioritization)
- [Alert handling workflow](#alert-handling-workflow)

---

## SOC components

A Security Operations Center (SOC) rests on three parts:

1. **People:** analysts, team leads, engineers
2. **Process:** playbooks, escalation paths, reporting procedures
3. **Technology:** SIEM, EDR, firewalls and other security tools

## The Level 1 analyst's job: alert triage

A Level 1 analyst's main job is alert triage: deciding what an alert means and what to do with it.

To understand an incident, answer the 5Ws:

1. **What** happened?
2. **When** did it happen?
3. **Where** did it happen (which host, system, or network)?
4. **Who** was involved or affected?
5. **Why** did it happen?

In short: who did what, where, and when, and why? It also helps to ask **how** it happened.

To report an incident:

- Answer the 5Ws
- Analyze the alert thoroughly
- Provide evidence, such as screenshots and log entries

## Social engineering

Social engineering works on trust and emotions (urgency, fear, curiosity, greed) rather than on technical weaknesses.

Two techniques that rely on it:

- **SEO poisoning:** the attacker manipulates search engine rankings (search engine optimization) so a malicious page appears high in the results.
- **Typosquatting:** the attacker registers a domain that looks like a real one (for example, with a small spelling change) and waits for someone to mistype or click it.

The two can be combined, but they are different techniques.

## Alert prioritization

When the queue is full, I decide what to work on first:

1. **Filter** for new alerts that no teammate is already investigating.
2. **Sort by severity:** critical, then high, then medium, then low.
3. **Within each severity, take the oldest first.** An alert that has been waiting gives an attacker more time to act, and it is closer to missing the team's response-time target.

## Alert handling workflow

1. Select an alert.
2. Assign it to myself.
3. Move it to **In progress**.
4. Read the alert's name, description, host, and IP or user.
5. Check whether the alert type has a **playbook** (a documented set of steps for that kind of alert).
   - If yes, follow the steps.
   - If not, investigate:
     - Who is affected?
     - What action took place?
     - Review the relevant events.
     - Use threat intelligence to check indicators.
6. Make a verdict:
   - **True positive:** real malicious or policy-violating activity.
   - **False positive:** the alert fired, but the activity is harmless.
7. Decide whether to escalate.
   - **Escalate:** add a clear comment with my findings and evidence so the next analyst does not repeat my work, then move on to the next alert.
   - **Do not escalate:** add a comment with the verdict and reasoning, close the alert, and move on to the next one.
