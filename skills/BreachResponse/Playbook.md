# Breach Response Playbook Reference

## Regulatory Framework

HIPAA breaches involving AI systems are governed by the same rules as all other HIPAA breaches, with the additional complexity that AI vendors process data in ways that make Factors 2 and 3 of the risk assessment more difficult to satisfy. Some incidents also trigger parallel frameworks that must be analyzed independently.

| Rule | Citation | Key Requirement |
|---|---|---|
| Breach definition | 45 CFR §164.402 | Impermissible use/disclosure presumed to be a breach unless low probability of compromise can be demonstrated across all four factors |
| 4-factor risk assessment | 45 CFR §164.402(2) | All four factors must support low probability to rebut the breach presumption |
| Individual notification | 45 CFR §164.404 | All affected individuals notified ≤60 days of discovery |
| Media notification | 45 CFR §164.406 | Required if ≥500 residents of a single state or jurisdiction affected |
| HHS notification | 45 CFR §164.408 | ≤60 days for ≥500 individuals; annual log for <500 |
| BA notification obligation | 45 CFR §164.410 | BA must notify CE without unreasonable delay and ≤60 days of BA's discovery |
| BAA requirement | 45 CFR §164.504(e) | Sharing PHI with a vendor without a BAA is an independent HIPAA violation |
| Documentation retention | 45 CFR §164.530(j) | 6 years from creation or last effective date — applies to both breach and non-breach determinations |
| SUD records (parallel framework) | 42 CFR Part 2 | Stricter confidentiality rules for substance use disorder treatment records from federally assisted programs |

---

## The 4-Factor Risk Assessment

The breach presumption is rebutted — and notification is NOT required — only if all four factors support a low probability that PHI has been compromised.

### Factor 1: Nature and Extent of PHI

**Increases severity:**
- Full name combined with other identifiers (DOB, SSN, address)
- Diagnosis, treatment, medication, or clinical note content
- Financial information (account numbers, insurance IDs)
- Large volume of records

**Sensitive category enhanced weighting — increases severity even at low volume:**
If the PHI includes any of the following categories, increase Factor 1 severity by one level regardless of record count. These categories carry higher harm probability due to stigma, discrimination risk, and targeted legal protections:
- HIV/AIDS status or STI diagnosis
- Psychiatric or mental health records
- Substance use disorder records (also triggers 42 CFR Part 2 analysis)
- Genetic information
- Reproductive health information (abortion history, fertility treatment, contraception)

**Decreases severity:**
- Only minimally identifiable elements with low re-identification risk
- Administrative information only (appointment times with no clinical detail)
- Very small number of individuals with non-sensitive categories

**AI-specific note:** If the user pasted a full clinical note or data export, assume high sensitivity. If they typed a general question that incidentally referenced one patient, assess each element carefully.

---

### Factor 2: The Unauthorized Person

**Increases severity (harder to rebut):**
- Consumer AI tool with no BAA — data handling outside organizational control
- Unknown third party
- Malicious actor with demonstrated capability or motive

**May decrease severity:**
- Approved enterprise vendor with a signed BAA (though this does not automatically make the disclosure authorized — breach determination still required)
- Enterprise tool with confirmed contractual data isolation

**AI-specific note:** Consumer-tier AI tools — even those from reputable vendors — almost always lack a BAA and routinely process inputs for model improvement. Disclosures to these tools are very difficult to characterize as low-probability.

---

### Factor 3: Whether PHI Was Actually Acquired or Viewed

**Accessible-but-not-accessed distinction:**

Explicitly distinguish between these two situations:

| Situation | Description | Assessment Guidance |
|---|---|---|
| **Confirmed accessed** | Logs show a retrieval event; recipient confirms viewing | Factor 3 is Adverse |
| **Accessible, access unconfirmed** | Misconfiguration window existed; message sent to wrong inbox but possibly unopened; data reachable but no log entry of access | Treat as Adverse unless logs affirmatively show no access — the CE bears the burden of demonstration, not just the absence of confirmed access |
| **Confirmed not accessed** | Vendor provides written confirmation of real-time deletion before processing; technical blocking confirmed; tool was offline | Factor 3 may be Favorable — document the basis in writing |

