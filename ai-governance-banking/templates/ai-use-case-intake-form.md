# AI Use Case Intake Form

**Design rule: one screen, roughly fifteen minutes.** Every field must change a downstream decision. If a field does not change tier, routing, or a control requirement, it does not belong here. Collect the rest during assessment, from the people who can answer it.

---

## Section 1: Identification

| Field | Purpose |
|---|---|
| Use case name | |
| Requesting business unit or product team | |
| **Accountable executive** (name and title) | Must have authority to suspend the use case |
| Day-to-day owner (name) | |
| Technical contact (name) | |
| Target production date | Drives scheduling, not priority |
| Affiliate(s) in scope | Determines applicable charter and supervision |
| Customer jurisdiction(s) | Determines state law applicability |

## Section 2: Purpose

| Field | Purpose |
|---|---|
| **What decision or task does this support?** (3 sentences) | The single most informative field on the form |
| What happens today without it? | Reveals whether this replaces a control or adds to one |
| Expected benefit, quantified if possible | Prevents governance effort on use cases nobody is committed to |
| Who is affected by the output? (customers, employees, both, neither) | Drives the impact dimension |

## Section 3: Data

| Field | Purpose |
|---|---|
| What data goes in? (list sources) | |
| **Highest data classification of any input** | Drives the data sensitivity dimension |
| Does any input include customer NPPI, account, or transaction data? | Yes triggers privacy review |
| Does any input include protected class data or a likely proxy? | Yes triggers fair lending review |
| Does data leave the bank environment? Where does processing occur? | Drives security and residency review |
| **Can the provider use our data to train or improve models?** | A yes above minimal sensitivity is a stop until contractually resolved |
| Retention period for inputs, prompts, and outputs | |

## Section 4: The system

| Field | Purpose |
|---|---|
| Built in house, purchased, or an AI feature in an existing product? | Routes third-party review |
| Vendor and product name | |
| Underlying model(s) and provider(s), if known | Concentration and fourth-party analysis |
| Is it generative, predictive, retrieval-based, or agentic? | Drives control set |
| **Can the system take actions in other systems?** If yes, list every action | Agentic systems are a distinct risk class |
| Does it connect to production systems or production data? | |

## Section 5: Oversight

| Field | Purpose |
|---|---|
| **Does a person review each output before it takes effect?** (in the loop / on the loop / neither) | Drives the autonomy dimension |
| Who is that person and what qualifies them to overrule it? | A reviewer without the expertise to disagree is not oversight |
| Can the system be turned off without a code release? How? | Kill switch requirement |
| What happens if it is wrong? Describe the worst realistic outcome | The field that surfaces risk the requester has already thought about but not written down |

## Section 6: Regulatory

| Field | Purpose |
|---|---|
| Does the output contribute to a credit decision, pricing, or adverse action? | Automatic Tier 1 |
| Does it contribute to BSA/AML or sanctions disposition? | Automatic Tier 1 |
| Does it produce free-form text delivered to a customer? | Automatic Tier 1 |
| Does it inform hiring, evaluation, or termination? | Automatic Tier 1 |
| Can it move money, change account status, or modify entitlements? | Automatic Tier 1 |
| Is there an existing model risk record for this or for a system it feeds? | Routes to model risk |

## Section 7: Attestation

> I confirm the information above is accurate to the best of my knowledge, that I will notify AI Governance of any change to purpose, data, oversight, or affiliate scope, and that this system will not be placed in production until the applicable review is complete.

Accountable executive signature and date.

---

## For governance use only

| Field | |
|---|---|
| Date received | |
| Impact / Data / Autonomy / Regulatory scores | |
| **Assigned tier and written rationale (2 sentences)** | The most audit-relevant record the program produces |
| Pattern matched, if any | |
| Routed to | |
| Target decision date | |
| Existing inventory record that may duplicate this | |
