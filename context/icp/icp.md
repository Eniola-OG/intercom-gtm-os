# ICP: Fin (formerly Intercom)

Built only from `context/docs/research/`. Each claim cites its file and source tag, for example `company.md C7`. INFERRED marks my reading of the research, not a stated fact. Anything the research doesn't support is under Open questions.

**Evidence caveat:** almost every customer data point comes from case studies Fin chose to publish (customers.md, header note). They show who has bought and succeeded, not the full customer base or the deals Fin lost.

## What we are selling into this ICP

| | |
|---|---|
| Lead product | **Fin AI Agent on the prospect's current helpdesk**: "$0.99 per outcome", "50 outcomes per month minimum", "No migration required" (company.md C7, C12) |
| Upsell | Intercom helpdesk seats from $19 per seat per month, plus Copilot for human agents (company.md C7, C8) |
| Why lead with Fin, not the helpdesk | Fin runs on Zendesk, Salesforce, HubSpot, Freshdesk and others "keeping Zendesk as your system of record" (company.md C12). Lightspeed kept Zendesk and Salesforce (customers.md K8). Vanta started Fin on its existing ticketing system and migrated later (customers.md K9). INFERRED: a no-migration first step is the shortest path to a yes |
| What we are really displacing | Not the helpdesk, but **the AI that comes with it**. See the Layer 2 table |
| Owner | Salesforce since 10 Sept 2026. Fin is positioned for "SMB and some commercial organizations" next to Agentforce (company.md C2, C3) |

## Layer 1: Firmographic

**The common thread (best-supported pattern):** a product-led or self-serve business with a very large end-user base, a small support team, and repeatable questions that come in through chat and email. That pattern runs through the stories more consistently than any one industry.

| Attribute | Fit | Evidence |
|---|---|---|
| Customer base shape (primary filter) | Millions of end users, or free-tier and self-serve users, served by a small team | Anthropic supports "free users at scale" (customers.md K10); Gamma "past 50 million users"; Magnific "100 million users"; Teachable "40 million students"; Rocket Money and Consensys "millions" of users (customers.md section 2) |
| Support team size | Small to mid-size human team. Published examples: "Three-person team" (WHOOP), "Team of 20 people" (Road), "12 support associates, several managers, and a head of support" (Birdie Care) | customers.md section 2, K11 |
| Industry (where the pattern shows up most) | AI products; B2B SaaS with self-serve signup; consumer fintech, trading and prediction markets | Anthropic, Glean, Synthesia, Gamma; Vanta, Clay, Personio, AppFolio; Rocket Money, Kalshi, Consensys, Topstep, Neo Financial (customers.md section 2) |
| Industry (secondary) | Digital health, education platforms, consumer subscription, marketplaces | Birdie Care, Circle Medical, Numan, Teachable, LSBU, Nuuly, WHOOP, MPB (customers.md section 2) |
| Company size: floor | More than 15 employees and more than $10M raised. Smaller companies go to the startup program | company.md C13 |
| Company size: ceiling | **Unknown.** Salesforce frames Fin for "SMB and some commercial organizations" (company.md C2), but no employee or revenue band is published. Fin's customers include large companies such as Lightspeed ("approximately 145,000 retail and restaurant locations", customers.md K8) | See Open question 1 |
| Region | US, UK and Ireland, EU (especially Germany), Australia | Fin offices (company.md C9). EU chatbot disclosure duty since 2 Aug 2026 (market.md M1) |
| Billing | Can pay in USD | "USD only" (company.md C7) |

## Layer 2: Technographic

Every target helpdesk already sells its own AI agent, so the pitch is "Fin beats the AI you already have". Each row names the incumbent AI and the proof we hold against it.