**HHS standard:** The CE must demonstrate low probability of acquisition — the absence of confirmed access is not the same as demonstrated non-access.

**Increases severity (harder to rebut):**
- Consumer AI tool with no deletion mechanism; inputs processed for model improvement
- Vendor cannot confirm data was not retained or processed
- Query logs known to be stored

**May decrease severity:**
- Vendor provides written confirmation of real-time deletion before processing
- Technical analysis confirms blocking at the network layer before transmission
- Tool was offline and submission was never received

**AI-specific note:** Unlike a misdirected fax — where you can call the recipient and confirm physical destruction — AI input processing is often opaque. Default conservatively.

---

### Factor 4: Extent of Risk Mitigation

**Increases mitigation:**
- Vendor confirms deletion of specific query in writing within hours
- Access revoked and exposure window was brief and bounded
- Affected individuals promptly notified and protective actions taken
- Contractual deletion right exercised successfully

**Decreases mitigation:**
- Vendor has no deletion capability
- Exposure duration extended or unknown
- Data may have been incorporated into model training before the deletion request

---

## State Law Overlay

Federal HIPAA sets a floor. Many states impose additional or stricter requirements — particularly for sensitive PHI categories and breach notification timelines. State law overlay must be assessed for every incident.

**Notification deadline:** If applicable state law imposes a notification window shorter than 60 days, the state deadline is the controlling deadline for individuals in that state.

**Key examples (non-exhaustive):**

| Jurisdiction | Category | Law | Practitioner Note |
|---|---|---|---|
| Texas | HIV/STI | TX Health & Safety Code §81.103 | Separate confidentiality protections independent of HIPAA; disclosure often requires specific patient authorization |
| California | Medical records | CA Civil Code §56.10 (CMIA) | Separate state notification obligations; consult counsel on timeline |
| California | HIV | CA Health & Safety Code §120980 | Enhanced restrictions on disclosure of HIV-related information |
| All states | Any | State breach notification statutes | Many states (e.g., NY, MA, CO) impose notification windows <60 days and/or broader definitions of "personal information" |

**Always:** Confirm applicable state law requirements with legal counsel for the specific jurisdiction(s) where the CE operates and where affected individuals reside.

---

## 42 CFR Part 2 — Substance Use Disorder Records

**Trigger:** PHI includes substance use disorder treatment records AND the originating program is federally assisted (receives federal funding or holds a DEA registration).

**Why this matters:** 42 CFR Part 2 is a separate federal confidentiality framework that is stricter than HIPAA on disclosure restrictions. An incident involving Part 2 records is not a HIPAA-only matter and requires parallel analysis.

**Key distinctions:**

| Issue | HIPAA | 42 CFR Part 2 |
|---|---|---|
| Individual notification | Permitted as part of breach response | May require patient consent before notification disclosing SUD treatment context |
| HHS notification | Required for reportable breaches | Disclosures that identify the SUD program may independently violate Part 2 |
| Media notification | Required if ≥500 in state | Part 2 may restrict public identification of the program |
| Enforcement | HHS OCR | HHS and DOJ |

**Required action:** Engage legal counsel with 42 CFR Part 2 experience before proceeding with any notifications in a Part 2 incident.

---

## Notification Deadlines and Recipients

| Recipient | Deadline | Trigger | Notes |
|---|---|---|---|
| Affected individuals | ≤60 days from CE's discovery | All reportable breaches | Written; first-class mail preferred; email if prior authorization obtained |
| HHS (immediate) | ≤60 days from CE's discovery | ≥500 individuals | Via HHS web portal; submit each breach separately |
| HHS (annual log) | By March 1 of following year | <500 individuals | Log format; all breaches from prior calendar year |
| Prominent media | ≤60 days from CE's discovery | ≥500 residents of same state/jurisdiction | Press release to major print/broadcast media |

