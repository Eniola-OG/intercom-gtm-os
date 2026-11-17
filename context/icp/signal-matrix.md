# Signal Matrix: Fin (formerly Intercom)

**Status: WORK IN PROGRESS.** Nothing here has been checked with Fin's sales team, and no Clay test has been run yet.
- Method: `knowledge-base/playbooks/signal-matrix-framework.md` and `workflow-anatomy.md`.
- Inputs: `context/icp/icp.md`, `context/icp/personas.md` and everything in `context/docs/research/`.
- Citations use file plus source tag, for example `customers.md K9`.
- INFERRED marks anything the research does not directly support.
- Volume is "Unknown until test pull" wherever no number exists. No counts are invented.

**What we sell:** one product leads every cell. The Fin AI Agent goes on the prospect's current helpdesk at "$0.99 per outcome" with "No migration required" (company.md C7, C12). The Intercom helpdesk is the upsell. Because the product is the same in every cell, **the angle is what changes from cell to cell** (framework: single-product company).

---

## Matrix 1: Segments × personas

### Why these rows

- **Rows are segments by product type.** The ICP's best-supported pattern is a self-serve product with a very large user base and a small support team (icp.md Layer 1). Within that pattern, buyers differ by what their users ask about and what proof lands. That splits cleanly into product categories a Clay operator can filter by industry and description.
- **The prospect's helpdesk is not a row.** One company can run Zendesk plus Decagon, which breaks the "one company, one cell" rule. Helpdesk is used in Matrix 2 as a routing enrichment instead.
- **Columns are the three personas** from personas.md.

### Segment definitions

Shared filters for all rows: more than 15 employees and more than $10M raised (company.md C13); HQ or major office in the US, UK, Ireland, EU or Australia (company.md C9); not a current Fin customer; not a Salesforce Service Cloud account (icp.md Not a fit). The upper size limit is still open (icp.md Open question 1).

| # | Segment | Target definition (filterable) | Reference customers (proof, from research) | Prospect examples (named customers of competing vendors, from competitors.md) | Priority |
|---|---|---|---|---|---|
| S1 | **AI-native products** | Main product is an AI application or model, sold self-serve or with a free tier | Anthropic, Glean, Gamma, Synthesia, Magnific (customers.md section 2) | Cohere, Grammarly (Forethought logos, competitors.md P6). Requires Clay research for more: industry "Artificial Intelligence" plus "free plan" or "sign up" on the site | **High** |
| S2 | **Self-serve B2B SaaS** | B2B software with online signup or a free trial, and a public help center | Vanta, Clay, Personio, AppFolio, DaySmart, Teachable (customers.md section 2) | Notion, Figma (Decagon, P3); GitHub, Box, Vimeo (Zendesk, P1); monday.com (Ada and HubSpot, P5, P10); Upwork, Thumbtack (Forethought, P6). INFERRED: several may be above the size ceiling | **High** |
| S3 | **Consumer fintech, trading and crypto** | Consumer money, investing, trading, prediction-market or crypto app | Rocket Money, Kalshi, Consensys, Topstep, Neo Financial, MONY Group, ZayZoon (customers.md section 2) | Chime, Square (Decagon, P3); Acorns (Forethought, P6). Rocket Mortgage, Vanguard and Santander (Sierra, P4) are INFERRED to be enterprise, so likely not a fit | **High** |
| S4 | **Digital health** | Patient- or carer-facing health app or care platform | Birdie Care, Circle Medical, Numan (customers.md section 2) | Sutter Health (Sierra, P4). INFERRED enterprise, likely not a fit. Requires Clay research for more | Medium |
| S5 | **Consumer subscription, education and marketplaces** | Subscription consumer products, learning platforms, recommerce | Nuuly, WHOOP, solidcore, LSBU, MPB (customers.md section 2) | Duolingo, Oura (Decagon, P3); Pinterest (Ada, P5); Discord (Zendesk, P1) | Low |

### Angle per cell