| Prospect's helpdesk | Incumbent AI we must beat | Proof we hold | Fit |
|---|---|---|---|
| **Zendesk** | Zendesk AI agents, "included in every Suite and Support plan", outcome-priced; Zendesk now owns Forethought (competitors.md P1, P6) | Birdie Care tried Zendesk and "Within a week, we pivoted back" (customers.md K11); Fathom: "> 60%reduction in response time, compared with Zendesk" (customers.md section 2); Lightspeed runs Fin on Zendesk (K8) | **Primary.** Largest installed base named in research: "Trusted by 32,000+ customers" (competitors.md P1) |
| **Freshdesk** | Freshdesk AI agents with "Free AI onboarding included" (competitors.md P9) | No named Fin customer on Freshdesk found | Secondary. No customer story found |
| **HubSpot Service Hub** | HubSpot Customer Agent at "$0.50" per resolution, "half the price of leading competitors" (competitors.md P10) | No named Fin customer on HubSpot found | **Hardest on price.** Pitch must be resolution rate, not cost. INFERRED |
| **Salesforce Service Cloud** | Agentforce, now a sister product under the same owner (company.md C2) | Lightspeed runs several Salesforce instances (K8) | Channel, not a competitive displacement. INFERRED: coordinate with Salesforce, don't cold-pitch against Agentforce |
| Front, Dixa, Zoho, Sprinklr, Gorgias | Not researched | None found | Supported (company.md C7). Low priority until there's evidence |
| A standalone AI vendor on top of any helpdesk (Decagon, Sierra, Ada) | The vendor itself | Vanta head-to-head: Fin about 73% vs the incumbent's about 49% on 400 conversations (customers.md K9) | Fit when results have stalled |

| Other attribute | Fit | Evidence |
|---|---|---|
| Channels | Live chat and email at volume; WhatsApp, SMS, Slack and voice are bonus | company.md C3. Vanta: email was the "highest-volume channel" (customers.md K9) |
| Knowledge base | A public help center exists | Vanta "700+ help center articles" (customers.md K9). Birdie doubled its help center (customers.md K11) |
| Systems Fin can act in | APIs and data connectors | Lightspeed used "Salesforce entitlements, internal APIs and custom logic" (customers.md K8) |

## Layer 3: Intent signals

Split by whether we can see the signal from outside today. The column shows what the research supports; the actual data source and tool get validated in Step 7.

**Observable now (lead with these)**

| # | Signal | Evidence (signals.md) | How it shows up publicly |
|---|---|---|---|
| 1 | Hiring support agents in bulk | "Every other company out there scales to 200+ in support." (Kalshi); "throwing bodies at the problem" (Lightspeed) | Job posts for support agent roles |
| 2 | New support or AI leader with an automation mandate | "Head of AI Support" (Anthropic), "AI & Solutions Manager" (MONY Group) | New job titles; job posts for AI support, AI ops, conversation analyst or knowledge manager roles (signals.md G9) |
| 3 | M&A that adds systems | Lightspeed (customers.md K8) | Acquisition news |
| 4 | Serves EU users with a chatbot on site | EU AI Act Article 50, in force 2 Aug 2026, fines "up to €15 million, or 3%" (market.md M1, M3) | EU presence plus a chat widget. INFERRED: a reason to review the bot, not a reason to switch on its own |

**Partly observable (need a proxy)**

| # | Signal | Evidence | Proxy (INFERRED) |
|---|---|---|---|
| 5 | Support volume spike or fast user growth | Underdog, Anthropic, Subsplash, Synthesia (signals.md row 1) | Funding rounds, user-growth announcements, event-driven businesses |
| 6 | Existing chatbot has stalled | Vanta (customers.md K9) | The vendor is visible through its widget; the stall isn't. Unverified (signals.md section 5) |
| 7 | Expanding into new regions or languages, or needing 24/7 cover | Topstep, Lightspeed (signals.md row 8) | Localised sites, international hiring |

**Not observable from outside (discovery questions, not targeting)**

| # | Signal | Evidence |
|---|---|---|
| 8 | Email is the biggest channel and has no automation | Vanta (signals.md row 12) |
| 9 | Regrets a recent helpdesk migration | Birdie Care (customers.md K11) |

