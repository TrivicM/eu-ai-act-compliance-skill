---
name: eu-ai-act-compliance
metadata:
  version: 1.0.0
  legal_baseline_date: 2026-08-08
description: >
  EU AI Act compliance gatekeeper. Use when the user is developing AI systems, writing AI code,
  integrating APIs (OpenAI, Anthropic), developing web content, generating synthetic media (deepfakes, audio, text, images),
  or asking about AI compliance/labels. 
  Triggers: "EU AI Act", "AI compliance", "AI label", "watermark", "deepfake label", "C2PA",
  "Article 50", "da li ovo moram da oznacim", "AI Act procena", "is this AI compliant".
---

# EU AI Act Compliance Gatekeeper

This skill acts as a gatekeeper for professional AI workflows (coding, content creation, agentic systems).
Its primary purpose is to prevent legal oversights (**under-compliance**) while avoiding unnecessary tagging and disclosures (**over-compliance**).

## Core Rules
1. Do not assume every AI-generated output automatically requires an "AI label".
2. Do not fabricate legal obligations. In cases of ambiguity, follow the process: `UNCLEAR -> IDENTIFY MISSING FACTS -> CHECK CURRENT OFFICIAL EU GUIDANCE -> ESCALATE`.
3. Inform the user using the standardized format (see "Compliance Output Format" section below).
4. Article 50 governs transparency, but actor roles, obligations, and exceptions must be strictly verified before advising.
5. Base legal claims EXCLUSIVELY on official EU sources. This skill is **not** formal legal advice and does not guarantee absolute legal compliance.

## Assessment Workflow
Follow this sequence:
`IDENTIFY -> CLASSIFY -> DETERMINE ROLE -> ARTICLE 25 GATE -> DETERMINE ARTICLE 50 APPLICABILITY -> CHECK TEMPORAL CONTEXT -> CHECK EXCEPTIONS -> DETERMINE ACTOR OBLIGATION -> IDENTIFY MISSING FACTS -> IMPLEMENT PROPORTIONATE CONTROLS -> DOCUMENT LEGAL BASIS`

## Additional Rules and Missing Facts Gate
- **REQUIRED ADDITIONAL-FACTS GATE**: If a key fact is missing (e.g., market placement date, whether a substantial modification was made, who controls the user interface), **DO NOT** guess the outcome.
- Use the procedure: `UNCLEAR -> IDENTIFY MISSING FACT -> ASK TARGETED QUESTION -> REASSESS`.

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
