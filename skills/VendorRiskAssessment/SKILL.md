---
name: VendorRiskAssessment
description: >
  Conduct structured AI vendor risk assessments against HIPAA compliance and data privacy standards.
  USE WHEN assess vendor, evaluate AI tool, vendor risk check, is tool HIPAA compliant, can we use tool with PHI,
  vet AI vendor, vendor due diligence, review AI product, AI procurement risk, vendor security review,
  OR user pastes vendor documentation or privacy policy for analysis.
---

# VendorRiskAssessment

Evaluate Generative AI vendors and tools for organizational adoption in healthcare and regulated industries. Produces a completed assessment report with status findings and a clear recommendation — not a blank form.

## Workflow Routing

| Workflow | Trigger | File |
|----------|---------|------|
| **Assess** | "assess vendor", "evaluate tool", "vendor risk check", "is [tool] HIPAA compliant" | `Workflows/Assess.md` |

## Quick Reference

- **5 assessment sections** (22 items): BAA, Data Handling, Access Controls, Security Posture, Output Reliability
- **Hard stops**: No BAA (1.1) or training on user data with no contractual opt-out (2.1) block PHI approval
- **4 status indicators**: Confirmed, Not Met, Unclear, Requires Verification
- **Output**: Completed assessment tables + summary block with recommendation

**Full assessment criteria:** `Checklist.md`

## Examples

**Example 1: Assess a vendor by name**
```
User: "Can we use Microsoft Azure OpenAI with PHI?"
-> Invokes Assess workflow
-> Walks through all 5 sections using available knowledge
-> Marks unverified items clearly
-> Produces assessment summary with recommendation
```

**Example 2: Analyze vendor documentation**
```
User: "Here's the privacy policy for [vendor], assess it"
-> Invokes Assess workflow
-> Extracts evidence from pasted documentation
-> Maps findings to checklist items
-> Flags gaps that need vendor follow-up
```

**Example 3: URL-based assessment**
```
User: "Evaluate this vendor: [trust page URL]"
-> Invokes Assess workflow
-> Fetches and analyzes URL content
-> Populates checklist from discovered evidence
-> Produces structured report
```
