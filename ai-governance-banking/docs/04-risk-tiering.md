# Risk Tiering

Tiering is the most important design decision in the program. It determines who reviews what, how long it takes, and whether teams use the front door or go around it.

## The four dimensions

Tier is driven by four factors. Score each, then take the tier indicated by the **highest** scoring dimension. Risk does not average.

### 1. Consumer and employee impact

| Score | Description |
|---|---|
| **High** | Output determines or materially influences a credit decision, account opening or closure, pricing, fraud or AML disposition affecting a customer, collections action, or an employment decision including hiring, evaluation, or termination |
| **Medium** | Output is delivered to a customer or employee as information, recommendation, or content, but a person decides what to do with it |
| **Low** | Output is used internally to inform analysis, with no direct path to a customer or employee outcome |
| **Minimal** | Output is a drafting aid or productivity assist reviewed by the author before any use |

### 2. Data sensitivity

| Score | Description |
|---|---|
| **High** | Customer non-public personal information, account or transaction data, credit bureau data, protected class data or close proxies, or material non-public information |
| **Medium** | Internal confidential business data, employee data, or aggregated customer data |
| **Low** | Internal data classified as general business use |
| **Minimal** | Public data only |

### 3. Autonomy

| Score | Description |
|---|---|
| **High** | The system acts or decides without a person reviewing the individual output, including agentic systems that execute actions against other systems |
| **Medium** | Human on the loop: aggregate monitoring with intervention capability, but no per-output review |
| **Low** | Human in the loop: every output reviewed by a qualified person before it takes effect |
| **Minimal** | Output is a suggestion the user may ignore entirely, with no default acceptance |

### 4. Regulatory exposure

| Score | Description |
|---|---|
| **High** | Subject to ECOA and Regulation B adverse action requirements, fair lending review, BSA/AML model expectations, SR 11-7 model risk, or a state high-risk AI designation |
| **Medium** | Subject to consumer disclosure obligations, UDAAP exposure, privacy law automated decision-making provisions, or Reg DD and Reg Z content requirements |
| **Low** | General GLBA safeguards and information security obligations |
| **Minimal** | No specific regulatory hook beyond internal policy |

## Tier definitions

| Tier | Trigger | Approver | Target turnaround | Requirements |
|---|---|---|---|---|
| **Tier 1: Critical** | Any dimension scored High **and** consumer-facing or credit-related | AI Risk Committee | 30 business days | Full risk assessment, model card, fairness testing, independent validation if it meets the model definition, privacy impact assessment, documented human oversight, monitoring plan, kill switch, legal review |
| **Tier 2: High** | Any dimension scored High | AI Governance working group | 15 business days | Risk assessment, model card, targeted fairness testing where protected class exposure exists, monitoring plan, kill switch, second line reviews by discipline |
| **Tier 3: Moderate** | Highest dimension is Medium | AI Governance Manager | 5 business days | Short-form assessment, documented owner, monitoring commitment, data handling confirmation |
| **Tier 4: Limited** | All dimensions Low or Minimal, and matches a pre-approved pattern | Self-service registration | Immediate | Registration record, acceptable use attestation |

## Pre-approved patterns

A pre-approved pattern is a combination of approved model, approved data classification, and approved usage conditions that the working group has already reviewed. A use case matching a pattern registers instead of being assessed.

**Starter patterns for a bank:**

| Pattern | Conditions |
|---|---|
| **P-01 Internal drafting assistant** | Approved enterprise GenAI tool, internal general business data only, human authors and reviews all output, no customer-facing publication without normal review, no automated action |
| **P-02 Meeting summarization** | Approved tool within the enterprise tenant, participants notified, output treated as a draft, no privileged or investigative discussions |
| **P-03 Code assistance** | Approved tool, no production secrets or customer data in prompts, all output through normal code review and SDLC, license and provenance scanning applied |
| **P-04 Internal document search and retrieval** | Retrieval limited to sources the user is already entitled to see, source citation displayed, no generation of new factual claims without citation |
| **P-05 Internal knowledge assistant for employees** | Curated internal content only, confidence and citation displayed, explicit fallback to a human channel, no policy or legal interpretation delivered as authoritative |

**Patterns are revoked as easily as they are granted.** Any incident involving a pattern suspends it pending working group review. This is what keeps a fast path from becoming an unmonitored one.

## Automatic Tier 1 triggers

Regardless of scoring, the following are always Tier 1:

- Any system contributing to a credit underwriting, pricing, or adverse action decision
- Any system producing or contributing to BSA/AML alerting, suspicious activity determination, or sanctions screening disposition
- Any customer-facing generative system that produces free-form text to a customer
- Any agentic system with authority to move money, change account status, or modify entitlements
- Any system used in hiring, performance evaluation, or termination decisions

## Reassessment triggers

Tier is not permanent. Reassessment is required when:

- The underlying model or model version changes materially, including a vendor updating a foundation model
- The data classification of inputs changes
- The use case extends to a new affiliate, new jurisdiction, or new customer segment
- Human oversight is reduced, including moving from in the loop to on the loop
- The system is connected to a new downstream system or granted new action authority
- An incident occurs
- On the scheduled cycle: annually for Tier 1 and 2, every two years for Tier 3

**The vendor update trigger is the one most often missed.** A third-party AI feature can change behavior overnight without a change request on the bank's side. [`07-third-party-ai.md`](07-third-party-ai.md) covers the contractual notice requirement that makes this trigger workable.

## Worked examples

| Use case | Impact | Data | Autonomy | Regulatory | Tier |
|---|---|---|---|---|---|
| Credit scoring model for small business lending | High | High | Medium | High | **1** |
| Generative assistant answering customer questions in the mobile app | Medium | High | Medium | High | **1** (automatic trigger) |
| AML alert prioritization and triage scoring | High | High | Medium | High | **1** |
| Marketing segmentation for a deposit campaign | Medium | Medium | Low | Medium | **2** |
| Fraud model scoring card transactions in real time | High | High | High | High | **1** |
| Contact center agent assist suggesting next best response to a live agent | Medium | High | Low | Medium | **2** |
| Internal policy question assistant for branch staff | Low | Low | Low | Minimal | **3** (Medium if it answers compliance questions) |
| Drafting assistant for internal presentations | Minimal | Low | Minimal | Minimal | **4** via P-01 |
| Vendor's AI-based resume screening in the applicant tracking system | High | Medium | Medium | High | **1** (automatic trigger) |

The resume screening example is the one that catches programs by surprise. It is usually enabled by a vendor inside a system HR already owns, nobody registered it, and it sits squarely inside employment decision-making.
