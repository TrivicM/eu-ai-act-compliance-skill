# EU AI Act Compliance Skill 🤖📜

> **"Do I need to label this as AI-generated, or am I good to go?"**

If you develop software, create content, or integrate AI agents and models, this is a question you will inevitably face.

The European Union's landmark legislation (**EU AI Act — Regulation (EU) 2024/1689**) establishes clear transparency rules:
* ⚠️ **Disclosure Required:** If AI generates or manipulates audio, image, or video content resembling real persons or authentic events (*deepfakes*), the law mandates clear labeling to prevent deception.
* ✅ **No Disclosure Required:** If you use AI solely for routine tasks like color correction, image upscaling, text formatting, or writing software code, there is no requirement to burden users with AI labels.

This project functions as a **smart digital judge and compliance assistant**. Its mission is to provide developers, creators, and organizations with instant, precise compliance assessments grounded directly in EU law.

---

### 📦 Repository Contents

1. 🧠 **`SKILL.md` (Rules & Orchestrator):** The core instruction set that guides your AI assistant on how to analyze use cases, ask targeted questions, and deliver legally sound assessments.
2. 📚 **`references/` (Legal Knowledge Base):** Verified reference guides covering key provisions of the EU AI Act — including Article 50 (transparency and marking obligations) and Article 25 (distinguishing *Provider* vs. *Deployer* responsibilities).

---

### 🔍 Assessment Pipeline

Every compliance question goes through a structured evaluation process — from identifying the type of AI involvement, through determining your legal role and checking applicable articles, to delivering a final assessment:

![Assessment Pipeline](pipeline.png)

If a key fact is missing at any step (e.g., who controls the user interface, or whether a model was substantially modified), the skill stops and asks a targeted question before proceeding. It never guesses.

---

### 🚀 Installation & Usage

#### STEP 1: Install in Your Environment
Copy this repository folder into your AI assistant or IDE skills directory (e.g., `.gemini/skills/`, `.agents/skills/`, or load it directly into your AI agent).

Alternatively, download the ready-made **`eu-ai-act-compliance.skill`** package from the [Releases](https://github.com/TrivicM/eu-ai-act-compliance-skill/releases) page and load it directly into your AI agent or IDE.

#### STEP 2: Ask in Plain Language
In your normal conversation with your AI assistant, simply describe what you are building or publishing:

> *"I am building a website and using AI tools to generate product images. Do I need to display an AI transparency label?"*

The assistant will automatically load this skill, evaluate your request against the relevant legal articles, and provide an accurate assessment with actionable next steps.

---

### 📝 Input Formats

No rigid format is required. Simply specify:
* What the AI system is doing (generating text, image, video, audio, or code).
* Where and how the output will be published (blog, social media, news portal, internal tool).
* Whether a human reviews and exercises editorial control before publication.

---

### ⚠️ Legal Disclaimer

This skill provides compliance assessments based on the official text of the EU AI Act (Regulation (EU) 2024/1689). It is designed as an engineering and practical decision-support tool for initial compliance checks and does not constitute formal legal advice from a licensed attorney.

---

### 📌 Project Metadata

| Parameter | Value |
| :--- | :--- |
| **Skill Version** | `1.0.0` |
| **Legal Baseline Date** | `2026-08-08` |
| **Primary Legislation** | EU AI Act — Regulation (EU) 2024/1689 (Articles 25 & 50) |
