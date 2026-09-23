# AI Risk Assessment

Scale this document to tier. Tier 1 completes all sections. Tier 2 completes sections 1 through 7. Tier 3 completes the short form at the end and nothing else.

**Reference:** `Use case ID` | `Tier` | `Assessment date` | `Assessor` | `Next reassessment`

---

## 1. System description

Purpose, in the requester's own words. Architecture: what components, what data flows where, what the system can do. Model(s) used and version(s). Deployment pattern: where it runs, who can reach it.

Include a data flow diagram for Tier 1.

## 2. Intended use and known limitations

**Intended use.** What this system is for, stated precisely enough that a reasonable person could identify a use outside it.

**Explicitly out of intended use.** The uses the system will not be relied on for. This list is a control: it is what the interface should warn about and what the acceptable use language should prohibit.

**Known limitations.** What the system is bad at, what it has not been tested on, what data it has not seen, and where its outputs should be treated with additional skepticism. Publish this to the users of the system. A limitations section that only lives in a governance file is not a control.

## 3. Data assessment

| Question | Response |
|---|---|
| Sources, classification, and owner for each input | |
| Lawful basis and permitted use confirmation from Data Governance | |
| Representativeness of training or reference data for the affected population | |
| Known gaps or skew in the data | |
| Retention and deletion, including at the provider | |
| Training use prohibition confirmed contractually (third-party only) | |

## 4. Risk identification

Assess each. Mark not applicable with a reason rather than leaving blank; a blank reads as unconsidered.

| Risk | Applicable | Description in this context | Inherent rating | Controls | Residual rating |
|---|---|---|---|---|---|
| Confabulation and factual error | | | | | |
| Disparate impact or unfair outcome | | | | | |
| Privacy and data leakage | | | | | |
| Prompt injection and adversarial manipulation | | | | | |
| Overreliance and automation bias | | | | | |
| Explainability insufficient for regulatory obligation | | | | | |
| Model drift and performance decay | | | | | |
| Third-party dependency and concentration | | | | | |
| Unauthorized action (agentic systems) | | | | | |
| Intellectual property and content provenance | | | | | |
| Availability and resilience | | | | | |
| Records and evidentiary integrity | | | | | |

Ratings: Low, Moderate, High, Critical. Use the bank's existing risk rating definitions rather than new ones.

## 5. Human oversight design

- Who reviews, at what point, and with what authority
- What qualifies that reviewer to disagree with the system
- How the interface communicates uncertainty, and whether it does
- How overrides are captured and reviewed
- **Automation bias mitigation:** what stops the review from becoming a rubber stamp. Be specific. Sampling, blind review, periodic calibration, or override rate monitoring with a threshold
- What the reviewer is measured on, since a reviewer measured on throughput will approve

## 6. Testing, evaluation, verification, and validation

| Element | Response |
|---|---|
| Evaluation method and why it is appropriate | |
| Test set: size, composition, how representative, version | |
| Acceptance criteria and thresholds, with rationale | |
| Results against criteria | |
| Adversarial and prompt injection testing performed and results | |
| Independent validation (model risk) status, if applicable | |
| Re-evaluation trigger and cadence | |

For generative systems, state plainly that this is an evaluation protocol rather than SR 11-7 validation, and describe why that is the appropriate method. See [`docs/06-model-risk-alignment.md`](../docs/06-model-risk-alignment.md).

## 7. Monitoring plan

Metrics, thresholds, frequency, owner, escalation path, and reporting destination. Reference [`docs/09-monitoring-and-metrics.md`](../docs/09-monitoring-and-metrics.md) for the metric set by system type.

Include the kill switch: what it is, who can invoke it, how long it takes, and when it was last tested.

## 8. Fairness and consumer impact (Tier 1, and Tier 2 with protected class exposure)

Reference the completed [`bias-and-fairness-test-plan.md`](bias-and-fairness-test-plan.md). Summarize here:

- Protected classes considered and proxy analysis performed
- Metrics used and thresholds applied, with the rationale for choosing them
- Results and any disparities found
- Remediation taken or accepted, and by whom
- Adverse action reason code approach and evidence that reasons are specific and accurate, where Regulation B applies

## 9. Regulatory analysis (Tier 1)

Applicable federal and state requirements per [`docs/11-regulatory-landscape.md`](../docs/11-regulatory-landscape.md), how each is satisfied, disclosure requirements by jurisdiction, and Legal sign-off on anything unsettled.

## 10. Decision

| Field | |
|---|---|
| Overall residual risk rating | |
| Recommendation | Approve / Approve with conditions / Not approved |
| **Conditions** (specific, testable, owner, due date) | |
| Residual risk accepted by (name, title, date) | |
| Reassessment date | |
| Second line sign-offs: Security / Privacy / Compliance / Model Risk / Legal | |

---

## Short form (Tier 3)

1. What does it do and who is affected?
2. What data goes in, and what is the highest classification?
3. Who reviews the output and what can they do about it?
4. What is the worst realistic outcome if it is wrong, and what limits that?
5. What will you monitor, how often, and who looks at it?
6. How do you turn it off?

Governance response: tier confirmation, conditions if any, reassessment date.
