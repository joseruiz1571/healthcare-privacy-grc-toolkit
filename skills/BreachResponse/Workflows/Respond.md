# Respond Workflow

Guide the response to a suspected or confirmed HIPAA breach involving an AI tool or automated system. Produce a completed breach determination, notification plan, and incident record — not a blank template.

---

## Triage Gate

Before gathering full facts, ask three questions. If all answers are clearly favorable, run an abbreviated analysis and close as non-breach. Reserve the full workflow for genuinely ambiguous or adverse cases.

| # | Question | Answer |
|---|---|---|
| Q1 | Was PHI disclosed outside an authorized treatment, payment, or healthcare operations workflow? | Y / N / Unknown |
| Q2 | Did the disclosure reach a recipient not authorized to receive this PHI? | Y / N / Unknown |
| Q3 | Has the incident been fully contained with no PHI committed to any permanent record or external system? | Y / N |

**If Q1=N AND Q2=N AND Q3=Y:** Flag as likely non-breach. Run abbreviated 4-factor analysis, document the determination with the 6-year retention reminder, and close. Do not advance to the full workflow.

**All other combinations:** Proceed to Step 1.

---

## Step 1: Gather Incident Facts

Collect the following before proceeding. Mark gaps as "Requires Verification" and note what must be confirmed.

| Fact | Why It Matters |
|---|---|
| What AI tool or system was involved? | Determines BAA status and data handling protections |
| What PHI was involved? (types, identifiers, sensitivity) | Factor 1; triggers state law and 42 CFR Part 2 checks |
| How many individuals are potentially affected? | HHS notification type and media threshold |
| **What is the exact discovery date?** | Starts the 60-day clock — must be a specific calendar date, not "yesterday" or "Day 0" |
| When did the incident occur (if different from discovery)? | Exposure window |
| Who reported or discovered it? | Chain of custody for the incident record |
| What happened? (brief description) | All notifications and documentation |
| Has containment action been taken? | Determines whether further containment is needed |
| What state(s) does the covered entity operate in or provide services to? | Required for state law overlay |
| Was a BAA executed with the vendor before the incident? | Triggers no-BAA branch if absent |

**Timing action — required:** Immediately after capturing the discovery date, output:

> "Discovery date: [DATE]. Federal notification deadline: [DATE + 60 DAYS]. All notifications must be completed by this date."

If the user cannot provide an exact date, document as "Estimated discovery date: [approximate date] — requires verification." Use the estimate for all deadline calculations, flag it prominently, and note that the actual date must be confirmed.

---

## Step 1.5: State Law Overlay Check

After capturing facts, run a mandatory state law check before proceeding.

**Ask:** Confirm the state(s) where the covered entity is located and where affected individuals reside.

**Check:** Does the PHI involve any of the following sensitive categories?
- HIV/AIDS status or STI diagnosis
- Psychiatric or mental health records
- Substance use disorder records
- Genetic information
- Reproductive health information

**Surface applicable law when triggered.** Examples:

| Jurisdiction | Category | Law | Key Requirement |
|---|---|---|---|
| Texas | HIV/STI | TX Health & Safety Code §81.103 | Separate confidentiality protections; patient authorization typically required for disclosure |
| California | Medical records broadly | CA Civil Code §56.10 (CMIA) | State notification obligations; consult counsel on whether deadline is shorter than federal |
| California | HIV | CA Health & Safety Code §120980 | Enhanced disclosure restrictions |
| Federal | Substance use disorder | 42 CFR Part 2 | Separate federal framework — see Step 1.6 |
| All states | Any | State breach notification statutes | Many states impose notification windows shorter than 60 days |

This is not exhaustive. Flag that legal counsel must confirm applicable state law for the specific jurisdiction.

**If state law imposes a shorter deadline:** Insert that date into the notification timeline at Step 6 as the controlling deadline, and note it supersedes the federal window.

---

## Step 1.6: 42 CFR Part 2 Check — Substance Use Disorder Records

**Trigger:** PHI includes substance use disorder treatment records.

**Ask:** Is the originating program federally assisted (receives federal funding or holds a DEA registration)?

**If yes to both, flag immediately:**

> **42 CFR PART 2 FLAG:** This incident involves SUD records governed by 42 CFR Part 2, a separate federal confidentiality framework that applies in addition to HIPAA. Part 2 imposes stricter disclosure restrictions. The breach determination and notification response must be analyzed under both frameworks. Do not treat this as a HIPAA-only incident. Engage legal counsel with Part 2 experience before proceeding with notification.

