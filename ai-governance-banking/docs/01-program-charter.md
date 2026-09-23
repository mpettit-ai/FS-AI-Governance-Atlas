# AI Governance Program Charter

## Purpose

To establish enterprise oversight of artificial intelligence so that the bank can adopt AI at the pace the business needs while meeting its obligations to customers, regulators, and shareholders.

The program exists to make AI adoption **faster and safer at the same time**. Those are not in tension if the mechanism is designed well. They are always in tension if the mechanism is a committee.

## Objectives

1. Maintain a complete and current inventory of AI systems in use or in development across all affiliates and lines of business.
2. Provide a single front door for AI use case review, with defined turnaround by risk tier.
3. Apply controls proportionate to risk, drawing on existing model risk, third-party risk, information security, privacy, and fair lending programs before creating new ones.
4. Produce evidence that satisfies internal audit and regulatory examination without a special project to assemble it.
5. Give the board and executive management a defensible view of AI risk exposure and its trend.

## Scope

**In scope.** Any system that uses machine learning, statistical learning, or generative models to produce an output that informs a decision, generates content, or takes an action, where that output affects a customer, an employee, a financial statement, a regulatory filing, or a risk decision. This includes:

- Models developed in house
- AI features embedded in purchased software, including features enabled by default in existing SaaS
- Third-party AI services, APIs, and foundation models
- Agents and workflows that chain models together
- Employee use of general purpose generative AI tools

**Out of scope.** Deterministic rules engines, standard statistical reporting, and robotic process automation that executes fixed logic without a learned component. These remain governed by existing change management and data governance.

**The boundary that matters most** is between this program and model risk management. It is defined in [`06-model-risk-alignment.md`](06-model-risk-alignment.md). Nothing is in both inventories as a separate record. Anything meeting the bank's model definition lives in the model inventory with an AI flag and the AI-specific requirements attached.

## Governance structure

| Body | Composition | Decides |
|---|---|---|
| **AI Risk Committee** | Chief Risk Officer (chair), CISO, Chief Data Officer, Model Risk, Chief Compliance Officer, General Counsel or delegate, business line representation | Tier 1 use cases, policy exceptions with residual high risk, program policy, and risk appetite |
| **AI Governance working group** | AI Governance Manager (chair), Model Risk, Information Security, Privacy, Compliance, Data Governance, Internal Product Management, Technology | Tier 2 use cases, tier assignment disputes, pattern approvals, standards and procedures |
| **AI Governance Manager** | Program owner | Tier 3 use cases, tier assignment, inventory integrity, metrics, and escalation |
| **Use case owner** | Named business or product accountable executive | Accuracy of submitted information, operation within approved conditions, and notification on material change |

The three lines model applies without modification. The business owns the risk. AI governance, model risk, compliance, and security are second line. Internal audit is third line and does not participate in approval.

## Authority

The AI Governance Manager may:

- Require registration of any in-scope system
- Assign or reassign risk tier
- Require conditions before production deployment
- Recommend suspension of a system operating outside approved conditions, with the decision resting with the accountable executive and the AI Risk Committee
- Escalate directly to the Chief Risk Officer

The program does not have unilateral authority to stop a business initiative. That is deliberate. A second line function that can stop work without consequence acquires the reputation of an obstacle, and its findings get negotiated rather than fixed. Authority here rests on documented risk and escalation, which is stronger and holds up in examination.

## Risk appetite statement (to be ratified by the AI Risk Committee)

The bank will not deploy AI systems that:

- Make a final adverse credit, account closure, or account denial decision without human review and without the ability to produce specific, accurate principal reasons as required by Regulation B
- Process or transmit customer non-public personal information to a third-party model where the contract does not prohibit use of that data for training
- Operate in a customer-facing capacity without disclosure where disclosure is required by applicable state law
- Lack a named accountable executive and a documented monitoring plan

Everything else is a matter of tier, controls, and documented acceptance.

## Success measures at twelve months

- Inventory coverage above 90 percent against independent discovery, measured by sampling procurement, CASB, and platform admin data for unregistered systems
- Median cycle time within published service levels for each tier
- Zero Tier 1 or Tier 2 systems in production without a completed assessment
- Internal audit able to test the program against its own documentation without a readiness project
- More than half of intake volume routed through pre-approved patterns

The last one is the real test. It means the fast path is working.
