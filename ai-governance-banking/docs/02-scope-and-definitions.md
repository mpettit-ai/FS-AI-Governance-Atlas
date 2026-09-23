# Scope and Definitions

Definitions are the part of an AI program most likely to be argued about and least likely to be settled. The approach here is to define as little as possible and to define it by consequence rather than by technique.

## The definitional trap

Any program that begins by defining artificial intelligence spends a quarter in a debate it cannot win. Vendors call everything AI. Engineers correctly point out that logistic regression has been in the credit shop since the 1970s. Legal wants a definition tight enough to defend and broad enough to be safe.

**Resolve it by asking a different question.** Not "is this AI," but:

1. Does the output influence a decision about a person, an account, a control, or a financial figure?
2. Is the relationship between input and output learned from data rather than specified by a person?
3. Can the output vary for materially similar inputs, or change over time without a code release?

If the answer to the first question is yes and either of the other two is yes, register it. The tier decides how much scrutiny follows. Registration is cheap. Being wrong about scope is not.

## Core definitions

**AI system.** A system that, for a given set of objectives, generates outputs such as predictions, recommendations, content, or decisions, where the mapping from input to output is derived from data rather than fully specified in advance. Adapted from ISO/IEC 22989 and the NIST AI RMF.

**Model.** As defined in the bank's model risk management policy, consistent with SR 11-7: a quantitative method that applies statistical, economic, financial, or mathematical theories, techniques, and assumptions to process input data into quantitative estimates. Most predictive AI in a bank is a model. Some generative AI is not, and that gap is the reason this program exists.

**Generative AI.** An AI system that produces new content such as text, code, images, audio, or structured data, typically built on a foundation model.

**Foundation model.** A model trained on broad data at scale and adaptable to a wide range of downstream tasks.

**Agentic system.** An AI system that plans and executes multi-step actions against tools, systems, or external services with limited human intervention per step. Agentic systems are treated as a distinct risk class because the relevant question shifts from output accuracy to action authority.

**Use case.** A specific application of an AI system to a specific business purpose with a named owner. The unit of governance is the use case, not the model. The same foundation model supporting a marketing draft assistant and a fraud narrative generator is two use cases with two tiers.

**Human in the loop.** A person reviews each individual output before it takes effect and has the authority and practical ability to override it. Not satisfied by a person who can review outputs in principle but reviews them in batch after the fact.

**Human on the loop.** A person monitors system behavior in aggregate and can intervene, but does not review each output.

**Consumer-facing.** The output is delivered to, or materially affects, a retail or small business customer, whether or not the customer knows AI was involved.

**Confabulation.** The generation of confidently stated but factually incorrect content. The term used in NIST AI 600-1 in preference to "hallucination," and preferable in bank documentation because it avoids implying intent or perception.

## What registration requires versus what assessment requires

| | Registration | Assessment |
|---|---|---|
| Trigger | Any in-scope system | Tier 1, 2, or 3 |
| Effort | One form, roughly fifteen minutes | Proportionate to tier |
| Produces | Inventory record | Risk assessment, conditions, approval |
| Who does it | Use case owner | Use case owner with second line |

Tier 4 systems register and stop there, provided they match a pre-approved pattern. This is what keeps the front door open.

## Affiliate and jurisdiction scope

A multi-state holding company with separately branded bank affiliates has to answer one question per use case that a single-charter institution does not: **which affiliates and which customer jurisdictions does this touch?**

This matters because:

- State AI disclosure obligations differ, and the Utah Artificial Intelligence Policy Act and the Colorado AI Act impose different duties on different actors
- State privacy laws differ in their treatment of automated decision-making and profiling
- A use case piloted in one affiliate and then extended to others is a material change requiring reassessment, not a rollout

The intake form captures affiliate and jurisdiction as required fields for this reason, and a change in either is an explicit reassessment trigger.

## Exclusions, stated plainly

The following are out of scope for this program and remain governed elsewhere:

- Deterministic rules engines and decision tables, governed by change management
- Standard reporting, business intelligence, and descriptive analytics without a learned component
- Robotic process automation executing fixed logic
- Spell check, search ranking within internal document stores, and similar embedded utility functions with no decision consequence
- Vendor AI used solely by the vendor to deliver a service, where the bank provides no data and receives no AI-derived output. If either of those is untrue, it is in scope through third-party risk.

The last exclusion is narrow on purpose. It is the one vendors will try to widen.
