---
name: BAAReview
description: >
  Review and negotiate Business Associate Agreements (BAAs) for AI and healthcare technology vendors.
  USE WHEN review BAA, evaluate business associate agreement, negotiate BAA, check BAA for AI vendor,
  does this BAA cover HIPAA requirements, BAA redlines, what should be in a BAA, BAA gap analysis,
  sign BAA, business associate contract review, 164.504 compliance,
  OR user pastes a BAA or vendor agreement text for analysis.
---

# BAAReview

Review vendor-provided Business Associate Agreements against HIPAA statutory requirements and AI-specific negotiation standards. Given a BAA document or vendor name, Claude identifies missing provisions, flags hard stops, produces a gap analysis, and recommends specific redlines — not a blank checklist.

## Workflow Routing

| Workflow | Trigger | File |
|----------|---------|------|
| **Review** | "review BAA", "evaluate BAA", "check this agreement", "should we sign this BAA" | `Workflows/Review.md` |

## Quick Reference

- **5 review sections:** Mandatory HIPAA elements, Breach notification, AI-specific provisions, Security safeguards, Termination rights
- **Hard stops:** 4 conditions that block signing as-is
- **10 AI-specific provisions** that standard templates omit
- **Breach notification target:** ≤30 days (statutory max is 60; push for shorter)
- **Output:** Completed gap analysis + hard-stop flags + specific redline recommendations

**Full checklist criteria:** `Checklist.md`

## Examples

**Example 1: Review a pasted BAA**
```
User: "Here's the BAA our AI vendor sent us, can you review it?"
-> Invokes Review workflow
-> Maps each provision against the 5-section checklist
-> Identifies gaps, missing AI-specific clauses, and hard stops
-> Produces list of specific redlines to request
```

**Example 2: Assess a vendor's BAA posture**
```
User: "Does Microsoft offer a compliant BAA for Azure OpenAI?"
-> Invokes Review workflow
-> Reviews known BAA terms from public knowledge
-> Identifies AI-specific provisions present and absent
-> Recommends what to verify or negotiate
```

**Example 3: Pre-negotiation preparation**
```
User: "We're about to negotiate a BAA with a new AI scribe vendor — what do we need?"
-> Invokes Review workflow
-> Produces a checklist of must-have and should-have provisions
-> Highlights AI-specific items to negotiate proactively
-> Notes which provisions vendors commonly resist and why
```
