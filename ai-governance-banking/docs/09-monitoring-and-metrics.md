# Monitoring and Metrics

A program that cannot report coverage cannot claim it has any. Metrics are also the mechanism that converts governance from an opinion into a managed function, which is what changes the conversation with the board and with examiners.

## Program metrics

Reported monthly to the working group, quarterly to the AI Risk Committee, and at least semiannually to the board risk committee.

| Metric | Definition | Why it earns its place | Target |
|---|---|---|---|
| **Inventory coverage** | Registered systems as a percentage of systems identified through independent discovery (procurement, CASB, platform admin, vendor attestation) | The only metric that tests whether the inventory is honest | Above 90 percent |
| **Intake cycle time by tier** | Median business days from submission to decision | Tests whether the front door is faster than the side door | Within published service levels |
| **Tier distribution** | Count and percentage by tier | A program with almost everything in Tier 1 is miscalibrated and will be routed around | Majority in Tiers 3 and 4 |
| **Pattern utilization** | Percentage of intake resolved through a pre-approved pattern | Direct measure of whether the fast path works | Above 50 percent at maturity |
| **Open conditions by age** | Approval conditions past due, bucketed 0-30, 31-60, 61-90, 90+ days | Where programs quietly fail | Zero past 90 days |
| **Exception aging and count** | Active exceptions by tier and age | Exceptions that never close are unaccepted risk | No Tier 1 exception past 12 months |
| **Incidents and near misses** | Count by category and severity, trended | Absence of incidents in a growing program means underreporting, not safety | Trend, not target |
| **Reassessment currency** | Percentage of Tier 1 and 2 systems within their reassessment cycle | Registers decay | Above 95 percent |
| **Shadow AI found** | Systems discovered rather than self-registered, trended | Should fall over time. If it does not, intake is not credible | Declining |

**Read these together.** Short cycle time with low coverage means the program is fast at governing the wrong population. High coverage with long cycle time means the program is about to lose the population it has.

## Use case monitoring

Every approved Tier 1, 2, and 3 system has a monitoring plan with a named owner. Requirements by system type:

### Predictive and decision systems

- Performance against declared metrics, on the model risk cadence
- Input drift and population stability
- Output distribution shift
- Override rate and override reason analysis where a human reviews
- Disparate impact metrics on the fairness testing cadence, at minimum annually for anything with protected class exposure
- Adverse action reason code distribution where Regulation B applies

### Generative systems

- Output sampling rate and review results, trended
- Confabulation rate against the evaluation set, on version change and on cadence
- Refusal rate: both under-refusal and over-refusal, since an assistant that refuses everything is a failed deployment that nobody reports
- Citation fidelity for retrieval systems: does the cited source actually support the statement
- Escalation-to-human rate and the reasons
- User-reported error volume
- Model version changes, whether initiated by the bank or the vendor

### Agentic systems

Everything under generative, plus:

- Action volume by type
- Failed and rejected actions
- Human confirmation rate for actions requiring it
- Any action taken outside the enumerated authority, which is a reportable incident regardless of outcome

## Thresholds and escalation

Monitoring without a threshold is data collection. Each plan defines:

| Level | Meaning | Response |
|---|---|---|
| **Green** | Within expected range | Continue, report on cycle |
| **Amber** | Outside expected range, no customer impact identified | Owner investigates within 5 business days, reports to governance manager |
| **Red** | Material deviation, customer impact, or control failure | Immediate notification to governance manager and second line, consider suspension, incident report opened |

Thresholds are set at approval, by the use case owner with second line concurrence, and revisited at reassessment. A threshold nobody can ever breach is not a threshold.

## Board reporting

One page, quarterly, within technology and model risk reporting rather than beside it:

1. Inventory: total systems, by tier, by category, with trend and coverage estimate
2. What changed: new Tier 1 and 2 systems approved, and what they do in one line each
3. Risk posture: open high residual risks, open conditions past due, active exceptions
4. Incidents: count, severity, and what was learned
5. Program health: cycle time against service level, pattern utilization
6. Forward view: what is coming in the next quarter and what it will require

**Say what is not yet covered.** A board report that presents a program as complete when the inventory is at 70 percent coverage is the kind of statement that becomes a problem in an examination. Reporting a known gap with a plan is a sign of a functioning program, not a weak one.
