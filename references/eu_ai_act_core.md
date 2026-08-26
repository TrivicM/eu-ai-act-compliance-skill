# EU AI Act - Core Framework and Roles (August 2026)

To determine whether and how obligations under the EU AI Act apply, it is essential to first identify actor roles and risk levels.

## 1. Provider vs. Deployer (Articles 3 & 25)

**Provider**:
- A natural or legal person who develops an AI system (or has an AI system developed) and places that system on the market or puts it into service under its own name or trademark.
- Holds primary obligations for system design (including marking requirements under Article 50(1) and 50(2)).

**Deployer**:
- A natural or legal person using an AI system under its own authority in a professional capacity (excluding personal, non-professional usage).
- Obligated to follow provider instructions and comply with specific disclosure rules (Articles 50(3) & 50(4)).

### Article 25 Gate (Provider Status Trigger)
Actor status depends on the **specific use-case facts**. Before assuming an actor is merely a Deployer, ALWAYS evaluate Article 25. An actor becomes a Provider (and assumes Article 50(1) and 50(2) obligations) if ANY of the following 3 conditions are met:
1. **Own name/trademark**: Places a high-risk AI system on the market or puts it into service under its own name or trademark.
2. **Substantial modification**: Makes a substantial modification to a high-risk AI system (or GPAI model, depending on rules) such that it remains high-risk (or transitions to a different category). *Caution*: Do not automatically equate fine-tuning, prompt engineering, API integration, or RAG with "substantial modification". Verify the facts and legal definition under Article 3.
3. **Intended purpose changed**: Modifies the intended purpose of an AI system that was not previously classified as high-risk, in such a way that it becomes a high-risk AI system.

**If facts are insufficient to determine Article 25 applicability:** Set `Actor = Unclear`. Targeted questions must be asked before finalizing the assessment.

### Third-Party API Rule
NEVER apply a simplistic rule such as "API Consumer = Automatically Deployer". You must analyze what the actor actually does with the API and execute the Article 25 check.
- **Scenario A (Routine Call)**: The developer calls an API (e.g., DALL-E) and displays results without modifying the model or re-branding it as their own proprietary system. *Status*: Most likely Deployer (machine-readable marking obligations remain with the Provider).
- **Scenario B-F (Integration, Fine-tuning, Rebranding)**: If the developer creates a wrapper in their own product, fine-tunes the model, brands the system as their own, or alters its intended purpose. *Status*: Do not assume. Request additional facts: "Are you placing the API output on the market under your own trademark? Have you modified the intended purpose?".

## 2. Risk Classification
- **Unacceptable Risk**: Prohibited (e.g., social scoring, subliminal manipulation).
- **High Risk**: Strict compliance requirements (employment systems, critical infrastructure, law enforcement).
- **Specific Transparency Risk (Article 50)**: Applies independently of whether the system is classified as "high-risk". The focus is on AI interaction and synthetic output.
- **Minimal Risk**: All other applications (permitted for free use with recommended voluntary codes of conduct).
