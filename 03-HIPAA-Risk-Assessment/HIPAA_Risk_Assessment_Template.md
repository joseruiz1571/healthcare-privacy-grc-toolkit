# HIPAA Security Rule Risk Assessment Template
### AI and Emerging Technology Focus

**Regulatory Basis:** 45 CFR §164.308(a)(1)(ii)(A) — Covered entities and business associates must conduct an accurate and thorough assessment of the potential risks and vulnerabilities to the confidentiality, integrity, and availability of electronic protected health information (ePHI).

---

## Assessment Metadata

| Field | Value |
|---|---|
| **Organization Name** | |
| **Assessment Scope** | AI Tools and Automated Systems Processing ePHI |
| **Assessment Lead** | |
| **Assessment Date** | |
| **Review Date (Next)** | *(recommend annually or upon material system change)* |
| **Version** | |

---

## Part 1: Scope Definition

### 1.1 Systems and Processes In Scope

List all AI tools, automated systems, and supporting infrastructure included in this assessment.

| System / Tool | Vendor | Version / Tier | ePHI Involved? | Business Function |
|---|---|---|---|---|
| | | | Yes / No | |
| | | | Yes / No | |
| | | | Yes / No | |

### 1.2 ePHI Data Flows

Describe how ePHI enters, moves through, and exits each in-scope system.

| Flow # | Source | Destination | Data Elements | Transmission Method |
|---|---|---|---|---|
| 1 | | | | |
| 2 | | | | |

### 1.3 Scope Exclusions

Identify any systems or processes explicitly excluded from this assessment and the reason.

| Excluded System | Justification |
|---|---|
| | |

---

## Part 2: Threat and Vulnerability Identification

### 2.1 Threat Catalog — AI-Specific

For each threat, confirm whether it is applicable to your environment. Add organization-specific threats as needed.

| Threat ID | Threat Description | Applicable? | Notes |
|---|---|---|---|
| T-01 | Workforce member inputs ePHI into an unapproved public AI tool | Yes / No / Unknown | |
| T-02 | AI vendor uses customer-submitted data to train or improve models | Yes / No / Unknown | |
| T-03 | Prompt injection attack causes AI to disclose ePHI from its context window | Yes / No / Unknown | |
| T-04 | AI-generated output contains hallucinated patient data presented as factual | Yes / No / Unknown | |
| T-05 | Vendor data breach exposes stored prompts or query logs containing ePHI | Yes / No / Unknown | |
| T-06 | Unauthorized user accesses AI interface due to insufficient access controls | Yes / No / Unknown | |
| T-07 | AI subprocessor (third-party model host, logging service) accesses ePHI without a BAA | Yes / No / Unknown | |
| T-08 | Model version update changes AI behavior in ways that affect output accuracy or data handling | Yes / No / Unknown | |
| T-09 | ePHI retained by vendor beyond contractually specified retention period | Yes / No / Unknown | |
| T-10 | Shadow AI adoption — workforce uses unapproved tools not covered by organizational controls | Yes / No / Unknown | |
| T-11 | AI-generated billing or coding output creates inaccurate claims (integrity risk) | Yes / No / Unknown | |
| T-12 | AI system unavailability disrupts care delivery processes that depend on it (availability risk) | Yes / No / Unknown | |

### 2.2 Vulnerability Catalog

For each vulnerability, assess whether it exists in the current environment.

| Vuln ID | Vulnerability | Present? | Evidence / Notes |
|---|---|---|---|
| V-01 | No organizational AI acceptable use policy | Yes / No / Partial | |
| V-02 | No formal AI vendor vetting process prior to adoption | Yes / No / Partial | |
| V-03 | BAAs not obtained from AI vendors processing ePHI | Yes / No / Partial | |
| V-04 | No workforce training on AI-related HIPAA obligations | Yes / No / Partial | |
| V-05 | Audit logging not enabled or not monitored for AI tool usage | Yes / No / Partial | |
| V-06 | No process for reviewing or responding to AI vendor model updates | Yes / No / Partial | |
| V-07 | No incident response procedure specific to AI-related ePHI disclosures | Yes / No / Partial | |
| V-08 | Role-based access controls not applied to AI tool access | Yes / No / Partial | |
| V-09 | No human review requirement for AI outputs used in clinical decisions | Yes / No / Partial | |
| V-10 | AI outputs not subject to accuracy verification before entry into medical records | Yes / No / Partial | |

---

## Part 3: Risk Analysis

### 3.1 Likelihood and Impact Definitions

**Likelihood:**

| Level | Score | Description |
|---|---|---|
| High | 3 | Threat is likely to occur; vulnerability is easily exploited or controls are absent |
| Medium | 2 | Threat could occur; partial controls exist but gaps remain |
| Low | 1 | Threat is unlikely; strong controls are in place |

**Impact:**

| Level | Score | Description |
|---|---|---|
| High | 3 | Significant harm to individuals; major regulatory penalty; large-scale ePHI compromise |
| Medium | 2 | Limited harm; moderate regulatory exposure; small-scale ePHI compromise |
| Low | 1 | Minimal harm; minor operational disruption; no or negligible ePHI exposure |

**Risk Score = Likelihood × Impact**

