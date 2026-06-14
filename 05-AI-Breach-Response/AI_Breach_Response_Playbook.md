# AI-Related Breach Response Playbook
### HIPAA Breach Notification Rule — Incident Response Procedures

**Regulatory Basis:** 45 CFR §§164.400–414 — Covered entities must notify affected individuals, HHS, and (in certain circumstances) the media following a breach of unsecured PHI. Business associates must notify the covered entity.

---

## Scope

This playbook governs the response to suspected or confirmed breaches involving AI tools and automated systems. It covers:

- PHI accidentally entered into an unapproved or public AI tool
- PHI exposed through a vendor data breach affecting AI systems
- PHI improperly disclosed via AI-generated output
- Unauthorized AI system access resulting in PHI exposure

This playbook supplements—and does not replace—the organization's general HIPAA breach response procedures.

---

## Key Definitions

**Breach (45 CFR §164.402):** The acquisition, access, use, or disclosure of PHI in a manner not permitted by the HIPAA Privacy Rule, which compromises the security or privacy of the PHI.

**Unsecured PHI:** PHI that is not rendered unusable, unreadable, or indecipherable to unauthorized individuals through the use of a technology or methodology specified by HHS. Unencrypted PHI is unsecured PHI.

**Security Incident:** The attempted or successful unauthorized access, use, disclosure, modification, or destruction of information or interference with system operations. Not every security incident is a breach.

**Discovery Date:** A breach is considered discovered on the first day the covered entity knows, or by exercising reasonable diligence would have known, that a breach occurred.

---

## Breach Response Phases

### Phase 1: Detection and Initial Triage (Day 0–1)

**Trigger events — initiate this playbook if any of the following are reported or observed:**

| Trigger | Example |
|---|---|
| Workforce member reports entering PHI into an unapproved AI tool | "I accidentally pasted a patient list into ChatGPT" |
| AI vendor notifies the organization of a data breach or security incident | Vendor email or phone call describing unauthorized access to customer data |
| Audit log review reveals PHI in AI tool query logs | Log analysis shows protected health information in API request payloads |
| AI-generated document contains PHI from another patient | Clinician notices output references a different patient's record |
| Unauthorized individual found to have accessed AI system containing PHI | IT reports an unknown account accessed the organization's AI workspace |

**Immediate actions (complete within 24 hours of detection):**

| # | Action | Responsible Party |
|---|---|---|
| 1.1 | Confirm detection — gather basic facts: what tool, what PHI, when, who, how many individuals potentially affected | Privacy Officer / Incident Responder |
| 1.2 | Contain the incident — take the minimum necessary action to stop ongoing exposure (disable account, revoke API key, contact vendor to suspend processing) | IT Security |
| 1.3 | Preserve evidence — do not delete query logs, email records, or screenshots that document the incident | IT Security / Privacy Officer |
| 1.4 | Open a formal incident record — document the date of discovery and all known facts | Privacy Officer |
| 1.5 | Notify Privacy Officer and Security Officer if not already involved | Incident Responder |
| 1.6 | Classify as Security Incident pending full breach determination — the 60-day notification clock begins on the discovery date | Privacy Officer |

---

### Phase 2: Breach Determination (Day 1–5)

Apply the HIPAA 4-factor risk assessment to determine whether the incident constitutes a reportable breach. An impermissible use or disclosure is presumed to be a breach unless the covered entity can demonstrate that there is a low probability that PHI has been compromised based on all four factors.

**4-Factor Risk Assessment (45 CFR §164.402(2)):**

| Factor | Questions to Answer | Finding |
|---|---|---|
| **Factor 1:** Nature and extent of the PHI involved, including types of identifiers and likelihood of re-identification | What PHI elements were exposed? (Name, DOB, SSN, diagnosis, treatment, insurance?) What is the re-identification risk? Were sensitive categories involved (mental health, substance use, HIV, reproductive health)? | |
| **Factor 2:** The unauthorized person who used or to whom the disclosure was made | Who received or could have received the PHI? Was it an AI vendor with a BAA? A public tool with no BAA? An unknown third party? What is the likelihood they would misuse the information? | |
| **Factor 3:** Whether the PHI was actually acquired or viewed | Can it be demonstrated that the data was not accessed or viewed beyond its initial exposure? Was the vendor able to confirm deletion of the query before processing? Was access technically prevented? | |
| **Factor 4:** The extent to which the risk to the PHI has been mitigated | Were steps taken to destroy or recover the PHI? Did the vendor confirm deletion? Was the affected individual notified and protective action taken? | |