The angle is written in the buyer's terms, using proof from the research. These are angle hypotheses, not copy.

| Segment | Champion (support leader) | Economic buyer (ops or finance) | Influencer (systems or AI owner) |
|---|---|---|---|
| **S1 AI-native** | **Free users at scale without a bigger team.** Anthropic hit "50.8%" resolution in just over a month and "1,700 hours saved in first month"; "Intercom's help center and Fin are now key cornerstones for how we support free users at scale." (customers.md K10) | **Support cost that doesn't grow with free signups.** Synthesia: ">275kadditional monthly queries handled with same headcount" (customers.md section 2) | **Build or buy.** Anthropic, a model maker, chose to buy (customers.md K10). Fin claims "+15%" "Confirmed resolutions vs Sonnet 5" (competitors.md P0, a vendor claim) |
| **S2 Self-serve SaaS** | **Beat the bot you already have.** Vanta: Fin about 73% vs the incumbent's about 49% on 400 conversations; now "71%" resolution and "96.7%CSAT YTD" (customers.md K9) | **Stop hiring at the same pace as customer growth.** "When support volume gets that high, your only option is throwing bodies at the problem." (Lightspeed, customers.md K8). Personio: "30kmonthly Fin resolutions" | **No migration.** "Fin worked with our complexity, not in spite of it." (Lightspeed, K8). Runs on Zendesk "keeping Zendesk as your system of record" (company.md C12) |
| **S3 Consumer fintech** | **Spikes when the market moves.** Kalshi: "80k+monthly Fin resolutions", "80%automation rate"; Topstep users reach support "in their native language at 2:00 in the morning" (customers.md section 5) | **Headcount savings.** ZayZoon: "millions of dollars of cost savings" ; Rocket Money "~$1MAnnual ROI from Fin" (customers.md section 2, 5) | **Safe in a regulated business.** MONY Group (regulated financial services): "98%Fin involvement rate", "64%Fin resolution rate" (customers.md section 2). SOC2, ISO 27001, ISO 42001 (company.md section 9) |
| **S4 Digital health** | **Grow the product without growing the team.** Birdie Care: product scope "doubled", expected headcount down "by 30%" (customers.md K11) | Numan: "19kHours saved annually" (customers.md section 2) | **Personal data in chat.** Birdie asks customers upfront (K11); HIPAA listed (company.md section 9) |
| **S5 Consumer subscription** | WHOOP, a "Three-person team": "~130%increase in attributed sales" (customers.md section 2) | solidcore: "$569kCosts saved annually" (customers.md section 2) | INFERRED: Fin for Ecommerce (company.md C6). Little research proof, so this cell stays weak |

### Segment assessment

Scores are my judgement (INFERRED), based on the evidence above.

| Segment | Signal density | Product fit | Reachability | Rank | Why |
|---|---|---|---|---|---|
| S2 Self-serve SaaS | High | High | High | **1** | Most reference customers, plus the clearest displacement proof (Vanta). US-heavy and well covered by job and tech data |
| S1 AI-native | High | High | High | **2** | Anthropic is the strongest proof Fin has. VC-backed and hiring fast. Smaller pool than S2 (INFERRED) |
| S3 Consumer fintech | High | High | Medium | **3** | Many reference customers. Regulated, so more objections. Volume spikes tie to market events |
| S4 Digital health | Medium | Medium | Medium | 4 | Three stories only. Privacy objections |
| S5 Consumer subscription | Medium | Low | High | 5 | Logos but little Fin proof. Ecommerce is unresearched |

**Priority cells for Matrix 2: S2, S1, S3.** This is my recommendation. Fin's sales team may rank them differently based on deals we can't see.

---

## Matrix 2: Buying signals

### How each signal is scored

The four tests come from workflow-anatomy.md. Each test is scored 1 to 5 (5 is best), for a total out of 20. Scores are judgement (INFERRED), with the evidence cited.
- **Reason:** is there a clear buying reason?
- **Volume:** are there enough companies showing the signal?
- **Data:** can we actually get the data?
- **Story:** does the signal give us a natural story to tell?

