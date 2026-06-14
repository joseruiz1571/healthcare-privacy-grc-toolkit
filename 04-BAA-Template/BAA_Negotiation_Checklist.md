# Business Associate Agreement Negotiation Checklist
### AI and Emerging Technology Vendors

**Regulatory Basis:** 45 CFR §164.504(e) — Covered entities may only permit a business associate to create, receive, maintain, or transmit ePHI on their behalf if the covered entity obtains satisfactory assurances, in the form of a written agreement, that the business associate will appropriately safeguard the information.

---

## How to Use This Checklist

Use this checklist in two ways:
1. **Reviewing a vendor-provided BAA** — check each item against the draft agreement and flag gaps
2. **Drafting or negotiating a BAA** — use each item as a required provision to include or negotiate

For AI vendors, the standard HIPAA BAA template is necessary but not sufficient. Items marked **[AI-SPECIFIC]** address risks unique to AI systems and must be negotiated explicitly — they will not appear in generic BAA templates.

---

## Section 1: Mandatory HIPAA BAA Elements (45 CFR §164.504(e)(2))

These are non-negotiable statutory requirements. A BAA missing any of these is legally deficient.

| # | Required Provision | Present? | Location in Agreement | Notes |
|---|---|---|---|---|
| 1.1 | Permitted uses and disclosures of PHI are specified and limited to what is necessary to perform services | Yes / No / Unclear | | |
| 1.2 | Business associate agrees not to use or further disclose PHI other than as permitted or required by the agreement or required by law | Yes / No / Unclear | | |
| 1.3 | Business associate agrees to use appropriate safeguards to prevent unauthorized use or disclosure of PHI | Yes / No / Unclear | | |
| 1.4 | Business associate agrees to report to the covered entity any unauthorized use or disclosure of PHI, including breaches under 45 CFR §164.410 | Yes / No / Unclear | | |
| 1.5 | Business associate agrees to ensure that any subcontractors who create, receive, maintain, or transmit PHI on behalf of the BA agree to the same restrictions | Yes / No / Unclear | | |
| 1.6 | Business associate agrees to make its internal practices, books, and records relating to PHI available to HHS for purposes of compliance determination | Yes / No / Unclear | | |
| 1.7 | At termination of the agreement, business associate agrees to return or destroy all PHI, or if return/destruction is not feasible, to extend protections to the PHI and limit further uses or disclosures | Yes / No / Unclear | | |

---

## Section 2: Breach Notification Obligations (45 CFR §164.410)

| # | Provision | Present? | Acceptable? | Notes |
|---|---|---|---|---|
| 2.1 | Business associate must notify the covered entity without unreasonable delay and no later than **60 calendar days** after discovery of a breach | Yes / No / Unclear | Yes / No | A shorter notice window (e.g., 10–30 days) is preferable and should be negotiated |
| 2.2 | Notification must include: identity of individuals affected; description of what happened; date of breach; date of discovery; PHI types involved | Yes / No / Unclear | Yes / No | |
| 2.3 | Notification must include the business associate's steps taken to investigate and mitigate the breach | Yes / No / Unclear | Yes / No | |
| 2.4 | Business associate must notify covered entity even for potential breaches pending the outcome of the 4-factor risk assessment | Yes / No / Unclear | Yes / No | |

**Negotiation note:** Many vendors default to the 60-day statutory maximum. Push for 10–30 days to give your organization time to meet its own notification obligations to individuals and HHS.

---

## Section 3: AI-Specific Provisions [AI-SPECIFIC]

These provisions are not in standard HIPAA BAA templates and must be explicitly negotiated with AI vendors.

