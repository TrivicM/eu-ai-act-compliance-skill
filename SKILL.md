---
name: eu-ai-act-compliance
description: >
  EU AI Act compliance gatekeeper. Use when the user is developing AI systems, writing AI code,
  integrating APIs (OpenAI, Anthropic), developing web content, generating synthetic media (deepfakes, audio, text, images),
  or asking about AI compliance/labels. 
  Triggers: "EU AI Act", "AI compliance", "AI label", "watermark", "deepfake label", "C2PA",
  "Article 50", "do I need to label this", "AI Act assessment", "is this AI compliant".
allowed-tools: Read, Grep, Glob, WebFetch, WebSearch
---

# EU AI Act Compliance Gatekeeper (v1.0.0)

> **Metadata:** Version 1.0.0 | Legal Baseline Date: 2026-08-26

This skill acts as a deterministic regulatory gatekeeper for professional AI workflows (software engineering, content creation, API integration, and autonomous agentic systems).
Its primary purpose is to prevent legal oversights (**under-compliance**) while avoiding unnecessary tagging and disclosures (**over-compliance**).

## What This Skill Changes
- **Prevents blanket AI-labeling hallucinations:** Stops the agent from falsely claiming that all AI-assisted code, SEO copy, or routine image edits require public AI labels under the EU AI Act.
- **Enforces the Article 25 Provider-Conversion Gate:** Evaluates whether an API consumer or deployer has crossed into *Provider* status via rebranding, substantial modification, or repurposing into a high-risk system.
- **Applies the 4-Step Deepfake & Editorial Review Tests:** Distinguishes regulated deepfakes and public-interest text (Article 50(4)) from fictional artwork, routine commercial copy, and human-edited publications.
- **Halts on Missing Legal Facts:** Replaces speculative guessing with a strict `UNCLEAR -> IDENTIFY MISSING FACT -> ASK TARGETED QUESTION` gate whenever determinative facts are absent.
- **Verifies Living Law against EUR-Lex:** Requires checking whether Regulation (EU) 2024/1689 or its transitional timelines have been amended prior to issuing high-confidence conclusions.

## Core Rules
1. Do not assume every AI-generated output automatically requires an "AI label".
2. Do not fabricate legal obligations. In cases of ambiguity, follow the process: `UNCLEAR -> IDENTIFY MISSING FACTS -> CHECK CURRENT OFFICIAL EU GUIDANCE -> ESCALATE`.
3. Inform the user using the standardized format (see "Compliance Output Format" section below).
4. Article 50 governs transparency, but actor roles, obligations, and exceptions must be strictly verified before advising.
5. Base legal claims EXCLUSIVELY on official EU sources. This skill is **not** formal legal advice and does not guarantee absolute legal compliance.

## Assessment Procedure (Step-by-Step)
Follow this sequence (`IDENTIFY -> CLASSIFY -> DETERMINE ROLE -> ARTICLE 25 GATE -> DETERMINE ARTICLE 50 APPLICABILITY -> CHECK TEMPORAL CONTEXT -> CHECK EXCEPTIONS -> DETERMINE ACTOR OBLIGATION -> IDENTIFY MISSING FACTS -> IMPLEMENT PROPORTIONATE CONTROLS -> DOCUMENT LEGAL BASIS`):

1. **Identify & Classify AI Involvement:** Determine the system architecture and output type (direct human-AI interaction, synthetic audio/image/video/text, emotion recognition/biometrics, deepfake, or AI-assisted source code).
2. **Determine Actor Role & Run Article 25 Gate:** Classify the user as *Provider* or *Deployer* under Article 3, then test all three Article 25 triggers (own trademark, substantial modification, or intended-purpose change).
3. **Evaluate Article 50 Applicability:** Match the workflow against Article 50(1) (interaction), 50(2) (machine-readable marking), 50(3) (emotion/biometric notice), and 50(4) (deepfakes & public-interest text).
4. **Check Temporal & Transitional Context:** Verify market placement dates against the 2 August 2026 application date and applicable transitional windows.
5. **Evaluate Statutory Exceptions & Human Editorial Control:** Test whether routine assistive editing (Article 50(2)), obvious context (Article 50(1)), artistic/satirical framing, or substantive human editorial responsibility (Article 50(4)) applies.
6. **Enforce Missing-Facts Gate:** If any determinative fact is missing (e.g., who controls the UI, market placement date, or whether model weights/architecture were modified), **DO NOT** guess — set affected fields to `Unclear` and ask a targeted question (`UNCLEAR -> IDENTIFY MISSING FACT -> ASK TARGETED QUESTION -> REASSESS`).
7. **Check External Triggers & Living Law:** Flag separate GDPR or Copyright/IP triggers where personal data or protected creative assets are involved, and verify current legal force against EUR-Lex when web access is available.
8. **Deliver Standardized Compliance Output:** Present the final assessment strictly using the 22-field `Compliance Output Format` below.

## Article 50 Decision Tree & Reference Files