Key distinctions to surface:
- Part 2 prohibits disclosure of SUD treatment records without patient consent except in narrow circumstances; the HIPAA breach notification framework does not automatically authorize those disclosures
- Individual notification may itself require patient authorization under Part 2 before it can be sent
- HHS notifications and media disclosures that identify the SUD program may independently violate Part 2

---

## Step 1.7: No-BAA Scenario Branch

**Trigger:** No BAA was executed with the vendor before the incident.

Flag as an independent HIPAA violation, separate from and in addition to the breach determination:

> **INDEPENDENT HIPAA VIOLATION:** Sharing PHI with a vendor without a signed BAA is a violation of 45 CFR §164.504(e) regardless of whether a reportable breach occurred. This requires separate remediation. Document this violation in the incident record alongside — but distinct from — the breach analysis.

Then prompt:
> "Was a BAA required and not obtained, or was the activity incorrectly believed to be exempt — for example, was de-identification assumed, a treatment exception claimed, or the vendor incorrectly categorized as not a business associate?"

The absence of a BAA does not change the 4-factor analysis — proceed with breach determination normally.

Add to post-incident remediation regardless of breach outcome:
- Immediately halt PHI sharing with the vendor
- Obtain a signed BAA before any future PHI sharing resumes
- Audit other vendor relationships for additional BAA gaps
- Update the vendor approval process to require BAA verification as a hard stop

---

## Step 1.8: Consumer / Unapproved AI Tool Branch

**Trigger:** Tool is a consumer-grade or unapproved AI product without an organizational BAA (e.g., ChatGPT Free/Plus, Microsoft Copilot personal, Google Gemini personal, Claude.ai personal, or any tool not covered by a signed organizational BAA).

Apply this guidance before the 4-factor analysis:

**Additional containment actions (add to Step 2):**
- Block the tool at the network level (DNS/firewall) to prevent recurrence
- File a written deletion request with the vendor immediately — document the request and any response received, even if the vendor denies the request or confirms no deletion mechanism exists
- Preserve all evidence of the submission (screenshots, session logs, sent history)

**4-factor pre-assessment:**
- Factor 2: Almost certainly Adverse — no BAA; data handling is not subject to organizational control
- Factor 3: Very difficult to satisfy — consumer tools typically process inputs for model improvement; confirming data was not retained or viewed requires vendor-provided written confirmation, which is rarely available

**Post-incident checklist additions (add to Step 8):**
- Obtain vendor data retention records in writing; document deletion request even if denied
- Initiate workforce discipline review per HIPAA §164.530(e)
- Assess whether the Acceptable Use Policy explicitly prohibits this tool and whether enforcement mechanisms are present

---

## Step 2: Containment Check

Confirm whether the incident is ongoing or contained before proceeding to breach analysis.

**Standard containment actions:**
- Disable the affected account or API key
- Contact the vendor to request suspension of processing and deletion of affected data
- Preserve all logs and evidence before any system changes

**Telemetry and transmission verification (when transmission is unconfirmed):**

If PHI may have been transmitted to an external system but transmission is not yet confirmed — for example, via IDE telemetry, browser extension autocomplete, or API calls whose logs have not been reviewed:

1. Send a written request to the vendor asking: (a) whether the submission was received and logged; (b) whether it was retained in any pipeline or training dataset; and (c) whether it can be deleted. Set a vendor response deadline of **5 business days**.
2. Until written confirmation of non-transmission or deletion is received, treat the transmission as confirmed for notification planning purposes.
3. Add "obtain written confirmation of telemetry/transmission status — deadline: [date]" to the containment checklist.
4. Document all vendor communications in the incident record, including non-responses.

---

## Step 3: Load Playbook Reference

Read `Playbook.md` for the full 4-factor analysis guidance, state law and 42 CFR Part 2 reference, scenario-specific guidance, and notification requirement details.

---

## Step 4: Conduct the 4-Factor Risk Assessment

Work through each factor. For each:
1. State the relevant facts
2. Identify whether facts are Confirmed / Unconfirmed / Inconclusive
3. Assess: **Adverse** (weighs toward breach) / **Favorable** (weighs toward rebuttal) / **Inconclusive** (treat as Adverse)
4. Note what additional information would resolve uncertainty

