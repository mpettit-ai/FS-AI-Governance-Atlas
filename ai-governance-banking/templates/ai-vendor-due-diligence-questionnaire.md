# AI Vendor Due Diligence Questionnaire

Additional questions layered onto the bank's existing third-party risk due diligence. Not a separate process. Scale to the vendor's criticality rating and the use case tier.

Answers should be contractual where marked **[contract]**. A policy page the vendor can revise unilaterally is not a commitment.

---

## 1. What the AI actually is

1. Describe all AI and machine learning functionality in the products we license, including features not currently enabled in our tenant.
2. Which functionality is enabled by default for new tenants?
3. Which underlying models do you use? Identify the provider, model family, and version for each.
4. Do you train your own models, fine-tune third-party models, or call third-party models through an API?
5. Which subprocessors, including model providers, process our data? **[contract: disclosure and change notice]**

## 2. Our data

6. Is our data used to train, fine-tune, or improve any model, including models serving other customers? **[contract: prohibition]**
7. Is our data used for any purpose other than delivering the contracted service?
8. Where is inference processed? List every geography. **[contract: residency]**
9. What is retained: prompts, inputs, outputs, embeddings, logs? For how long? Can retention be set to zero? **[contract]**
10. Is our data isolated from other customers' data at the tenant level, including in any vector store or index?
11. How is our data deleted at termination, and will you certify deletion? **[contract]**
12. Can our data be surfaced to another customer through any mechanism, including model memorization?

## 3. Model behavior and quality

13. What evaluation have you performed? Provide methodology and results or a summary.
14. What accuracy or error-rate commitments will you make? **[contract where material]**
15. What fairness or bias testing have you performed, across which attributes, and what were the results?
16. What red teaming or adversarial testing has been performed, by whom, and how recently?
17. How does the system behave when it does not know an answer? Does it refuse, hedge, or generate?
18. For retrieval systems: does the system respect our users' existing entitlements, and how is that enforced?

## 4. Change management

19. Will you notify us before changing the underlying model or model provider? How far in advance? **[contract]**
20. Will you notify us before enabling new AI functionality in our tenant? **[contract]**
21. Can we require affirmative opt-in for new AI features rather than default enablement? **[contract]**
22. What is your process for evaluating a new model version before rolling it out to customers?
23. Do you provide a version pinning option or a staged rollout we can participate in?

## 5. Security

24. How do you protect against prompt injection, including injection embedded in documents we upload?
25. What input and output filtering is applied, and can we configure it?
26. What logging is available to us: prompts, outputs, model version, user, retrieved sources? Can we export it?
27. Describe your AI supply chain security: model provenance, dependency management, and artifact integrity.
28. What is your incident notification commitment, and does it cover model behavior failures as well as security incidents? **[contract]**

## 6. Transparency and regulatory support

29. Can you support our explainability obligations if this output contributes to a credit decision or other adverse action? Describe how, specifically.
30. Can you produce, for a given output, the inputs and model version that generated it?
31. Do you hold ISO/IEC 42001 certification or equivalent independent AI assurance? Provide the report.
32. What in your SOC 2 scope covers AI-specific controls, and what is out of scope?
33. Will you support our regulatory examinations and provide information directly to examiners if required? **[contract]**

## 7. Resilience and exit

34. What availability commitment applies to AI functionality specifically, as distinct from the base product?
35. What is the degraded mode if the model is unavailable? Does the product still function?
36. If you discontinue this AI functionality, what notice do we receive? **[contract]**
37. What do we retain on exit: data, configuration, fine-tuning, prompt libraries?

## 8. The vendor's own posture

38. Do you have an AI governance program? Who owns it and to whom do they report?
39. What is your policy on your own employees' use of AI tools with customer data?
40. Have you had an AI-related incident, and what changed as a result?

---

## Scoring

Rate each area Acceptable, Acceptable with conditions, or Not acceptable. The items that should be treated as near-absolute for anything above minimal data sensitivity:

- Question 6, training use prohibition, contractual
- Question 8, processing residency
- Question 19, model change notice
- Question 29, explainability support where adverse action applies

A vendor unwilling to commit contractually to the first of those has told you something about how they intend to use the relationship.
