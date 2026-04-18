# Breach Response Playbook Reference

## Regulatory Framework

HIPAA breaches involving AI systems are governed by the same rules as all other HIPAA breaches, with the additional complexity that AI vendors process data in ways that make factors 2 and 3 of the risk assessment more difficult to satisfy.

| Rule | Citation | Key Requirement |
|---|---|---|
| Breach definition | 45 CFR §164.402 | Impermissible use/disclosure presumed to be a breach unless low probability of compromise can be demonstrated |
| 4-factor risk assessment | 45 CFR §164.402(2) | Four specific factors must be assessed to rebut the breach presumption |
| Individual notification | 45 CFR §164.404 | All affected individuals notified ≤60 days of discovery |
| Media notification | 45 CFR §164.406 | Required if ≥500 residents of a single state or jurisdiction affected |
| HHS notification | 45 CFR §164.408 | ≤60 days for ≥500 individuals; annual log for <500 |
| BA notification obligation | 45 CFR §164.410 | BA must notify CE without unreasonable delay and ≤60 days |
| Documentation retention | 45 CFR §164.530(j) | 6 years from creation or last effective date |

---

## The 4-Factor Risk Assessment

The breach presumption is rebutted — and notification is NOT required — only if all four factors support a low probability that PHI has been compromised.

### Factor 1: Nature and Extent of PHI

**Increases severity:**
- Full name + other identifiers (DOB, SSN, address)
- Diagnosis, treatment, or medication information
- Mental health, substance use disorder, HIV status, reproductive health
- Financial information (account numbers, insurance IDs)
- Large volume of records

**Decreases severity:**
- Only a few de-identified elements with low re-identification risk
- Administrative information only (appointment times with no clinical detail)
- Very small number of individuals

**AI-specific consideration:** If the user pasted a full note or a data export, assume high sensitivity. If they typed a general question that incidentally revealed one patient's information, assess carefully.

### Factor 2: The Unauthorized Person

**Increases severity (harder to rebut):**
- Public AI tool with no BAA (e.g., consumer ChatGPT, Bard, Claude free tier)
- Unknown third party
- Malicious actor known to be motivated

**May decrease severity:**
- Approved vendor with a signed BAA (though this does not automatically make the disclosure authorized)
- Enterprise tool where the vendor has confirmed contractual data isolation

**AI-specific consideration:** Consumer-tier AI tools — even those from reputable vendors — almost always lack a BAA and routinely use inputs for model improvement. Disclosures to these tools are very difficult to characterize as low risk.

### Factor 3: Whether PHI Was Actually Acquired or Viewed

**Increases severity (harder to rebut):**
- Consumer AI tool that processes all inputs (no opt-out; no deletion mechanism)
- Vendor cannot confirm data was not retained or accessed
- Query logs known to be stored and accessible

**May decrease severity:**
- Vendor confirms real-time deletion before processing (and can document this)
- Technical analysis shows the data was blocked at a network layer before transmission
- The tool was offline at the time of the attempted submission

**AI-specific consideration:** This factor is very difficult to satisfy for public AI tools. Unlike a misdirected fax (where you can call the recipient and confirm deletion), AI input processing is often opaque. Default conservatively toward "acquired."

### Factor 4: Extent of Risk Mitigation

**Increases mitigation:**
- Vendor confirms deletion of specific query within hours
- Access revoked and the exposure was limited in time
- Individual notified promptly and protective actions taken
- Contractual right to deletion exercised successfully

**Decreases mitigation:**
- Vendor has no deletion capability
- Exposure duration was extended or unknown
- Data may have been used in model training before deletion request

---

## Notification Deadlines and Recipients

| Recipient | Deadline | Trigger | Notes |
|---|---|---|---|
| Affected individuals | ≤60 days from discovery | All reportable breaches | Written; first-class mail preferred; email if prior authorization |
| HHS (immediate) | ≤60 days from discovery | ≥500 individuals | Via HHS web portal; submit each breach separately |
| HHS (annual log) | By March 1 of following year | <500 individuals | Log format; submit all breaches from prior calendar year |
| Prominent media | ≤60 days from discovery | ≥500 residents of same state/jurisdiction | Press release to major print/broadcast media in affected area |

**Clock start:** The 60-day clock begins on the date of discovery — the first day the covered entity knew, or by exercising reasonable diligence would have known, of the breach. A BA's delayed notification does not extend the CE's deadline.

---

## AI-Specific Scenarios

### Scenario A: PHI in Unapproved Consumer AI Tool

**Risk assessment default posture:** HIGH. Treat as reportable breach unless specific evidence supports all four factors.

- Factor 2 is almost always adverse (no BAA; unknown data handling)
- Factor 3 is rarely satisfiable (no deletion mechanism; inputs often used for training)
- Err toward notification; consult legal counsel immediately

### Scenario B: Vendor Breach of Approved AI System (BAA in Place)

**Risk assessment:** Moderate complexity. The BAA establishes obligations but does not resolve the 4-factor analysis.

- Factor 2: Vendor had authorization to hold PHI, but the breach disclosed to an unauthorized party
- Factor 3: Request vendor technical report on what was accessed; do not assume logs were not viewed
- Factor 4: Assess vendor's mitigation actions critically; confirm in writing

**Key action:** The covered entity's clock runs from CE discovery, not from BA notification. Begin the 4-factor analysis immediately upon learning of the vendor breach, even before the vendor provides its full report.

### Scenario C: AI Output Discloses Wrong Patient's PHI

**Risk assessment:** HIGH if the output was disclosed to a patient or third party.

- The disclosure already occurred (to the wrong recipient)
- Factor 3 is not in question — the information was received
- Focus the analysis on Factor 1 (sensitivity) and Factor 4 (can the disclosed document be retrieved and confirmed destroyed?)

**Post-incident investigation:** Determine whether the AI system has a data contamination issue (cross-patient context leakage) that requires the vendor to investigate the model or the deployment configuration.

---

## Required Notification Elements (45 CFR §164.404(c))

Individual notification letters must include all five elements:

1. A brief description of what happened, including the date of the breach and date of discovery (if known)
2. A description of the types of unsecured PHI involved (e.g., full name, SSN, date of birth, diagnosis)
3. Steps the individual should take to protect themselves from potential harm
4. A brief description of what the covered entity is doing to investigate the breach, mitigate harm, and protect against future breaches
5. Contact information (toll-free phone number, email, website, or mailing address) for individuals to ask questions

---

## Status Indicators for Incident Assessment

| Status | Meaning |
|--------|---------|
| Confirmed | Fact established through documentation or direct knowledge |
| Unconfirmed | Asserted but not yet verified by documentation or vendor confirmation |
| Adverse | Factor weighs toward breach determination |
| Favorable | Factor weighs against breach determination (toward rebuttal) |
| Inconclusive | Insufficient information to assess; treat as Adverse pending clarification |
