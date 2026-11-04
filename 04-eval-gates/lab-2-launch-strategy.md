# Module 4 · Launch Strategy · Ascend IQ Copilot

## 4.0 Release Criteria

| Gate | Failure | Metric | Threshold | Dataset | Method | Runs at |
|---|---|---|---|---|---|---|
| Hard | Missing facts (#HALLUCINATION) | Share of answers where all factual attributes (titles, roles, dates, prices, amounts, certifications, speaker status, locations, counts) exactly match the reference | 100% detection of P0 cases (1 of 1 caught) | Ascend IQ golden set | Code-based check | Release |
| Soft | Row 3 · Latency: exceeded the maximum response time | Share of responses that exceed the 10-second response time target | 0% of responses exceed 10 seconds | Ascend IQ golden set | Code-based check | Staging |
| Advisory | Row 14 · Relevance: the answer doesn’t answer the question | Share of answers that fully answer the user's question | 100% of answers address the user's question on the golden set | Ascend IQ golden set | Human review | Release |

## CI Gate Request for Engineering

- **Hard gate · Missing facts (#HALLUCINATION).** Check: the code-based check, run on the Ascend IQ golden set at Release. Measures: Share of answers where all factual attributes (titles, roles, dates, prices, amounts, certifications, speaker status, locations, counts) exactly match the reference. Passes when: 100% detection of P0 cases (1 of 1 caught). On a fail: block the release.
- **Soft gate · Row 3 · Latency: exceeded the maximum response time.** Check: the code-based check, run on the Ascend IQ golden set at Staging. Measures: Share of responses that exceed the 10-second response time target. Passes when: 0% of responses exceed 10 seconds. On a fail: pause the release until the PM signs off on an override.
- **Advisory gate · Row 14 · Relevance: the answer doesn’t answer the question.** Check: the human review, run on the Ascend IQ golden set at Release. Measures: Share of answers that fully answer the user's question. Passes when: 100% of answers address the user's question on the golden set. On a fail: post a warning, and don't block.

## Mitigation Plan · Soft Gate

If our Soft gate fails (latency exceeds the 10-second response time target), I recommend a staged rollout because it lets us test it with a small group first and iron out any issues before a full launch.

If our Soft gate fails (slang is detected in responses), I recommend a beta label because it allows us to release the feature while we collect more data and improve the tone checks before rolling it out to everyone.
