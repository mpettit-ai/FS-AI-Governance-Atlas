# Model Card

A model card is the durable record of what a system is, what it was tested on, and what it should not be used for. It is written for the next person, who will not have been in any of the meetings.

Required for Tier 1 and Tier 2. Maintained by the use case owner, versioned, and updated on every model version change.

---

## Identification

| Field | |
|---|---|
| System name and inventory ID | |
| Version and date | |
| Owner (accountable executive, day-to-day owner) | |
| Developer (internal team or vendor) | |
| Model type (predictive, generative, retrieval, agentic, hybrid) | |
| Underlying model(s) and version(s), including foundation model and provider | |
| Tier | |
| Model risk inventory ID, if applicable | |

## Intended use

- **Primary intended use.** Precise enough that an off-label use is identifiable.
- **Intended users.** Who operates it and what training they receive.
- **Out of scope uses.** The explicit list. This is the control.
- **Affiliates and jurisdictions approved for.**

## Inputs and outputs

- Input features or prompt structure, and the data classification of each
- Output format and how it is consumed downstream
- Systems that consume this output, which is what makes dependency mapping possible
- Confidence, uncertainty, or citation information surfaced to the user, if any

## Training and reference data

- Sources, date range, and volume
- Representativeness of the affected population, with the analysis that supports the claim
- Known gaps, skew, or underrepresented segments
- Preprocessing, exclusions, and handling of missing data
- For third-party foundation models: what the provider has disclosed about training data, and what they have not

## Evaluation

| Element | |
|---|---|
| Test set description and version | |
| Metrics and why these metrics | |
| Results | |
| Performance by relevant segment, including protected class analysis where applicable | |
| Adversarial and robustness testing performed | |
| Comparison to the prior version or to the existing process | |
| Date of evaluation and who performed it | |

## Limitations

The section that earns the document its place. Be specific and be candid.

- Conditions under which performance degrades
- Populations, products, or scenarios the system has not been tested on
- Known failure modes and how they present
- What the system cannot explain about its own output
- Where a human should not defer to it

**Publish this to users.** Limitations known only to governance are documentation, not a control.

## Human oversight

Review point, reviewer qualification, override mechanism, override rate to date, and automation bias controls in place.

## Monitoring

Metrics tracked, thresholds, frequency, owner, and where results are reported. Current status against thresholds.

## Fairness

Approach, metrics, thresholds, results, disparities found, and remediation. Adverse action reason approach where Regulation B applies.

## Change history

| Version | Date | What changed | Who approved | Reassessment triggered |
|---|---|---|---|---|

**Include vendor-initiated changes.** A foundation model update behind a third-party product is a change to this system whether or not the bank initiated it.
