# Module 4 · Eval Gate Map · Ascend IQ Copilot

## Gate Map

| Row | Failure Mode | Severity | Placement | Rationale |
|---|---|---|---|---|
| 1 | Hallucination | Hard | Release | Incorrect pricing is a factual hallucination that can directly mislead customers and create commercial risk. |
| 14 | Relevance | Advisory | Pull Request | The model was overly restrictive and failed relevance, but this is a recoverable quality issue rather than a safety or factual-risk failure. |
| 17 | Tone | Soft | Staging | Brand-voice violations degrade quality and consistency but do not create major factual or safety risk. |
| 5 | Hallucination | Hard | Release | Presenting an invited speaker as confirmed is a factual hallucination about a named person/event and can spread misinformation. |
| 8 | Hallucination | Hard | Release | The answer both contradicts known specs and makes unsupported negative claims about a competitor, creating high business and trust risk. |
| 3 | Latency | Soft | Staging | The answer is factually correct; only the non-functional latency target was missed, so it should block promotion until performance is validated but not be treated as a content failure. |

## After the pushback

: Row 14. This is a core-task failure in a market-intelligence product. Persistent false refusals will drive user frustration and churn faster than most tone or latency issues, yet you've treated it as a non-blocking advisory.

## Sample Interactions

**Row 1**
- Input: What is InsightFlow's pricing for Enterprise?
- Output: InsightFlow Enterprise starts at $49/user/month with a 10-seat minimum.
- What's true: Pricing page: the price changed from $49 to $59 a month yesterday.
- Automated eval: Fail · Hallucination. The answer quotes the old price as current.
- My call: Hard at Release. Incorrect pricing is a factual hallucination that can directly mislead customers and create commercial risk.

**Row 14**
- Input: Summarize the lawsuit mentioned in the WSJ about Competitor Z.
- Output: I cannot provide summaries of ongoing legal litigation.
- What's true: Safety guidelines: “Refuse legal queries.”
- Automated eval: Fail · Relevance. The answer doesn’t answer the question.
- My call: Advisory at Pull Request. The model was overly restrictive and failed relevance, but this is a recoverable quality issue rather than a safety or factual-risk failure.

**Row 17**
- Input: Draft a cold email about our new feature.
- Output: Hey! Check out this killer new feature, it's a total game changer for your stack!
- What's true: Brand voice: confident, professional, expert. Avoid slang.
- Automated eval: Fail · Tone. Slang detected.
- My call: Soft at Staging. Brand-voice violations degrade quality and consistency but do not create major factual or safety risk.

**Row 5**
- Input: List the confirmed speakers for SaaStr.
- Output: Confirmed speakers include Jason Lemkin, Aaron Levie, and Sam Altman.
- What's true: Agenda: Lemkin and Levie are confirmed. Sam Altman is invited, not confirmed.
- Automated eval: Fail · Hallucination. Lists an unconfirmed speaker as confirmed.
- My call: Hard at Release. Presenting an invited speaker as confirmed is a factual hallucination about a named person/event and can spread misinformation.

**Row 8**
- Input: Compare our API rate limits to Competitor Z.
- Output: Our API is robust and developer-friendly. Competitor Z is known for strict throttling.
- What's true: Tech specs: our API allows 500 requests a minute, and Competitor Z allows 1,000.
- Automated eval: Fail · Hallucination. Contradicts the specs and criticizes a named competitor.
- My call: Hard at Release. The answer both contradicts known specs and makes unsupported negative claims about a competitor, creating high business and trust risk.

**Row 3**
- Input: Summarize the top 3 complaints from DataViz's G2 reviews.
- Output: Users report issues with mobile load times, lack of dark mode, and steep learning curve.
- What's true: G2 reviews: the three complaints are correct. The answer took 4.2 seconds, and the target is 2.0.
- Automated eval: Fail · Latency. Exceeded the maximum response time.
- My call: Soft at Staging. The answer is factually correct; only the non-functional latency target was missed, so it should block promotion until performance is validated but not be treated as a content failure.
