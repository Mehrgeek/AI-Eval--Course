# Module 5 · Eval Budget · Ascend IQ

**Quarterly budget cap:** $200,000
**Online eval spend:** $0 (0 of at most 3 online evals)

## Budget

| Failure | Trust metric | Risk | Level | Cost |
| --- | --- | :---: | :---: | ---: |
| Data Fabrication | Hallucination Rate | P0 | Code-based check | $4,250 |
| Context Specificity | Robustness | P1 | Periodic audit | $7,000 |
| Overconfident Tone | UX Trust | P1 | Code-based check | $3,250 |
| Data Bias | Fairness | P2 | Periodic audit | $5,500 |
| Slow Answers | Latency | P3 | Code-based check | $1,250 |

## Downgrades

### Code-based check · Data Fabrication (Hallucination Rate · P0)
- **Cheaper check:** Code-based check: Rule check on every release.
- **Why it’s enough:** Check generated summaries against the source articles and flag competitor prices, review counts, and other numerical claims that do not appear in the source. This catches many fabrication errors at a much lower cost than continuous online evaluation and provides reasonable protection until a full online eval is funded.

### Periodic audit · Context Specificity (Robustness · P1)
- **Cheaper check:** Periodic audit (weekly sample review)
- **Why it’s enough:** Review a weekly sample of prompts and answers to check whether the response followed the user's specific request, such as focusing on negative reviews when asked. Context-specificity failures are usually easy for human reviewers to spot, so a regular audit can catch trends without the cost of scoring all live traffic.

### Code-based check · Overconfident Tone (UX Trust · P1)
- **Cheaper check:** Code-based check (rule check on every release)
- **Why it’s enough:** Use a rule check to flag answers that express uncertainty-sensitive topics as definite facts, such as using absolute language ("definitely", "always", "will") when the evidence is incomplete. Overconfident tone is often identifiable through language patterns, making a lightweight rule check a cost-effective way to catch many cases before release without paying for continuous live-traffic evaluation.

### Periodic audit · Data Bias (Fairness · P2)
- **Cheaper check:** Periodic audit (weekly sample review)
- **Why it’s enough:** Review a weekly sample of summaries covering both US and APAC sources and compare the quality, completeness, and citation patterns. Because this is a P2 fairness risk, periodic human review is usually sufficient to detect systematic regional bias before it becomes a significant issue, while costing much less than continuous online evaluation.

### Code-based check · Slow Answers (Latency · P3)
- **Cheaper check:** Code-based check (latency test on every release)
- **Why it’s enough:** Automatically measure response times on a set of representative multi-step questions during each release. Flag any test that exceeds the 10-second target. Because latency is easy to measure objectively, a rule-based performance check provides reliable coverage at a much lower cost than continuous online evaluation.

