---
name: HIPAARiskAssessment
description: >
  Conduct a structured HIPAA Security Rule risk assessment for AI and emerging technology systems.
  USE WHEN conduct risk assessment, HIPAA risk analysis, assess risks for AI tools, security risk assessment,
  risk and vulnerability analysis, what are our AI risks, evaluate our risk posture,
  complete a risk assessment, document risks for AI adoption, 164.308 risk analysis,
  OR user needs to satisfy the HIPAA Security Rule risk analysis requirement.
---

# HIPAARiskAssessment

Produce a completed HIPAA Security Rule risk assessment for AI and emerging technology systems, satisfying the requirement at 45 CFR §164.308(a)(1)(ii)(A). Given context about the organization's environment and tools, Claude walks through all six assessment parts, populates the risk register, and produces a prioritized remediation plan — not a blank form.

## Workflow Routing

| Workflow | Trigger | File |
|----------|---------|------|
| **Assess** | "conduct risk assessment", "HIPAA risk analysis", "assess AI risks", "complete a risk assessment" | `Workflows/Assess.md` |

## Quick Reference

- **6 assessment parts:** Scope, Threats & Vulnerabilities, Risk Analysis, Risk Response, Control Inventory, Summary
- **12 AI-specific threats** pre-cataloged (T-01 through T-12)
- **10 AI-specific vulnerabilities** pre-cataloged (V-01 through V-10)
- **Risk scoring:** Likelihood × Impact (1–9 scale), four levels: Critical / High / Medium / Low
- **4 response options:** Mitigate, Accept, Transfer, Avoid
- **Output:** Completed risk register + prioritized remediation plan + certification block

**Full assessment criteria:** `RiskAssessment.md`

## Examples

**Example 1: Assess a specific AI deployment**
```
User: "We're deploying Epic's ambient AI documentation tool. Help me do a risk assessment."
-> Invokes Assess workflow
-> Scopes assessment to the specific tool and ePHI flows
-> Works through threat catalog, marking applicable threats
-> Scores risks and recommends remediation actions
```

**Example 2: Annual organizational assessment**
```
User: "We need to complete our annual HIPAA risk assessment for AI tools"
-> Invokes Assess workflow
-> Gathers inventory of all AI tools in use
-> Produces comprehensive risk register across all systems
-> Prioritizes top remediation items
```

**Example 3: Pre-adoption risk analysis**
```
User: "Before we approve this AI scribe tool, what risks should we document?"
-> Invokes Assess workflow
-> Focuses on adoption-phase threats (T-01 through T-10)
-> Identifies control gaps that must be addressed before go-live
-> Documents residual risk for executive sign-off
```
