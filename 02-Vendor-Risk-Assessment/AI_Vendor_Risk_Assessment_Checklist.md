# AI Vendor Risk Assessment Checklist

**Purpose:** This checklist supports the evaluation of Generative AI tools and vendors prior to organizational adoption. It is designed to ensure compliance with HIPAA requirements and institutional data privacy standards before any tool is approved for use by workforce members.

**Instructions:** Complete this checklist for each AI tool under consideration. All items marked "Required" must receive a satisfactory response before the tool may be approved for any use case involving PHI. Items 1.1 and 2.1 are hard stops — failure on either blocks PHI approval regardless of other findings.

---

## Section 1: Business Associate Agreement (Required)

| # | Assessment Item | Status | Notes |
|---|----------------|--------|-------|
| 1.1 | Does the vendor offer a signed Business Associate Agreement (BAA)? | ☐ Yes ☐ No | **If No, STOP. Tool cannot be approved for PHI use cases.** |
| 1.2 | Does the BAA address the vendor's obligations for breach notification? | ☐ Yes ☐ No | Must align with 45 CFR §164.410 requirements. |
| 1.3 | Does the BAA specify permitted uses and disclosures of PHI? | ☐ Yes ☐ No | |
| 1.4 | Does the BAA require the vendor to return or destroy PHI upon termination? | ☐ Yes ☐ No | |

---

## Section 2: Data Handling and Privacy (Required)

| # | Assessment Item | Status | Notes |
|---|----------------|--------|-------|
| 2.1 | Is user input data used to train or improve the vendor's AI model? | ☐ Yes ☐ No | If Yes, tool is not suitable for PHI. Confirm opt-out is contractual, not just a setting. |
| 2.2 | Is data encrypted in transit (TLS 1.2+)? | ☐ Yes ☐ No | |
| 2.3 | Is data encrypted at rest (AES-256 or equivalent)? | ☐ Yes ☐ No | |
| 2.4 | What is the vendor's data retention policy? | ☐ Documented | Specify retention period: _______ |
| 2.5 | Can the organization request deletion of specific data inputs? | ☐ Yes ☐ No | Important for incident mitigation. |
| 2.6 | Where is data processed and stored geographically? | ☐ Yes ☐ No | Specify region(s): _______ |

---

## Section 3: Access Controls and Authentication

| # | Assessment Item | Status | Notes |
|---|----------------|--------|-------|
| 3.1 | Does the tool support Single Sign-On (SSO) integration? | ☐ Yes ☐ No | |
| 3.2 | Does the tool support role-based access controls (RBAC)? | ☐ Yes ☐ No | |
| 3.3 | Does the vendor maintain audit logs of user activity? | ☐ Yes ☐ No | Logs are critical for incident investigation. |
| 3.4 | Can administrators view and export usage logs? | ☐ Yes ☐ No | |

---

## Section 4: Vendor Security Posture

| # | Assessment Item | Status | Notes |
|---|----------------|--------|-------|
| 4.1 | Does the vendor hold SOC 2 Type II certification? | ☐ Yes ☐ No | Request most recent report. |
| 4.2 | Does the vendor hold ISO 27001 certification? | ☐ Yes ☐ No | |
| 4.3 | Does the vendor maintain a vulnerability management program? | ☐ Yes ☐ No | |
| 4.4 | Does the vendor have a documented incident response plan? | ☐ Yes ☐ No | |
| 4.5 | Has the vendor experienced a data breach in the past 24 months? | ☐ Yes ☐ No | If Yes, request details and remediation summary. |
| 4.6 | Does the vendor use subprocessors who may access PHI? | ☐ Yes ☐ No | If Yes, confirm subprocessors are covered under the BAA chain. Request the vendor's subprocessor list. |
| 4.7 | How does the vendor communicate model updates and version changes? | ☐ Documented | Can the organization pin model versions? What is the deprecation policy? Model behavior changes can have compliance implications. |

---

## Section 5: Output Reliability

| # | Assessment Item | Status | Notes |
|---|----------------|--------|-------|
| 5.1 | Does the vendor document known limitations of AI-generated outputs? | ☐ Yes ☐ No | |
| 5.2 | Does the tool provide source attribution or confidence indicators? | ☐ Yes ☐ No | Relevant for clinical or billing use cases. |
| 5.3 | Has the organization defined which use cases require human review of AI outputs? | ☐ Yes ☐ No | Refer to Acceptable Use Policy addendum. |

---

## Assessment Summary

| Field | Entry |
|-------|-------|
| **Tool Name** | |
| **Vendor** | |
| **Version/Tier Evaluated** | |
| **Proposed Use Case(s)** | |
| **PHI Involvement** | ☐ Yes ☐ No |
| **Assessed By** | |
| **Date** | |
| **Recommendation** | ☐ Approve ☐ Approve with Conditions ☐ Deny |
| **Conditions (if applicable)** | |

---

*This document is a sample assessment checklist created for portfolio purposes. It is intended to demonstrate practical vendor risk management in a healthcare compliance context.*
