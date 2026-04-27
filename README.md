# Healthcare Privacy GRC Toolkit

Practical governance, risk, and compliance resources for managing AI adoption risks in healthcare environments, with a focus on HIPAA privacy compliance.

## Contents

### Policies
- **[AI Acceptable Use Addendum](01-AI-Acceptable-Use-Policy/AI_Acceptable_Use_Addendum.md)** — Policy addendum governing Generative AI tool use by healthcare workforce members. Covers PHI protections, approved vs. unapproved tools, human oversight requirements, and incident reporting. Includes scenario-based guidance for the most common use cases.

### Assessment Tools
- **[AI Vendor Risk Assessment Checklist](02-Vendor-Risk-Assessment/AI_Vendor_Risk_Assessment_Checklist.md)** — Structured checklist for evaluating AI vendors before organizational adoption. Covers BAA requirements, data handling practices, access controls, vendor security posture, subprocessor chain coverage, and output reliability. Hard stops block approval when critical requirements are unmet.
- **[HIPAA Risk Assessment Template](03-HIPAA-Risk-Assessment/HIPAA_Risk_Assessment_Template.md)** — Complete risk assessment template satisfying 45 CFR §164.308(a)(1)(ii)(A). Includes a pre-cataloged threat library (12 AI-specific threats), a vulnerability catalog (10 items mapped to HIPAA citations), likelihood-impact risk register, risk response planning, and a control inventory with regulatory citations.
- **[BAA Negotiation Checklist](04-BAA-Template/BAA_Negotiation_Checklist.md)** — Structured checklist for reviewing and negotiating Business Associate Agreements with AI vendors. Covers all seven mandatory HIPAA elements per 45 CFR §164.504(e)(2) and 10 AI-specific provisions that standard BAA templates omit — including model training prohibitions, data retention limits, version change notification, and subprocessor chain coverage.

### Incident Response
- **[AI Breach Response Playbook](05-AI-Breach-Response/AI_Breach_Response_Playbook.md)** — Six-phase incident response playbook for HIPAA breaches involving AI tools and automated systems. Covers breach determination via the 4-factor risk assessment (45 CFR §164.402), notification requirements for individuals, HHS, and media, business associate coordination, and post-incident review. Includes pre-documented guidance for common AI breach scenarios.

### Claude Code Skills

These skills make the toolkit interactive. Install any skill and Claude will conduct the assessment with you — producing a completed output, not a blank form.

- **[AI Vendor Risk Assessment](skills/VendorRiskAssessment/)** — Given a vendor name, documentation, or URL, walks through all checklist items, assigns status findings, flags hard stops, and produces a structured report with a recommendation.
- **[HIPAA Risk Assessment](skills/HIPAARiskAssessment/)** — Given an AI tool inventory and organizational context, conducts a full HIPAA Security Rule risk assessment: applies the threat and vulnerability catalogs, scores risks, assigns responses, and produces a prioritized remediation plan.
- **[BAA Review](skills/BAAReview/)** — Given a BAA document or vendor name, identifies missing mandatory provisions, flags hard stops, assesses all 10 AI-specific provisions, and produces specific redline recommendations — not a gap list.
- **[Breach Response](skills/BreachResponse/)** — Given incident details, conducts the 4-factor risk assessment, determines whether breach notification is required, identifies notification recipients and deadlines, drafts individual notification language, and produces the incident record.

#### Installing Skills

Requires [Claude Code](https://claude.ai/code) (the Claude CLI).

```bash
# Copy the skill directory into your Claude skills folder
cp -r skills/VendorRiskAssessment ~/.claude/skills/

# Repeat for any other skills you want to install
cp -r skills/HIPAARiskAssessment ~/.claude/skills/
cp -r skills/BAAReview ~/.claude/skills/
cp -r skills/BreachResponse ~/.claude/skills/
```

Once installed, invoke a skill by name in Claude Code:

```
/VendorRiskAssessment

Can we use Microsoft Azure OpenAI with PHI?
```

Claude will walk through the full assessment and produce a structured report with a recommendation.

## About

These resources were developed at the intersection of healthcare information governance and AI risk management. The toolkit reflects a background in library and information science — a field that has long grappled with the same core problems healthcare privacy compliance addresses: how information is classified, who may access it, how long it is retained, and what happens when it is disclosed improperly. That grounding informs both the structure of these documents and the emphasis on information lifecycle at each stage of AI adoption.

The skills layer is what makes this toolkit different from a document repository. Each skill encodes the assessment logic — hard stops, scoring rules, AI-specific provisions, regulatory citations — so that running an assessment produces a completed, auditable output rather than a blank form to fill in later.

## Contact

Jose Ruiz-Vazquez — [LinkedIn Profile](https://www.linkedin.com/in/joseruiz1571)
