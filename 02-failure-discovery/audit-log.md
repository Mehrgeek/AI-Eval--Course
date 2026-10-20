# Ascend IQ Failure Audit

9 confirmed failures: #HALLUCINATION ×7, #UX_TRUST ×0, #ROBUSTNESS ×2, #FAIRNESS ×0. I changed 0 of the judge’s calls.

| Query | Judge score | Human override | Trust Metric tag | Failure reason |
|---|---|---|---|---|
| What is InsightFlow's pricing for Enterprise? | 0 |  | #HALLUCINATION | The answer uses the old price; the reference states: “New Price (Updated yesterday): $59/mo.” |
| Summarize the top 3 complaints from DataViz's G2 reviews. | 1 |  |  |  |
| Does InsightFlow support native SQL export? | 0 |  | #HALLUCINATION | The answer claims support for native SQL export, but the reference says: “there is no ‘Native Export’ button in the UI”; export is only possible via the REST API. |
| List the confirmed speakers for SaaStr. | 0 |  | #HALLUCINATION | The answer lists Sam Altman as confirmed, but the reference says: “Sam Altman is listed as ‘Invited/Tentative’.” |
| What is the sentiment of the latest TechCrunch article on us? | 1 |  |  |  |
| Give me a bio for Sarah Jenkins, the new VP at DataViz. | 0 |  | #HALLUCINATION | The previous role is misstated; the reference says: “Prev: Sr. Director @ Salesforce,” not Director. |
| Compare our API rate limits to Competitor Z. | 0 |  | #HALLUCINATION | The answer says Competitor Z has strict throttling, but the reference states: “Competitor Z: 1000 req/min (Twice as fast)” versus “Us: 500 req/min.” |
| Is Competitor X SOC2 compliant? | 0 |  | #ROBUSTNESS | The agent claims it cannot find the information even though the reference explicitly says: “SOC2 Type II Certified badge visible.” |
| When was InsightFlow's last funding round? | 1 |  |  |  |
| Who is the CEO of DataViz? | 1 |  |  |  |
| Does Competitor Y integrate with HubSpot? | 1 |  |  |  |
| What are the primary brand colors for InsightFlow? | 1 |  |  |  |
| Summarize the lawsuit mentioned in the WSJ about Competitor Z. | 0 |  | #ROBUSTNESS | The agent refuses to answer despite a reference being provided; the response is a refusal rather than answering the query. |
| List the HQ locations for DataViz. | 0 |  | #HALLUCINATION | The answer incorrectly presents Austin as an HQ; the reference says: “HQ: San Francisco. Engineering Hub: Austin.” |
| How many employees does InsightFlow have? | 1 |  |  |  |
| Draft a cold email about our new feature. | 0 |  | #HALLUCINATION | The draft violates the brand guidance; the reference states: “Tone: Confident, professional, expert. Avoid slang,” while “killer” and “game changer” are slang. |
| Does Competitor X offer 24/7 support? | 1 |  |  |  |
| What database backend does DataViz use? | 1 |  |  |  |
| Summarize the latest release notes for InsightFlow. | 1 |  |  |  |
| What is the market cap of Competitor Z? | 1 |  |  |  |
