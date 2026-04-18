# Assess Workflow

Produce a completed HIPAA Security Rule risk assessment for AI and emerging technology systems.

## Step 1: Gather Input

Accept any combination of:
- **Organization context** — size, type (covered entity vs. BA), existing policies
- **System inventory** — AI tools in use or under consideration, with vendor names and use cases
- **Existing controls** — policies, training programs, technical safeguards already in place
- **Specific focus** — pre-adoption assessment, annual review, post-incident review

If the user provides only minimal context, proceed using reasonable assumptions for a typical healthcare organization and mark all assumption-based findings as "Requires Verification."

**Important:** Before scoring risks, clarify whether ePHI is actually involved. Not all AI tool use in healthcare involves ePHI (e.g., a scheduling assistant that processes only names and appointment times may not). Scope affects every subsequent scoring decision.

## Step 2: Load Assessment Criteria

Read `RiskAssessment.md` for the full threat catalog, vulnerability catalog, scoring methodology, and summary requirements.

## Step 3: Define Scope (Part 1)

Work with the user to populate:
- In-scope systems and tools
- ePHI data flows for each system
- Any explicit exclusions

Output as a markdown table. If a system is mentioned but the data flow is unclear, mark it "Requires Verification" and note what to confirm.

## Step 4: Assess Threats and Vulnerabilities (Part 2)

Work through the 12 threat catalog items (T-01 through T-12). For each:
1. State whether it is **Applicable / Not Applicable / Unknown** given the scoped environment
2. Provide a one-line rationale
3. Note the relevant vulnerability (V-xx) from the catalog

Do not skip threats. If a threat is not applicable, state why. This demonstrates thoroughness to an auditor.

**Output each section as a markdown table:**
```markdown
| Threat ID | Threat | Applicable? | Rationale | Related Vulnerability |
```

## Step 5: Score Risks (Part 3)

For each applicable threat-vulnerability pair:
1. Assign **Likelihood** (1–3) with rationale
2. Assign **Impact** (1–3) with rationale
3. Calculate **Risk Score** (Likelihood × Impact)
4. Assign **Risk Level** (Critical / High / Medium / Low)
5. Note current controls, if any

**Scoring rules:**
- If no controls exist for a threat, likelihood is at minimum Medium (2)
- If ePHI volume is large (>500 individuals potentially affected), impact is at minimum Medium (2)
- If the threat involves sensitive ePHI categories (mental health, substance use, HIV status), increase impact by one level

## Step 6: Assign Risk Responses (Part 4)

For each risk entry:
1. Select a response: Mitigate / Accept / Transfer / Avoid
2. If Mitigate: specify the control action, suggested owner role, and a reasonable target date
3. If Accept: note the residual risk level and that written rationale with executive sign-off is required
4. If Transfer: cite the contract or insurance mechanism
5. If Avoid: note the activity to be stopped and any alternative

Do not recommend "Accept" for any Critical or High risk without flagging it prominently as requiring executive sign-off documentation.

## Step 7: Inventory Controls (Part 5)

Produce the administrative and technical safeguard tables from `RiskAssessment.md`, populating status as:
- **In Place** — confirmed by user input
- **Planned** — user has indicated this is in progress or planned
- **Gap** — not in place and not planned

For each Gap, add a note referencing the risk(s) it contributes to.

## Step 8: Produce Assessment Summary (Part 6)

After all parts are complete, produce the summary block:

```
HIPAA RISK ASSESSMENT SUMMARY
----------------------------------------------
Organization:
Scope:                  AI Tools and Automated Systems Processing ePHI
Assessment Date:        [today's date]
Assessed By:            Claude (AI-assisted assessment — requires human review and sign-off)

OVERALL RISK POSTURE:
  Critical:   [count]
  High:       [count]
  Medium:     [count]
  Low:        [count]

TOP PRIORITY REMEDIATIONS:
  1. [Action] — Owner: [role] — Target: [date]
  2. [Action] — Owner: [role] — Target: [date]
  3. [Action] — Owner: [role] — Target: [date]

OPEN ITEMS REQUIRING VERIFICATION:
  [List items needing organizational input]

CERTIFICATION REQUIRED:
  This assessment must be signed by the Privacy Officer and Security Officer
  before it constitutes compliant documentation under 45 CFR §164.308(a)(1)(ii)(A).
----------------------------------------------
```

## Step 9: Next Steps

After the summary, provide 3–5 concrete next steps, such as:
- Policies or procedures to create or update
- Vendor documentation to request
- Training programs to establish
- Technical controls to implement
- Timeline for re-assessment (recommend annually or upon material change)

## Notes for Agentic Use

If invoked by an agent rather than a human:
- Accept system inventory and organizational context as structured input
- Return the completed assessment as structured markdown
- The Assessment Summary block is the primary machine-readable output
- Flag Critical and High risks with the prefix `PRIORITY:` for downstream pipeline parsing
- Always include the certification reminder — this assessment requires human sign-off to be legally effective
