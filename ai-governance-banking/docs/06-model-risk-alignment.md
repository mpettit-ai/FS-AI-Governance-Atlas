# Alignment with Model Risk Management (SR 11-7)

This is the most consequential boundary in a bank AI program. Get it wrong in either direction and the program fails: draw it too narrowly and AI-specific risk goes ungoverned, draw it too broadly and you have built a shadow model risk function that second line will reject and audit will flag as duplicative.

## The starting position

SR 11-7 (and OCC 2011-12) has governed models in banks since 2011. It establishes model definition, inventory, development standards, independent validation, ongoing monitoring, and governance. It is mature, examined, and understood by the board.

**The AI program does not replace any of that.** It extends it where AI introduces risk the model risk framework was not designed around, and it covers the AI that falls outside the model definition entirely.

## Three categories

### Category A: AI that is a model

Predictive and decision models. Credit scoring, fraud detection, AML transaction monitoring, deposit attrition, pricing, capital and stress testing inputs.

**Governance:** stays in the model inventory. Follows the full model risk lifecycle including independent validation. Model risk owns it.

**What AI governance adds:** an AI flag on the model record, plus requirements the model risk framework does not fully address for machine learning:

- Explainability sufficient to produce Regulation B principal reasons where adverse action applies
- Fairness and disparate impact testing with documented methodology and thresholds
- Training data provenance and representativeness documentation
- Drift monitoring on inputs as well as outputs
- Third-party model transparency where the model is vendor-supplied

### Category B: AI that is not a model

Generative assistants, summarization, content generation, retrieval systems, classification of unstructured text, agentic workflows. These typically fail the SR 11-7 model definition because they do not produce a quantitative estimate.

**Governance:** this program owns it end to end. This is the gap the program exists to fill.

**What applies:** tier-based assessment, an evaluation protocol in place of validation, human oversight requirements, output monitoring, and incident reporting.

### Category C: AI inside a model

A model whose inputs include AI-derived features. A credit model consuming a machine-learned fraud score, or an AML model consuming an entity resolution output.

**Governance:** the consuming model stays in the model inventory. The AI-derived input is registered separately with its own tier, and the dependency is recorded in both directions.

**Why this matters:** an AI component upstream of a regulated model inherits the downstream model's regulatory exposure without necessarily inheriting its validation. This is the most common place a bank has undocumented AI risk sitting inside a fully validated model.

## The boundary test

Apply in order:

1. **Does it meet the bank's model definition as written in the model risk policy?** If yes, Category A. Do not relitigate the definition.
2. **Does its output feed a system that meets the model definition?** If yes, Category C.
3. **Otherwise, Category B.**

The test uses the bank's own existing definition deliberately. Proposing a new definition is how an AI program picks a fight with a function it needs as an ally.

## Where the two frameworks meet

| Topic | SR 11-7 practice | AI governance addition |
|---|---|---|
| Inventory | Model inventory with tiering by materiality | AI flag, AI tier, dependency mapping, coverage of non-model AI |
| Development standards | Conceptual soundness, documentation | Training data provenance, representativeness, fairness by design |
| Validation | Independent validation, outcomes analysis, benchmarking | Evaluation protocols for generative systems, adversarial and prompt injection testing |
| Ongoing monitoring | Performance monitoring, back-testing | Input drift, output drift, override rates, confabulation rates, refusal behavior |
| Vendor models | Vendor model risk expectations | AI-specific due diligence, training data use restrictions, model change notice |
| Change management | Model change policy | Vendor-initiated foundation model changes as a reassessment trigger |
| Governance | Model risk committee, board reporting | AI Risk Committee, integrated reporting rather than a parallel report |

## What generative systems cannot borrow from SR 11-7

Be straightforward about this, in program documentation and with examiners.

Outcomes analysis assumes a measurable ground truth and a stable relationship between input and output. A generative system producing free-form text to a customer has neither in the usual sense. Claiming to validate it the way a PD model is validated invites a finding.

**What the program requires instead, documented as its own method:**

- A fixed, versioned evaluation set of representative and adversarial inputs, maintained by the use case owner and reviewed by second line
- Defined acceptance criteria: factual accuracy against source, appropriate refusal, absence of prohibited content, citation fidelity for retrieval systems
- Human review sampling in production at a defined rate, with results trended
- Re-evaluation on model version change and on a fixed cadence
- Documented known limitations, published to the users of the system

This is a defensible method. It is not validation, and the documentation should not call it validation.

## Reporting

One integrated view to the board risk committee, not two. AI risk reporting is a section within model and technology risk reporting, showing:

- Inventory by tier and by category A/B/C
- Coverage against discovery
- Open conditions and exceptions by age
- Incidents and near misses
- Validation and evaluation status for Tier 1 and 2

Two separate reports on overlapping populations is how a board loses confidence that anyone has the full picture.
