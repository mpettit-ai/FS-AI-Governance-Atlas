# Roles and Responsibilities

## Three lines, unmodified

The AI program does not invent a new accountability structure. It places AI inside the one the bank already has and that examiners already understand.

- **First line:** the business or product function that owns the use case, owns the risk, and operates the controls
- **Second line:** AI governance, model risk, information security, privacy, compliance, and legal. Independent challenge and oversight. No ownership of the outcome
- **Third line:** internal audit. Tests design and operating effectiveness. Does not participate in approval, does not advise on design beyond general expectations

## Roles

### Use case owner (first line, named individual)

- Submits accurate and complete intake
- Owns the risk and the business outcome
- Operates the controls and the monitoring plan
- Notifies governance of any reassessment trigger
- Closes conditions by their due dates
- Reports incidents

**Must be named and must be at a level with authority to stop the use case.** A use case owner who cannot suspend the system they own is a placeholder.

### AI Governance Manager (second line, program owner)

- Owns the framework, standards, and procedures
- Runs intake, triage, and tier assignment
- Maintains the inventory and the risk register
- Coordinates second line review and consolidates findings
- Approves Tier 3, recommends on Tier 1 and 2
- Produces metrics and reporting
- Maintains the regulatory watch and updates the program for changes
- Escalates to the Chief Risk Officer

### Model Risk Management (second line)

- Owns the model definition and the model inventory
- Determines whether a use case meets the model definition
- Performs independent validation for in-scope models
- Sets validation standards and monitors validation currency

### Information Security (second line)

- Reviews architecture, data flow, entitlements, and logging
- Performs or commissions adversarial and prompt injection testing
- Owns DLP coverage of AI destinations and approved tool configuration
- Investigates AI security incidents

### Privacy (second line)

- Determines lawful basis, minimization, and retention requirements
- Performs privacy impact assessments
- Owns the position on customer data in training and inference
- Determines automated decision-making disclosure obligations by jurisdiction

### Compliance (second line)

- Identifies applicable regulation per use case
- Owns fair lending and UDAAP review of AI-influenced decisions
- Determines disclosure requirements by state and by affiliate
- Reviews customer-facing generative output paths

### Legal (second line, Tier 1)

- Reviews contractual terms, intellectual property, and liability allocation
- Interprets regulatory obligations where unsettled
- Advises on litigation and examination exposure

### Data Governance (second line)

- Owns data classification and the authoritative record of data ownership
- Confirms data lineage and permitted use for training and inference

### Internal Audit (third line)

- Tests the program against its own documentation
- Tests a sample of use cases for adherence to approved conditions
- Reports independently to the audit committee

### AI Risk Committee

- Approves Tier 1 use cases
- Sets and ratifies risk appetite
- Approves policy and material standards changes
- Approves high residual risk acceptances and Tier 1 exceptions
- Reviews the metrics pack quarterly

## RACI

R = responsible, A = accountable, C = consulted, I = informed

| Activity | Use case owner | AI Gov Mgr | Model Risk | InfoSec | Privacy | Compliance | Legal | AI Risk Cmte | Audit |
|---|---|---|---|---|---|---|---|---|---|
| Submit intake | A/R | I | | | | | | | |
| Assign tier | C | A/R | C | | | | | I | |
| Model definition determination | C | C | A/R | | | | | I | |
| Risk assessment | R | A | C | C | C | C | C | I | |
| Security review | C | I | | A/R | C | | | | |
| Privacy impact assessment | C | I | | C | A/R | C | C | | |
| Fair lending and disparate impact review | C | C | C | | | A/R | C | I | |
| Independent validation | C | I | A/R | | | | | I | |
| Tier 1 approval | C | R | C | C | C | C | C | A | I |
| Tier 2 approval | C | A/R | C | C | C | C | I | I | |
| Tier 3 approval | C | A/R | I | I | I | I | | | |
| Tier 4 registration | A/R | I | | | | | | | |
| Operate controls | A/R | I | | C | | | | | |
| Monitor and report on use case | A/R | C | C | | | | | I | |
| Maintain inventory | C | A/R | C | | | | | I | I |
| Incident response | R | C | C | A/R | C | C | C | I | I |
| Exception approval (Tier 1) | R | C | C | C | C | C | C | A | I |
| Program metrics and board reporting | I | A/R | C | C | C | C | | I | I |
| Independent testing of the program | I | I | I | I | I | I | I | I | A/R |

## Skills the program needs

Worth stating, because it affects hiring and because it is the honest constraint on how fast a program can mature.

- **Regulatory fluency:** SR 11-7, the interagency third-party guidance, Regulation B, GLBA, and state AI law
- **Enough technical depth to ask the right question:** how a retrieval system can bypass entitlements, why a fairness metric can look clean and still hide disparate impact, what a model version change actually changes
- **Facilitation:** most of the job is getting functions that do not report to each other to reach a decision on a deadline
- **Writing:** the program's output is documents that have to hold up under examination, and precision in them is a control
