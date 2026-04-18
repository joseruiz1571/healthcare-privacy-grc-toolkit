# HIPAA Risk Assessment Criteria

## Regulatory Basis

45 CFR §164.308(a)(1)(ii)(A) requires covered entities and business associates to conduct an accurate and thorough assessment of the potential risks and vulnerabilities to the confidentiality, integrity, and availability of ePHI. This assessment must be documented and kept current.

A compliant risk assessment must address:
1. The scope of systems and data flows involving ePHI
2. Identification of threats and vulnerabilities
3. Assessment of likelihood and impact for each risk
4. Current controls and residual risk
5. A prioritized remediation plan

---

## Status Indicators

Use these consistently throughout the assessment:

| Status | Meaning |
|--------|---------|
| Confirmed | Directly evidenced by documentation or direct knowledge |
| Not Present | Control or requirement is explicitly absent |
| Partial | Partially implemented; gaps remain |
| Requires Verification | Cannot be confirmed without additional information from the organization |

---

## Part 1: Scope

### Required Scope Elements

| Element | Guidance |
|---|---|
| **In-scope systems** | All AI tools, automated processing systems, and supporting infrastructure that create, receive, maintain, or transmit ePHI |
| **ePHI data flows** | How ePHI enters each system, how it is processed, where it is transmitted, and how it exits or is deleted |
| **Scope exclusions** | Any systems explicitly excluded, with documented justification |

**Important:** Identify the specific product tier being assessed. Consumer-grade and enterprise-grade versions of the same AI product can have dramatically different compliance profiles (e.g., consumer ChatGPT vs. Azure OpenAI with a BAA).

---

## Part 2: Threat Catalog — AI-Specific

These 12 threats are pre-cataloged for AI systems. Assess each as Applicable / Not Applicable / Unknown.

| Threat ID | Threat | CIA Triad | Typical Likelihood Driver |
|---|---|---|---|
| T-01 | Workforce member inputs ePHI into an unapproved public AI tool | Confidentiality | Absence of acceptable use policy or training |
| T-02 | Vendor uses customer-submitted data to train or improve AI models | Confidentiality | Consumer-tier products; missing contractual opt-out |
| T-03 | Prompt injection causes AI to disclose ePHI from its context window | Confidentiality | Public-facing or multi-tenant AI deployments |
| T-04 | AI-generated output contains hallucinated patient data presented as factual | Integrity | Absence of human review requirement |
| T-05 | Vendor data breach exposes stored prompts or query logs containing ePHI | Confidentiality | Inadequate vendor vetting; no BAA |
| T-06 | Unauthorized user accesses AI interface due to insufficient access controls | Confidentiality | Shared accounts; no RBAC; no SSO |
| T-07 | Subprocessor accesses ePHI without a BAA | Confidentiality | Vendor BAA does not cover subprocessor chain |
| T-08 | Model version update changes data handling or output behavior | Integrity | No model version pinning; no change notification process |
| T-09 | ePHI retained by vendor beyond contractual retention period | Confidentiality | Vague or absent retention terms in BAA |
| T-10 | Shadow AI — workforce uses unapproved tools outside organizational controls | Confidentiality | No approved alternatives; no monitoring |
| T-11 | AI-generated billing or coding output creates inaccurate claims | Integrity | No human review before claim submission |
| T-12 | AI system unavailability disrupts ePHI-dependent care processes | Availability | No downtime procedures; over-reliance on AI workflow |

---

## Part 3: Vulnerability Catalog — AI-Specific

These 10 vulnerabilities are pre-cataloged for AI governance. Assess each as Present / Not Present / Partial.

| Vuln ID | Vulnerability | HIPAA Control Gap |
|---|---|---|
| V-01 | No organizational AI acceptable use policy | §164.308(a)(1) — Security Management Process |
| V-02 | No formal AI vendor vetting process | §164.308(a)(1) — Security Management Process |
| V-03 | BAAs not obtained from AI vendors processing ePHI | §164.308(b)(1) — Business Associate Contracts |
| V-04 | No workforce training on AI-related HIPAA obligations | §164.308(a)(5) — Security Awareness and Training |
| V-05 | Audit logging not enabled or monitored for AI tool usage | §164.312(b) — Audit Controls |
| V-06 | No process for reviewing AI vendor model updates | §164.308(a)(8) — Evaluation |
| V-07 | No incident response procedure for AI-related ePHI disclosures | §164.308(a)(6) — Security Incident Procedures |
| V-08 | RBAC and access controls not applied to AI tool access | §164.312(a)(1) — Access Controls |
| V-09 | No human review requirement for AI outputs in clinical decisions | §164.308(a)(1) — Risk Management |
| V-10 | AI outputs not verified for accuracy before entry into medical records | §164.308(a)(1) — Risk Management |

---

## Part 4: Risk Scoring

### Scoring Matrix

Risk Score = Likelihood (1–3) × Impact (1–3)

| | Low Impact (1) | Medium Impact (2) | High Impact (3) |
|---|---|---|---|
| **High Likelihood (3)** | Medium (3) | High (6) | Critical (9) |
| **Medium Likelihood (2)** | Low (2) | Medium (4) | High (6) |
| **Low Likelihood (1)** | Low (1) | Low (2) | Medium (3) |

**Risk Level Thresholds:**
- Critical (7–9): Requires immediate remediation; executive escalation required
- High (4–6): Remediation required; assign owner and target date
- Medium (2–3): Address in next planning cycle
- Low (1): Monitor; accept with documentation

### Guidance for Likelihood Scoring

- **High (3):** No controls exist, or controls have known failures; threat actor is motivated and has demonstrated capability
- **Medium (2):** Partial controls exist; some gaps remain; threat is plausible
- **Low (1):** Strong controls in place; threat would require unusual circumstances

### Guidance for Impact Scoring

- **High (3):** Large volume of ePHI (>500 individuals); sensitive data categories (mental health, HIV, substance use); likely breach notification required; significant regulatory penalty exposure
- **Medium (2):** Limited ePHI volume; notification may be required; moderate harm to individuals possible
- **Low (1):** Minimal ePHI exposure; harm to individuals unlikely; operational disruption only

---

## Part 5: Risk Response Options

| Response | When to Use | Documentation Required |
|---|---|---|
| **Mitigate** | Risk level is unacceptable; controls can reduce it | Specific control(s) to implement, owner, target date |
| **Accept** | Residual risk is Low or Medium and cost of mitigation exceeds benefit | Written rationale, residual risk level, executive sign-off |
| **Transfer** | Risk can be contractually shifted (BAA, cyber insurance) | Contract reference or policy citation |
| **Avoid** | Risk cannot be mitigated to acceptable level; activity should not occur | Decision documentation; alternative identified |

---

## Part 6: Assessment Summary Requirements

A compliant assessment summary must include:

1. **Overall risk posture** — count of risks at each level (Critical / High / Medium / Low)
2. **Top 3–5 priority remediations** with owners and target dates
3. **Control inventory status** — administrative and technical safeguards mapped to HIPAA citations
4. **Certification block** — signed by Privacy Officer and Security Officer

The summary serves as the primary evidence of §164.308(a)(1)(ii)(A) compliance in the event of an HHS audit or investigation.
