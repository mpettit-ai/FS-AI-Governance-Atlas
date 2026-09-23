# Regulatory Landscape

Current as of September 2026. This area moves quickly, and the program should maintain this document on a quarterly review cycle with Legal and Compliance. Nothing here is legal advice.

## Federal banking supervision

**No federal banking regulator has issued a comprehensive AI rule.** The consistent position across the agencies has been that existing requirements apply to AI, and that the use of a novel technology does not create an exception to any of them. That position is itself the most important thing to understand: AI is examined through the model risk, third-party risk, consumer compliance, information security, and operational risk lenses that already exist.

| Source | What it governs | AI relevance |
|---|---|---|
| **SR 11-7 / OCC 2011-12** | Model risk management | The anchor. Most predictive AI in a bank is a model and follows this lifecycle |
| **SR 13-19 and the 2023 Interagency Guidance on Third-Party Relationships** | Third-party risk | Applies to purchased AI, AI features in existing software, and the model providers behind them |
| **FFIEC IT Examination Handbook** | Technology risk, architecture, operations | Applies to AI infrastructure, resilience, and change management |
| **GLBA and the Safeguards Rule** | Customer information protection | Governs customer data in prompts, training, and inference |
| **BSA/AML program requirements** | Financial crime | Model expectations for transaction monitoring and sanctions screening; the agencies have encouraged innovation while holding the effectiveness standard constant |

## Consumer protection and fair lending

This is where AI creates the sharpest exposure for a bank, because the obligations are specific and the enforcement record is real.

**ECOA and Regulation B.** A creditor taking adverse action must provide specific and accurate principal reasons. Two CFPB circulars address AI directly:

- **Circular 2022-03** states that the adverse action requirement applies regardless of the technology used, and that a creditor cannot rely on a checklist of sample reasons if those do not accurately describe the actual basis for the decision.
- **Circular 2023-03** addresses complex models specifically: a creditor cannot justify a vague or generic reason on the basis that the model is too complex to explain. If the model cannot produce accurate reasons, that is a reason not to use the model for that purpose.

**The practical consequence.** Explainability is not a nice-to-have for credit AI. It is a gating requirement, and it should be tested before development, not discovered after. The program encodes this as an automatic Tier 1 trigger for anything touching a credit decision.

**Fair Housing Act and disparate impact.** A facially neutral model producing disparate outcomes creates exposure whether or not protected class variables are used. Proxy variables are the usual mechanism. Fairness testing methodology and thresholds belong in the assessment, not in a later remediation.

**UDAAP.** A generative system that gives a customer an inaccurate answer about a fee, a rate, or a right creates unfairness and deception exposure. This is the clearest reason customer-facing generative systems are automatic Tier 1.

**FCRA.** Relevant where AI processes consumer report data or where an AI-derived score functions as a consumer report.

## State law

A multi-state bank holding company with separately branded affiliates faces a genuinely different problem from a single-charter institution: the applicable rule can vary by charter and by customer location for the same use case.

**Utah Artificial Intelligence Policy Act (SB 149, 2024, as amended).** Utah was the first state to enact legislation specifically regulating generative AI. The original Act, effective May 1, 2024, confirmed that existing consumer protection law applies to AI (a party cannot defend by blaming the AI) and required disclosure, on request, that a consumer is interacting with generative AI.

**The 2025 amendments matter more to a bank than the original.** SB 226, together with SB 332, SB 271, and HB 452, took effect May 7, 2025. SB 226 narrowed the general disclosure duty and added a **proactive** disclosure requirement for high-risk interactions, which are defined to include interactions involving financial data and the provision of advice on financial matters. A bank operating a customer-facing generative assistant in Utah sits squarely inside that definition. The amendments also extended the Act's repeal date to July 2027, so the statute is expected to be revisited.

**Colorado AI Act, as replaced.** The original SB 24-205 was a comprehensive statute imposing duty of care, risk management program, and impact assessment obligations on developers and deployers of high-risk AI systems, with lending explicitly among the consequential decisions covered. It never took effect in that form. Its date was pushed from February 2026 to June 30, 2026 by SB 25B-004, a federal court then blocked enforcement following a constitutional challenge, and on May 14, 2026 Governor Polis signed **SB 189**, which delayed the effective date to **January 1, 2027** and substantially scaled the law back.

**What that means practically.** The replacement framework moves away from the risk-management-and-impact-assessment model toward disclosure, transparency, and targeted protections around automated decision-making. Do not build a Colorado compliance program against the original SB 24-205 text; a good deal of published guidance still describes it. Confirm the operative requirements and date with Counsel before committing to design work, and note that this area has changed three times in under two years.

**California.** The CCPA as amended, with regulations addressing automated decision-making technology and risk assessments, plus AI transparency legislation.

**Texas, Nevada, Arizona, Washington.** Varying privacy statutes and developing AI legislation. Washington's My Health My Data Act has implications where health-adjacent data is involved.

**The operational answer.** Rather than varying behavior by state for customer-facing generative systems, adopt the most protective standard enterprise-wide for disclosure and human escalation. For a bank with a Utah footprint that standard is effectively set by the Utah amendments already, since financial advice and financial data are the high-risk categories. Where a requirement is genuinely state-specific and expensive (impact assessment filings, appeal mechanisms), handle it by jurisdiction. The intake form captures affiliate and jurisdiction so this determination is made once, at the front door, rather than discovered later.

## International

Relevant where the institution has non-US operations, non-US customers, or vendors subject to these regimes.

**EU AI Act.** Risk-based, with prohibited practices, high-risk obligations, and transparency requirements. Creditworthiness assessment of natural persons is classified as high risk. Obligations phase in over several years from entry into force in 2024. Relevant to a US regional bank mainly through vendors, who will build to it, and as a template other jurisdictions borrow from.

**ISO/IEC 42001:2023.** Not law. A certifiable AI management system standard, structured like ISO 27001. Useful as an assurance mechanism to ask vendors about, and as a maturity target.

## Maintaining this

Quarterly review with Legal and Compliance. The regulatory watch should cover:

- Federal banking agency guidance, circulars, and speeches, which often signal expectations before guidance issues
- CFPB circulars, advisory opinions, and enforcement actions
- State legislative sessions in every state with a bank affiliate or material customer base
- Examination feedback received by the institution and by peers, where shared through industry groups
- Enforcement actions against other institutions involving AI or models

**The most useful question to ask internal audit early:** if you audited AI governance in twelve months, what would you look for? That answer is a better forward indicator of examination focus than most published guidance.
