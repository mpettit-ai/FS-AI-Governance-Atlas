# NIST AI RMF Crosswalk

The AI RMF has four functions: **GOVERN, MAP, MEASURE, MANAGE**. GOVERN is cross-cutting; the other three run across the AI lifecycle.

This crosswalk does two things. It maps each function to the artifact in this repository that implements it, and it identifies **which existing bank program already covers it**. That second column is the one that matters in a bank. Most institutions discover they already satisfy a large share of GOVERN and MANAGE through model risk and third-party programs, and that the real gaps sit in MEASURE for generative systems.

---

## GOVERN

Culture, accountability, policy, and oversight. Build this first. The other three functions have nothing to stand on without it.

| Subcategory | Requirement in plain terms | Existing bank program | Artifact |
|---|---|---|---|
| GOVERN 1.1 | Legal and regulatory requirements are understood and documented | Compliance, Legal | [`11-regulatory-landscape.md`](11-regulatory-landscape.md) |
| GOVERN 1.2 | Trustworthy AI characteristics are integrated into policy | New | [`policy/ai-governance-standard.md`](../policy/ai-governance-standard.md) |
| GOVERN 1.3 | Processes are in place to determine risk tolerance | Enterprise Risk Management | Charter risk appetite statement |
| GOVERN 1.4 | Risk management process and outcomes are documented and monitored | Model Risk, ERM | [`registers/ai-risk-register.csv`](../registers/ai-risk-register.csv) |
| GOVERN 1.5 | Ongoing monitoring and periodic review are planned, with resourcing | Model Risk (validation cycle) | [`09-monitoring-and-metrics.md`](09-monitoring-and-metrics.md) |
| GOVERN 1.6 | An inventory of AI systems is maintained | Model inventory (partial) | [`registers/ai-inventory.csv`](../registers/ai-inventory.csv) |
| GOVERN 1.7 | Decommissioning processes exist | IT asset lifecycle (partial) | Control CAT-GOV-07 |
| GOVERN 2.1 | Roles and responsibilities are documented | Three lines model | [`10-roles-and-raci.md`](10-roles-and-raci.md) |
| GOVERN 2.2 | Personnel are trained on their AI responsibilities | Security awareness (extend) | Control CAT-GOV-09 |
| GOVERN 2.3 | Executive leadership is accountable for AI risk | Board risk committee | Charter |
| GOVERN 3.2 | Decision-making related to AI is informed by a diverse team | Model validation independence | [`10-roles-and-raci.md`](10-roles-and-raci.md) |
| GOVERN 4.1 | A culture of risk identification and reporting exists | Risk culture, whistleblower | Control CAT-GOV-11 |
| GOVERN 4.3 | Incident and error reporting processes exist | Incident response, operational risk event capture | [`templates/ai-incident-report.md`](../templates/ai-incident-report.md) |
| GOVERN 5.1 | Feedback from external stakeholders is collected | Complaint management, CFPB complaint monitoring | Control CAT-GOV-13 |
| GOVERN 6.1 | Third-party AI risk policies are in place | Third-party risk management | [`07-third-party-ai.md`](07-third-party-ai.md) |
| GOVERN 6.2 | Contingency exists for third-party AI failure or discontinuation | Business continuity, vendor exit planning | Control CAT-TPR-06 |

**Where banks are typically strong:** 1.3, 1.5, 2.1, 2.3, 6.1. The structures exist and only need AI added to their scope.
**Where banks are typically weak:** 1.6 (inventory completeness for embedded and third-party AI), 1.7 (nobody retires anything), 4.3 (AI failures do not map cleanly to operational risk event taxonomies).

---

## MAP

Establish context and identify risks. This is what the intake form and risk assessment do.

| Subcategory | Requirement in plain terms | Artifact |
|---|---|---|
| MAP 1.1 | Context, purpose, and stakeholders are established | Intake form sections 1 to 3 |
| MAP 1.2 | Interdisciplinary AI team perspectives are incorporated | Working group review |
| MAP 1.5 | Organizational risk tolerance is applied | [`04-risk-tiering.md`](04-risk-tiering.md) |
| MAP 2.1 | The task and method are defined | Intake form, model card |
| MAP 2.2 | System knowledge limits are documented | [`templates/model-card.md`](../templates/model-card.md), limitations section |
| MAP 2.3 | Scientific integrity and TEVV considerations are addressed | [`templates/ai-risk-assessment.md`](../templates/ai-risk-assessment.md) |
| MAP 3.1 | Benefits are examined, not assumed | Intake form, expected benefit field |
| MAP 3.4 | Operator proficiency is defined | Assessment, human oversight section |
| MAP 3.5 | Human oversight is defined and assigned | Assessment, human oversight section |
| MAP 4.1 | Third-party and data provenance risks are mapped | [`templates/ai-vendor-due-diligence-questionnaire.md`](../templates/ai-vendor-due-diligence-questionnaire.md) |
| MAP 5.1 | Impacts to individuals, groups, and society are characterized | Assessment, impact section; fairness test plan |
| MAP 5.2 | Feedback channels for affected individuals are established | Complaint routing, adverse action reason codes |

