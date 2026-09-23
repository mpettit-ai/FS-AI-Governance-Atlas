# 90-Day Implementation Plan

Starting from nothing, or close to it. The goal at day 90 is not a finished program. It is a front door that is faster than going around it, a credible inventory, and the first real metrics in front of leadership.

**Guiding principle:** every phase produces something usable. Nothing waits for the whole design to be finished.

---

## The short version

> The first thirty days I would not change anything. I would read what already exists, meet model risk, security, privacy, legal, compliance, and the product teams, and build the real inventory including what nobody has registered. Days thirty to sixty I would design intake and risk tiering with the product teams rather than for them, and map existing risk statements and controls to the AI RMF functions so the gaps are visible. Days sixty to ninety I would run real use cases through it and bring leadership the first metrics: coverage, cycle time, tier distribution, and open risk.

---

# Days 1 to 30: Discover and Baseline

**Objective:** understand what exists before proposing anything. Resist the urge to demonstrate value by changing things in week two.

## What to read, in this order

1. **The model risk management policy and the SR 11-7 program documentation.** First for a reason. The bank already governs models. Any AI program that ignores that structure gets rejected by second line and flagged as duplicative by audit.
2. **Any existing AI policy, standard, or guidance**, however immature.
3. **Existing AI risk statements and controls.** Read them before writing new ones.
4. **The data classification standard.** You cannot tier use cases without it.
5. **Third-party risk policy and the vendor assessment process.** Every foundation model provider is a third party, and so is every AI feature inside software you already own.
6. **Information security policy, privacy policy, records retention schedule.**
7. **Fair lending program documentation and recent fair lending analyses.**
8. **Recent internal audit findings and regulatory exam feedback** touching technology, model risk, or consumer compliance.

## Who to meet, and the question that matters for each

| Who | The question |
|---|---|
| **Model Risk Management** | "Where does an AI system stop being a model under your definition, and where does it start being something you would not cover?" The single most important boundary in the program |
| **Information Security** | "What is your current position on data leaving the environment through AI tools, and how is that enforced today?" |
| **Privacy** | "What is our position on customer data in model training and inference, and has it been documented?" |
| **Compliance and Fair Lending** | "Which regulatory obligations do you already believe AI touches, and where are you unsure?" |
| **Legal** | "What contractual terms have we already accepted from AI vendors that you would not accept again?" |
| **Internal Audit** | "If you audited AI governance in twelve months, what would you look for?" Ask early. The answer tells you exactly what to build toward |
| **Data Governance** | "Where is the authoritative record of what data exists and who owns it?" |
| **The AI platform team** | "What is deployed today, what is in flight, and what have people asked for that you have said no to?" |
| **Product and engineering leaders** | "Walk me through your last risk review. What made it painful?" |
| **Business line leads** | "What are you using AI for that I would not find in any system of record?" |

## How to find the AI already in use

Do not rely on asking. People do not report what they do not think is AI. Run parallel discovery:

- **The model inventory.** Some AI is already registered as models. Start here.
- **Procurement and contract records.** Search for AI, ML, copilot, assistant, model, and the major provider names.
- **Expense and corporate card data.** Individual subscriptions surface here before anywhere else.
- **CASB, proxy, and SaaS discovery data.** Traffic to AI services reveals tools nobody registered.
- **AI platform admin consoles.** Actual usage by team.
- **Existing SaaS you already own.** Ask every material vendor what AI functionality exists in your tenant and what is enabled. This is usually the largest single source of ungoverned AI, and the answers take weeks to come back, so send the questions in week one.

**The framing to use:** discovery is harder than registration. The systems already on a list were never the risk.

## What you produce by day 30

- A **baseline inventory** marked by confidence level. Incomplete is fine; honest about what you do not know is required
- A **stakeholder map** of who decides what today
- A **gap analysis against the AI RMF GOVERN function specifically.** GOVERN first, because the other three functions have nothing to stand on without it
- A **one-page read for leadership:** what exists, what is missing, what you propose to build first, and what you need

---

# Days 31 to 60: Design and Socialize

**Objective:** build the mechanism with the people who will use it, before you turn it on.

## Build the intake

Use [`templates/ai-use-case-intake-form.md`](../templates/ai-use-case-intake-form.md) as the starting point and cut it further. One screen, fifteen minutes. Put it in whatever tooling exists rather than in a document. A form in a document does not produce a queue you can measure.

