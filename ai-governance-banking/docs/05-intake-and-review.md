# Intake and Review Workflow

The program lives or dies here. If the front door is slower than going around it, teams go around it, and the inventory becomes a record of the compliant rather than a record of the real.

## Design principles

1. **One front door.** A single intake regardless of whether the outcome is model risk validation, a security review, a privacy assessment, or a pattern registration. The governance function routes. The requester does not have to know which second line function owns what.
2. **Tier before assess.** Tier assignment happens within one business day of submission, from the intake form alone. The requester learns immediately what the path looks like.
3. **Parallel, not serial.** Security, privacy, compliance, and model risk review concurrently against the same package. Serial routing is where fifteen days becomes sixty.
4. **The assessment is proportionate.** A Tier 3 use case does not get a Tier 1 questionnaire. Asking a marketing analyst forty questions about adversarial robustness teaches them the program is not serious about their time.
5. **Conditions, not vetoes.** Most outcomes are approval with conditions. A clean no should be rare enough that it carries weight.

## The workflow

```
  Requester submits intake form
            |
            v
  [Day 1] Triage and tier assignment          <- AI Governance Manager
            |
     +------+---------------------+
     |                            |
     v                            v
  Matches pre-approved       Requires assessment
  pattern (Tier 4)           (Tier 1, 2, 3)
     |                            |
     v                            v
  Register and confirm       Assessment package issued
  Done, same day             (scaled to tier)
                                  |
                                  v
                       Parallel second line review
                    Security | Privacy | Compliance |
                    Model Risk | Legal (Tier 1)
                                  |
                                  v
                       Findings consolidated,
                       conditions drafted
                                  |
                                  v
                    Approval decision by tier authority
                                  |
                       +----------+----------+
                       |                     |
                       v                     v
              Approved with            Not approved
              conditions               (documented rationale,
                       |                alternatives offered)
                       v
              Registered in inventory,
              monitoring plan active,
              reassessment date set
```

## Stage detail

### Triage, day 1

The governance manager reads the intake and does four things:

1. Confirms the use case is in scope and is one use case rather than several bundled together
2. Assigns tier and records the rationale, because the rationale is what gets challenged later
3. Checks the inventory for an existing system that already does this, which is more common than teams expect
4. Tells the requester the tier, the path, the target date, and what they need to produce

**The tier rationale is a written field, not a dropdown.** Two sentences. This is the single most audit-relevant record the program produces and the thing an examiner will sample.

### Assessment

Packages by tier:

| Tier | Package |
|---|---|
| 1 | Full risk assessment, model card, fairness test plan and results, privacy impact assessment, security review including adversarial testing, monitoring plan, kill switch evidence, legal review, independent validation where the model definition is met |
| 2 | Risk assessment, model card, targeted fairness testing where protected class exposure exists, security review, monitoring plan, kill switch evidence |
| 3 | Short-form assessment: purpose, data, oversight, failure mode, monitoring commitment |
| 4 | Registration and acceptable use attestation |

### Parallel review

Each second line function reviews within the tier service level, against a defined question set rather than open-ended judgment:

- **Information Security:** data flow and residency, authentication and entitlements, prompt injection and adversarial exposure, logging, secrets handling, connection to production systems
- **Privacy:** lawful basis, data minimization, retention, whether inputs can be used for vendor training, automated decision-making disclosure obligations
- **Compliance:** applicable regulation, disclosure requirements, fair lending exposure, UDAAP exposure, recordkeeping
- **Model Risk:** does this meet the model definition, what validation applies, what is the conceptual soundness view
- **Legal (Tier 1):** contractual terms, intellectual property and training data provenance, liability allocation, regulatory interpretation

**A non-response within the service level is treated as no objection, and that is recorded.** This is what keeps the program's turnaround commitment credible when it depends on functions that do not report to it. It also, in practice, is what gets functions to respond.

### Conditions and approval

Conditions must be **specific, testable, and owned**. "Ensure appropriate monitoring" is not a condition. "Report monthly on override rate and escalate to the working group if override rate exceeds 15 percent, owner J. Smith" is a condition.

Every approval records:

- Tier and rationale
- Residual risk rating and who accepted it
- Conditions with owners and due dates
- Reassessment date
- Monitoring plan and its owner

### After approval

The use case enters the inventory as an active record. Conditions with due dates are tracked to closure in the risk register. **Tracking conditions to closure is where most programs quietly fail.** An approval with open conditions that nobody follows up on is worse than no approval, because it creates documentary evidence of a control that did not operate.

## Exceptions

Where a use case cannot meet a requirement, the exception follows the bank's existing exception and risk-acceptance process rather than a new one. AI-specific additions:

- Exceptions for Tier 1 systems require AI Risk Committee approval and cannot exceed twelve months
- Every exception requires a documented compensating control and a remediation plan, not just an expiry date
- Exception aging is a reported program metric

## Shadow AI

Discovery will find AI already in production that never came through intake. The response determines whether teams trust the program.

**The approach:** register first, assess second, and do not punish. A team that self-reports a system gets a fast, non-punitive path to compliance. A system found through discovery gets the same path. Enforcement is reserved for continued operation after a documented decision, and for the automatic Tier 1 categories where the risk does not permit patience.

The reason is practical. Every program that opened with enforcement got a smaller inventory, not a smaller problem.
