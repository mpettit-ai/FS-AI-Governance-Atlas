# AI Incident Report

An AI incident is any event where an AI system produced an incorrect, harmful, unauthorized, or unexpected outcome, or operated outside its approved conditions. **Near misses are reported.** A program that only hears about incidents with customer impact is hearing about a fraction of what happened.

Incidents feed the bank's existing operational risk event capture and, where applicable, security incident response. This template covers the AI-specific detail those processes do not ask for.

---

## Identification

| Field | |
|---|---|
| Incident ID | |
| Date and time of occurrence, and of detection | |
| Detection method (monitoring, user report, customer complaint, audit, vendor notification) | |
| System and inventory ID | |
| Tier | |
| Reported by | |
| Severity (Critical / High / Moderate / Low) | |

**The gap between occurrence and detection is a metric.** Track it. It measures whether monitoring works.

## Category

- [ ] Incorrect output (confabulation, factual error, miscalculation)
- [ ] Unfair or disparate outcome
- [ ] Data leakage or privacy breach
- [ ] Prompt injection or adversarial manipulation
- [ ] Unauthorized action taken by an agentic system
- [ ] Operation outside approved conditions or scope
- [ ] Unregistered system found in production
- [ ] Availability or performance failure
- [ ] Vendor-initiated model change without notice
- [ ] Inappropriate or prohibited content generated
- [ ] Other

## What happened

Narrative. What the system did, what it should have done, and the sequence of events. Include the specific inputs and outputs where they can be captured, redacted as necessary.

## Impact

| Question | |
|---|---|
| Were customers affected? How many, and how? | |
| Were employees affected? | |
| Was customer data exposed? To whom? | |
| Was a regulatory obligation implicated? | |
| Was a financial decision affected? Is it reversible? | |
| Was any incorrect output relied upon downstream? | |
| Estimated financial impact | |

## Immediate response

Actions taken, when, and by whom. Whether the system was suspended and for how long. Whether the kill switch was used and whether it performed as documented.

## Root cause

Go past the proximate cause. For AI incidents the useful question is usually not what the model did but why the design permitted it.

- Technical cause
- Control that should have caught it, and why it did not
- **Whether this failure mode was identified in the risk assessment.** If it was, the control failed. If it was not, the assessment method has a gap, and that gap is the more important finding
- Whether any other system shares the cause

## Notification

| Party | Required? | Notified? | Date |
|---|---|---|---|
| Use case owner and accountable executive | | | |
| AI Governance | | | |
| Information Security | | | |
| Privacy | | | |
| Compliance | | | |
| Legal | | | |
| Operational risk event capture | | | |
| Vendor | | | |
| Affected customers | | | |
| Regulator | | | |

Regulatory and customer notification determinations are made by Legal and Compliance, not by the program.

## Remediation

| Action | Owner | Due | Status |
|---|---|---|---|

## Program-level follow-through

Three questions, answered in writing:

1. **Do other systems share this exposure?** Query the inventory and say what was checked.
2. **Does the assessment template need a new question?** Most incidents that were not anticipated point to a question the intake or assessment never asked.
3. **Does a pre-approved pattern need to be suspended or amended?** Any incident involving a pattern suspends it pending working group review.

## Closure

Closed by, date, residual risk accepted by, and a one-line statement of what changed as a result. An incident that closes without anything changing is not closed.