**Determination outcomes:**

| Outcome | Condition | Action |
|---|---|---|
| **Breach — notification required** | Cannot demonstrate low probability of compromise across all four factors | Proceed to Phase 3 |
| **Not a breach — document and close** | All four factors support low probability of compromise | Document findings, retain record for 6 years, close incident |
| **Inconclusive — escalate** | Cannot make a determination with available information | Engage legal counsel; treat as breach pending further investigation |

**Documentation requirement:** The 4-factor analysis must be documented in writing and retained for 6 years regardless of outcome.

---

### Phase 3: Notification Planning (Day 5–20)

If the incident is determined to be a reportable breach, plan notifications to all required parties.

#### 3.1 Identify Affected Individuals

| Step | Action |
|---|---|
| 3.1.1 | Determine the number of individuals whose PHI was involved |
| 3.1.2 | Identify the specific individuals, if possible |
| 3.1.3 | Determine whether any affected individuals are in a state with shorter notification windows than the federal 60-day requirement |
| 3.1.4 | Identify any individuals whose PHI involved sensitive categories requiring enhanced handling |

#### 3.2 Notification Requirements Summary

| Recipient | Deadline | Threshold | Method |
|---|---|---|---|
| **Affected individuals** | ≤60 days after discovery | All individuals whose unsecured PHI was involved | Written notice (first-class mail; email if authorized) |
| **HHS** | ≤60 days after discovery | Breaches affecting ≥500 individuals | Online via HHS Breach Portal |
| **HHS (annual log)** | By March 1 of the following calendar year | Breaches affecting <500 individuals | Online via HHS Breach Portal |
| **Prominent media** | ≤60 days after discovery | Breaches affecting ≥500 residents of a single state or jurisdiction | Press release to major print/broadcast outlets |

#### 3.3 Required Content of Individual Notification (45 CFR §164.404(c))

Each notification to affected individuals must include:

| # | Required Element |
|---|---|
| 1 | Brief description of what happened, including the date of the breach and the date of discovery (if known) |
| 2 | Description of the types of unsecured PHI involved (e.g., name, SSN, date of birth, diagnosis) |
| 3 | Steps individuals should take to protect themselves from potential harm |
| 4 | Brief description of the covered entity's investigation and mitigation steps |
| 5 | Contact information (toll-free number, email, website, or postal address) for individuals to ask questions |

#### 3.4 AI-Specific Notification Language Guidance

When the breach involved an AI tool, consider including in the notification:

