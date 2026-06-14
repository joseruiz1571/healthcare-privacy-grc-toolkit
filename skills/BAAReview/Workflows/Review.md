# Review Workflow

Review a Business Associate Agreement for HIPAA compliance and AI-specific adequacy. Produce a gap analysis with specific redline recommendations — not a blank checklist.

## Step 1: Gather Input

Accept any combination of:
- **BAA document text** — paste full or partial agreement text
- **Vendor name** — proceed using available knowledge of vendor's standard BAA terms; mark findings as "Requires Verification"
- **Specific concerns** — user identifies particular provisions to focus on

If the user provides only a vendor name, proceed using public knowledge about that vendor's BAA terms, clearly distinguish between confirmed and assumed findings, and flag all items for verification with the actual document.

**Important:** Many AI vendors offer multiple product tiers with different BAA terms (e.g., a self-service tier with no BAA vs. an enterprise tier with a full BAA). Confirm which product and tier is being assessed before proceeding.

## Step 2: Load Review Criteria

Read `Checklist.md` for the full 5-section checklist, hard stop rules, and summary template.

## Step 3: Section 1 — Mandatory HIPAA Elements

Check all seven statutory requirements from §164.504(e)(2). For each:
1. State whether the provision is present, and where (quote or cite clause if text was provided)
2. Assign a status: Present — Acceptable / Present — Needs Redline / Absent — Required
3. If Absent or Needs Redline, specify exactly what language to add or request

Flag any absent mandatory element immediately as a **hard stop before proceeding.**

## Step 4: Section 2 — Breach Notification

Assess the breach notification provisions. Pay particular attention to:
- **The notice window** — extract the exact language and convert to calendar days
  - If ≤30 days: note as strong
  - If 31–60 days: note as acceptable but recommend negotiating shorter
  - If >60 days or unspecified: flag as hard stop (non-compliant)
- Whether the five required notification elements from §164.410(c) are all present

## Step 5: Section 3 — AI-Specific Provisions

This is where most vendor BAAs fall short. Work through all 10 AI-specific items. For each:
1. Confirm whether the provision is present
2. If present: assess whether it is contractually binding or merely settings-based
   - Settings-based controls (e.g., "opt out of training in your account settings") are **not** equivalent to contractual prohibitions — call this out explicitly
3. If absent: assign priority (Hard Stop / High / Medium) and specify recommended language

**Critical check for item 3.1 (model training prohibition):**
- Look for phrases like "we will not use your data to train our models" — verify whether this is in the BAA/DPA or only in the general terms of service
- Terms of service can be modified unilaterally by the vendor; BAA provisions require mutual agreement to change
- If only in the ToS, mark as Absent — Required and recommend moving it into the BAA

## Step 6: Sections 4 and 5 — Security and Termination

Work through the security safeguards and termination provisions tables. These are typically present in vendor BAAs but may lack specificity. Flag:
- Missing encryption standards
- Termination provisions that say "return or destroy" but do not specify a timeframe
- No procedure for infeasible destruction (relevant for AI systems)

## Step 7: Hard Stop Check

Before producing the summary, explicitly check all five hard stop conditions from the checklist. If any are triggered:
- Display prominently: **HARD STOP: [condition]. Do not sign as-is.**
- Specify exactly what must change to resolve the hard stop

## Step 8: Produce Review Summary

After all sections are complete, produce the summary block using the template from `Checklist.md`.

**Summary rules:**
- List all hard stops under HARD STOPS IDENTIFIED
- List specific redlines as numbered action items, not vague suggestions
  - Bad: "Strengthen data retention language"
  - Good: "Add clause: 'Vendor shall delete all Customer PHI and associated metadata within 90 days of processing, unless deletion is requested earlier under Section X.'"
- Recommendation logic:
  - **Do not sign** if any hard stop exists
  - **Sign after redlines** if there are High or Medium gaps with no hard stops
  - **Sign as presented** only if all required provisions are Present — Acceptable and no AI-specific hard stops exist

## Step 9: Next Steps

After the summary, provide 3–5 concrete next steps, such as:
- Specific provisions to send back to vendor as redlines
- Questions to escalate to legal counsel
- Subprocessor list to request and review
- Internal policies that must be in place before the BAA is signed (e.g., incident response plan, access controls)
- Re-review trigger (e.g., "re-review this BAA when the vendor makes material updates to its AI systems")

## Notes for Agentic Use

If invoked by an agent rather than a human:
- Accept BAA text, vendor name, or URL as input
- Return the completed review as structured markdown
- The Review Summary block is the primary machine-readable output
- Flag hard stops with the prefix `HARD STOP:` for downstream pipeline parsing
- Always include the legal review reminder — this output is for compliance analysis, not legal advice
