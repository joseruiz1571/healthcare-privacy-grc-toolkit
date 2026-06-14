# AI Vendor Risk Assessment Checklist

## Status Indicators

Use these consistently throughout the assessment:

| Status | Meaning |
|--------|---------|
| Confirmed | Directly evidenced in provided documentation |
| Not Met | Documentation explicitly contradicts requirement |
| Unclear | Documentation exists but is ambiguous |
| Requires Verification | No documentation available; must be requested from vendor |

Never present "Requires Verification" items as confirmed findings. Always specify what documentation or vendor contact would resolve the gap.

---

## Section 1: Business Associate Agreement (REQUIRED)

**Hard stop rule:** If item 1.1 is Not Met, flag immediately — tool cannot be approved for PHI use cases. Continue the assessment for completeness but make the blocker prominent.

| # | Assessment Item | Guidance |
|---|----------------|----------|
| 1.1 | Does the vendor offer a signed Business Associate Agreement (BAA)? | If No, STOP. Tool cannot be approved for PHI use cases. |
| 1.2 | Does the BAA address breach notification obligations? | Must align with 45 CFR 164.410 requirements. |
| 1.3 | Does the BAA specify permitted uses and disclosures of PHI? | |
| 1.4 | Does the BAA require return or destruction of PHI upon termination? | |

---

## Section 2: Data Handling and Privacy (REQUIRED)

**Hard stop rule:** If item 2.1 is Yes with no contractual opt-out, tool is not suitable for PHI use cases.

| # | Assessment Item | Guidance |
|---|----------------|----------|
| 2.1 | Is user input data used to train or improve the vendor's AI model? | Confirm opt-out is contractual, not just a settings toggle. A setting can be changed by the vendor; a contract cannot. |
| 2.2 | Is data encrypted in transit (TLS 1.2+)? | |
| 2.3 | Is data encrypted at rest (AES-256 or equivalent)? | |
| 2.4 | What is the vendor's data retention policy? | Specify retention period if documented. |
| 2.5 | Can the organization request deletion of specific data inputs? | Important for incident mitigation. |
| 2.6 | Where is data processed and stored geographically? | Specify region(s). Data residency matters for some regulatory contexts. |

---

## Section 3: Access Controls and Authentication

| # | Assessment Item | Guidance |
|---|----------------|----------|
| 3.1 | Does the tool support Single Sign-On (SSO) integration? | |
| 3.2 | Does the tool support role-based access controls (RBAC)? | |
| 3.3 | Does the vendor maintain audit logs of user activity? | Critical for incident investigation. |
| 3.4 | Can administrators view and export usage logs? | |

---

## Section 4: Vendor Security Posture

| # | Assessment Item | Guidance |
|---|----------------|----------|
| 4.1 | Does the vendor hold SOC 2 Type II certification? | Request most recent report. |
| 4.2 | Does the vendor hold ISO 27001 certification? | |
| 4.3 | Does the vendor maintain a vulnerability management program? | |
| 4.4 | Does the vendor have a documented incident response plan? | |
| 4.5 | Has the vendor experienced a data breach in the past 24 months? | If yes, request details and remediation summary. |
| 4.6 | Does the vendor use subprocessors who may access PHI? | If yes, confirm subprocessors are covered under the BAA chain. Request the vendor's subprocessor list. |
| 4.7 | How does the vendor communicate model updates and version changes? | Can the customer pin model versions? What is the deprecation policy? Model behavior changes can have compliance implications. |

---

## Section 5: Output Reliability and Organizational Readiness

| # | Assessment Item | Guidance |
|---|----------------|----------|
| 5.1 | Does the vendor document known limitations of AI-generated outputs? | |
| 5.2 | Does the tool provide source attribution or confidence indicators? | Relevant for clinical or billing use cases. |
| 5.3 | Has the organization defined which use cases require human review of AI outputs? | This is an organizational control, not a vendor capability. Flag if Acceptable Use Policy is absent. |

---

## Assessment Summary Template

```
ASSESSMENT SUMMARY
----------------------------------------------
Tool Name:
Vendor:
Version / Tier Evaluated:
Proposed Use Case(s):
PHI Involvement:        Yes / No
Assessed By:            Claude (AI-assisted assessment)
Date:                   [today's date]

HARD STOPS IDENTIFIED:
  [List any Section 1 or Section 2 blockers, or "None"]

OPEN ITEMS REQUIRING VERIFICATION:
  [List all Requires Verification items with what to request]

RECOMMENDATION:
  [ ] Approve
  [ ] Approve with Conditions
  [ ] Deny

CONDITIONS / NOTES:
  [If approving with conditions, list them clearly]
----------------------------------------------
```
