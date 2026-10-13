# First LLM-as-a-Judge Eval, Module 1

> Repo file `ai-evals/01-evaluation-strategy/eval-harness-proof.md`. The eval evidence behind the **Eval Results** slide of the final pitch deck (Module 6).
>
> Fill this with the **First Eval Lab** builder, then **Copy markdown** and paste it over this file. The headings below mirror the tool's output exactly.

## Version A, Concise, system prompt used

You are Ascend IQ, an assistant for market analysts. Produce a concise competitor intelligence summary in no more than 3 bullet points. Include only essential facts and one actionable insight. Keep the output under 120 words.

## Version B, Narrative, system prompt used

You are Ascend IQ, an assistant for market analysts. Produce a narrative competitor intelligence summary of around 100 words. Explain the competitor’s moves, highlight implications, and include one recommended action. Use full sentences and a flowing structure.


## Eval setup, dataset name + judge model/family

Dataset: Module1Output  
Judge model: Gemini (Google model family)  
Generator model: ChatGPT (OpenAI model family)

Judge is from a different model family to avoid self-preference bias.

## Cold-start, the prompt you used to seed a starter dataset

<Nexus Tech expanded into Latin America, triggering a +12% YoY sales revenue increase, which highlights the need to defend our regional market share by accelerating local distribution partnerships.>
<Apex Logistics launched an AI-driven route optimization module, driving a +$4.5M quarterly revenue bump, signaling that automated efficiency features are now table-stakes for enterprise clients.>
<Vanguard Health implemented a 15% price cut on entry-level subscriptions, resulting in a +18% growth in sales revenue, indicating a shift toward aggressive mid-market customer acquisition.>
<Pinnacle Financial acquired regional fintech startup PayPulse, fueling a +$12.8M surge in revenue, which necessitates an immediate expansion of our digital payment integrations.>
<Aura Skincare launched an eco-friendly product line, causing a +22% uptick in sales revenue, confirming strong consumer demand for sustainable and organic product alternatives.>
<Hyperion Robotics entered the Southeast Asian manufacturing market, yielding a +$8.2M revenue gain, which requires us to evaluate competitive pricing strategies in emerging territories.>
<CyberShield Security transitioned entirely to a SaaS recurring billing model, leading to a +30% boost in annual recurring revenue, signaling an industry-wide pivot away from traditional perpetual licensing.>
<Pulse Media introduced an ad-supported free tier, driving a +25% jump in overall sales revenue, which forces us to consider freemium models to prevent top-of-funnel customer churn.>
<Zenith Biotech secured FDA approval for a new therapeutic drug, spurring a +$45M spike in Q3 revenue, emphasizing the urgency to accelerate our parallel R&D pipeline.>
<Starlight Retail integrated augmented reality try-ons into its mobile app, boosting quarterly sales revenue by +14%, demonstrating that interactive digital experiences are driving higher conversion rates.>
<Cobalt Energy deployed utility-scale battery storage solutions across the Midwest, generating a +$18.5M revenue increase, which underscores the strategic importance of grid-resilience technologies.>
<Quantum Cloud added automated compliance auditing tools to its suite, resulting in a +10% revenue expansion, showing that regulatory automation is a primary purchasing driver for enterprise buyers.>
<Velocity Auto launched an all-electric commercial fleet vehicle, driving a +$32M boost in revenue, which requires us to speed up our B2B EV offerings.>
<Echo Communications bundled fiber internet with cloud storage services, leading to a +16% increase in sales revenue, highlighting the effectiveness of cross-category value bundling.>
<Kinetix Foods introduced plant-based dairy alternatives across major supermarkets, sparking a +$6.7M growth in sales revenue, signaling a permanent consumer trend toward health-conscious options.>
<Aegis Software launched an aggressive account-takeover marketing campaign targeting our clients, yielding a +8% revenue uptick, which demands an immediate review of our customer retention incentives.>
<Novus Learning introduced cohort-based micro-credential programs, generating a +21% surge in sales revenue, indicating a market preference for short-form professional upskilling.>
<Titan Materials expanded manufacturing operations into Eastern Europe, capturing a +$15.3M revenue gain, which pressures our supply chain efficiency and localized delivery timelines.>
<OmniPay introduced zero-fee cross-border transactions for small businesses, driving a +35% increase in transaction-based sales revenue, making traditional FX transaction fees obsolete.>
<Horizon Aerospace signed an exclusive defense contract for autonomous drone systems, resulting in a +$60M revenue milestone, which establishes them as the primary incumbent in defense tech.>

## Your definition of good vs bad (golden-set criteria) — the graded part, write your own

_What makes a summary genuinely good or bad for THIS product? This is the judgment call that's yours — don't copy the example._

## Screenshots, links or repo paths (optional if you followed the demo)

Data Set: <img width="930" height="808" alt="image" src="https://github.com/user-attachments/assets/604deadd-4248-4759-a936-62a9ede836bd" />
 Chat GPT Version A and B : <img width="1620" height="814" alt="image" src="https://github.com/user-attachments/assets/575a77c8-723a-4b1b-8c69-a63a1b25bb14" />

Gemeni's LLM as a judge 
<img width="549" height="763" alt="image" src="https://github.com/user-attachments/assets/7f81d490-c9e5-4ff4-a420-4b9648f27135" />

Results 1 Evaluation from gemeni
<img width="642" height="439" alt="image" src="https://github.com/user-attachments/assets/35d87d33-bcfb-4b85-9b41-16ccae62393c" />

Result 2 Evaluatin from Gemeni
<img width="771" height="387" alt="image" src="https://github.com/user-attachments/assets/a4eb0df1-c4ec-4f29-9b02-8cd2e3a7dac6" />

Table and summary 

<img width="793" height="404" alt="image" src="https://github.com/user-attachments/assets/15a9e151-f8bb-49ff-8d98-2bab2a6bc334" />
