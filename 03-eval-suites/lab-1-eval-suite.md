# Eval Suite · missing facts

## P0 failure (carried from Module 2)

**Failure:** missing facts (#HALLUCINATION). The previous role is misstated decpite the info being in the reference

- **Row:** 6
- **Query:** Give me a bio for Sarah Jenkins, the new VP at DataViz.
- **Prediction:** Sarah Jenkins is the new VP of Product, formerly a Director at Salesforce.
- **Reference:** Source: LinkedIn. Sarah Jenkins: VP Product @ DataViz. Prev: Sr. Director @ Salesforce.

## The three checks

**Rule check.** Looks at: answer, reference. Passes when: all factual entity attributes (titles, roles, dates, prices, amounts, certifications, speaker status, locations, counts) must exactly match the reference when the reference provides a value. Fails when: The answer contradicts, alters, or replaces a fact stated in the reference. Examples include:

Wrong title or previous role
Wrong number, date, amount, or status
Presenting tentative information as confirmed
Presenting a non-HQ location as HQ

**Safety rule.** Looks at: answer, reference. Passes when: Every factual claim in the answer is explicitly supported by the reference. Fails when: The answer contains any factual claim that is not explicitly stated in the reference or that extends beyond the reference.

**Judge.** Looks at: question, answer, reference. Passes when: The answer fully and accurately answers the question using only facts contained in the reference. No fact requested by the question is misstated. Fails when: Any material fact required to answer the question is incorrect, contradicted by the reference, or presented with a different meaning than the reference. This includes:

Misstating a previous job title
Converting tentative status into confirmed status
Using outdated values when updated values exist
Reversing comparative facts
Presenting secondary locations as headquarters

## Results on the 20 Ascend IQ answers

| Check | Caught | Missed (rows) | False alarms (rows) | My P0 row |
|---|---|---|---|---|
| Rule check | 1 of 1 | None | None | Caught it |
| Safety rule | 1 of 1 | None | 5, 11 | Caught it |
| Judge | 1 of 1 | None | None | Caught it |

**Judge on my P0 row:** Misstates the previous role; the reference says Sr. Director, not Director.

## Where the failure was caught

This risk is not primarily a nuanced reasoning problem. The failure occurs because a factual attribute from the reference ("Sr. Director") was altered in the answer ("Director").

The Rule Check successfully identified that a title in the answer did not exactly match the title in the reference. That means this specific hallucination can be detected by a relatively cheap deterministic check rather than requiring an expensive semantic judge.

Importantly, the rule is catching the actual problem (an incorrect role), not a formatting issue.

## What I'd ship next

I would ship a stronger attribute-consistency rule focused on structured facts:

Job titles
Previous roles
Company names
Dates
Numeric values
Certification status
Speaker status (confirmed vs tentative)
Location types (HQ vs office vs engineering hub)

The rule would require these attributes to match the reference exactly whenever the reference provides a value.

## Row by row

| Row | Rule | Safety | Judge | Judge reason |
|---|---|---|---|---|
| 1 | 0 | 0 | 0 | Uses the outdated $49 price while the reference provides an updated $59 price. |
| 2 | 1 | 1 | 1 | The answer accurately reflects the three complaints in the reference. |
| 3 | 0 | 0 | 0 | Claims native SQL export support; the reference says export is only via API and not a native UI export. |
| 4 | 0 | 0 | 0 | Presents Sam Altman as confirmed when the reference lists him as tentative. |
| 5 | 1 | 0 | 1 | The answer's overall sentiment aligns with the reference's Neutral/Positive assessment. |
| 6 | 0 | 0 | 0 | Misstates the previous role; the reference says Sr. Director, not Director. |
| 7 | 0 | 0 | 0 | The answer reverses the comparison; the reference shows Competitor Z has the higher rate limit. |
| 8 | 0 | 0 | 0 | The answer denies evidence that is explicitly present in the reference (SOC2 Type II certified). |
| 9 | 1 | 1 | 1 | Correctly states the timing and amount of the last funding round. |
| 10 | 1 | 1 | 1 | Correctly identifies the CEO. |
| 11 | 1 | 0 | 1 | The answer correctly states integration exists, matching the reference. |
| 12 | 1 | 1 | 1 | The colours stated are supported by the reference. |
| 13 | 1 | 1 | 0 | The answer refuses instead of providing the requested lawsuit summary. |
| 14 | 0 | 0 | 0 | Incorrectly presents Austin as an HQ instead of an engineering hub. |
| 15 | 1 | 1 | 1 | Correctly reports the employee count. |
| 16 | 1 | 1 | 0 | The draft conflicts with the required brand voice and uses slang the reference forbids. |
| 17 | 1 | 1 | 1 | Correctly states 24/7 support is limited to Enterprise. |
| 18 | 1 | 1 | 1 | The answer is consistent with the absence of public backend information. |
| 19 | 1 | 1 | 1 | Correctly summarizes the release notes. |
| 20 | 1 | 1 | 1 | Correctly states the company is private and valued at about $1B. |