**Clock start:** The 60-day clock begins on the date the covered entity knew, or by exercising reasonable diligence would have known, of the breach. A BA's delayed notification to the CE does not extend the CE's deadline — the CE's clock starts at the CE's discovery, not when the BA gets around to reporting.

---

## Notification Population Scoping

When the affected population is uncertain:

| Situation | Approach |
|---|---|
| Logs confirm specific records were accessed | Notify those individuals; document the log evidence supporting the scope |
| Logs confirm access events but not which specific records | Notify all individuals whose records were reachable during the access window |
| Logs unavailable or incomplete | Default to the broader population of potentially affected individuals |
| Large universe accessible, small number confirmed | Document the scoping methodology explicitly; obtain legal review before limiting notifications |

**Principle:** The CE bears the burden of demonstrating that specific individuals were not affected. When in doubt, notify the broader group. Undernotification creates greater legal exposure than overnotification.

---

## BAA Notification Responsibility

After a breach determination, review the BAA for notification responsibility allocation:

| Question | Why It Matters |
|---|---|
| Does the BAA assign notification responsibility to the CE or the BA? | Determines who drafts and sends individual notifications |
| What is the BA's contractual notification window to the CE? | Must be ≤60 days of BA's discovery; shorter is better — this is what to negotiate |
| Did the BA notify within its contractual window? | If not, this is itself a material BAA breach |
| Does the BAA address liability and indemnification for BA-caused breaches? | Relevant for cost recovery; engage legal counsel |

If the vendor caused or contributed to the breach and failed to notify within the contractual window: document the BAA breach and flag indemnification terms for legal review.

---

## AI-Specific Scenarios

### Scenario A: PHI in Unapproved Consumer AI Tool

**Default posture:** HIGH risk. Treat as reportable breach unless specific evidence supports all four factors.

**Pre-assessment findings:**
- Factor 2: Adverse — consumer tools have no BAA; data handling is outside organizational control
- Factor 3: Very difficult to satisfy — consumer tools process inputs for model improvement and lack deletion mechanisms; written vendor confirmation is rarely available

**Containment specifics:**
- Block the tool at the network level (DNS/firewall) to prevent recurrence
- File a written deletion request with the vendor immediately — document the request and any response, even denial
- Preserve all submission evidence (session logs, browser history, sent history)

**Post-incident:**
- Obtain vendor data retention records in writing
- Initiate workforce disciplinary review (see Respond.md Step 8)
- Review whether the Acceptable Use Policy explicitly prohibits this tool and whether technical enforcement is present

---

### Scenario B: Vendor Breach of Approved AI System (BAA in Place)

**Risk assessment:** Moderate complexity. A BAA establishes obligations but does not resolve the 4-factor analysis.

- Factor 2: Vendor had authorization to hold PHI, but the breach disclosed to an unauthorized party — Adverse
- Factor 3: Request vendor technical report on what was accessed; do not assume logs were not viewed — default Adverse pending written confirmation
- Factor 4: Assess vendor mitigation actions critically; require written confirmation of all claims

**Key action:** The CE's 60-day clock runs from CE's discovery, not from BA notification. Begin the 4-factor analysis immediately upon learning of the vendor breach, before the vendor provides its full report.

**Telemetry and transmission verification:**
When PHI may have been transmitted but transmission is unconfirmed (e.g., API logs not yet reviewed, IDE telemetry, background sync):
1. Request written confirmation from the vendor within 5 business days: was the data received, retained, and can it be deleted?
2. Treat as transmitted for planning purposes until written confirmation is received
3. Document all vendor communications including non-responses

---

### Scenario C: AI Output Discloses Wrong Patient's PHI

**Risk assessment:** HIGH if the output was disclosed to a patient or third party.

- Factor 3 is not in question — the information was received by the wrong party
- Focus analysis on Factor 1 (sensitivity of the PHI) and Factor 4 (can the disclosed document be retrieved and confirmed destroyed?)

