# External Triggers (GDPR & Copyright/IP)

This skill focuses primarily on the EU AI Act. However, it must trigger alerts when a workflow involves elements governed by other key legal frameworks. EU AI Act compliance does not automatically guarantee compliance with GDPR or Intellectual Property laws.

## 1. GDPR Trigger (Data Protection)
If an AI workflow processes or generates any of the following, set `GDPR trigger` to `Yes` and alert the user:
- Images featuring identifiable real persons (facial photos).
- Voice recordings (voices of specific individuals).
- Customer records (names, physical addresses, contact information).
- Employee data, CVs, job applications.
- Transcripts of private chats or emails.
- Any biometric identifiers or sensitive personal data.

**User Message**: "You are processing personal data. EU AI Act compliance does not automatically satisfy GDPR requirements. Verify the lawful basis for processing under GDPR (e.g., consent or legitimate interest). Perform a dedicated Data Protection Impact Assessment (DPIA)."

## 2. Copyright / IP Trigger (Intellectual Property)
If an AI workflow involves generating or relying on any of the following materials, set `Copyright/IP trigger` to `Yes` and alert the user:
- Generating marketing images, photography, or video assets.
- Composing or generating music.
- Generating extensive text (e.g., books, published articles).
- Generating brand logos or corporate visual identity.
- Substantial copying or extraction of proprietary source code.

**User Message**: "Potential third-party rights or IP licensing review required. AI-generated content is not automatically copyright-free, nor can purely AI-generated works be copyrighted in many jurisdictions. Conversely, generation does not inherently constitute infringement. Perform a dedicated intellectual property and licensing review."
