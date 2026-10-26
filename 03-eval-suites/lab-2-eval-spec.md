# Eval Spec · missing facts (#HALLUCINATION), an output risk - Reference-grounding hallucinations in factual attributes. The agent changes or misstates information that is explicitly present in the reference, such as previous job titles, roles, prices, dates, speaker status, locations, certifications, or other structured facts.

| Part | Spec |
|---|---|
| Target risk | missing facts (#HALLUCINATION), an output risk - Reference-grounding hallucinations in factual attributes. The agent changes or misstates information that is explicitly present in the reference, such as previous job titles, roles, prices, dates, speaker status, locations, certifications, or other structured facts. |
| Evaluator | Rule Check (primary evaluator). Pass when all factual entity attributes (titles, roles, dates, prices, amounts, certifications, speaker status, locations, counts) exactly match the reference whenever the reference provides a value. Fail when any factual attribute is altered, omitted, downgraded, or contradicted compared with the reference. Returns 1 for pass and 0 for fail. |
| Threshold | Ship threshold: 100% detection of P0 cases (1 of 1 caught). Lab 1 support: Real cases = 1. Rule Check caught 1 of 1, Missed 0, False Alarms 0. Safety Rule caught 1 of 1, Missed 0. Judge caught 1 of 1, Missed 0, False Alarms 0. Pass if the evaluator catches all identified P0 cases. Fail if any P0 case is missed. |
| Business stakes | Ascend IQ provides market intelligence to VP-level decision makers. If factual attributes are changed despite being present in the source, executives may make decisions using incorrect competitive intelligence, trust may be reduced, and incorrect information may appear in reports and customer-facing deliverables. |
| Owner | AI Quality & Evaluation Team. Monitor the reference-grounding metric, review failures, update grounding rules, and block releases that fail the detection threshold for P0 hallucination risks. |

## Messages

**Engineering · acceptance criteria:** Pass only when all factual entity attributes (titles, roles, dates, prices, amounts, certifications, speaker status, locations, counts) exactly match the reference whenever the reference provides a value. Fail if any factual attribute is altered, omitted, downgraded, or contradicted compared with the reference. Ship only if 100% detection of P0 cases (1 of 1 caught) is maintained; any missed P0 case fails.

**Design · what the user sees:** If the answer is blocked, show a message that one or more factual attributes did not match the reference source and present a corrected answer grounded only in the reference values.

**Leadership · risk and return:** This removes P0 hallucination risk where factual attributes already present in the reference are changed. It is worth the cost because incorrect executive bios, pricing, certifications, speaker status, or company information can lead to bad decisions and reduced trust in Ascend IQ.