**Post-incident investigation:** Determine whether the AI system has a cross-patient context leakage problem — whether the model or deployment configuration can generate outputs contaminated with other patients' data. This may require vendor investigation and may warrant suspending the use case until root cause is confirmed.

---

### Scenario D: PHI Incorporated Into AI Model Training

**Novel risk — no analog in traditional breach scenarios.**

**What happened:** PHI was used to fine-tune or pre-train an AI model, either by the covered entity or by a vendor processing the CE's data.

**Key risk:** PHI incorporated into model weights may be recoverable via model inversion attacks or membership inference attacks, even if the original training data is deleted. The model itself may constitute ongoing impermissible PHI storage.

**Immediate actions:**
- Suspend model deployment pending legal and technical assessment
- Engage legal counsel to assess whether model weights must be destroyed or can be retained under legal hold
- Request the vendor's complete data lineage documentation: which data was used, in which training run, and whether it can be isolated or removed

**Breach determination:** The 4-factor analysis applies, but Factor 3 is complicated — PHI encoded in model weights is potentially "accessible" to anyone with access to the model, including via inference attacks, even if it cannot be directly retrieved. Engage counsel with AI-specific technical knowledge.

**Documentation:** Record this as a distinct risk category in the organization's HIPAA risk assessment (Threat T-02, Vulnerability V-03 in the Risk Assessment Template).

---

### Scenario E: PHI Belongs to Patients of Another Covered Entity

**Trigger:** The PHI involved in the incident originates from a partner health system, a data sharing arrangement, or another covered entity — not from the CE managing the response.

**Examples:**
- Training data sourced from a partner health system's records
- A data exchange that routed another CE's patient records through the organization's AI system
- Research data received under a data use agreement that was subsequently mishandled

**Required actions:**
1. Identify the originating covered entity — they have independent HIPAA notification obligations to their own patients that they can only meet if notified promptly
2. Notify the originating CE as soon as the incident is confirmed — do not wait for the CE's own breach determination to be finalized
3. Review the data sharing agreement or BAA between the organizations: who bears notification responsibility, and what are the contractual timelines?
4. The originating CE may have a separate discovery date and separate 60-day clock; document the date your organization notified them

---

## Multi-Entity / Compound Incident Handling

When a single root incident involves multiple separate disclosure events:
- Enumerate each downstream disclosure as a separately identified event in the incident record (Event 1, Event 2, etc.)
- Assess each event independently — separate 4-factor analysis, separate notification obligation, potentially separate discovery dates
- Flag when a secondary disclosure may constitute a separate breach with its own 60-day clock
- If notification populations overlap between events, note the overlap and avoid duplicate individual notifications while ensuring full coverage

---

## Required Notification Elements (45 CFR §164.404(c))

Individual notification letters must include all five elements:

1. A brief description of what happened, including the date of the breach and date of discovery (if known)
2. A description of the types of unsecured PHI involved (e.g., full name, SSN, date of birth, diagnosis)
3. Steps the individual should take to protect themselves from potential harm
4. A brief description of what the covered entity is doing to investigate the breach, mitigate harm, and protect against future breaches
5. Contact information (toll-free phone number, email, website, or mailing address) for individuals to ask questions

**AI-specific notification language guidance:** Use plain language. Do not use terms like "large language model," "prompt," or "inference." Describe the tool as "an AI writing assistant" or "an automated documentation tool" as appropriate. If the vendor confirmed deletion, state that plainly. Explain what has changed operationally.

---

## Status Indicators for Incident Assessment

| Status | Meaning |
|--------|---------|
| Confirmed | Fact established through documentation or direct knowledge |
| Unconfirmed | Asserted but not yet verified by documentation or vendor confirmation |
| Adverse | Factor weighs toward breach determination |
| Favorable | Factor weighs against breach determination (toward rebuttal) |
| Inconclusive | Insufficient information to assess; treat as Adverse pending clarification |
| Accessible — Unconfirmed Access | PHI was reachable by an unauthorized party but access is not confirmed; treat as Adverse unless logs affirmatively show no access event |