```markdown
## 4-Factor Risk Assessment

| Factor | Key Facts | Status | Assessment |
|--------|-----------|--------|------------|
| Factor 1: Nature and extent of PHI | | | Adverse / Favorable / Inconclusive |
| Factor 2: Who received the PHI | | | Adverse / Favorable / Inconclusive |
| Factor 3: Whether PHI was acquired/viewed | | | Adverse / Favorable / Inconclusive |
| Factor 4: Extent of risk mitigation | | | Adverse / Favorable / Inconclusive |
```

**Factor 1 — Sensitive category weighting:**
If PHI includes any of the following, increase the Factor 1 severity assessment by one level and note it explicitly, even if record volume is small:
- HIV/AIDS status or STI diagnosis
- Psychiatric or mental health records
- Substance use disorder records
- Genetic information
- Reproductive health information

Small volumes of sensitive-category PHI can cause significant individual harm. Volume alone does not determine Factor 1 severity.

**Factor 3 — Accessible-but-not-accessed distinction:**
Distinguish explicitly between:
- **Confirmed accessed:** Logs show a retrieval event, or the recipient has confirmed viewing
- **Accessible but unconfirmed:** A misconfiguration window existed; a message was delivered to the wrong inbox but may be unopened; data was reachable but no access event is logged

For the accessible-but-unconfirmed case: HHS guidance requires notification unless the covered entity can affirmatively demonstrate low probability of acquisition — this is a high bar. Treat as accessed for notification scoping unless logs definitively show no access event. Note this explicitly in the Factor 3 finding.

**Determination rules:**
- **BREACH:** Any factor is Adverse or Inconclusive and cannot be resolved with available information
- **NON-BREACH:** All four factors are Favorable AND the basis for each is documented in writing
- **INCONCLUSIVE:** Escalate to legal counsel; treat as BREACH for planning purposes

Apply scenario-specific guidance from `Playbook.md` (Scenarios A through E).

---

## Step 5: Produce Breach Determination

Output the determination block with machine-readable prefixes on the DETERMINATION line — not only in prose:

```
HIPAA BREACH DETERMINATION
----------------------------------------------
Incident:              [Brief description]
Discovery Date:        [Exact calendar date]
Federal Deadline:      [Exact calendar date = Discovery Date + 60 days]
State Deadline:        [Exact date if state law applies, or "N/A"]
DETERMINATION:         BREACH: / NON-BREACH: / INCONCLUSIVE:

BASIS:
  [2–4 sentences on the key factors driving the determination]

INDEPENDENT VIOLATIONS IDENTIFIED:
  [BAA gap, missing AUP enforcement, etc. — or "None"]

IF BREACH:
  Estimated individuals:  [Number or range]
  Notifications required:
    [ ] Affected individuals (deadline: [exact date])
    [ ] HHS — immediate portal (≥500 individuals) (deadline: [exact date])
    [ ] HHS — annual log (<500 individuals) (by March 1 of following year)
    [ ] Media — ≥500 residents of single state/jurisdiction (deadline: [exact date])

IF NON-BREACH:
  Basis documented:     Yes — retain this record for 6 years per 45 CFR §164.530(j)
  Retention expiration: [Creation date + 6 years]
----------------------------------------------
```

**After producing the determination, run these two additional checks:**

**BAA notification responsibility check:**
Review the BAA and prompt the organization to confirm:
- Does the BAA assign breach notification responsibility to the Business Associate or the Covered Entity?
- What is the BA's contractual notification window to the CE? (Statutory maximum: 60 days from BA's discovery; push for shorter in negotiations)
- If the vendor caused or contributed to the breach: document the BAA breach and flag that indemnification and liability terms should be reviewed by legal counsel.

**Model weights check (when PHI was used in AI training):**
If PHI may have been incorporated into AI model training or fine-tuning:

> **MODEL WEIGHTS FLAG:** PHI used in AI model training may be encoded in model weights and potentially recoverable via model inversion attacks. The model itself may constitute ongoing impermissible PHI storage with no analog in traditional breach scenarios. Recommended actions: (1) suspend model deployment immediately; (2) engage legal counsel to assess whether model weights must be destroyed or can be retained under legal hold; (3) request the vendor's data lineage documentation to determine scope of PHI incorporation.

---

## Step 6: Notification Plan (if breach)

### Individual Notification Draft

Draft a notification letter including all five required elements per 45 CFR §164.404(c). Use plain language; do not use technical jargon about AI systems.

### Notification Population Scoping

