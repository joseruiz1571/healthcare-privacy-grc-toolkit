# Healthcare Privacy GRC Toolkit

Practical governance, risk, and compliance resources for managing emerging technology risks in healthcare environments, with a focus on HIPAA privacy compliance.

## Contents

### Policies
- **[AI Acceptable Use Addendum](01-AI-Acceptable-Use-Policy/AI_Acceptable_Use_Addendum.md)** — A policy addendum addressing the use of Generative AI tools by healthcare workforce members. Covers PHI protections, approved vs. unapproved tools, human oversight requirements, and incident reporting procedures. Includes scenario-based guidance for common use cases.

### Assessment Tools
- **[AI Vendor Risk Assessment Checklist](02-Vendor-Risk-Assessment/AI_Vendor_Risk_Assessment_Checklist.md)** — A structured checklist for evaluating AI vendors prior to organizational adoption. Covers Business Associate Agreement requirements, data handling practices, access controls, vendor security posture, and output reliability.
- **[HIPAA Risk Assessment Template](03-HIPAA-Risk-Assessment/HIPAA_Risk_Assessment_Template.md)** — A complete risk assessment template satisfying 45 CFR §164.308(a)(1)(ii)(A). Includes a pre-cataloged threat and vulnerability library specific to AI systems, a likelihood-impact risk register, risk response planning, and a control inventory mapped to HIPAA Security Rule citations.
- **[BAA Negotiation Checklist](04-BAA-Template/BAA_Negotiation_Checklist.md)** — A structured checklist for reviewing and negotiating Business Associate Agreements with AI vendors. Covers all mandatory HIPAA elements per 45 CFR §164.504(e)(2), breach notification requirements, and 10 AI-specific provisions that standard BAA templates omit — including model training prohibitions, data retention limits, and subprocessor chain coverage.

### Incident Response
- **[AI Breach Response Playbook](05-AI-Breach-Response/AI_Breach_Response_Playbook.md)** — A six-phase incident response playbook for HIPAA breaches involving AI tools and automated systems. Covers breach determination using the 4-factor risk assessment (45 CFR §164.402), notification requirements for individuals, HHS, and media, business associate coordination, and post-incident review. Includes pre-documented guidance for the three most common AI breach scenarios.

### Claude Code Skills
- **[AI Vendor Risk Assessment](skills/VendorRiskAssessment/)** — Given a vendor name, documentation, or URL, walks through 22 checklist items across 5 sections, assigns status findings, flags hard stops, and produces a structured assessment report with a recommendation.
- **[HIPAA Risk Assessment](skills/HIPAARiskAssessment/)** — Given an organization's AI tool inventory and environment context, conducts a full HIPAA Security Rule risk assessment: applies the AI-specific threat and vulnerability catalogs, scores risks on a likelihood-impact matrix, assigns risk responses, and produces a prioritized remediation plan.
- **[BAA Review](skills/BAAReview/)** — Given a BAA document or vendor name, identifies missing mandatory provisions, flags hard stops, assesses all 10 AI-specific provisions, and produces specific redline recommendations — not a gap list.
- **[Breach Response](skills/BreachResponse/)** — Given incident details, conducts the 4-factor risk assessment, determines whether breach notification is required, identifies all notification recipients and deadlines, drafts individual notification language, and produces the incident record.

**Installing skills:** Copy any skill directory from `skills/` into your `~/.claude/skills/` directory.

## About

These resources were developed to address the growing intersection of healthcare privacy compliance and AI adoption. They reflect practical experience in information governance, privacy policy development, and institutional risk management.

## Contact

Jose Ruiz-Vazquez — [LinkedIn Profile](https://www.linkedin.com/in/joseruiz1571)