**Design rule:** the intake should produce the risk documentation as a byproduct. If the assessment re-asks what the form already captured, teams experience governance as duplicate work and route around it.

## Set the tiering, then calibrate it against reality

Take the tiering model in [`docs/04-risk-tiering.md`](../docs/04-risk-tiering.md) and run every system in your baseline inventory through it on paper. Two things will happen:

1. You will find the criteria push too much into Tier 1 and Tier 2. Recalibrate before you publish, not after.
2. You will find systems that are automatic Tier 1 and have been in production for a year. That is a finding, and the way you handle it sets the program's reputation. Register first, assess second, do not punish.

## Publish the pre-approved patterns

This is the mechanism that makes product teams trust the program. Start with three to five patterns covering the highest-volume internal uses, and publish them with their conditions. A team whose use case matches a pattern registers and moves on the same day.

## Map controls to the framework

Run the crosswalk in [`docs/03-nist-ai-rmf-crosswalk.md`](../docs/03-nist-ai-rmf-crosswalk.md) against existing policies and controls. Most banks find a meaningful share of GOVERN and MANAGE already satisfied through model risk and third-party programs, and that the real gaps concentrate in MEASURE for generative systems. Fill in this order: GOVERN, MAP, MANAGE, MEASURE. MEASURE last because it is the most technical and the least useful without the other three in place.

## Settle decision rights

Write down who decides what and get it agreed rather than drafted. Ambiguity here is what stalls programs at month six. Use the RACI in [`docs/10-roles-and-raci.md`](../docs/10-roles-and-raci.md) as a starting draft and walk it through each second line function individually before taking it to committee.

## Publish turnaround commitments

30, 15, 5, and same-day by tier. Publishing a commitment you might miss is uncomfortable and it is also the thing that makes the front door credible. Then measure yourself against it publicly, including when you miss.

## What you produce by day 60

- Live intake, in tooling
- Published tiering criteria and turnaround commitments
- Pre-approved pattern list, version one
- Control set mapped to the four functions with gaps identified and owned
- An agreed RACI
- A draft AI standard and acceptable use policy reflecting all of the above

---

# Days 61 to 90: Operate and Measure

**Objective:** run it on real work, then show leadership what it produced.

## Run a deliberate mix

Take a handful of live use cases across tiers, including at least one Tier 1. You want the process tested where it hurts before you scale it.

**Instrument the friction.** Track where submissions stall, which questions get asked back, and where teams give up. That is your improvement backlog, and bringing it to product leadership unprompted builds more credibility than any policy document.

## Publish the first metrics

Coverage, cycle time by tier, tier distribution, pattern utilization, open conditions by age, exceptions outstanding, shadow AI found. Definitions are in [`docs/09-monitoring-and-metrics.md`](../docs/09-monitoring-and-metrics.md).

**The metric that matters most to leadership is coverage.** Everything else is meaningless if the inventory is not credible.

**The metric that matters most to product teams is cycle time.** Publish it even when it is bad. Especially when it is bad.

## Close the loop

- First formal report to leadership, including what is not working yet
- A prioritized program backlog for the next quarter
- A written recommendation on tooling: extend the existing GRC platform, or something purpose-built. Ninety days is enough to know what you need and too early to have bought it

---

# What Will Go Wrong

**The inventory is worse than anyone thought.** Likely. Report it plainly as a baseline rather than as a scandal, and use it to justify the discovery investment.

**Model risk and AI governance get territorial.** Address it in week one by asking where their definition ends rather than by proposing a boundary. Deference early buys cooperation later.

**A team ships something without coming through intake.** Ask why the front door did not work for them, fix that, then register the use case. Punishment teaches people to hide, which is the opposite of what an inventory needs.

**Everything lands in Tier 1.** The criteria are wrong. Recalibrate rather than defend.

**Leadership wants a maturity score at day 90.** Give a baseline against the four functions and be clear it is a starting measurement rather than an achievement.

---

# Why This Sequence

**Discovery before design,** because a process built around imagined use cases will not fit the real ones.

**GOVERN before MAP, MEASURE, and MANAGE,** because without decision rights and accountability the other three produce findings nobody can act on.

**Design with the product teams rather than for them,** because adoption is the whole game and a process handed down is a process routed around.

**Operate before optimize,** because ninety days of real submissions teach you more about friction than another month of design.
