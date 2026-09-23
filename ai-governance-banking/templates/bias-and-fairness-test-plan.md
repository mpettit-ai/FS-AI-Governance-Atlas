# Bias and Fairness Test Plan

Required for Tier 1, and for Tier 2 where the system touches protected classes or their likely proxies. Completed before deployment and repeated at least annually.

**A note on scope.** Fairness testing is a compliance activity with legal consequence, not a data science exercise. The methodology, thresholds, and interpretation should be agreed with Compliance and, for credit-related systems, with Legal before testing begins. Choosing a metric after seeing the results is not a defensible position.

---

## 1. Scope

| Field | |
|---|---|
| System and version | |
| Decision or output being tested | |
| Population affected | |
| Regulatory hook (ECOA/Reg B, FHA, UDAAP, state) | |
| Prepared with (Compliance, Legal, Model Risk) | |

## 2. Protected classes and proxies

**Classes in scope.** Race, color, religion, national origin, sex, marital status, age, receipt of public assistance income, and exercise of rights under the Consumer Credit Protection Act, plus familial status and disability for housing-related credit. Confirm the applicable list with Compliance for the product in question.

**Proxy analysis.** Identify features that correlate with a protected class even though the class itself is not an input. Common candidates in banking: ZIP code and census tract, educational institution, employer, device and channel, language preference, tenure, and product history. Document the correlation analysis performed and the decision on each feature.

**Where class data is not collected.** For non-mortgage products, protected class data is generally not collected. State the proxy methodology used, its known error rate, and its limitations. Bayesian Improved Surname Geocoding is commonly used for race and ethnicity; it is an estimate and the documentation should say so.

## 3. Metrics and thresholds

Select before testing. Document why each was selected for this decision context.

| Metric | What it measures | When it fits |
|---|---|---|
| Adverse impact ratio (selection rate ratio) | Rate of favorable outcome for a group relative to the reference group | Approval, selection, and targeting decisions |
| Standardized mean difference | Difference in score distribution between groups | Continuous scores |
| Equal opportunity difference | Difference in true positive rate | Where the cost of a missed positive falls on the consumer |
| Predictive parity | Whether a given score means the same thing across groups | Risk scores used for pricing |
| Error rate disparity | Difference in false positive or false negative rate | Fraud, AML, and identity systems, where a false positive is a customer harm |

**Thresholds.** State the threshold, the rationale, and what happens when it is breached. The four-fifths rule is a common reference point in employment contexts and is sometimes borrowed in lending, but it is a screening heuristic rather than a legal standard for credit. Do not present it as one.

**For generative and non-decision systems**, quality-of-service disparity is the relevant test: does response accuracy, helpfulness, tone, or escalation rate vary across name origin, dialect, language, or channel. Construct matched test inputs that vary only on the attribute under test.

## 4. Test design

- Data set used, its time period, and its size by group
- How reference and comparison groups are defined
- Controls for legitimate business factors, with those factors named and justified
- Statistical significance approach and how practical significance is distinguished from statistical significance
- Who performs the testing, and their independence from development

## 5. Results

| Group | N | Outcome rate | Ratio to reference | Threshold | Pass / Fail |
|---|---|---|---|---|---|

Include distributional detail, not only the summary ratio. A metric can pass at the aggregate level and fail within a segment that matters.

## 6. If a disparity is found

Document in this order:

1. **Confirm it.** Rule out data artifacts, sample size effects, and definitional errors.
2. **Explain it.** Identify the feature or interaction driving the disparity.
3. **Search for a less discriminatory alternative.** This step is not optional where the regulatory hook is ECOA or FHA. Document the alternatives evaluated, their performance, and the basis for the selection made. The search itself is evidence.
4. **Remediate or accept.** If remediation is not taken, the acceptance is made by the AI Risk Committee with Legal concurrence, documented, and time-bound.

**Do not skip step 3 and go straight to acceptance.** The absence of a documented search for a less discriminatory alternative is a finding in itself.

## 7. Explainability and adverse action

Where the system contributes to adverse action under Regulation B:

- Method used to derive principal reasons for an individual decision
- Evidence that the reasons produced are specific and accurate to the actual basis of the decision, not selected from a generic list
- Sample of reason codes produced, reviewed by Compliance
- What happens when the method cannot produce an accurate reason

Per CFPB Circular 2023-03, model complexity is not a defense for a vague or inaccurate reason. If the system cannot produce accurate principal reasons, that is a finding on the system, not on the notice.

## 8. Ongoing testing

Cadence (at minimum annual for Tier 1), triggers for off-cycle testing (model change, population change, material performance shift), owner, and where results are reported.