When the affected population is uncertain (e.g., logs confirm N access events but up to M records were accessible):
- Notify individuals whose records were **confirmed accessed** via log evidence — not the full universe of potentially accessible records
- Document the scoping methodology explicitly in the incident record
- If logs are unavailable or incomplete, default to the broader population
- Flag that this determination requires legal review before notifications are sent

### Multi-Entity / Compound Incident Handling

When a single incident involves multiple separate disclosure events (e.g., an EHR data export and a separate research data warehouse query):
- Enumerate each downstream disclosure as a separate event in the incident record
- Assess each event independently for notification obligations — each may have its own discovery date and notification clock
- Flag when a secondary disclosure may constitute a separate breach

### Originating Third-Party Check

When PHI belongs to patients of a different covered entity (e.g., a partner health system's data used in training, or a shared data exchange):
- Identify the originating covered entity — they have independent notification obligations to their own patients
- Review the data sharing agreement or BAA between organizations: does it assign breach notification responsibility and specify timelines?
- Notify the originating CE promptly so they can fulfill their own HIPAA obligations

### HHS Notification Summary

Identify which notification type is required and provide the key fields for the HHS web portal submission.

### Notification Timeline

Map all deadlines to specific calendar dates:

| Milestone | Target Date |
|---|---|
| Discovery date (clock starts) | [Exact date] |
| Breach determination complete | [Date + 5 days] |
| Affected individuals identified; population scoped | [Date + 20 days] |
| Notification letters drafted and legally reviewed | [Date + 40 days] |
| Individual notifications sent | [Date + 55 days] |
| HHS / media notification | [Date + 59 days] |
| State law deadline (if shorter than federal) | [Exact date] |

---

## Step 7: Complete Incident Record

Populate the incident record template from `Playbook.md` with all known facts, the 4-factor analysis, the determination, and notification plan.

**Documentation retention applies to ALL outcomes — breach and non-breach alike:**
- Both determinations are required compliance records under 45 CFR §164.530(j)
- Retention period: 6 years from the date of creation
- Add the retention expiration date to every incident record before closing

Note prominently: this record requires review and sign-off by the Privacy Officer before it is considered final.

---

## Step 8: Post-Incident Review Checklist

Produce a checklist tailored to the specific incident:

1. **Root cause:** What specific gap (policy, training, technical control, vendor) enabled this incident?
2. **Control gap:** Which existing control failed or was absent?
3. **Policy update:** Does the Acceptable Use Policy or any other policy need revision?
4. **Training:** Does workforce training need to be updated or repeated?
5. **Vendor relationship:** Should the vendor's approval status or BAA terms be revisited?
6. **Risk assessment update:** Does the HIPAA risk assessment need to reflect this incident as a confirmed threat or vulnerability?

**Workforce discipline track (when incident involved workforce action):**

First, characterize the nature of the violation — this affects disciplinary response but does not affect the notification obligation:
- **Intentional violation:** Employee knowingly used an unapproved tool or disclosed PHI without authorization
- **Negligence:** Employee failed to follow a policy they knew or should have known existed
- **Good-faith error:** Employee was unaware of the policy or reasonably misunderstood an ambiguous situation

Required post-incident actions regardless of characterization:

- [ ] Initiate workforce disciplinary review per HIPAA §164.530(e); document the process and outcome in writing
- [ ] Retrain the affected workforce member on the Acceptable Use Policy and relevant HIPAA obligations; require a signed acknowledgment upon completion
- [ ] Assess whether the Acceptable Use Policy requires revision or whether enforcement mechanisms (technical controls, monitoring, access restrictions) are insufficient to prevent recurrence
- [ ] If this is a repeat violation by the same individual: escalate to HR and assess whether termination is warranted under the organization's sanction policy

---

## Notes for Agentic Use

If invoked by an agent rather than a human:
- Accept incident description as structured or unstructured text input
- Return the completed breach determination and notification plan as structured markdown
- The Breach Determination block is the primary machine-readable output
- Use these prefixes on the DETERMINATION line (not only in prose) for reliable downstream parsing:
  - `BREACH:` — confirmed breach requiring notification
  - `NON-BREACH:` — confirmed non-breach; documentation required
  - `INCONCLUSIVE:` — requires legal escalation; treat as BREACH for planning
- Always output the discovery date and notification deadline as specific calendar dates, never relative offsets
- Always surface the 6-year retention reminder for both BREACH and NON-BREACH outcomes
- Always include the Privacy Officer sign-off reminder — this output requires human review before any notifications are sent