---

## MEASURE

Analyze, assess, benchmark, and monitor. **This is the weakest function in most bank AI programs**, and the gap is concentrated in generative systems where there is no established validation practice equivalent to what model risk does for predictive models.

| Subcategory | Requirement in plain terms | Artifact |
|---|---|---|
| MEASURE 1.1 | Metrics and methods are identified and applied | Assessment, TEVV section |
| MEASURE 2.1 | Test sets and metrics are documented | Model card, evaluation section |
| MEASURE 2.2 | Human subject evaluation is applied where relevant | Fairness test plan |
| MEASURE 2.3 | Performance is measured against declared objectives | Monitoring plan |
| MEASURE 2.5 | System validity and reliability are evaluated | Model Risk validation, or GenAI evaluation protocol |
| MEASURE 2.6 | Safety risks are evaluated | Assessment, failure mode section |
| MEASURE 2.7 | Security and resilience are evaluated, including adversarial testing | [`08-genai-controls.md`](08-genai-controls.md) |
| MEASURE 2.8 | Transparency and explainability are evaluated | Assessment, explainability section, Reg B reason codes |
| MEASURE 2.9 | Model explanation is validated | Model Risk validation |
| MEASURE 2.10 | Privacy risk is evaluated | Privacy impact assessment |
| MEASURE 2.11 | Fairness and bias are evaluated | [`templates/bias-and-fairness-test-plan.md`](../templates/bias-and-fairness-test-plan.md) |
| MEASURE 2.12 | Environmental impact is evaluated | Optional, tier 1 only |
| MEASURE 3.1 | Approaches exist to identify risks not previously measured | Red teaming, incident trending |
| MEASURE 4.2 | Measurement results are informed by domain expert feedback | Business validation sign-off |

**The honest gap.** For a generative use case there is no regulatory-grade validation standard equivalent to SR 11-7 outcomes analysis. A program that claims otherwise is overstating. What can be done, and what this framework requires at Tier 1 and Tier 2, is a documented evaluation protocol: a fixed test set of representative prompts, defined acceptance thresholds for accuracy and refusal behavior, adversarial and prompt injection testing, and periodic re-evaluation on a set cadence. That is defensible. Calling it validation is not.

---

## MANAGE

Prioritize, respond, and recover.

| Subcategory | Requirement in plain terms | Existing bank program | Artifact |
|---|---|---|---|
| MANAGE 1.2 | Risks are prioritized based on impact | ERM risk rating | Tiering model |
| MANAGE 1.3 | Responses to high priority risks are planned | Issue management | Risk register |
| MANAGE 1.4 | Residual risk is documented and accepted by an authorized party | Risk acceptance and exception process | Assessment sign-off |
| MANAGE 2.1 | Resources are allocated to risk treatment | Program budget | Charter |
| MANAGE 2.2 | Mechanisms sustain the value of deployed AI | Model performance monitoring | Monitoring plan |
| MANAGE 2.3 | Procedures exist to respond to previously unknown risks | Incident response | [`templates/ai-incident-report.md`](../templates/ai-incident-report.md) |
| MANAGE 2.4 | Mechanisms exist to supersede, disengage, or deactivate a system | Change management, kill switch requirement | Control CAT-MNG-05 |
| MANAGE 3.1 | Third-party AI risks are monitored | Ongoing vendor monitoring | [`07-third-party-ai.md`](07-third-party-ai.md) |
| MANAGE 4.1 | Post-deployment monitoring is planned and executed | Model monitoring | Monitoring plan |
| MANAGE 4.3 | Incidents and near misses are communicated | Operational risk event reporting | Incident template |

**Control CAT-MNG-05 deserves emphasis.** Every Tier 1 and Tier 2 system must have a documented, tested way to turn it off that does not require a code release. Examiners ask this. Teams rarely have an answer before they are asked.