| Score Range | Risk Level |
|---|---|
| 7–9 | Critical |
| 4–6 | High |
| 2–3 | Medium |
| 1 | Low |

### 3.2 Risk Register

Map identified threats and vulnerabilities to risk entries. Add rows as needed.

| Risk ID | Threat | Related Vulnerability | Likelihood (1–3) | Impact (1–3) | Risk Score | Risk Level | Current Controls | Residual Risk |
|---|---|---|---|---|---|---|---|---|
| R-01 | T-01 (Unapproved AI tool) | V-01, V-04 | | | | | | |
| R-02 | T-02 (Vendor model training) | V-02, V-03 | | | | | | |
| R-03 | T-03 (Prompt injection) | V-05, V-08 | | | | | | |
| R-04 | T-04 (Hallucinated ePHI) | V-09, V-10 | | | | | | |
| R-05 | T-05 (Vendor breach) | V-03, V-07 | | | | | | |
| R-06 | T-06 (Unauthorized access) | V-08 | | | | | | |
| R-07 | T-07 (Subprocessor without BAA) | V-03 | | | | | | |
| R-08 | T-08 (Model version update) | V-06 | | | | | | |
| R-09 | T-09 (Data retention) | V-02, V-03 | | | | | | |
| R-10 | T-10 (Shadow AI) | V-01, V-04 | | | | | | |

---

## Part 4: Risk Response

For each risk in the register, select a response and define the remediation plan.

**Response options:**
- **Mitigate** — implement or strengthen controls to reduce likelihood or impact
- **Accept** — formally accept the risk; document rationale and residual risk level
- **Transfer** — shift risk contractually (e.g., via BAA, cyber insurance)
- **Avoid** — eliminate the activity or system creating the risk

| Risk ID | Response | Remediation Action | Owner | Target Date | Status |
|---|---|---|---|---|---|
| R-01 | | | | | |
| R-02 | | | | | |
| R-03 | | | | | |
| R-04 | | | | | |
| R-05 | | | | | |
| R-06 | | | | | |
| R-07 | | | | | |
| R-08 | | | | | |
| R-09 | | | | | |
| R-10 | | | | | |

---

## Part 5: Control Inventory

Document the administrative, physical, and technical safeguards currently in place or planned.

### Administrative Safeguards (45 CFR §164.308)

| Control | Required / Addressable | Status | Notes |
|---|---|---|---|
| AI Acceptable Use Policy | Addressable | In Place / Planned / Gap | |
| AI Vendor Risk Assessment Process | Addressable | In Place / Planned / Gap | |
| Workforce Training on AI and HIPAA | Required | In Place / Planned / Gap | |
| Sanction Policy for AI Policy Violations | Required | In Place / Planned / Gap | |
| Incident Response Procedure (AI-specific) | Required | In Place / Planned / Gap | |
| Information Access Management for AI Tools | Required | In Place / Planned / Gap | |

### Technical Safeguards (45 CFR §164.312)

| Control | Required / Addressable | Status | Notes |
|---|---|---|---|
| Unique user authentication for AI tool access | Required | In Place / Planned / Gap | |
| Automatic session timeout on AI interfaces | Addressable | In Place / Planned / Gap | |
| Audit logging of AI tool user activity | Required | In Place / Planned / Gap | |
| Encryption in transit (TLS 1.2+) | Addressable | In Place / Planned / Gap | |
| Encryption at rest (AES-256 or equivalent) | Addressable | In Place / Planned / Gap | |

---

## Part 6: Assessment Summary

### 6.1 Overall Risk Posture

| Risk Level | Count |
|---|---|
| Critical | |
| High | |
| Medium | |
| Low | |

**Overall Assessment:** *(Summarize the organization's risk posture in 2–3 sentences. Note the most significant risks and whether the current control environment is adequate.)*

### 6.2 Priority Remediation Items

List the top 3–5 actions required to materially reduce risk, in priority order.

| Priority | Action | Risk(s) Addressed | Target Date |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |

### 6.3 Certification

By signing below, the assessment lead certifies that this assessment reflects an accurate and thorough analysis of risks to ePHI as required under 45 CFR §164.308(a)(1)(ii)(A).

| Role | Name | Signature | Date |
|---|---|---|---|
| Assessment Lead | | | |
| Privacy Officer | | | |
| Security Officer | | | |
| Executive Sponsor | | | |

---

## Appendix A: Regulatory Reference

| Regulation | Citation | Requirement |
|---|---|---|
| HIPAA Security Rule — Risk Analysis | 45 CFR §164.308(a)(1)(ii)(A) | Conduct accurate and thorough assessment of risks to ePHI |
| HIPAA Security Rule — Risk Management | 45 CFR §164.308(a)(1)(ii)(B) | Implement security measures sufficient to reduce risks to a reasonable and appropriate level |
| HIPAA Security Rule — Evaluation | 45 CFR §164.308(a)(8) | Perform periodic technical and non-technical evaluations |
| HIPAA Security Rule — Audit Controls | 45 CFR §164.312(b) | Implement hardware, software, and/or procedural mechanisms to record and examine activity |
| HIPAA Security Rule — Transmission Security | 45 CFR §164.312(e)(1) | Implement technical security measures to guard against unauthorized access to ePHI transmitted over networks |
