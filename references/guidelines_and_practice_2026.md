# Official EU Guidelines and Code of Practice (August 2026)

This document clarifies practical implementation based on the official *European Commission Guidelines on transparency obligations* and the *Code of Practice on Transparency of AI-Generated Content* (2026).

## 1. Source Hierarchy
When assessing compliance, official 2026 EU Guidelines take precedence over informal interpretations from third-party blogs or news articles. The Regulation (EU AI Act) sets the legal framework, while Guidelines and Codes of Practice define technical and practical expectations.

## 2. Implementation of Machine-Readable Marking (Article 50(2))
- **No Legally Mandated Single Standard**: The AI Act requires marking outputs to be "effective, interoperable, robust, and reliable" (in light of generally acknowledged state of the art).
- **C2PA, IPTC, Watermarking**: These technologies (including digital watermarks and Content Credentials) represent **possible implementation mechanisms**. They are recognized as best practices in the 2026 Guidelines.
- **Rule for Advisory Output**: Never claim "C2PA is a legally mandatory standard under the Act". The correct statement is: "Implement an effective machine-readable marking/provenance mechanism. C2PA is a strongly recommended implementation under the 2026 Code of Practice."

## 3. Clear and Distinguishable Disclosure (Article 50(4) & (5))
- Notifications must be designed so that a reasonably informed and observant person cannot easily overlook them.
- **Proportionality**: Do not recommend intrusive or oversized visual badges for benign content. Disclosures must be clear without needlessly obstructing user experience or content enjoyment.
- **Timing**: Disclosures must be present at the outset (first exposure) – e.g., a corner badge at the start of a deepfake video or an audio warning preceding a synthetic sound clip.

## 4. Legal Uncertainty Rule
- If Guidelines and the Code of Practice offer no definitive answer for a specific edge case, do not attempt to invent rules or exceptions.
- State `Unclear` in the assessment report and recommend legal escalation or monitoring future guidance from the EU AI Office.