| # | Provision | Present? | Acceptable? | Notes |
|---|---|---|---|---|
| 3.1 | **Model training prohibition:** Vendor agrees not to use customer-submitted PHI or de-identified data derived from customer PHI to train, fine-tune, or improve AI models | Yes / No / Unclear | Yes / No | This must be a **contractual obligation**, not a user-configurable setting. A setting can be changed unilaterally by the vendor; a contract cannot. |
| 3.2 | **Training opt-out survivability:** If a training opt-out exists, the agreement specifies that the opt-out remains in effect regardless of product tier changes, account migrations, or terms-of-service updates | Yes / No / Unclear | Yes / No | |
| 3.3 | **Data retention limit:** Agreement specifies a maximum retention period for query inputs, outputs, and associated metadata | Yes / No / Unclear | Yes / No | Shorter is better. Push for 30–90 days. Default vendor retention (often 30 days to 2 years) may not align with breach response needs. |
| 3.4 | **Deletion capability:** Covered entity has the right to request deletion of specific inputs or sessions containing PHI prior to standard retention expiration | Yes / No / Unclear | Yes / No | Critical for incident response — if PHI is accidentally entered, you need the ability to purge it |
| 3.5 | **Subprocessor disclosure:** Vendor provides and maintains a list of subprocessors who may access or process PHI, and commits to notifying the covered entity before adding new subprocessors | Yes / No / Unclear | Yes / No | Includes model hosting providers, logging services, and annotation vendors |
| 3.6 | **Subprocessor BAA chain:** Vendor confirms that all subprocessors with access to PHI are subject to BAA-equivalent agreements | Yes / No / Unclear | Yes / No | |
| 3.7 | **Model version change notification:** Vendor commits to providing advance notice of material changes to model behavior, data handling practices, or underlying model architecture | Yes / No / Unclear | Yes / No | Model updates can change how data is processed. You need time to re-assess compliance before updates are applied to your tenancy. |
| 3.8 | **Version pinning:** Agreement specifies whether the covered entity can pin to a specific model version and for how long | Yes / No / Unclear | Yes / No | |
| 3.9 | **Audit log access:** Covered entity can access, export, and retain audit logs of all user sessions and API calls | Yes / No / Unclear | Yes / No | Required for HIPAA audit controls (§164.312(b)) and breach investigation |
| 3.10 | **Right to audit:** Covered entity or its designee has the right to audit the vendor's compliance with the BAA terms, upon reasonable notice | Yes / No / Unclear | Yes / No | Many vendors resist this; at minimum negotiate the right to request SOC 2 reports and respond to security questionnaires |

---

## Section 4: Security Safeguards

| # | Provision | Present? | Acceptable? | Notes |
|---|---|---|---|---|
| 4.1 | Vendor commits to encryption in transit (TLS 1.2 or higher) | Yes / No / Unclear | Yes / No | |
| 4.2 | Vendor commits to encryption at rest (AES-256 or equivalent) | Yes / No / Unclear | Yes / No | |
| 4.3 | Vendor commits to maintaining a vulnerability management program | Yes / No / Unclear | Yes / No | |
| 4.4 | Vendor commits to an annual penetration test or equivalent security evaluation | Yes / No / Unclear | Yes / No | |
| 4.5 | Vendor provides evidence of current SOC 2 Type II certification upon request | Yes / No / Unclear | Yes / No | |

---

## Section 5: Termination Rights

| # | Provision | Present? | Acceptable? | Notes |
|---|---|---|---|---|
| 5.1 | Covered entity has the right to terminate the agreement immediately upon a material breach of the BAA by the business associate | Yes / No / Unclear | Yes / No | |
| 5.2 | Upon termination, vendor will return or destroy all PHI within a specified timeframe | Yes / No / Unclear | Yes / No | Negotiate a specific window (e.g., 30 days). "Upon termination" alone is insufficient. |
| 5.3 | If destruction is not feasible (e.g., PHI embedded in model weights), vendor must document why and extend equivalent protections indefinitely | Yes / No / Unclear | Yes / No | This is a realistic scenario for AI systems — address it explicitly |

---

## Negotiation Summary

```
BAA REVIEW SUMMARY
----------------------------------------------
Vendor:
Product / Service:
BAA Version Reviewed:
Review Date:
Reviewer:

STATUTORY ELEMENTS (Section 1):
  All present:    Yes / No
  Missing items:  [List]

BREACH NOTIFICATION (Section 2):
  Notice window:           [X] days  (target: ≤30 days)
  Required elements present: Yes / No

AI-SPECIFIC PROVISIONS (Section 3):
  Model training prohibition:      Yes / No / Absent
  Data retention specified:        Yes / No / Absent  ([X] days/months)
  Deletion capability:             Yes / No / Absent
  Subprocessor list committed:     Yes / No / Absent
  Version change notification:     Yes / No / Absent

HARD STOPS (any one = do not sign as-is):
  [ ] Model training prohibition absent with no alternative contractual control
  [ ] Subprocessor chain not covered by BAA-equivalent agreements
  [ ] Breach notification window > 60 days (non-compliant on its face)
  [ ] Return/destroy provision absent

RECOMMENDED ACTION:
  [ ] Sign as presented
  [ ] Sign with the following redlines: [list]
  [ ] Do not sign — request revision of: [list]

OPEN NEGOTIATION ITEMS:
  [List items to raise with vendor]
----------------------------------------------
```

---

## Appendix: Key Regulatory References

| Provision | Citation |
|---|---|
| BAA required elements | 45 CFR §164.504(e)(2) |
| Subcontractor BAA requirement | 45 CFR §164.504(e)(2)(ii)(D) |
| Breach notification by business associate | 45 CFR §164.410 |
| Breach definition and risk assessment | 45 CFR §164.402 |
| Termination for material breach | 45 CFR §164.504(e)(2)(iii) |
| HHS access to records | 45 CFR §164.504(e)(2)(ii)(H) |