- To determine roles (Provider vs. Deployer, Article 25 Gate, Third-Party API rules), read: [eu_ai_act_core.md](references/eu_ai_act_core.md).
- For direct transparency obligations, Temporal/Transitional rules, exceptions, and human editorial control, read: [article_50.md](references/article_50.md).
- For specific technological implementation examples and EU 2026 Guidelines, read: [guidelines_and_practice_2026.md](references/guidelines_and_practice_2026.md).
- For rules distinguishing public content from AI-generated code and Operational Governance / Best Practices, read: [ai_web_development.md](references/ai_web_development.md).
- For a catalog of UI/UX implementation patterns without legal mandate, read: [implementation_patterns.md](references/implementation_patterns.md).
- For separate legal frameworks (GDPR/Copyright), read: [external_triggers.md](references/external_triggers.md).

## Living-law / Current-law Verification

This skill treats the EU AI Act as a **living legal source**. During every assessment, you MUST:
1. **Current-law source-of-truth rule**: Treat the consolidated EUR-Lex text of Regulation (EU) 2024/1689 together with all applicable amending regulations as the **primary legal source of truth**.
2. Local files in `references/` represent **secondary cached guidance** and must not override current official text. The `legal_baseline_date` in metadata indicates only the last embedded review date, NOT a mandatory frozen legal state.
3. Prior to drawing conclusions, verify whether the relevant provision has been amended, deferred, repealed, or affected by subsequent EU legislation (when web access is available).
4. Determine which legal version applies on the **assessment date**. Verify transitional and deferred deadlines.
5. Clearly distinguish between law currently in force, deferred provisions, Commission guidance, and best practices.
6. If the current official source cannot be verified online, **explicitly state**: **"Current-law verification unavailable — assessment based on the locally stored legal references and may require re-verification."** In this scenario, reduce legal confidence rather than silently relying on historical references.

## Before and After (Worked Example)

**User Prompt:** *"We used an AI API to generate a blog post about our new espresso machine and published it on our company website. Do we need to display an 'AI-Generated' label under the EU AI Act?"*

- **Before (Default Model without Skill):** *"Yes. Under the EU AI Act transparency rules, any AI-generated text published on a public website must include a visible disclosure informing readers that the text was written by AI."* *(Incorrect — conflates commercial marketing copy with public-interest news text and confuses Provider vs. Deployer duties).*
- **After (With `eu-ai-act-compliance` Skill):** Distinguishes **Provider** machine-readable marking (Article 50(2), handled by the upstream AI provider) from **Deployer** visible disclosure (Article 50(4) subparagraph 2). Because a commercial product blog post is **not** text published to inform the public on *matters of public interest* (such as news, elections, or public health), **no visible deployer disclosure label is required** (`Obligation for this actor: Not required`, `Disclosure: Not required`).

## What This Skill Will Not Do
- **Not formal legal representation:** Does not replace a qualified EU legal professional or issue legally binding opinions.
- **Not a full Annex III High-Risk conformity audit:** Does not audit quality management systems (Article 17), technical documentation (Annex IV), or CE marking procedures beyond checking Article 25 role-conversion triggers.
- **Not a full GDPR DPIA or IP clearance engine:** Flags when personal data (GDPR) or copyright/IP risks are triggered by an AI workflow, but does not conduct full data protection impact assessments or license audits.
- **Does not mutate or watermark files on disk:** Operates strictly as a read-only analytical gatekeeper; it does not inject binary C2PA manifests or modify source code files unless explicitly asked by the user.

## Compliance Output Format

When a user requests a compliance review (e.g., "Do I need to label this?", "Can I publish this?"), **always** respond in the following format:

```markdown
### AI Act assessment
- **AI involvement:** ...
- **Actor:** Provider / Deployer / Both / Unclear
- **Provider-status trigger / Article 25 check:** ...
- **AI system/use case:** ...
- **Content type:** ...
- **Article 50 applicability:** Yes / No / Potentially / Unclear
- **Applicable provision:** ...
- **Exception:** ...
- **Temporal context:** ...
- **Obligation for this actor:** Required / Not required / Provider responsibility / Deployer responsibility / Shared / Unclear
- **Human review:** Required / Relevant / Not specifically required / Unclear
- **Disclosure:** Required / Not required / Unclear
- **Machine-readable marking:** Required / Not required / Provider responsibility / Unclear
- **GDPR trigger:** Yes / No / Unclear
- **Copyright/IP trigger:** Yes / No / Unclear
- **Risk level:** Low / Medium / High / Unclear
- **Action before publication/deployment:** ...
- **Legal confidence:** High / Medium / Low
- **Legal source checked:** ...
- **Source date/version:** ...
- **Assessment date:** ...
- **Current-law verification:** Verified / Not available / Unclear
```

If missing facts prevent full completion of this format, explicitly state what is missing before providing a final assessment. (Legal confidence: "High" may only be used if provisions are clear, official guidelines are verified, and no essential facts are missing).
