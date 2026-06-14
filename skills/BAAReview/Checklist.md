# BAA Review Checklist

## Status Indicators

Use these consistently throughout the review:

| Status | Meaning |
|--------|---------|
| Present — Acceptable | Provision exists and meets the requirement |
| Present — Needs Redline | Provision exists but is deficient; specific revision needed |
| Absent — Required | Provision is legally required and missing; hard stop if not added |
| Absent — Recommended | Provision is not legally required but represents best practice for AI vendors |
| Requires Verification | Cannot be determined from the text; must be confirmed with vendor |

---

## Section 1: Mandatory HIPAA BAA Elements (45 CFR §164.504(e)(2))

**Rule:** All seven items must be present. Absence of any = legally deficient BAA.

| # | Requirement | Statutory Citation |
|---|---|---|
| 1.1 | Permitted uses and disclosures specified and limited to what is necessary | §164.504(e)(2)(i) |
| 1.2 | Prohibition on use or disclosure beyond what is permitted | §164.504(e)(2)(ii)(A) |
| 1.3 | Appropriate safeguards to prevent unauthorized use/disclosure | §164.504(e)(2)(ii)(B) |
| 1.4 | Report unauthorized uses, disclosures, and breaches to covered entity | §164.504(e)(2)(ii)(C), §164.410 |
| 1.5 | Subcontractors subject to same restrictions via their own agreements | §164.504(e)(2)(ii)(D) |
| 1.6 | Make records available to HHS for compliance purposes | §164.504(e)(2)(ii)(H) |
| 1.7 | Return or destroy PHI at termination; if not feasible, extend protections | §164.504(e)(2)(ii)(J) |

---

## Section 2: Breach Notification

| # | Requirement | Target Standard |
|---|---|---|
| 2.1 | Notice window specified | ≤30 days from discovery (statutory max is 60) |
| 2.2 | Required notification elements included (who, what, when, types of PHI) | All five elements per §164.410(c) |
| 2.3 | Mitigation steps included in notification | Yes |
| 2.4 | Potential breaches reportable pending risk assessment | Yes — do not require BA to wait for certainty |

---

## Section 3: AI-Specific Provisions [AI-SPECIFIC]

Standard HIPAA BAA templates do not address these. All 10 should be present for AI vendors handling PHI.

| # | Provision | Priority |
|---|---|---|
| 3.1 | **Model training prohibition** — contractual, not settings-based | Hard stop if absent for PHI use |
| 3.2 | Training opt-out survives product tier changes and ToS updates | High |
| 3.3 | Maximum data retention period specified (push for ≤90 days) | High |
| 3.4 | Covered entity can request deletion of specific PHI-containing inputs | High |
| 3.5 | Subprocessor list provided and maintained; notice required before adding new ones | High |
| 3.6 | Subprocessor BAA chain confirmed | High |
| 3.7 | Advance notice of material model version changes | Medium |
| 3.8 | Version pinning option specified with duration | Medium |
| 3.9 | Covered entity can access and export audit logs | High |
| 3.10 | Right to audit or receive SOC 2 reports on request | Medium |

---

## Section 4: Security Safeguards

| # | Requirement | Minimum Standard |
|---|---|---|
| 4.1 | Encryption in transit | TLS 1.2+ |
| 4.2 | Encryption at rest | AES-256 or equivalent |
| 4.3 | Vulnerability management program | Documented |
| 4.4 | Annual security evaluation or penetration test | Documented |
| 4.5 | SOC 2 Type II available on request | Yes |

---

## Section 5: Termination

| # | Requirement | Notes |
|---|---|---|
| 5.1 | Right to immediate termination for material breach | Must be covered entity's right, not just optional |
| 5.2 | Return/destroy PHI within a specified timeframe post-termination | Push for 30 days; "upon termination" is too vague |
| 5.3 | Procedure if destruction is infeasible (relevant for AI model weights) | Must extend equivalent protections indefinitely |

---

## Hard Stops

Any one of these blocks signing as-is:

| # | Condition |
|---|---|
| H-1 | One or more Section 1 mandatory elements are absent |
| H-2 | Model training prohibition absent with no equivalent contractual control (Section 3.1) |
| H-3 | Subprocessor chain not covered by BAA-equivalent agreements (Section 3.6) |
| H-4 | Breach notification window exceeds 60 days (non-compliant on its face) |
| H-5 | Return/destroy provision absent (Section 1.7) |

---

## Negotiation Summary Template

```
BAA REVIEW SUMMARY
----------------------------------------------
Vendor:
Product / Service:
BAA Version:
Review Date:
Reviewed By:         Claude (AI-assisted review — requires legal review before signing)

SECTION 1 — MANDATORY ELEMENTS:
  All present:      Yes / No
  Missing:          [list item numbers]

SECTION 2 — BREACH NOTIFICATION:
  Notice window:    [X] days  (target: ≤30)
  Required elements complete: Yes / No

SECTION 3 — AI-SPECIFIC PROVISIONS:
  Model training prohibition (contractual): Present / Absent
  Data retention period:                    [X] days / Not specified
  Deletion capability:                      Present / Absent
  Subprocessor list commitment:             Present / Absent
  Version change notification:              Present / Absent

HARD STOPS IDENTIFIED:
  [List or "None"]

RECOMMENDED REDLINES:
  [Numbered list of specific changes to request]

RECOMMENDED ACTION:
  [ ] Sign as presented
  [ ] Sign after receiving redlines listed above
  [ ] Do not sign — requires material revision

OPEN ITEMS FOR VENDOR FOLLOW-UP:
  [List]
----------------------------------------------
```
