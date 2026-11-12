# Campaign Strategy: Fin (formerly Intercom)

Generated 2026-11-12 with `/campaign-strategy`, built from:
- `CLAUDE.md` and everything in `context/`
- `knowledge-base/playbooks/workflow-anatomy.md`

Every claim cites a context file. INFERRED marks my reading.
- **Volume:** a relative band (High, Medium, Low, Very low), because no source in the research gives counts. A Clay test pull sets the real numbers (signal-matrix.md open item 1).
- **Customer names:** a name may appear in copy only once it's authorised in `context/messaging/facts.md`, which doesn't exist yet.

**What we sell:** the Fin AI Agent on the prospect's current helpdesk, "$0.99 per outcome", "No migration required" (company.md C7, C12). The Intercom helpdesk is the upsell.
**Base audience:** icp.md. Priority segments are S2 self-serve SaaS, S1 AI-native and S3 consumer fintech (signal-matrix.md).
**Key differentiators:** runs on any helpdesk; a published 76% average across 12,000+ customers; outcome pricing; its own Apex models (positioning.md).

---

## Customer discovery analysis

The full table is in `context/docs/case-studies.md` (5 detailed stories, 29 with results, 5 testimonials).

**Patterns:**
- **Industries:** AI products, self-serve SaaS and consumer fintech make up most stories (case-studies.md).
- **Size:** very large end-user bases ("millions of users", "100 million users") with small support teams ("Three-person team", "Team of 20 people") (case-studies.md).
- **Roles that bought:** Director or Head of Customer Support, Head of CX, Head of AI Support, VP of Information Systems, Operations Lead (personas.md).
- **Common problems:** volume outgrowing the team, a bot that stopped improving, messy systems, build vs buy (value-proposition.md).

**Challenge to the targeting:**
- The stories show buyers outside support too. Fin for Sales books meetings: Fellow's "Fin more than tripled its meeting bookings quarter over quarter – from 24 to 86." (case-studies.md); "$9.99" per qualification (company.md C7).
- That opens a second persona at the same accounts, demand generation and sales leaders. It's idea 4, the Creative (non-ICP) campaign.

**Best lookalike seeds:**
- Vanta, Clay and Personio (S2)
- Anthropic and Gamma (S1)
- Kalshi and Rocket Money (S3)

All published in case-studies.md.

---

## Ranked ideas

**How the ranking works:**
- Ideas are ranked by **signal strength** (how strongly the filter shows a need right now) plus **data ease** (how reliably we can get the data without manual research). Each is scored 1 to 5, and ties go to the stronger signal.
- Scores are my judgement (INFERRED), based on signal-matrix.md where a signal is already scored.
- Targeting levels: Broad, Focused or Niche.

