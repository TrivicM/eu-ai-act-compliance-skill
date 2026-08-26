# Web Development & AI Agent Specifics

This document clarifies how EU AI Act rules apply to software source code versus public-facing media content, with specific focus on autonomous AI agent workflows (e.g., Antigravity, Lovable, Claude).

## 1. AI-Generated Code vs. Public-Facing Content

**AI-Generated Source Code (HTML/CSS/JS, Python, SQL, DB Schemas):**
- **Systemic Applicability (Article 50 applicability):** The AI tool or system used for coding may fall under general transparency obligations (e.g., provider obligations under Article 50(2) regarding machine-readable marking in model outputs). Therefore, AI coding is not globally exempt from Article 50.
- **Obligation for This Actor (Obligation for this actor):** For a developer or deployer using AI to write routine code (e.g., React components, backend logic, utility scripts), the mere fact that AI was used to generate source code **DOES NOT** trigger a public disclosure/labeling obligation under Article 50(4) and 50(5). Source code generation is not intended to inform the public on matters of public interest like synthetic news text or deepfake media.
- Do not require mandatory visual AI badges on the user interface for source code. Prevent **over-compliance**, while accurately distinguishing systemic applicability from individual actor obligations.

**AI-Generated Public Content (Website copy, marketing images, UI media):**
- If an agent or system generates text published to inform the public on matters of public interest (Article 50(4)), that text must be disclosed, **unless** a human performs substantial editorial review and assumes responsibility.
- Images and media (Articles 50(2) & 50(4)) are subject to specific machine-readable and visible marking checks based on Provider and Deployer roles.

## 2. Operational Governance & Best Practices (AI Agent Safety Gate)

Autonomous AI agents capable of executing environment actions must incorporate safety checkpoints — **Human Approval Gates**.
**IMPORTANT**: These checkpoints represent **internal operational safety governance**, NOT a direct statutory mandate under Article 50 of the EU AI Act (the law does not prohibit agents from deploying code). Do not present these operational safeguards to users as statutory requirements of the AI Act.

An agent must pause and request explicit user confirmation BEFORE executing any of the following actions:
1. **Production Deployment**: Publishing software or applications to live production servers.
2. **Public Release of Synthetic Content**: Automated distribution of deepfake material or media subject to marking rules.
3. **Legal Documentation**: Modifying Privacy Policies, Terms of Service, or legal contracts.
4. **External Bulk Communications**: Sending automated mass emails or direct messages without human editorial review.

The agent must highlight any potential AI Act transparency or safety implications relevant to the requested approval.
