# AI Governance Framework for Regional Banking

A working reference implementation of an AI governance program for a multi-state regional bank holding company, built on the **NIST AI Risk Management Framework (AI RMF 1.0)** and aligned to the supervisory expectations that already apply to banks: **SR 11-7 model risk management**, the **2023 Interagency Guidance on Third-Party Relationships**, fair lending law, and **GLBA**.

This is not a policy library scraped from templates. It is the set of artifacts a governance manager would actually need on day one: an intake that product teams will use, a risk tiering model that maps to existing bank risk taxonomy, a control catalog crosswalked to AI RMF subcategories, and registers that survive an audit.

---

## Why this exists

Most published AI governance material is written for technology companies. Banks have a different problem. They already have a model risk function with thirty years of supervisory history behind it, a third-party risk program, a fair lending program, and an internal audit function that will test whatever gets built. An AI governance program that ignores those structures gets rejected by second line and duplicated by audit within a year.

So the design premise here is **alignment before addition**. Every artifact in this repository answers one of two questions:

1. Where does an existing bank control already cover this AI risk, and what needs to extend to reach it?
2. Where does AI introduce a risk that no existing control addresses, and what is the smallest new mechanism that closes it?

---

## What is in here

| Path | What it holds |
|---|---|
| [`docs/`](docs/) | The program design: charter, scope and definitions, AI RMF crosswalk, risk tiering, intake and review workflow, SR 11-7 alignment, third-party AI, GenAI-specific controls, monitoring and metrics, RACI, and the regulatory landscape |
| [`policy/`](policy/) | Drafting-ready policy and standard language: acceptable use, the AI governance standard, and documentation requirements |
| [`templates/`](templates/) | The working forms: use case intake, risk assessment, model card, vendor AI due diligence questionnaire, fairness test plan, AI incident report |
| [`controls/`](controls/) | A control catalog crosswalked to NIST AI RMF subcategories and NIST SP 800-53 Rev. 5 |
| [`registers/`](registers/) | Starter schemas for the AI inventory and the AI risk register, with worked example rows |
| [`implementation/`](implementation/) | A 90-day plan that says how, not just what |

**Start here:** [`docs/01-program-charter.md`](docs/01-program-charter.md), then [`docs/04-risk-tiering.md`](docs/04-risk-tiering.md), then [`templates/ai-use-case-intake-form.md`](templates/ai-use-case-intake-form.md). Those three are the load-bearing pieces. Everything else supports them.

---

## The design in one page

**Scope is defined by consequence, not by technology.** The program does not try to decide what counts as artificial intelligence. It asks what decision the system influences and who is affected by it. A regression model that denies credit is in scope. A generative assistant that drafts internal meeting notes is in scope at the lowest tier. The definition question is a debate you can lose for a year; the consequence question is answerable in one conversation.

**Four risk tiers, with a defined owner and a defined turnaround for each.** Tier assignment is driven by consumer impact, data sensitivity, autonomy of the decision, and regulatory exposure. Tier 1 goes to the AI Risk Committee. Tier 4 is self-service against a pre-approved pattern. If everything requires a committee, teams route around the program, and then governance is a document rather than a control.

**Pre-approved patterns are the throughput mechanism.** A use case that matches an already-reviewed pattern (approved model, approved data class, human in the loop, no consumer-facing output) is registered rather than assessed. This is what keeps cycle time defensible and it is the single most important thing separating a program people use from a program people avoid.

**SR 11-7 is the anchor, not a competitor.** Anything meeting the bank's model definition stays in the model risk inventory and follows the validation lifecycle. AI governance adds AI-specific requirements on top rather than creating a parallel inventory. The boundary between the two is written down in [`docs/06-model-risk-alignment.md`](docs/06-model-risk-alignment.md), because an undefined boundary is where accountability disappears.

**Metrics from day one.** Coverage, cycle time, tier distribution, exception aging, and open risk by tier. A program that cannot report coverage cannot claim it has any.

---

## Framework and regulatory basis

**Core framework**
- NIST AI Risk Management Framework 1.0 (GOVERN, MAP, MEASURE, MANAGE)
- NIST AI 600-1, Generative AI Profile (the twelve GenAI risks, including confabulation, data leakage, and information integrity)
- ISO/IEC 42001:2023, AI management systems
- NIST SP 800-53 Rev. 5 for control mapping

**Banking supervision**
- SR 11-7 / OCC 2011-12, Supervisory Guidance on Model Risk Management
- Interagency Guidance on Third-Party Relationships: Risk Management (2023)
- FFIEC IT Examination Handbook
- Gramm-Leach-Bliley Act, Safeguards Rule and privacy provisions

**Consumer protection and fair lending**
- ECOA and Regulation B, including adverse action notice requirements
- CFPB Circular 2022-03 and Circular 2023-03: a complex or proprietary model does not excuse a lender from providing specific and accurate reasons for adverse action
- Fair Housing Act, FCRA, and UDAAP

**State law, which matters for a multi-state holding company**
- Utah Artificial Intelligence Policy Act (SB 149, 2024, as amended by SB 226 in 2025), including proactive disclosure for high-risk interactions involving financial data or financial advice
- Colorado's AI law as replaced by SB 189 (May 2026), effective January 1, 2027, and substantially scaled back from the original SB 24-205
- California, Texas, Nevada, Arizona, and Washington privacy and AI developments

A multi-state footprint means the governing rule for a given use case can differ by charter and by customer location. The intake form captures jurisdiction for exactly this reason.

---

## How to use this

1. Read the charter and the scope definitions. Change the definitions to match your bank's existing model definition and data classification standard. Do not adopt them as written.
2. Run the crosswalk in [`docs/03-nist-ai-rmf-crosswalk.md`](docs/03-nist-ai-rmf-crosswalk.md) against your current policies and controls. Most banks find they already satisfy a meaningful share of GOVERN and MANAGE through existing model risk and third-party programs.
3. Build the inventory before you build the process. An intake with no baseline inventory governs only what arrives next.
4. Pilot the intake on three real use cases before publishing it. The form always survives contact with reality worse than you expect.

---

## Author

**Michael Pettit**, CISSP, AIGP, PMP, MBA

Ten years in security governance and technology risk at a public, SOX-regulated Fortune 500: enterprise exception and risk-acceptance ownership, third-party security assessment, control governance across a 100,000-asset environment spanning more than 1,200 locations in 22 countries, and a mandatory security review gate built into the capital approval process.

Herriman, Utah. [LinkedIn](https://www.linkedin.com/in/michael-pettit-2b535b98)

---

## Disclaimer

This is an independent reference implementation developed for educational and professional portfolio purposes. It is not affiliated with, endorsed by, or derived from the internal materials of any financial institution. It does not constitute legal, regulatory, or compliance advice. Nothing here has been reviewed by counsel. Any institution adopting these artifacts should have them reviewed by its own legal, compliance, model risk, and internal audit functions before use.

Licensed under the MIT License. See [`LICENSE`](LICENSE).
