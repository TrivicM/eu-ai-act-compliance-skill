# Implementation Patterns Catalog (UI/UX)

This reference contains practical, technology-neutral frontend examples for implementing visible and machine-readable disclosures. These represent recommended best practices for web applications, **not legally mandated UI formats**.

## 1. HTML Badge for AI-Generated Images (Example)
**STATUS: Implementation Option / Best Practice — not a legally mandated visual format.** The law mandates clear visibility, not a specific CSS design.
Good practice for *clear and distinguishable* disclosure on public-interest media or images.
```html
<figure style="position: relative; display: inline-block;">
  <img src="ai-generated-image.jpg" alt="Building illustration" />
  <figcaption style="
    position: absolute; 
    bottom: 8px; 
    left: 8px; 
    background-color: rgba(0, 0, 0, 0.7); 
    color: white; 
    padding: 4px 8px; 
    font-size: 12px; 
    border-radius: 4px; 
    pointer-events: none;
    font-family: sans-serif;
  ">
    ✨ AI Generated
  </figcaption>
</figure>
```
*Note: Label copy may be adapted for language and context; the objective is noticeability.*

## 2. AI Interaction Disclosure (Chatbot Header)
When a user initiates a conversation with an AI Chatbot (Article 50(1)).
```html
<div class="chatbot-header">
  <div class="bot-info">
    <span class="bot-name">Customer Support AI</span>
    <!-- Clear disclosure at first interaction -->
    <span class="ai-disclaimer" style="font-size: 0.8em; color: #666;">
      (Automated AI Assistant)
    </span>
  </div>
</div>
```

## 3. Machine-Readable Metadata (Integration Pattern)
Applies primarily to Providers (or Deployers assuming Provider status under Article 25).
On web pages, machine-readable signatures (such as C2PA) may be embedded directly within image files. Frontend applications can verify manifests if publicly accessible or expose microformat tags for automated crawling.

## 4. Accessibility (a11y)
Disclosures must be accessible to persons with disabilities (Article 50(5)):
- Images marked as AI-generated must convey this information via `alt` attributes or dedicated `aria` descriptions.
- Example: `<img src="ai_art.png" alt="AI-generated artwork: Forest in autumn" aria-details="ai-disclaimer-text">`
