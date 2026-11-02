# Module 5 · Coverage Matrix · Competitor Signal Tracker

## Coverage Row

| Product | Hallucination Rate | Fairness | Latency | UX Trust | Robustness |
|---|---|---|---|---|---|
| Competitor Signal Tracker | ❌ Gap | ❌ Gap | ✅ Covered | ❌ Gap | ⚠️ Partial |

## What Runs Today

- A timer alerts if the nightly scoring run takes more than 2 hours.
- A style check flags summaries written in a casual or alarmist tone before they reach the sales team.

## Accepted Gap

**Fairness.** n internal tool used by Ascend teams, not directly by customers. The current use case focuses on competitor intelligence rather than decisions about people or customer groups. Because of that, the immediate impact of fairness issues is relatively low compared with risks such as hallucinated competitor information reaching sales teams. Running a full fairness evaluation programme would cost more than the risk it mitigates right now.

We’ll look again: We would revisit this decision if the tool begins influencing customer-facing recommendations, expansion into new regions introduces significantly different source data, or teams report potential bias in competitor coverage. We will review the fairness gap during the next quarterly eval budget review, or sooner if customer-facing use cases are added.

## Critical Gap

The tracker produces summaries used by sales and strategy teams. A made-up competitor claim could directly lead to poor business decisions, making hallucination the highest-priority risk to address next.

## After the Pressure Test

The feedback changes three things:

UX Trust should be ⚠️ Partial, not ❌ Gap

You do have a style check for casual or alarmist tone.
That is a UX trust check, just not a complete one.
So a trust-related evaluation exists, making it partial coverage.

Robustness should be ❌ Gap, not ⚠️ Partial

Nothing you've described tests whether the tracker handles difficult, unusual, or edge-case inputs.
The latency timer is not a robustness check.
Therefore there is no robustness coverage.

The Hallucination gap needs a concrete closure plan

Your explanation of why hallucinations matter is good.
What's missing is the actual eval:
Check: factual accuracy / hallucination eval
Data: sampled competitor summaries compared against source articles
Frequency: weekly (or nightly) evaluation
Threshold: e.g., fail if >5% contain unsupported claims

So the revised row would be:

Hallucination Rate: ❌ Gap
Fairness: ❌ Gap
Latency: ✅ Covered
UX Trust: ⚠️ Partial
Robustness: ❌ Gap

The most important improvement is not actually the marks. It's adding a specific hallucination eval with data, cadence, and pass/fail threshold, because that's what a manager will look for when you say it's the highest-priority gap.
