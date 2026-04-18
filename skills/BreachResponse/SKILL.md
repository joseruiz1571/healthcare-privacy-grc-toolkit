---
name: BreachResponse
description: >
  Guide HIPAA breach response for AI-related incidents, including breach determination, notification planning, and documentation.
  USE WHEN breach response, PHI accidentally entered into AI tool, vendor breach, AI breach incident, data breach notification,
  was this a HIPAA breach, do we need to notify HHS, 4-factor risk assessment, breach determination,
  incident response for AI, how long do we have to notify, breach notification letter,
  OR user describes a specific incident involving PHI and an AI tool.
---

# BreachResponse

Guide the response to a suspected or confirmed HIPAA breach involving AI tools and automated systems. Given incident details, Claude conducts the 4-factor risk assessment, determines whether breach notification is required, identifies notification deadlines and recipients, drafts documentation, and produces a post-incident review checklist — not a blank form.

## Workflow Routing

| Workflow | Trigger | File |
|----------|---------|------|
| **Respond** | "breach response", "PHI in AI tool", "vendor breach", "do we need to notify", "was this a breach" | `Workflows/Respond.md` |

## Quick Reference

- **6 response phases:** Detection, Breach Determination, Notification Planning, BA Coordination, Execution, Post-Incident Review
- **4-factor risk assessment** per 45 CFR §164.402(2)
- **Notification deadlines:** Individuals and HHS ≤60 days; media ≤60 days if ≥500 in a state
- **3 AI scenarios** pre-documented: unapproved tool use, vendor breach, wrong-party output disclosure
- **Output:** Completed 4-factor analysis + notification plan + incident record + post-incident checklist

**Full playbook:** `Playbook.md`

## Examples

**Example 1: Assess a specific incident**
```
User: "A nurse accidentally pasted a patient list into ChatGPT. What do we do?"
-> Invokes Respond workflow
-> Gathers incident facts (what PHI, how many patients, what tool)
-> Conducts 4-factor risk assessment
-> Determines whether notification is required
-> Produces incident record and notification plan with deadlines
```

**Example 2: Vendor breach response**
```
User: "Our AI vendor just notified us of a data breach. What are our obligations?"
-> Invokes Respond workflow
-> Identifies the covered entity's notification clock start date
-> Guides the 4-factor analysis based on available vendor information
-> Produces notification plan with all three recipient types
```

**Example 3: Near-miss documentation**
```
User: "We think we caught it in time — nothing was actually sent. Do we still need to document this?"
-> Invokes Respond workflow
-> Explains the breach determination standard (low probability of compromise)
-> Guides 4-factor analysis to determine if it was truly a non-breach
-> Produces required documentation for the non-breach determination
```
