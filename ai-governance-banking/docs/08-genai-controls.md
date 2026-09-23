# Generative AI Controls

Generative systems introduce failure modes the bank's existing control set was not designed for. This section maps those to controls, using the twelve risks in **NIST AI 600-1, the Generative AI Profile**, framed for a banking context.

## The twelve GenAI risks, in a bank

| Risk | What it looks like in a bank | Primary controls |
|---|---|---|
| **Confabulation** | An assistant states an incorrect fee, rate, or policy to a customer or to a branch employee who repeats it | Retrieval grounding with citation, fixed evaluation set with accuracy thresholds, human review for customer-facing output, published limitations, output sampling in production |
| **Data privacy** | Customer NPPI entering a third-party model; inference of information the customer did not provide | Data loss prevention on prompts, tenant isolation, contractual training prohibition, zero retention, approved-tool-only policy |
| **Information security** | Prompt injection, insecure plugin and tool use, model supply chain compromise, credential exposure in prompts | Input and output filtering, least privilege on tool and system access, adversarial testing before launch, no secrets in prompts, logging of prompts and outputs |
| **Harmful bias and homogenization** | Disparate outcomes in marketing targeting, collections treatment, or service quality; convergence on a single model creating correlated errors | Fairness testing, disparate impact analysis, model diversity where feasible, human review at decision points |
| **Intellectual property** | Generated content reproducing protected material; unclear ownership of output; training data provenance claims | Vendor indemnity, output scanning for code, legal review of publication paths, provenance documentation |
| **Information integrity** | Synthetic content used in fraud, including voice cloning against phone verification; fabricated documents in loan files | Content provenance where available, fraud control updates, stepped-up authentication that does not rely on voice alone, employee awareness |
| **Value chain and component integration** | Dependency on a model provider several layers removed from the contracted vendor | Subprocessor disclosure, dependency mapping, concentration analysis |
| **Human-AI configuration** | Automation bias: reviewers approving output because the system produced it; overreliance by branch and contact center staff | Oversight design that requires an independent judgment, override rate monitoring, training, interface design that surfaces uncertainty |
| **Environmental** | Compute footprint of training and inference | Tier 1 disclosure, procurement consideration |
| **Dangerous or violent content** | Low direct relevance; matters for customer-facing systems and content moderation | Content filtering, escalation path to a human |
| **CBRN information** | Not applicable in a banking context in ordinary use | Vendor safety controls relied upon |
| **Obscene or abusive content** | Customer-facing systems generating inappropriate content; employee misuse | Content filtering, acceptable use policy, logging |

## The controls that matter most, in order

**1. Approved tools only, with a real alternative.** An acceptable use policy that prohibits unapproved AI tools without providing a sanctioned one produces shadow usage, not compliance. The enterprise tool has to be good enough to use.

**2. Data loss prevention on prompts.** Prompt content is an egress channel that most DLP deployments do not inspect. Extend existing DLP policy to AI destinations and to the prompt field of sanctioned tools where the platform supports inspection.

**3. Retrieval grounding with citation for anything factual.** A system that answers questions about bank policy should retrieve the policy and cite it, not generate from parametric memory. This single design choice eliminates a large share of confabulation risk and makes errors traceable.

**4. Entitlement-aware retrieval.** A retrieval system must respect the requesting user's existing entitlements. A system that can surface content the user could not otherwise access has created an access control bypass with a friendly interface. This is the most common serious finding in early enterprise deployments.

**5. Prompt injection testing before launch.** Any system that processes untrusted input, including customer messages, documents, emails, or web content, must be tested for injection before production. Any system that also has tool or action authority must be tested with the assumption that injection will succeed, and its blast radius bounded accordingly.

**6. Bounded action authority for agentic systems.** For any system that can act rather than only respond: enumerate every action it can take, apply least privilege, require human confirmation for anything irreversible or financial, log every action with the reasoning trace, and provide a documented kill switch.

**7. Logging.** Prompts, outputs, model version, user, timestamp, and retrieved sources, retained per the bank's records schedule. Without this, no incident can be investigated and no examiner question can be answered.

**8. Output sampling in production.** A defined percentage of outputs reviewed by a qualified person, with results trended. This is the closest generative equivalent to ongoing monitoring, and it is what detects drift after a vendor model update.

## Disclosure

Where a customer interacts with a generative system, disclosure is required or advisable depending on jurisdiction. The Utah Artificial Intelligence Policy Act requires disclosure on request for regulated occupations and proactively in some contexts; other states differ. The defensible default for a multi-state institution is **clear proactive disclosure in every customer-facing generative interaction**, along with an obvious path to a human.

This is a case where the compliance floor and good practice point the same direction, and where varying disclosure by state creates more operational risk than it avoids.

## What to test before a customer-facing launch

A minimum pre-launch evaluation, documented and repeatable:

- Accuracy against a fixed question set with a defined threshold
- Refusal behavior: does it decline appropriately on advice it should not give, including legal, tax, and investment advice
- Prompt injection resistance, including injection embedded in customer-supplied documents
- Data leakage: can it be induced to reveal other customers' data, system prompts, or internal content
- Fair treatment: does response quality vary across customer segments and dialect or language variation
- Escalation: does the path to a human work, under load, at the point a customer is frustrated
- Failure behavior: what the customer sees when the model is unavailable

The escalation test is the one most often skipped and the one most likely to generate complaints.
