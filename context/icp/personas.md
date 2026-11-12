# Buyer personas: Fin (formerly Intercom)

Built only from `context/docs/research/`. Quotes are exact and come from named people in Fin's customer stories, so they describe buyers who already bought. Each quote cites its file and source tag. INFERRED marks my reading. Gaps are listed at the end.

## 1. Champion: the support leader

| | |
|---|---|
| **Job titles** | Director of Customer Support (Vanta, Underdog); Head of Product Support (Anthropic); Head of CX and Head of Support (Clay); VP, Global Support (Lightspeed); Head of Customer Operations (Numan); Support Lead (Consensys); Operations Lead (Kalshi) (customers.md sections 2, 4, 5) |
| **Measured on** | Resolution rate, CSAT, hours saved, deflection against a target, first response time. Vanta had a 50% resolution target and reports "96.7%CSAT YTD" (customers.md K9). Anthropic reports "1,700 hours saved in first month" (K10) |
| **What makes them start looking** | Volume outgrows the team; the current bot stops improving; a channel such as email has no AI coverage (signals.md rows 1, 3, 12) |

**Top three pains, in their own words**
1. "If LeBron James gets injured, we will get thousands of inbound questions within a 10-minute span," (Andre Gamboa, Director of Customer Support, Underdog; customers.md section 5)
2. "It felt like we had outgrown the setup, and it was only a matter of time before it stopped holding." (Margarita Wilshire, Director of Customer Support, Vanta; customers.md K9)
3. "Every other company out there scales to 200+ in support." (Shannon Magiera, Operations Lead, Kalshi; customers.md section 5)

**Objections**
- *Our content isn't ready.* Fin's own checklist names "Content is outdated, duplicated or contradictory" (signals.md G10). Answer from research: Anthropic launched "In under a week" and went from 36% to 50.8% resolution (customers.md K10).
- *AI will hurt CSAT.* INFERRED objection. Counter-proof: Vanta "96.7%CSAT YTD" (K9); Birdie kept "a score of over 90% for more than a year" (customers.md K11).
- *Customers will share personal data with a bot.* Birdie Care raised privacy and now asks customers upfront (customers.md K11).

## 2. Economic buyer: the operations or finance owner

| | |
|---|---|
| **Job titles** | Director of Operations (Rocket Money); Chief Digital Officer (solidcore); General Manager, Operations (Sharesies); Chief Operating Officer and Chief Financial Officer (INFERRED from Fin's own leadership roles, no customer example found) (customers.md sections 2, 5) |
| **Measured on** | Cost to serve, support headcount, ROI. Published outcomes: "~$1MAnnual ROI from Fin" (Rocket Money), "$569kCosts saved annually" (solidcore), "$359kSalary savings in 6 months" (Nuuly), expected headcount down "by 30%" (Birdie Care) (customers.md sections 2, 4) |
| **What makes them start looking** | A support headcount plan that grows in line with customers. Fin's framing: "you don't have to have the same linear growth" (signals.md G8) |

**Top three pains, in their own words**
1. "When support volume gets that high, your only option is throwing bodies at the problem." (Yamine Gluchow, VP of Information Systems, Lightspeed; customers.md K8)
2. "Where humans cannot scale, AI is actually amplifying that human capability." (speaker not stated, AppFolio; customers.md section 5)
3. Gap: no economic buyer pain quote found. The nearest is an outcome quote: "We're in the millions of dollars of cost savings from leveraging Fin, just from employee salaries and benefits." (speaker not stated, ZayZoon; customers.md section 5)

**Objections**
- *Salesforce now owns Fin. Will pricing or the roadmap change?* Competitors pitch exactly this (competitors.md P17, P18). Salesforce says Fin "will continue to serve its customers" and "works seamlessly with the help desks" companies already use (company.md C3).
- *A cheaper agent exists.* HubSpot charges "$0.50" per resolution and says it is "half the price of leading competitors" (competitors.md P10), against Fin's $0.99 (company.md C7).
- *Usage-based cost is hard to budget.* INFERRED objection. Facts that help: "only charged for one outcome per conversation" and "not charged when a conversation is simply passed to your team without an outcome" (company.md C7).

## 3. Influencer: the systems or AI owner

| | |
|---|---|
| **Job titles** | VP of Information Systems (Lightspeed); Senior Revenue Operations Lead (Birdie Care); Head of AI Support (Anthropic); AI & Solutions Manager (MONY Group); SVP of Global Sales (Vanta) (customers.md sections 4, 5) |
| **Measured on** | INFERRED from their roles: system reliability, integration effort, data security, and for sales leaders, a clean handoff from support to sales. Not stated in the research |
| **What makes them start looking** | A build-or-buy decision on an AI agent (Anthropic), messy systems after M&A (Lightspeed), or a regretted helpdesk migration (Birdie Care) (signals.md rows 4, 5, 6) |

**Top three pains, in their own words**
1. Lightspeed's systems after M&A: "numerous Salesforce instances, overlapping ERPs, and siloed data." (story text, customers.md K8)
2. "We had a brief period where we looked at Zendesk and actually started trying to implement it." (Luke Cullimore, Birdie Care; customers.md K11)
3. "If you're debating whether to build your own AI solution or buy one," ... (Isabel Larrow, Head of AI Support, Anthropic; customers.md K10)

**Objections**
- *We'd rather build it ourselves.* Anthropic faced the same choice and bought (customers.md K10).
- *We can't migrate off our helpdesk.* "Deploy Fin on any helpdesk over API. No migration required." (company.md C12). Lightspeed: "We didn't have to untangle everything, Fin worked with our complexity, not in spite of it." (customers.md K8)
- *We want to choose our own model.* Fin runs on its own Apex models (company.md section 2); rivals pitch model choice (competitors.md P17). Fin claims "+15%" "Confirmed resolutions vs Sonnet 5" (competitors.md P0).
- *Security and permissions.* Fin lists SOC2, ISO 27001, ISO 42001, HIPAA (company.md section 9); its own checklist flags permission scoping (signals.md G10).

## Gaps

- No economic buyer pain quote in the research. Interviews or call notes would fill it.
- What influencers are measured on is INFERRED.
- How deals actually close (who signs, how long it takes): not found.