| Rank | Campaign | Level | Mother intent | Segment and persona | Signal and data source | Angle | Volume per month | Difficulty | Signal | Data | Tier |
|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | **Hiring support agents in bulk (S2)** | Focused | Hiring specific roles | S2, champion | 3+ support agent roles posted in 30 days; Clay Find Jobs at Company | Put Fin in front of your helpdesk instead of the next hires | High: job posts are the highest-volume signal type (signal-matrix.md #1) | Low to medium | 5 | 5 | **Tier 1**: spec already approved |
| 2 | **Hiring support agents in bulk (S1 and S3 replicas)** | Focused | Hiring specific roles | S1 and S3, champion | Same build, keyword swaps ("Community Support", "Trading Support") | S1: free users at scale. S3: spikes when the market moves | High | Low (reuses #1) | 5 | 5 | **Tier 1**: same Clay build, new keywords |
| 3 | **Hiring AI-support or CX-automation roles** | Focused | Hiring specific roles | S2 and S1, champion and influencer | AI Support, CX Automation, Conversation Analyst, Knowledge Manager posts; Clay Find Jobs | You've decided to automate. Test Fin before you build | Low: new, rare titles (signal-matrix.md #2) | Medium: many already run an AI agent | 5 | 4 | **Tier 1**: strongest buying reason |
| 4 | **Fin for Sales: hiring inbound SDRs** (Creative non-ICP) | Focused | Hiring specific roles | S2, a new persona: demand generation or sales leader | Inbound SDR or BDR job posts; Clay Find Jobs | Qualify and book inbound leads 24/7 before adding reps | Medium: SDR posts are common (INFERRED) | Medium: new persona, thin proof (Fellow only) | 4 | 5 | **Tier 2**: new persona, one proof point |
| 5 | **Champion migration** | Niche | Champion migration | Any segment, champion | People named in Fin case studies who change company; Clay job change tracking | You ran Fin at your last company | Very low: a few dozen named people | Medium | 5 | 3 | **Tier 2**: best signal, tiny list |
| 6 | **24/7 and night-shift support hiring** | Niche | Hiring specific roles (job description parsing) | S2, S3, champion | Support posts that mention "24/7", "night shift", "weekend" or "overnight"; Clay Find Jobs plus a regex on the description | Fin "works 24 hours a day, every day" (voice.md V2) | Medium (INFERRED) | Low to medium | 4 | 4 | **Tier 1**: same build as #1, sharp story |
| 7 | **New support leader (last 90 days)** (New Hire) | Focused | New leadership (past 90 days) | S2, S1, S3, champion | Head, Director or VP of Support or CX with a start date under 90 days; Clay Find People | A quick win in your first quarter | Medium (signal-matrix.md #3) | Medium: start dates can lag | 4 | 4 | **Tier 1**: reliable titles, reaches the champion directly |
| 8 | **Hiring multilingual or new-region support** | Niche | Hiring specific roles | S2, S3, champion | Support posts with language or new-country keywords; Clay Find Jobs | Cover new languages without new hires (Topstep, Lightspeed) | Low | Low (reuses #1) | 4 | 4 | **Tier 1**: near-free variant of #1 |
| 9 | **Recently funded (Series B or later, last 90 days)** | Focused | Fundraising | S1, S2, economic buyer | Crunchbase via Clay | Growth without support cost growing at the same pace | Medium (INFERRED) | Low | 3 | 5 | **Tier 2**: easy data, weaker link to buying |
| 10 | **Big support team, no AI-support role** | Niche | Have or don't have specific team | S2, economic buyer | 10+ people with support titles and no AI-support or automation title (a reliable title check, not a tech check); Clay Find People count | "Your team of N" set against what Synthesia handles with the same headcount | Medium (INFERRED) | Medium | 3 | 4 | **Tier 2**: Golden ICP style, needs a careful count |
| 11 | **Headcount hypergrowth (25%+ in 6 months)** | Focused | Hypergrowth (headcount) | S1, S2, economic buyer | Clay Company Headcount | Support load follows headcount | Medium | Low | 3 | 4 | **Tier 2**: proxy signal |
| 12 | **LinkedIn engagers on AI-support content** | Niche | LinkedIn content engagement | S1, S2, champion | People who react or comment on posts about AI customer service; a LinkedIn scraping tool (Proposed) | You're looking at AI support. Here's how Vanta tested it | Low to medium | High: third-party data, quality varies | 3 | 2 | **Tier 3**: data reliability |
| 13 | **Post-acquisition systems** | Niche | Niche-specific play (M&A) | S2, influencer | Acquirer in the last 6 months; Crunchbase via Clay | Fin works across merged systems (Lightspeed) | Very low | Low | 3 | 4 | **Tier 3**: too few targets |
| 14 | **Decagon displacement** | Niche | Competitor customers | S2, S1, champion and influencer | Decagon widget detected; BuiltWith via Clay (verified) | Test Fin against your current AI agent (Vanta 73% vs 49%) | Low | Medium: only Decagon is verified | 3 | 3 | **Tier 2**: clear story, small list |
| 15 | **Zendesk shops with a large support team** | Niche | Companies using specific software | S2, champion | Zendesk widget (BuiltWith) plus 10+ support titles (Clay Find People) | Zendesk includes AI. Test it against Fin on your own tickets | Medium | Medium | 2 | 4 | **Tier 2**: static, no timing |
| 16 | **Lookalike of reference customers** (Lookalike) | Broad | Lookalike of customers | S2, S1, S3, champion | Clay Lookalike Companies seeded with Vanta, Clay, Personio, Anthropic, Gamma, Kalshi, Rocket Money | Companies like you already run Fin | High | Low | 2 | 4 | **Tier 2**: no timing, strong proof |
| 17 | **Help center readiness check** (Creative stretch) | Focused | Website content mentions | S2, champion | Prospect's public help center crawled (crawl4ai, Live); article count and last-updated dates | Fin's own readiness checklist applied to their help center (signals.md G10) | Medium | Medium | 2 | 3 | **Tier 2**: real value, slower build |
| 18 | **Creative Ideas: three uses of Fin** (Creative Ideas) | Broad | Mass sending campaigns | S2, S1, S3, champion | Base list; website analysis with a Clay Use AI column | Three specific ideas from their own site | High | Low | 1 | 4 | **Tier 2**: no signal, fast build |
| 19 | **Ecommerce brands on Gorgias or Shopify** (Creative non-ICP) | Focused | Companies using specific software | S5, champion | Gorgias or Shopify detected; BuiltWith via Clay | Fin for Ecommerce. WHOOP: "~130%increase in attributed sales" | Medium (INFERRED) | Medium: weak proof, Gorgias is a rival | 1 | 4 | **Tier 3**: outside priority segments, little proof |

**Required types:**
- Creative Ideas: #18
- New Hire: #7
- Lookalike: #16
- Creative (non-ICP): #4, with #19 as a second

**Creative stretch:** #5, #6, #10 and #17. **Golden ICP style:** #10.

---

## Campaign overviews (for the copywriter)

Value proposition categories: make money, save time, save money, mitigate risk.

1. **Hiring support agents in bulk (S2)**
   - Value: save money.
   - Hook: their open role, using `{{example_role_title}}` and `{{hiring_scale}}`.
   - Routes on helpdesk (Zendesk, HubSpot, none) and whether an AI agent is already on the site.
   - Proof per route: Lightspeed on Zendesk; Vanta head-to-head.
   - CTA: test Fin on their own conversations.
   - Fully specced: `output/campaigns/hiring-support-agents-in-bulk/workflow-spec.md`.
2. **S1 and S3 replicas**
   - Value: save money.
   - Same spec. Swap the title keywords and the Inclusion segment.
   - S1 proof: Anthropic's free users at scale. S3 proof: Kalshi's "80k+monthly Fin resolutions".
   - Built after #1 has results.
3. **Hiring AI-support roles**
   - Value: save time.
   - Hook: "you're hiring a {{example_role_title}}". The company has already chosen to automate.
   - Route on whether an AI widget is detected. If yes, use the head-to-head angle. If no, use build vs buy (Anthropic bought).
   - Persona: champion first, then influencer.
4. **Fin for Sales: hiring inbound SDRs**
   - Value: make money.
   - Audience: a different persona at S2 accounts.
   - Hook: their SDR post, set against "Fin more than tripled its meeting bookings ... from 24 to 86" (Fellow).
   - Price: "$9.99" per qualification (company.md C7).
   - Fin for Sales engages "high intent visitors" and books meetings (company.md C15, search source), so the pitch is inbound leads on their website, not outbound prospecting.
5. **Champion migration**
   - Value: save time.
   - List: the people named in Fin case studies (case-studies.md), tracked for job changes.
   - Hook: they've used Fin before.
   - Use only names that are public on Fin's own pages. Don't contact people who didn't publish their association. INFERRED rule.
6. **24/7 and night-shift support hiring**
   - Value: save money.
   - The job description says they need people around the clock.
   - Angle: Fin "works 24 hours a day, every day" (voice.md V2). Topstep's 2am native-language quote.
   - Same Clay build as #1, plus a regex on the description.
7. **New support leader**
   - Value: save time.
   - Acknowledge the new role.
   - Angle: a quick result in the first quarter. Lightspeed's early resolution went from 20% to "over 70%".
   - No people search needed, since the leader from the signal is the contact.
   - INFERRED: that new leaders review tools early comes from the framework, not the research.
8. **Multilingual or new-region support**
   - Value: save money.
   - Hook: the language or region in their post.
   - Proof: Lightspeed "12+ languages", Topstep.
9. **Recently funded**
   - Value: save money.
   - Persona: economic buyer.
   - One line on `{{recent_round}}`, then the cost angle (Rocket Money ~$1M annual ROI).
   - Funding is context, not the main reason (signal-matrix.md #5).
10. **Big support team, no AI-support role**
    - Value: save money.
    - Count support titles at the company (for example "14 people on your support team").
    - Angle: what Synthesia handles "with same headcount".
    - Only the title check is inverted, which is reliable. We never assume a tool is absent.
11. **Headcount hypergrowth**
    - Value: save money.
    - Angle: support volume grows with the company.
    - Fallback for accounts with no hiring signal.
12. **LinkedIn engagers**
    - Value: save time.
    - Reference the topic they engaged with, not the post itself.
    - Proof: Vanta's test.
    - Build only after the Tier 1 workflows run.
13. **Post-acquisition systems**
    - Value: mitigate risk.
    - Persona: influencer.
    - Proof: Lightspeed's "numerous Salesforce instances, overlapping ERPs, and siloed data." and "Fin worked with our complexity".
14. **Decagon displacement**
    - Value: make money (more resolved).
    - Offer a head-to-head on their own conversations.
    - Never criticise the incumbent by name in copy. INFERRED rule.
15. **Zendesk shops with a big support team**
    - Value: save money.
    - Angle: keep Zendesk "as your system of record" and test Fin against Zendesk's included AI.
    - Supporting proof: Birdie Care.
16. **Lookalike**
    - Value: save money.
    - "Companies like {{company_name}} run Fin": pick the closest seed customer per segment.
    - Names only from facts.md.
17. **Help center readiness check**
    - Value: mitigate risk.
    - Crawl their help center. Report article count, how old the articles are, and possible duplicates, set against Fin's checklist ("Content is outdated, duplicated or contradictory", signals.md G10).
    - Offer the full review as a front-end offer.
18. **Creative Ideas**
    - Value: save time.
    - "I had an idea for {{company_name}}..." followed by three uses drawn from their site, for example:
      - questions their help center already answers
      - a pricing page Fin for Sales could qualify on
      - a language they serve
    - CTA: would any of these be worth a look?
19. **Ecommerce on Gorgias or Shopify**
    - Value: make money.
    - Fin for Ecommerce angle, with WHOOP proof.
    - Weak research base, so keep it Tier 3 until there are more ecommerce stories.

---

## No-AI campaigns

**Before agent number four**
- **Why it works:** list #1 already says they're hiring support agents, so the message doesn't need personalising.
- **Core message:** they're hiring support agents. Fin resolves an average of 76% across 12,000+ customers and costs $0.99 per outcome, with no migration. Ask whether they'd test it on last month's conversations before the next hire (company.md C6, C7, C12).

**Your helpdesk stays**
- **Why it works:** for a list of Zendesk users (#15), the single biggest objection is migration, and one line removes it.
- **Core message:** Fin runs on Zendesk, "keeping Zendesk as your system of record" (company.md C12). Ask if they'd see it on their own tickets.

---

## Front-end offers

1. **A test on your own conversations.** Run Fin on a sample of the prospect's real conversations and compare it with what they use now. This mirrors Vanta's 400-conversation head-to-head (case-studies.md). The prospect sees their own resolution rate before buying.
2. **Help center readiness review.** Apply Fin's five readiness checks (content, scope, procedural, data, execution; signals.md G10) to their public help center and send the findings. It's useful even if they don't buy, and it leads into idea #17.
3. **The 14-day free trial.** "14-day free trial", "No credit card required" (company.md C8). It suits self-serve S2 and S1 companies. For accounts on another helpdesk, note the "50 outcomes per month minimum" after the trial (company.md C7).

---

## What to build next

- **#1 is already specced.** Build it in Clay first.
- **#2, #6 and #8 reuse #1's Clay build** with new keywords, so they're the cheapest next launches.
- **#3 and #7 are the next new builds**, one on job posts and one on people search.
- **Don't build Tier 2 or 3 ideas** until #1 has run through one weekly feedback loop (gtm-system.md step 11).