- A plain-language description of the AI tool involved (without jargon)
- A statement on whether the vendor confirmed deletion of the affected data
- An explanation of what has changed (e.g., the tool has been removed from authorized use)
- Reassurance about the nature of AI tool processing (if relevant to the individual's concern)

---

### Phase 4: Business Associate Coordination

If the breach originated with or was discovered by a business associate (AI vendor):

| Step | Action | Deadline |
|---|---|---|
| 4.1 | Confirm the vendor has provided formal written notification per the BAA terms | Confirm within 24 hours of vendor contact |
| 4.2 | Request the vendor's incident report, including: what happened, what data was affected, what mitigation was taken, and what the vendor's current risk assessment concludes | Within 5 business days |
| 4.3 | Confirm whether the vendor has deleted or returned all affected PHI | Within 5 business days |
| 4.4 | Assess whether the vendor breach notification provides sufficient information to complete the 4-factor risk assessment | Immediately upon receipt |
| 4.5 | Note: the covered entity's 60-day notification clock runs from the covered entity's discovery date — not from when the BA notified the CE. A delayed BA notification does not extend the CE's deadline. | Ongoing |

---

### Phase 5: Execution and Documentation (Day 20–60)

| Step | Action | Responsible Party | Target Date |
|---|---|---|---|
| 5.1 | Draft individual notification letters | Privacy Officer + Legal Counsel | Day 20–30 |
| 5.2 | Obtain executive review and approval of notification language | Privacy Officer | Day 30–40 |
| 5.3 | Send individual notifications | Privacy Officer | Day 40–55 |
| 5.4 | Submit HHS notification (or add to annual log) | Privacy Officer | Day 55–60 |
| 5.5 | Issue media notification if applicable | Communications + Legal | Day 55–60 |
| 5.6 | Retain copies of all notifications and supporting documentation | Privacy Officer | Ongoing — 6-year retention |

---

### Phase 6: Post-Incident Review (Day 60–90)

**Complete a post-incident review for all confirmed breaches and for significant near-misses.**

| Review Item | Questions |
|---|---|
| **Root cause analysis** | What specifically caused the incident? Was it a policy gap, a training gap, a technical control gap, or a vendor failure? |
| **Control effectiveness** | Did existing controls detect or prevent the incident? If not, why not? |
| **Process failure** | Was there a point where a correct decision could have prevented or limited the breach? |
| **Policy update needed?** | Does the Acceptable Use Policy, Vendor Risk Assessment process, or any other policy need revision? |
| **Training update needed?** | Does workforce training need to be updated or repeated as a result of this incident? |
| **Vendor action needed?** | Should this vendor's approval status be revisited? Should the BAA be renegotiated? |
| **Risk assessment update needed?** | Does the organization's HIPAA risk assessment need to be updated to reflect this incident as a new threat or vulnerability? |

**Post-incident review output:** Written findings document, retained for 6 years. Updated risk assessment if warranted.

---

## AI-Specific Incident Scenarios

### Scenario A: PHI Entered Into Unapproved Public AI Tool

**What happened:** A workforce member copy-pasted PHI (e.g., a patient note, a list of names, a lab result) into a consumer AI tool such as a free-tier chatbot not covered by a BAA.

**Key determinations:**
- Factor 2: The public AI vendor almost certainly does not have a BAA. Treating the disclosure as to an unauthorized party is the conservative and likely correct approach.
- Factor 3: Consumer AI tools typically process inputs for model improvement. Confirming the data was not "acquired or viewed" is very difficult. Default to treating as acquired.
- Factor 1: Severity depends on the sensitivity of the PHI involved.

**Likely outcome:** Reportable breach unless the PHI was minimal and sensitivity was very low. Engage legal counsel.

**Preventive control gap revealed:** Acceptable Use Policy not enforced; AI tool approval process absent; workforce training insufficient.

---

### Scenario B: Vendor Breach Exposing Stored Query Logs

**What happened:** An approved AI vendor (with a signed BAA) experienced a data breach. The vendor's notification states that query logs, including user-submitted content, were accessed by an unauthorized third party.

**Key determinations:**
- Factor 2: An unauthorized external party accessed the data. This is a significant negative factor.
- Factor 3: Unless the vendor can technically confirm that specific queries were not accessed, assume they were.
- Factor 4: Assess what the vendor has done — deletion, account isolation, patching. Evaluate credibility of the vendor's mitigation claims.

**Likely outcome:** Reportable breach if PHI was present in any query logs. Covered entity notification clock started when the CE discovered or was notified of the breach.

**Vendor response actions:** Request the vendor's full incident report. Evaluate whether continued BAA relationship is appropriate. Document all communications.

---

### Scenario C: PHI in AI-Generated Output Disclosed to Wrong Party

**What happened:** An AI tool generated a clinical summary or document containing PHI from one patient that was then sent to a different patient or to an unauthorized party.

**Key determinations:**
- This is a disclosure of PHI to an unauthorized person — the breach determination turns primarily on Factors 1 and 4.
- Factor 3 is not in question — the information was received by the wrong party.
- The AI system generated the error; investigate whether the underlying cause was a training data issue, a context window contamination, or a human workflow failure.

**Likely outcome:** Reportable breach. The disclosure itself is impermissible. Focus notification response on both the individual whose PHI was disclosed and any recipient who received PHI they were not authorized to receive.

**Post-incident action:** Review AI output verification procedures. Determine whether the use case requires enhanced human review before disclosure. Investigate whether the AI system has a cross-patient context leakage problem — whether the model or deployment configuration can generate outputs contaminated with other patients' data. This may require vendor investigation and warrant suspending the use case until root cause is confirmed.

---

### Scenario D: PHI Incorporated Into AI Model Training

**What happened:** PHI was used to fine-tune or pre-train an AI model, either by the covered entity or by a vendor processing the covered entity's data.

**Key determinations:**
- Factor 3 is complicated — PHI encoded in model weights may be accessible to anyone with access to the model, including via model inversion or membership inference attacks, even if the original training data is deleted. The model itself may constitute ongoing impermissible PHI storage with no analog in traditional breach scenarios.
- The 4-factor analysis applies, but this scenario requires legal and technical expertise beyond standard breach response.

**Likely outcome:** HIGH risk of reportable breach. The PHI may be unrecoverable from the model without destroying the model itself. Engage legal counsel with AI-specific technical knowledge before making the breach determination.

**Immediate actions:**
- Suspend model deployment pending legal and technical assessment.
- Engage legal counsel to assess whether model weights must be destroyed or can be retained under legal hold.
- Request the vendor's complete data lineage documentation: which data was used, in which training run, and whether it can be isolated or removed.

**Post-incident action:** Record this as a distinct risk category in the organization's HIPAA risk assessment (Threat T-02, Vulnerability V-03).

---

### Scenario E: PHI Belongs to Patients of Another Covered Entity

**What happened:** The PHI involved in the incident originates from a partner health system, a data sharing arrangement, or another covered entity — not from the covered entity managing the response.

**Examples:** Training data sourced from a partner's records; a data exchange that routed another covered entity's patient records through the organization's AI system; research data received under a data use agreement that was subsequently mishandled.

**Key determinations:**
- The responding organization may not be the covered entity with primary notification obligations to the affected individuals — the originating covered entity has independent HIPAA obligations to their own patients.
- Review the data sharing agreement or BAA between the organizations: who bears notification responsibility, and what are the contractual timelines?

**Required actions:**
1. Identify the originating covered entity and notify them promptly — do not wait for your own breach determination to be finalized before notifying them, as their 60-day clock runs independently.
2. Document the date and method of notification to the originating covered entity.
3. Determine, with legal counsel, whether the responding organization has independent notification obligations in addition to those of the originating covered entity.

---

## Incident Documentation Template

```
INCIDENT RECORD
----------------------------------------------
Incident ID:
Date/Time of Discovery:
Discovered By:
Description of Incident:

INITIAL FACTS:
  AI Tool / Vendor Involved:
  Type of PHI Involved:
  Estimated Number of Individuals Affected:
  Date(s) of Incident:

CONTAINMENT ACTIONS TAKEN:

4-FACTOR RISK ASSESSMENT:
  Factor 1 (Nature and extent):
  Factor 2 (Unauthorized person):
  Factor 3 (Acquired or viewed):
  Factor 4 (Risk mitigation):

DETERMINATION:
  [ ] Breach — notification required
  [ ] Not a breach — document and close
  [ ] Inconclusive — escalating to legal counsel

NOTIFICATIONS REQUIRED:
  Individuals:     Yes / No — Deadline: ___________
  HHS:             Yes / No — Deadline: ___________
  Media:           Yes / No — Deadline: ___________

NOTIFICATIONS COMPLETED:
  Individual letters sent:     Date: ___________
  HHS submission completed:    Date: ___________
  Media notification issued:   Date: ___________

POST-INCIDENT REVIEW COMPLETED:   Date: ___________

Records Retained By:
Retention Expiration:   (6 years from creation)
----------------------------------------------
```

---

## Regulatory Reference

| Requirement | Citation |
|---|---|
| Breach definition | 45 CFR §164.402 |
| 4-factor risk assessment | 45 CFR §164.402(2) |
| Individual notification requirements | 45 CFR §164.404 |
| 60-day notification deadline | 45 CFR §164.404(b) |
| Required content of notification | 45 CFR §164.404(c) |
| Media notification (≥500 in state) | 45 CFR §164.406 |
| HHS notification | 45 CFR §164.408 |
| Business associate breach notification obligation | 45 CFR §164.410 |
| 6-year documentation retention | 45 CFR §164.530(j) |
