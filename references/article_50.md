# Article 50 - Transparency Obligations (EU AI Act)

> **Legislative source:** Based on Regulation (EU) 2024/1689 as consolidated on EUR-Lex (version of 27 July 2026), incorporating Amending Regulation (EU) 2026/1744.
> **Current-law verification:** The applicable legal text must be verified against the latest EUR-Lex version before issuing a compliance assessment.

This reference outlines obligations for AI systems interacting with natural persons or generating synthetic content, based on the official text of the Regulation.

## A. Human Interaction (Article 50(1))
- **Rule**: Design and develop the system to ensure natural persons are informed that they are interacting with an AI system.
- **Responsibility**: Depends on interface architecture (do not hardcode as Provider-only; usually falls on the entity controlling user access).
- **Interactive Voice & Telephony**: Inbound and outbound telephone voicebots or real-time voice agents must audibly disclose that the caller/callee is speaking with an AI system at the immediate outset of the conversation.
- **Exception**: When obvious from the context and circumstances of use (e.g., an app explicitly titled 'AI Voice Assistant'), or where authorized by law to detect, prevent, or investigate criminal offenses.

## B. Machine-Readable Marking of Synthetic Media (Article 50(2))
- **Rule**: AI systems generating synthetic audio, image, video, or text content must mark outputs in a machine-readable format to ensure artificial generation or manipulation is detectable.
- **Responsibility**: Provider.
- **Implementation State-of-the-Art (2026 Code of Practice)**:
  - Technical metadata standards (e.g., C2PA / Content Credentials cryptographic manifests, IPTC DigitalSourceType metadata).
  - Imperceptible / steganographic watermarking where technically feasible, resilient to compression and transcoding.
- **Exception**: Systems performing routine editing or auxiliary tasks (e.g., color correction, upscaling, audio noise reduction, spell-checking, code syntax autocompletion) that do not substantially alter the semantics of input data, or where authorized by law.

## C. Emotion Recognition & Biometric Categorization (Article 50(3))
- **Rule**: Natural persons must be notified of the operation of emotion recognition or biometric categorization systems to which they are exposed.
- **Responsibility**: Deployer.

## D. Deepfakes / Manipulated Media (Article 50(4) - subparagraph 1 & Article 3(60))
- **Legal Definition (Article 3(60))**: AI-generated or manipulated image, audio, or video content that resembles existing persons, objects, places, entities, or events and would falsely appear to a person to be authentic or truthful.
- **Voice Cloning & Audio Deepfakes**: Replicating a real person's recognizable voice characteristics using generative voice synthesis constitutes a deepfake if it would falsely appear authentic to a reasonable listener.
- **Mandatory 4-Step Decision Tree (Before concluding "Deepfake"):**
  1. Is the content AI-generated or AI-manipulated?
  2. Is the content an image, audio, or video?
  3. Does the content resemble **existing persons, objects, places, entities, or events**?
  4. Would it **falsely appear to a reasonable person to be authentic or truthful**?
- **Distinction from Fictional / Creative Works**: The skill MUST NOT automatically declare every realistic AI image or fictional voice a deepfake. Generic fictional or creative realistic artwork that does not depict existing entities or deceive users about authentic real-world events does not meet the deepfake threshold.
- **Rule for Deepfakes**: The deployer must disclose that the content has been artificially generated or manipulated (visible/audible disclosure).
- **Responsibility**: Deployer.
- **Artistic & Satirical Exception (Article 50(4) Subparagraph 3)**: Where the synthetic content forms part of an evidently artistic, creative, satirical, parodic, or analogous work:
  - The disclosure obligation is **adapted rather than eliminated**: Deployers must provide appropriate disclosure that does not impede the display or enjoyment of the work (e.g., in accompanying descriptions, title cards, or end credits).

## E. Text on Matters of Public Interest (Article 50(4) - subparagraph 2)
- **Definition**: AI-generated or manipulated text published with the purpose of informing the public on matters of public interest (e.g., news, elections, politics, public health).
- **What is NOT "Public Interest"**: Standard commercial blogs, marketing copy, product descriptions, technical documentation, SEO content, and routine corporate communications **do not** qualify as public interest. Merely publishing content on a public website does not activate Article 50(4). If facts are ambiguous: `UNCLEAR -> Request facts regarding text intent`.
- **Rule**: Must disclose that the text has been artificially generated or manipulated.
- **Responsibility**: Deployer.
- **Human Review Gate (Exception)**: Disclosure is **not** required if both conditions are satisfied:
  1. The content has undergone a process of **substantial** human review OR editorial control. This requires genuine editorial responsibility (editorial judgement), NOT superficial proofreading, formatting, or spell-checking.
  2. A natural or legal person holds legal/editorial responsibility for publishing the content.

## F. Form of Disclosure (Article 50(5))
- Disclosures under paragraphs 1-4 must be provided in a **clear and distinguishable manner**.
- **Timing**: At the latest at the time of **first interaction or first exposure**.

## G. Temporal Context / Transitional Rules (Regulation 2024/1689 & Amending Regulation 2026/1744)
- **General Application Date**: Article 50 obligations apply starting **2 August 2026**.
- **Transitional Window for Article 50(2) (Regulation 2026/1744)**: AI systems generating synthetic content (audio, image, video, text) **placed on the market before 2 August 2026** receive a dedicated transitional window until **2 December 2026** to comply with machine-readable marking rules under Article 50(2). After this date, legacy systems must also comply.
- **Article 111 (High-Risk & GPAI)**: Do not use Article 111 as a generic grandfathering clause for all AI systems. Article 111 applies specifically to *high-risk* AI systems and *GPAI* models (which have longer transitional timelines, e.g., August 2027 or later). For standard synthetic content systems, the 2 December 2026 deadline applies.
- Always verify the market placement date before confirming Provider obligations. Do not extend transitional deferrals to Deployers publishing new content if the rule applies strictly to Providers.
