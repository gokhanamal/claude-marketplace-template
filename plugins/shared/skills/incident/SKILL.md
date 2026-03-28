---
name: incident
description: Guide an incident response from detection through resolution and post-mortem
---

You are helping manage an active incident. Follow these steps in order.

## Step 1: Triage (first 5 minutes)

Ask the engineer for:
- What is broken or degraded?
- When did it start?
- What changed recently (deploy, config, infra)?
- Who is affected and how many?

Based on the answers, assign a severity:
- **P0**: Total outage or data loss. Page the on-call lead immediately.
- **P1**: Significant degradation affecting many users. Notify the team channel.
- **P2**: Limited impact. Handle during business hours if stable.

## Step 2: Containment

Help the engineer identify and take the fastest action to limit impact:
- Roll back the most recent deploy if a deploy correlates with the start time
- Disable the feature flag if the issue is scoped to a new feature
- Increase capacity if the issue is resource exhaustion
- Route traffic away from the affected region if the issue is regional

## Step 3: Communication

Draft a status update for the team channel:
> **[INCIDENT - P{severity}]** {what is affected} is {description of impact}. We are investigating. Updates every 15 minutes.

## Step 4: Resolution

Work through the root cause with the engineer. Ask for:
- Logs, traces, or metrics that narrow down the failure
- Recent changes to the affected system
- Whether the issue is reproducible in a non-production environment

## Step 5: Post-mortem

After resolution, create a post-mortem document with:
- **Timeline**: Key events with timestamps
- **Root cause**: What actually went wrong
- **Contributing factors**: What made this possible or harder to detect
- **Impact**: Duration, users affected, data affected if any
- **Action items**: Specific, assigned tasks to prevent recurrence

---

**Customize this skill** by adding your actual alerting channel names, escalation contacts,
runbook links, and any compliance requirements for incident documentation.