Iron Law check: "Could I send this to a Clay operator right now with zero ambiguity?"
- Credit costs for each Clay action aren't in our playbook (`clay/actions-data-credits.md` gives only the typical "6-20 credits per fully enriched record"). They need checking in Clay.
- Volume is "Unknown until test pull" everywhere. No source gives counts.

### Signals that passed

| # | Type | Signal (observable event) | Mother intent (workflow-anatomy.md) | Data source | Tool / Clay action | Key filters | Research support | Reason | Volume | Data | Story | Total | Status |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Universal | **Hiring support agents in bulk** | Hiring specific roles plus hiring velocity | Job posts (LinkedIn Jobs, Indeed, company career pages) | Clay "Find Jobs at Company"; Apify for boards Clay misses (clay/expert.md) | Titles: Customer Support, Support Specialist, Support Agent, Technical Support, Customer Experience Associate. Posted in the last 30 days. Starting threshold of 3+ open support roles (INFERRED, to tune) | Kalshi "scales to 200+ in support"; Lightspeed "throwing bodies at the problem" (personas.md) | 5 | 4 | 5 | 5 | **19** | VERIFIED |
| 2 | Universal | **Hiring AI-support or CX-automation roles** | Hiring specific roles | Job posts | Clay "Find Jobs at Company" | Titles: AI Support, Support Operations, CX Automation, Conversation Analyst, Knowledge Manager, AI Ops (signals.md G9). Last 30 days | New roles "conversation analysts, knowledge managers, AI ops" (signals.md G9); "Head of AI Support" at Anthropic (customers.md K10) | 5 | 2 | 5 | 4 | **16** | VERIFIED |
| 3 | Universal | **New support leader in the last 365 days** | New leadership (past 365 days) | People profiles | Clay "Find People at Company", filtered by title and start date | Titles: Head, Director or VP of Support, Customer Support, CX, Customer Operations. Start date in the last 365 days, labelled "New in role" (0 to 180 days) or "First year" (181 to 365 days). Widened from 90 days on 2026-11-17: a Clay test pull at 180 days left 3 qualified people | Titles from personas.md. INFERRED: the idea that new leaders review tools early comes from the framework, not the research. Only "New in role" rows get the new-leader opener | 4 | 3 | 4 | 4 | **15** | VERIFIED |
| 4 | Universal | **Hiring multilingual or new-region support** | Hiring specific roles (location and language variant of #1) | Job posts | Clay "Find Jobs at Company" | Titles from #1 plus "German-speaking", "Spanish-speaking", "Japanese", "bilingual", "APAC", or a job location in a country new for the company | Topstep "Asia-Pacific ... at 2:00 in the morning"; Lightspeed "12+ languages" (signals.md row 8) | 4 | 2 | 4 | 5 | **15** | VERIFIED |
| 5 | Universal | **Recent funding round (Series B or later, last 90 days)** | Fundraising | Crunchbase | Crunchbase via Clay (clay/expert.md) | Round type, announced in the last 90 days, more than $10M total raised | INFERRED: reference customers are VC-backed tech companies (signals.md section 3). No direct link to buying was found | 3 | 4 | 5 | 3 | **15** | VERIFIED (use as secondary enrichment) |
| 6 | Universal | **Headcount growth of 25%+ in 6 months** | Hypergrowth (headcount) | Company headcount snapshots | Clay "Company Headcount" | 25%+ growth in 6 months (the framework's default, INFERRED for Fin) | Proxy for "volume spike" (icp.md Layer 3, signal 5) | 3 | 3 | 4 | 3 | **13** | VERIFIED (use as secondary enrichment) |
| 7 | Universal | **Helpdesk widget on site: Zendesk, HubSpot or Freshdesk, with no Intercom widget** | Companies using specific software | BuiltWith | BuiltWith via Clay "Find Technology Stack" | Detect Zendesk Chat or Web Widget, HubSpot Messages or Conversations, Freshdesk. Exclude Intercom | BuiltWith has pages for Zendesk Chat and HubSpot Messages ([builtwith.com Zendesk](https://builtwith.com/bpxio.zendesk.com), [HubSpot Messages trends](https://trends.builtwith.com/widgets/Hubspot-Messages), checked 2026-11-12). Freshdesk detection not verified | 2 | 5 | 4 | 4 | **15** | VERIFIED (COMPOUND, routing only) |
| 8 | Universal | **Standalone AI agent on site (Decagon, Ada, Sierra)** | Competitor customers | BuiltWith | BuiltWith via Clay | Detect Decagon (verified on [BuiltWith](https://trends.builtwith.com/widgets/Decagon/Future-Customers/Slovakia), checked 2026-11-12). Ada and Sierra not verified | Vanta's 73% vs 49% head-to-head (customers.md K9) | 3 | 2 | 3 | 4 | **12** | VERIFIED (PARTIAL, COMPOUND) |
| 9 | Universal | **Made an acquisition in the last 6 months** | Niche-specific play (M&A) | Crunchbase acquisitions | Crunchbase via Clay | Acquirer, deal in the last 6 months | Lightspeed only (customers.md K8) | 3 | 1 | 4 | 4 | **12** | VERIFIED (low volume) |
| L | List source | **Lookalikes of Fin reference customers** | Lookalike of customers | Clay seed list built from customers.md | Clay "Lookalike Companies" | Seed with S1 to S3 reference customers | Not a timing signal. It builds the account list that signals 1 to 9 then run against | n/a | n/a | n/a | n/a | n/a | List source, not a signal |

### Signals killed, and why

| Signal | Why killed |
|---|---|
| Support volume spike (directly) | Not observable from outside (icp.md Layer 3). Replaced by proxies #5 and #6 |
| Existing chatbot has stalled | The vendor is visible (#8), but the stall isn't |
| Email has no automation | Not observable. Keep as a discovery question |
| Regrets a recent helpdesk migration | Not observable. Keep as a discovery question (Birdie Care, customers.md K11) |
| EU AI Act chatbot disclosure | The deadline passed on 2 Aug 2026 (market.md M1). It's a reason to review the bot, not to switch (icp.md). Framework guardrail: "Don't raise topics nobody asked about" |
| Salesforce Service Cloud accounts | A channel, not a cold signal. Same owner as Agentforce (icp.md Not a fit) |
| Companies leaving Fin after the acquisition | A retention signal, not an acquisition signal (signals.md section 4) |
| Content or intent (blog RSS, LinkedIn posts) | No research shows support leaders post buying intent. Partial coverage only (framework) |

### Plays per priority segment

The same Clay builds serve every segment. Only the keywords, the proof and the angle change.

| # | Signal | S2 Self-serve SaaS | S1 AI-native | S3 Consumer fintech |
|---|---|---|---|---|
| 1 | Hiring support agents | Add "Technical Support Engineer". Proof: Vanta, Lightspeed | Add "Community Support", "User Support". Proof: Anthropic | Add "Member Support", "Trading Support", "Payments Support". Proof: Kalshi, Rocket Money |
| 2 | AI-support roles | Proof: Vanta "AI orchestration" quote (customers.md K9) | Proof: Anthropic "Head of AI Support" | Proof: MONY Group "AI & Solutions Manager" |
| 3 | New support leader | Angle: beat the current bot | Angle: build or buy | Angle: safe in a regulated business |
| 4 | Multilingual or new region | Proof: Lightspeed "12+ languages" | INFERRED: global free users | Proof: Topstep, APAC at 2am |
| 5, 6 | Funding, headcount (enrichment) | Secondary line: growth context | Same | Same |
| 7 | Helpdesk widget (routing) | Zendesk route: Birdie, Fathom proof. HubSpot route: resolution rate, not price (icp.md Layer 2) | Same routes | Same routes |
| 8 | AI-agent widget (routing) | Vanta head-to-head | Same | Same |
| 9 | M&A | Lightspeed proof | INFERRED rare | INFERRED rare |
| Product | All cells | Lead: Fin AI Agent on the current helpdesk. Upsell: Intercom helpdesk and Copilot | Same | Same |

**What can be built once:** every signal that passed (9 of 9) is universal. One Clay build serves all three priority segments with keyword swaps. **No niche-specific signal was found in the research.** INFERRED idea to research later: new state money-transmitter licences on NMLS for S3, a source the framework lists for US fintech.

---

## Top signals to build first

| Rank | Signal | Score | Why first |
|---|---|---|---|
| **1** | **#1 Hiring support agents in bulk** | 19/20 | Highest-volume signal type in the framework. Data is easy to get with Clay "Find Jobs at Company". Customers say it themselves: "throwing bodies at the problem". The story writes itself: Fin instead of the next hire |
| **2** | **#2 Hiring AI-support or CX-automation roles** | 16/20 | Strongest buying reason: the company has already decided to automate support. Lower volume, but the same Clay build as #1 with different titles. Route on #7 and #8 to catch companies already using a competitor |
| **3** | **#3 New support leader in the last 365 days** | 15/20 | Reaches the champion directly through a different Clay action ("Find People"). Gives a timing hook that doesn't depend on hiring |
| **4** | **#4 Hiring multilingual or new-region support** | 15/20 | Almost free: a variant of #1's build. The 24/7, many-languages story has strong proof (Topstep, Lightspeed) |

**Secondary enrichments for every workflow:** #7 helpdesk widget (picks the Zendesk or HubSpot route), #8 AI-agent widget, #5 funding, #6 headcount growth. The workflow-anatomy.md rule allows 2 to 4 per workflow.

**What would change this ranking:** a test pull showing #1's volume is too low after the ICP filter, or Fin's sales team saying new leaders (#3) convert better.

---

## Matrix 3: Workflow tracker

| W # | Status | Workflow name | Mother intent | Segment | Persona | Enrichments | Channel | Launch date | Clay URL | Copy URL | Total leads | Bounce |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| W1 | Spec approved 2026-11-12 (output/campaigns/hiring-support-agents-in-bulk/workflow-spec.md) | Hiring support agents | Hiring specific roles | S2, S1, S3 | Champion, then economic buyer | #7, #8, #5, #6 | | | | | | |
| W2 | Planned | Hiring AI-support roles | Hiring specific roles | S2, S1, S3 | Champion, influencer | #7, #8 | | | | | | |
| W3 | Planned | New support leader (365 days, two timing labels) | New leadership | S2, S1, S3 | Champion | #7, #8, #5 | | | | | | |
| W4 | Planned | Hiring multilingual support | Hiring specific roles | S2, S1, S3 | Champion | #7, #6 | | | | | | |
| W5 | Planned | Recent funding | Fundraising | S1, S2 | Economic buyer | #1, #7 | | | | | | |
| W6 | Planned | Headcount hypergrowth | Hypergrowth (headcount) | S2, S1, S3 | Economic buyer | #1, #7 | | | | | | |
| W7 | Planned | Displace standalone AI agent | Competitor customers | S2, S1, S3 | Champion, influencer | #1, #3 | | | | | | |
| W8 | Planned | Post-acquisition systems | Niche-specific play (M&A) | S2 | Influencer | #7 | | | | | | |

---

## Open items

1. Volume for every signal: run a test pull in Clay once the account is set up (CLAUDE.md Tools: "Clay (account not set up yet)").
2. Credit cost for each Clay action: not in our playbook.
3. Whether BuiltWith detects Freshdesk, Ada and Sierra.
4. The size ceiling for the shared filters (icp.md Open question 1).
5. Validation by Fin's sales team of the segment ranking and the top four signals.
