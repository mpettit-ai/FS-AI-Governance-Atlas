# AI Governance Standard

**Status:** standard, issued under the bank's Information Technology Risk Policy and Enterprise Risk Management Policy.
**Owner:** AI Governance.
**Applies to:** all affiliates, lines of business, and third parties developing or operating AI systems for the bank.
**Review:** annual, or on material regulatory change.

---

## 1. Scope

As defined in [`docs/02-scope-and-definitions.md`](../docs/02-scope-and-definitions.md). Any system producing outputs derived from data rather than fully specified logic, where those outputs affect a customer, an employee, a financial statement, a regulatory filing, or a risk decision.

Systems meeting the bank's model definition remain governed by the Model Risk Management Policy. This standard adds AI-specific requirements and governs AI that falls outside that definition.

## 2. Requirements

### 2.1 Registration

**R-01.** Every in-scope AI system shall be registered in the AI inventory before production deployment.

**R-02.** Registration shall identify an accountable executive with authority to suspend the system.

**R-03.** AI functionality enabled within existing purchased software constitutes a new AI system and shall be registered.

### 2.2 Risk assessment and approval

**R-04.** Every registered system shall be assigned a risk tier per [`docs/04-risk-tiering.md`](../docs/04-risk-tiering.md), with a documented written rationale.

**R-05.** Tier 1, 2, and 3 systems shall complete a risk assessment proportionate to tier prior to production deployment.

**R-06.** Tier 4 systems shall match a pre-approved pattern. A system not matching a pattern is not Tier 4.

**R-07.** Approval conditions shall be specific, testable, assigned to a named owner, and tracked to closure.

**R-08.** No system shall be deployed to production prior to the completion of its applicable review.

### 2.3 Data

**R-09.** Input data shall be classified, and the highest classification present shall drive control requirements.

**R-10.** Customer non-public personal information shall not be transmitted to a third-party AI service absent a contractual prohibition on use of that data for model training or improvement.

**R-11.** Data processing location shall be known, documented, and consistent with the bank's data residency requirements.

**R-12.** Retention of prompts, inputs, and outputs shall be defined and consistent with the bank's records retention schedule.

### 2.4 Human oversight

**R-13.** Every Tier 1 and Tier 2 system shall have a documented human oversight design identifying the reviewer, the review point, and the reviewer's authority and qualification.

**R-14.** Reduction in human oversight, including a change from human in the loop to human on the loop, constitutes a material change requiring reassessment.

**R-15.** Systems with human review shall monitor override rate, with a defined threshold and escalation.

### 2.5 Consumer protection

**R-16.** No AI system shall render a final adverse credit decision, account closure, or account denial without human review.

**R-17.** Any system contributing to an adverse action under Regulation B shall be capable of producing specific and accurate principal reasons. Inability to do so is a bar to that use.

**R-18.** Systems with protected class exposure shall complete fairness testing prior to deployment and at least annually thereafter, with a documented search for less discriminatory alternatives where a disparity is identified.

**R-19.** Customer-facing generative systems shall disclose that the customer is interacting with an AI system and shall provide a clear path to a human.

### 2.6 Security and resilience

**R-20.** Systems processing untrusted input shall undergo prompt injection testing prior to deployment.

**R-21.** Agentic systems shall operate under least privilege, with every permitted action enumerated, human confirmation required for irreversible or financial actions, and complete action logging.

**R-22.** Every Tier 1 and Tier 2 system shall have a documented and tested means of deactivation that does not require a code release.

**R-23.** Prompts, outputs, model version, user, timestamp, and retrieved sources shall be logged for Tier 1 and Tier 2 systems.

**R-24.** Retrieval systems shall enforce the requesting user's existing entitlements.

### 2.7 Third parties

**R-25.** Third-party AI shall complete AI-specific due diligence within the bank's third-party risk process.

**R-26.** Contracts for Tier 1 and Tier 2 third-party AI shall include prohibition on training use of bank data, processing location commitment, notice before material model change, subprocessor disclosure, and AI-inclusive incident notification.

**R-27.** Vendor-initiated model changes shall trigger reassessment.

### 2.8 Monitoring and change

**R-28.** Every Tier 1, 2, and 3 system shall have a monitoring plan with metrics, thresholds, frequency, owner, and escalation path.

**R-29.** Reassessment shall occur on any trigger defined in [`docs/04-risk-tiering.md`](../docs/04-risk-tiering.md) and on cycle: annually for Tier 1 and 2, biennially for Tier 3.

**R-30.** Decommissioned systems shall be recorded as retired in the inventory, with data disposition documented.

### 2.9 Incidents

**R-31.** AI incidents and near misses shall be reported to AI Governance and captured in the bank's operational risk event process.

**R-32.** Any incident involving a pre-approved pattern shall suspend that pattern pending working group review.

## 3. Exceptions

Exceptions follow the bank's existing exception and risk-acceptance process. Tier 1 exceptions require AI Risk Committee approval, may not exceed twelve months, and require a documented compensating control and remediation plan.

## 4. Enforcement and reporting

Compliance with this standard is tested by Internal Audit. Adherence metrics are reported to the AI Risk Committee quarterly and to the board risk committee at least semiannually.
