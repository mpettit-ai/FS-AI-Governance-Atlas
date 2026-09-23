# AI Documentation Requirements

What must exist, for whom, and how long it is kept. Documentation is the program's only durable output and the only thing an examiner can test.

## The principle

Every document has to answer a question someone will actually ask. The questions, in practice:

- **The examiner:** how do you know what AI you have, and how do you know it works as intended?
- **Internal audit:** did the program do what its own documentation says it does?
- **The next owner:** what is this, what is it for, and what should I not do with it?
- **The incident responder:** what was the system supposed to do, and what changed recently?

A document that serves none of these is overhead.

## Required artifacts by tier

| Artifact | Tier 1 | Tier 2 | Tier 3 | Tier 4 |
|---|---|---|---|---|
| Intake record and tier rationale | Required | Required | Required | Required |
| Inventory entry, maintained | Required | Required | Required | Required |
| Risk assessment | Full | Sections 1-7 | Short form | Not required |
| Model card | Required | Required | Not required | Not required |
| Data flow diagram | Required | Recommended | Not required | Not required |
| Privacy impact assessment | Required | If NPPI present | Not required | Not required |
| Security review record | Required | Required | Screening only | Not required |
| Adversarial and prompt injection test results | Required | Required if untrusted input | Not required | Not required |
| Evaluation protocol and results | Required | Required | Not required | Not required |
| Independent validation report | If model | If model | Not applicable | Not applicable |
| Fairness test plan and results | Required | If protected class exposure | Not required | Not required |
| Monitoring plan | Required | Required | Commitment only | Not required |
| Kill switch documentation and test evidence | Required | Required | Not required | Not required |
| Approval record with conditions and residual risk acceptance | Required | Required | Required | Registration only |
| Legal review record | Required | If novel | Not required | Not required |
| Vendor due diligence record | If third party | If third party | If third party | Pattern covers |
| Acceptable use attestation | Required | Required | Required | Required |

## Version control

**Everything is versioned.** The version in force at the time of any decision must be recoverable, because the question "what was the approved configuration when this happened" is the first question in every incident and the second question in every examination.

Minimum: document version, effective date, author, approver, and change summary. Model cards additionally record the model version and provider, including vendor-initiated changes.

## Retention

Aligned to the bank's records retention schedule. Where the schedule is silent on AI artifacts, the defaults:

| Artifact | Retention |
|---|---|
| Intake, assessment, and approval records | Life of the system plus 7 years |
| Model cards, all versions | Life of the system plus 7 years |
| Fairness testing results | 7 years, or the applicable ECOA and FHA record retention period, whichever is longer |
| Adverse action reason code evidence | Per Regulation B requirements |
| Monitoring results | 3 years, or life of the system if shorter |
| Prompt and output logs | Per records retention classification of the underlying content, and no shorter than is needed to investigate an incident |
| Incident records | 7 years |
| Committee minutes and decisions | Per corporate records schedule |

**Prompt logs deserve deliberate thought.** They may contain customer information, they are discoverable, and they are also the only way to investigate an AI incident. The retention decision should be made by Legal and Records Management jointly rather than defaulting to whatever the platform does.

## What good documentation looks like

- **Specific.** "Monitoring will be performed regularly" fails. "Override rate reviewed monthly by the operations manager, escalated to the working group above 15 percent" passes.
- **Owned.** Every requirement and condition names a person, not a team.
- **Current.** A model card describing a version retired eight months ago is worse than no model card, because it is evidence of a control that stopped operating.
- **Candid about limits.** A limitations section that says the system was not tested on a population it will encounter is a stronger document than one that omits it. Examiners and auditors read the omissions.
