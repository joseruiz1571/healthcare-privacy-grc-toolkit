# Assess Workflow

Conduct a structured AI vendor risk assessment against HIPAA compliance and data privacy standards.

## Step 1: Gather Input

Accept any combination of:
- **Vendor or tool name** — proceed using available knowledge, mark findings as "Requires Verification"
- **Pasted documentation** — privacy policies, security pages, BAA summaries, SOC 2 reports
- **URLs** — fetch content from vendor trust/security/privacy pages

If the user provides only a vendor name with no documentation, proceed but clearly mark every finding as "Requires Verification" unless the information is well-established public knowledge (e.g., major cloud vendors with published trust pages).

**Important:** Identify the specific product tier or SKU being assessed. Many vendors offer both consumer and enterprise products with very different compliance profiles (e.g., consumer Gemini vs. Vertex AI Gemini API, ChatGPT free tier vs. Azure OpenAI). State which product variant is being assessed and note if the consumer version does NOT meet requirements.

## Step 2: Load Assessment Criteria

Read `Checklist.md` for the full assessment checklist, status indicators, and summary template.

## Step 3: Execute Assessment

Work through each section in order (Sections 1-5). For each checklist item:

1. **State the evidence** — what the documentation says, or what is publicly known
2. **Assign a status** — Confirmed / Not Met / Unclear / Requires Verification
3. **Write an assessor note** — explain the finding, the gap, or what to request from the vendor

**Output each section as a markdown table:**

```markdown
## Section N: [Section Name]

| # | Assessment Item | Status | Assessor Note |
|---|----------------|--------|---------------|
| N.1 | [Item text] | [Status] | [Finding] |
```

### Hard Stop Rules

- **Item 1.1 (BAA):** If Not Met, output immediately: **BLOCKER: No BAA available. Tool cannot be approved for PHI use cases.**
- **Item 2.1 (Training data):** If Yes with no contractual opt-out: **BLOCKER: User data used for model training with no contractual opt-out. Not suitable for PHI.**

Continue the full assessment even if blockers are found — the organization needs the complete picture.

## Step 4: Produce Assessment Summary

After all five sections are complete, produce the summary block using the template from `Checklist.md`.

**Summary rules:**
- List all hard stops under HARD STOPS IDENTIFIED
- List all "Requires Verification" items under OPEN ITEMS with what specific documentation to request
- Recommendation logic:
  - **Deny** if any hard stop exists that cannot be resolved
  - **Approve with Conditions** if there are open verification items but no hard stops
  - **Approve** only if all required items are Confirmed and no hard stops exist

## Step 5: Next Steps

After the summary, provide 3-5 concrete next steps the assessor should take, such as:
- Specific documents to request from the vendor
- Questions to ask during vendor calls
- Internal policies to verify or create
- Timeline recommendations for re-assessment

## Notes for Agentic Use

If invoked by an agent rather than a human:
- Accept vendor name, documentation text, or URL as structured input
- Return the completed assessment as structured markdown
- The Assessment Summary block is the primary machine-readable output
- Flag hard stops with the prefix `BLOCKER:` for downstream pipeline parsing
