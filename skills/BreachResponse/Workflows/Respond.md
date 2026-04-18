# Respond Workflow

Guide the response to a suspected or confirmed HIPAA breach involving an AI tool or automated system. Produce a completed breach determination, notification plan, and incident record — not a blank template.

## Step 1: Gather Incident Facts

Collect the following information before proceeding. If the user cannot provide all details, proceed with available information and mark gaps as "Requires Verification."

| Fact | Why It Matters |
|---|---|
| What AI tool or system was involved? | Determines whether a BAA exists and what data handling protections apply |
| What PHI was involved? (types, identifiers, sensitivity) | Factor 1 of the risk assessment |
| How many individuals are potentially affected? | Determines HHS notification type (immediate vs. annual log) and media notification threshold |
| When did the incident occur? | Helps establish the exposure window |
| When was it discovered? | Starts the 60-day notification clock |
| Who reported or discovered it? | Establishes the chain of custody for the incident record |
| What happened? (brief description) | Needed for all notifications and documentation |
| Has containment action been taken? | Guides whether further containment is needed |

**Important timing reminder:** State immediately that the 60-day notification clock began on the date of discovery. Even if the breach determination is pending, document the discovery date and count down from it.

## Step 2: Containment Check

Before proceeding to the breach analysis, confirm whether the incident is still ongoing or has been contained.

If the incident is ongoing (e.g., a tool is still processing PHI, an account is still active), advise immediate containment actions:
- Disable the affected account or API key
- Contact the vendor to request suspension of processing and deletion of affected data
- Preserve all logs and evidence before any system changes

## Step 3: Load Playbook Reference

Read `Playbook.md` for the full 4-factor analysis guidance, scenario-specific guidance, and notification requirement details.

## Step 4: Conduct the 4-Factor Risk Assessment

Work through each factor explicitly. For each:
1. State the relevant facts
2. Identify whether those facts are Confirmed / Unconfirmed / Inconclusive
3. Assess whether the factor weighs Adverse or Favorable toward a breach determination
4. Note what additional information would resolve uncertainty

**Output the assessment as a structured table:**
```markdown
## 4-Factor Risk Assessment

| Factor | Key Facts | Status | Assessment |
|--------|-----------|--------|------------|
| Factor 1: Nature and extent of PHI | | | Adverse / Favorable / Inconclusive |
| Factor 2: Who received the PHI | | | Adverse / Favorable / Inconclusive |
| Factor 3: Whether PHI was acquired/viewed | | | Adverse / Favorable / Inconclusive |
| Factor 4: Extent of risk mitigation | | | Adverse / Favorable / Inconclusive |
```

**Determination rules:**
- **Breach — notification required:** Any factor is Adverse or Inconclusive and cannot be resolved
- **Not a breach:** All four factors are Favorable AND the basis for each is documented
- **Inconclusive:** Escalate to legal counsel; treat as breach for planning purposes

Apply scenario-specific guidance from `Playbook.md` for consumer AI tools (Scenario A), vendor breaches (Scenario B), and wrong-party output (Scenario C).

## Step 5: Produce Breach Determination

State the determination clearly:

```
BREACH DETERMINATION
----------------------------------------------
Incident:         [Brief description]
Discovery Date:   [Date]
Determination:    Breach — Notification Required / Not a Breach / Inconclusive

BASIS:
  [2–4 sentence summary of the key factors driving the determination]

IF BREACH:
  Notification deadline:  [60 days from discovery date = specific date]
  Estimated individuals:  [Number]
  Notification required to:
    [ ] Affected individuals
    [ ] HHS (immediate — ≥500)
    [ ] HHS (annual log — <500)
    [ ] Media (≥500 in single state/jurisdiction)
----------------------------------------------
```

## Step 6: Notification Plan (if breach)

If the determination is Breach, produce a notification plan:

1. **Individual notification draft** — Produce a draft notification letter including all five required elements per 45 CFR §164.404(c). Tailor the description of the AI tool and incident to plain language appropriate for affected individuals.

2. **HHS notification summary** — Identify which notification type is required (immediate portal submission vs. annual log) and provide the key fields the organization will need to complete.

3. **Timeline** — Map out the 60-day window with recommended milestones:
   - Day 0: Discovery date (clock starts)
   - Day 1–5: Complete breach determination
   - Day 5–20: Identify affected individuals; draft notifications
   - Day 20–40: Legal review of notification language
   - Day 40–55: Send individual notifications
   - Day 55–60: Submit HHS notification

## Step 7: Complete Incident Record

Populate the incident record template from `Playbook.md` with all known facts, the 4-factor analysis, the determination, and notification plan. This document:
- Is required for HIPAA compliance regardless of breach/non-breach outcome
- Must be retained for 6 years
- Serves as the primary evidence in an HHS investigation or audit

Note prominently: This record requires review and sign-off by the Privacy Officer before it is considered final.

## Step 8: Post-Incident Review Checklist

After the immediate response is complete, prompt the organization to conduct a post-incident review. Produce a checklist tailored to the specific incident:

1. Root cause: What specific gap (policy, training, technical control, vendor) enabled this incident?
2. Control gap: Which existing control failed or was absent?
3. Policy update: Does the Acceptable Use Policy or any other policy need revision?
4. Training: Does workforce training need to be updated or repeated?
5. Vendor relationship: Should the vendor's approval status or BAA terms be revisited?
6. Risk assessment: Does the organization's HIPAA risk assessment need to be updated?

## Notes for Agentic Use

If invoked by an agent rather than a human:
- Accept incident description as structured or unstructured text input
- Return the completed breach determination and notification plan as structured markdown
- The Breach Determination block is the primary machine-readable output
- Flag breach determinations with the prefix `BREACH:` and non-breaches with `NON-BREACH:` for downstream parsing
- Always include the Privacy Officer sign-off reminder — this output requires human review before any notifications are sent
- Always state the discovery date and notification deadline in the output — these are time-critical