## Layer 4: Persona

Full detail is in `personas.md`.

| Role | Typical titles from the research | Role in deal |
|---|---|---|
| Champion | Director of Customer Support, Head of Support, Head of CX, Head of Product Support | Owns the queue and the resolution rate. Runs the trial |
| Economic buyer | VP or Head of Operations, COO, Chief Digital Officer, General Manager Operations | Owns cost to serve and support headcount |
| Influencer | VP of Information Systems, RevOps lead, Head of AI Support, sales leader | Owns systems, integrations and the build-or-buy call |

## Layer 5: Engagement readiness

A company is ready to buy when most of these are true. They come from Fin's "five kinds of AI readiness" (signals.md G10) and the customer stories.

| Readiness | Ready looks like | Not ready yet looks like (Fin's words, signals.md G10) |
|---|---|---|
| Content | Help center articles kept current (customers.md K9, K11) | "Content is outdated, duplicated or contradictory" |
| Data | APIs exist for the account data Fin needs (customers.md K8) | "APIs are missing, unstable, or only partially implemented" |
| Execution | Permissions can be scoped to specific actions | "Permissions can't be limited to specific actions without granting full admin access" |
| Volume | Enough repeat questions to clear "50 outcomes per month minimum" (company.md C7). INFERRED: far above that in practice, since stories cite thousands per month | Not stated by Fin |
| Ownership | A named support leader to run setup and tuning. Lightspeed went from "20% resolution" to "over 70%" over time (customers.md K8) | INFERRED: no owner means the trial stalls |

INFERRED: companies that are not ready yet belong in a nurture track built on Fin's Blueprint content (company.md C11), not in direct outbound.

## Not a fit

| Who | Why | Evidence |
|---|---|---|
| Startups with fewer than 15 employees or up to $10M raised | Fin gives them "1 year of Fin free + 93% off Intercom", so they go to the self-serve startup program, not outbound | company.md C13 |
| Current Fin customers | Existing customers. INFERRED: Intercom helpdesk customers not yet on Fin are an expansion motion, not cold outbound | company.md section 4 |
| Salesforce Service Cloud accounts as cold targets | Same owner as Agentforce. INFERRED: work them through Salesforce, not through outbound against Agentforce | company.md C2 |
| Large enterprises wanting a deeply customised build | Salesforce positions Agentforce as the "deeply customizable platform" and Fin as fast time to value for SMB and commercial | company.md C2. INFERRED split |
| Companies whose volume is mainly voice in a contact centre | Fin Voice is a "custom pricing plan" for "select customers" | company.md C7. INFERRED weaker fit |
| Teams with no help content and no APIs | They fail Fin's own readiness checks | signals.md G10 |
| Companies that refuse a vendor tied to Salesforce or want to choose their own model | This is the main pitch of the "switch from Fin" vendors | competitors.md P17, P18. INFERRED: disqualify only if stated |
| Businesses with very low conversation volume | They can't clear the 50-outcome minimum on another helpdesk | company.md C7. INFERRED |

## Open questions (research does not answer)

1. **Company size ceiling.** No employee or revenue band for Fin's best customers is published (customers.md section 7). Next step: pull named customers into Clay, read their headcount, and set the band from real data.
2. Revenue split by region. Not found (company.md section 8).
3. Whether Salesforce changes Fin's pricing, brand or support for other helpdesks after the close (company.md section 10).
4. How well technographic tools detect Zendesk, HubSpot or Freshdesk widgets. Not verified (signals.md section 5).
5. How fast companies buy after a trigger. Not found (signals.md section 5).
6. Whether ecommerce brands on Shopify are a priority segment, given Fin for Ecommerce exists (company.md C6) but few ecommerce stories were found.
7. Whether Fin wins on HubSpot and Freshdesk at all. No customer story on either was found.
