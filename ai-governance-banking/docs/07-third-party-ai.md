# Third-Party and Embedded AI

Most of a bank's AI exposure is not built in house. It is purchased, and a large share of it arrives switched on inside software the bank already owns.

## The three ways third-party AI enters

1. **Deliberately procured AI.** A model, platform, or AI-native product bought on purpose. This is the smallest category and the best governed, because it goes through procurement and third-party risk like anything else.
2. **AI features inside existing software.** The largest source of ungoverned AI in most institutions. A vendor ships an AI assistant in a product the bank has owned for six years. No contract change, no procurement event, no review, and often a default-on configuration.
3. **Individually adopted tools.** Employees using consumer AI services, sometimes on corporate cards, sometimes on personal accounts with bank data.

## Governing what arrives without a procurement event

**Ask the vendors directly.** For each material vendor, send a standing question: what AI or machine learning functionality exists in the products we license, what is enabled in our tenant, what data does it process, and where does that processing occur. Repeat annually and on renewal. Most institutions find several systems they did not know about on the first pass.

**Establish contractual notice.** At renewal, add a requirement that the vendor notify the bank before enabling new AI functionality or materially changing an existing model. Without this, the reassessment trigger in the tiering model has no way to fire.

**Default to off.** Where the product supports it, new AI features should require an affirmative enablement decision through the intake process rather than arriving on. Negotiate this where it is not the default.

**Monitor technically.** CASB, proxy, and SaaS discovery data reveal traffic to AI services. Expense and corporate card data reveal individual subscriptions. Neither is complete alone.

## Due diligence, layered onto existing third-party risk

The 2023 Interagency Guidance on Third-Party Relationships already requires risk-based due diligence, contract provisions, and ongoing monitoring proportionate to criticality. AI does not need a separate program. It needs additional questions inside the existing one.

The full question set is in [`templates/ai-vendor-due-diligence-questionnaire.md`](../templates/ai-vendor-due-diligence-questionnaire.md). The questions that matter most:

1. **Is our data used to train, fine-tune, or improve your models, or any shared model?** The answer must be no for anything above minimal data sensitivity, and it must be in the contract rather than in a policy page the vendor can revise.
2. **Where is inference processed, and does any data leave the contracted region?**
3. **What is the retention period for prompts, inputs, and outputs, and can it be set to zero?**
4. **Which underlying foundation models do you use, from which providers, and will you notify us before changing them?** Subprocessor changes at the model layer are the version of fourth-party risk that AI makes acute.
5. **What evaluation, fairness testing, and red teaming have you performed, and will you share results or a summary?**
6. **What accuracy, availability, and error-rate commitments will you make contractually?**
7. **What happens to our data and our configuration at termination?**
8. **Can you support our explainability obligations if this output contributes to an adverse action?**

## Contract provisions to require

| Provision | Why |
|---|---|
| Prohibition on use of bank data for model training | The single most important term. Without it, customer data may be embedded in a model the bank cannot reach |
| Data residency and processing location commitment | GLBA, state privacy law, and examiner expectation |
| Notice before material model change or model provider change | Makes the reassessment trigger operable |
| Right to audit or right to receive independent assurance reports | SOC 2 alone does not cover model behavior |
| Disclosure of subprocessors including model providers | Fourth-party risk |
| Output ownership and intellectual property indemnity | Generated content and training data provenance claims |
| Termination assistance and data deletion certification | Exit planning under the interagency guidance |
| Incident notification within a defined period, covering AI-specific failures | Standard security incident terms often do not cover model behavior failures |

## Ongoing monitoring

Third-party AI is not assessed once. Minimum ongoing activity by criticality:

- **Critical and high:** annual reassessment, review of SOC 2 and any model assurance artifacts, tracking of model version changes, performance and error-rate review against contractual commitments, and confirmation that no new AI functionality has been enabled
- **Moderate:** biennial reassessment, annual confirmation of configuration and data handling
- **All:** inclusion in the vendor concentration analysis

**Concentration risk deserves specific attention.** If several critical use cases depend on one foundation model provider, that is a concentration even when the contracts run through different vendors. The dependency map in the inventory is what makes this visible, and it is a question examiners have begun asking.

## Exit planning

For every Tier 1 and Tier 2 third-party AI system, document:

- What the bank does if the service becomes unavailable for a day, a week, or permanently
- Whether an alternative provider exists and what switching would require
- What data and configuration the bank retains on exit
- Whether the business process can operate manually at reduced volume

The honest answer for some use cases is that the process stops. That is an acceptable answer if it is documented and accepted at the right level. It is not acceptable to have never asked.
