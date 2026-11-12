# Company: Intercom (now Fin)

Raw research, not conclusions. Public sources only.
Every fact carries a source tag like [C1]. The source table at the bottom gives the URL, the date checked and how it was read.
- **Fetched** = the page itself was read.
- **Search** = only a search engine summary was read, not the page. Treat these as weaker.
- **INFERRED** = my reading, not stated by a source.
- Quotes are exact but some were cut to 125 characters by the fetch tool. A cut quote ends with "...".

---

## 1. Headline change: Intercom is now Fin, and Fin is now owned by Salesforce

- **Renamed on 12 May 2026.** CEO post: "We're changing the name of our company to Fin. Intercom will live on as our customer service software platform, but Fin is our future." [C1]
- "All of our 1,400 employees are now employed by Fin." [C1]
- **Salesforce signed to acquire Fin on 15 June 2026:** "Salesforce will acquire Fin for approximately $3.6 billion, subject to customary purchase price adjustments." [C2]
- **The acquisition closed on 10 September 2026.** Salesforce "today announced it has completed its acquisition of Fin, formerly Intercom, an industry-leading customer agent company." [C3]
- **After the close:** "As part of Salesforce's AI Labs, Fin will continue to serve its customers, advance its AI agent capabilities, and build market-defining AI models and technology." [C3]
- **Other helpdesks after the close:** "Fin's fast-to-deploy AI agent works seamlessly with the help desks and systems companies already use across the entire customer experience." [C3] Neither Salesforce release says whether Fin stays a separate brand or keeps its own pricing. **Not found.**
- **Fit with Agentforce:** Fin's "packaged offerings and proprietary models will complement Agentforce's deeply customizable platform", with "fast time-to-value options especially well-suited for SMB and some commercial organizations." [C2]
- **Leadership after the deal**, from McCabe's X post as quoted by TechCrunch: "I'll still be CEO, Des will still be running R&D, we'll both still be committed to continuing to lead this category." [C4]
- **Naming today:** "Fin" is both the company and the AI agent. "Intercom" is the name of the helpdesk product. [C1] The blog post also says "we just launched a complete rebuild, Intercom 2". [C1]
- **Websites:** intercom.com/about redirects (308) to fin.ai/about. [C9] The intercom.com homepage still sells the helpdesk and links to fin.ai. [C5]

INFERRED: since 10 September 2026, any prospect talking to "Intercom" is buying from a Salesforce business unit. That changes how competitors pitch against it (see competitors.md and signals.md).

## 2. What they sell

### Products
| Product | What it is, in their words or the source's | Source |
|---|---|---|
| Fin AI Agent ("Customer Agent") | "Fin is the highest performing customer agent on the market" | [C6] |
| Fin for Service / Sales / Ecommerce / Success | Fin roles across the customer journey. Section heading: "Fin works across the entire customer journey" | [C6] |
| Fin for Sales | Launched April 2026. It engages "high intent visitors", collects qualification data, creates leads in Salesforce, HubSpot and Attio, and books meetings (Search) | [C15] |
| Fin Voice | Phone channel. "custom pricing plan", available to select customers who work with sales | [C7] |
| Apex models (Apex 2.0, Apex Flash 2.0, Apex for Procedures) | Fin's own AI models. Section heading: "Fin performs best because it runs on our proprietary AI Models" | [C6] |
| Procedures | Configured workflows that Fin runs, including handoffs to humans | [C7] |
| Fin Operator | Back-office tool for the teams that configure, monitor and improve Fin | [C4] [C10] |
| Intercom helpdesk (Intercom 2) | "a fully-featured AI-powered helpdesk": inbox, ticketing, proactive support, help center | [C5] [C1] |
| Copilot (Copilot 2) | AI assistant for human agents in the inbox | [C5] [C7] |
| Blueprint | "Fin comes with the Blueprint for AI transformation". Readiness guidance for customers | [C6] [C11] |

### Channels
- Salesforce lists "live chat, email, WhatsApp, SMS, voice, and Slack." [C3]
- "Fin speaks dozens of languages, and works 24 hours a day, every day." [C6]

### Helpdesks Fin runs on
- fin.ai/pricing lists: Intercom, Salesforce, HubSpot, Freshworks (Freshdesk), Dixa, Front, Zoho, Sprinklr, Gorgias, plus custom channels. [C7]
- The integrations page lists Intercom (native), Zendesk, Freshdesk, Salesforce Service Cloud, HubSpot Service Hub, and "Any helpdesk" over API. [C12]
- Zendesk claim: "Fin resolves Zendesk tickets and messaging conversations, keeping Zendesk as your system of record." [C12]
- "Deploy Fin on any helpdesk over API. No migration required." [C12]

## 3. Pricing model

Outcome-based for Fin, plus per-seat for the helpdesk. Checked on the live pages on 2026-11-12. [C7] [C8]

- **Fin AI Agent:** "From $0.99 per Fin outcome". "No seats required." [C8]
- **What counts as an outcome:** "You're only charged for one outcome per conversation, even if Fin takes multiple actions." [C7]
  - Resolution: "No further help is requested after Fin's last answer." [C7]
  - Procedure handoff: "Fin completes a Procedure you've configured to hand off to a human." [C7]
  - Prices: "Resolutions, Procedure handoffs, disqualifications, and self-serve routings are $0.99 each. Qualifications are $9.99 each." [C7]
  - "You're not charged when a conversation is simply passed to your team without an outcome." [C7]
- **Fin on another helpdesk:** "$0.99 per outcome" with a "50 outcomes per month minimum". [C7]
- **Intercom helpdesk seats** (from intercom.com/pricing): [C8]
  - Essential: shown as "$29$19 per seat/mo" with "New customers save 35%". The page doesn't label which figure is monthly and which is annual.
  - Advanced: "$85 per seat/mo", includes 20 free Lite seats.
  - Expert: "$132 per seat/mo", includes 50 free Lite seats.
  - The monthly versus annual split for each plan is **Not found** in the text that was read.
  - fin.ai shows "$19 per helpdesk seat per month" for Fin with the Intercom helpdesk. [C7]
  - Minimum: "1 Full seat minimum". [C8]
- **Copilot:** "$29 per agent/month billed annually, or $35 per agent/month billed monthly, for unlimited usage." [C8] fin.ai lists "$35 Per user per month". [C7]
- **Add-ons:** Pro "From $100/mo". Proactive Support Plus "$99/mo". Extra credits "$0.01 per credit". [C8]
- **Trial:** "14-day free trial", "No credit card required". [C8]
- **Startup program:** "Startups get 1 year of Fin free + 93% off Intercom". Eligibility: "Up to $10M in funding.", "Fewer than 15 employees.", "Not currently a Fin customer." [C13]
  - The linked pricing article's slug says "pre-june-29-2026", so the terms may have changed since. Current terms are **Not found**. [C13]
- **Contracts:** none needed for self-serve Essential and Advanced. Contracts are required for Enterprise. [C8]
- **Self-claim:** "Fin invented and championed outcome based pricing" [C6]

## 4. Scale: customers, revenue, usage

| Metric | Figure, exact wording | Source |
|---|---|---|
| Customers, all products | "30,000+ companies use our products." | [C9] |
| Customers, all products | "Trusted by 30,000+ leading brands" | [C5] |
| Fin customers | "Over 12,000 of the world's most forward looking brands use Fin" | [C6] |
| Fin resolution rate | "averaging 76% across 12,000+ customers, with many seeing over 85%" | [C6] |
| Fin volume | "Currently at 2 million weekly resolutions and growing fast" | [C6] |
| Company ARR | "has surpassed $400M in annual recurring revenue" | [C9] |
| Company ARR timing | Silicon Republic: it "surpassed $400m in annual recurring revenue in March" (2026) | [C14] |
| Fin ARR | Crossed $100M ARR, "growing at 3.5x" (SiliconANGLE, April 2026, Search) | [C15] |
| Growth | "is doubling growth year on year" | [C9] |
| Historical revenue | "US$200 million (2021)" | [C16] |
| Price paid by Salesforce | approximately $3.6 billion | [C2] |

- Two customer counts are in use: 30,000+ for all products and 12,000+ for Fin. INFERRED: the gap is roughly 18,000 helpdesk customers who aren't yet using Fin, an obvious upsell pool.
- Fin's revenue as a share of total company ARR: **Not found** in a primary source. Third-party estimates exist (Dealroom, Sacra) but were not verified.

## 5. Funding

From Wikipedia. Valuations for each round are **Not found**. [C16]

| Date | Round | Amount | Lead |
|---|---|---|---|
| 2012 | Angel / seed | Not stated | Biz Stone, then a seed round including David Sacks, 500 Global and others |
| March 2013 | Series A | $6M | Social Capital |
| January 2014 | Series B | $23M | Bessemer Venture Partners |
| ~2016 (the page is inconsistent) | Series C-1 / D | $50M | Index Ventures |
| 2018 | Series D | $125M | Kleiner Perkins, with GV participating |
| March 2026 | Venture debt | $250M | Hercules Capital |

- Silicon Republic ties the March 2026 debt raise to a plan for "650 new hires" that year. [C14]
- Total equity raised: **Not found** in a primary source. Search results give conflicting totals ($240.8M and $490.8M), so neither is used here.

## 6. Team size

- "now have more than 1,400 people across six global offices." [C9]
- "All of our 1,400 employees are now employed by Fin." (May 2026) [C1]
- "1,013 (2022)" [C16]
- Open roles: "See 114 open roles". The per-office counts add up to 120 (Berlin 6, Chicago 18, Dublin 40, London 30, San Francisco 23, Sydney 3). [C17]
- Headcount after the Salesforce close: **Not found**. SalesforceBen wrote that "It is currently unclear what will happen to Fin's ~1,400 employees." [C14b]

## 7. Leadership

Titles exactly as listed on fin.ai/about. [C9]

| Name | Title |
|---|---|
| Eoghan McCabe | "CEO and Chairman of the Board" |
| Des Traynor | "Chief Strategy Officer & Co-founder" |
| Archana Agrawal | "President" |
| Paul Adams | "Chief Product Officer" |
| Fergal Reid | "Chief AI Officer" |
| Darragh Curran | "Chief Technology Officer" |
| Ciaran Lee | "Chief Engineer & Co-founder" |
| Jordan Neill | "Chief Operating Officer" |
| Dan Griggs | "Chief Financial Officer" |
| Lauren Cullen | "SVP, People" |

- Board: Eoghan McCabe, Des Traynor, Cameron Deatsch, Talia Goldberg, Eileen Naughton, Abhijeet Dwivedi, Bobby Pinero. [C9]
- History: Karen Peacock became CEO on 1 July 2020, and McCabe was reappointed CEO in October 2022. [C16]
- Founders: Eoghan McCabe, Des Traynor, Ciaran Lee and David Barrett, in 2011. [C9] [C16]
- Whether fin.ai/about reflects any leadership change after the Salesforce close: **Not found**.

## 8. Markets and offices

- Offices: San Francisco (55 2nd Street, 4th Floor), London, Chicago, Dublin, Sydney and Berlin. [C9]
- HQ: San Francisco. [C16]
- Berlin R&D hub opened in October 2025. [C16]
- Revenue split by region: **Not found**.
- Billing is in USD only. [C7]
- Segment focus in Salesforce's words: "fast time-to-value options especially well-suited for SMB and some commercial organizations." [C2]
- Named customers run from startups to large companies such as Anthropic, Atlassian and Lightspeed (see customers.md). Revenue split by customer size: **Not found**.

## 9. Certifications and trust

- Listed on fin.ai: SOC2, ISO 27001, ISO 42001, AIUC-1, ISO 27701, HIPAA. [C6]
- "a 99.8% SLA" [C6]

## 10. Gaps

- What Salesforce ownership means for Intercom/Fin pricing, branding and the roadmap for other helpdesks after the close. Only the "AI Labs" line and the "works seamlessly with the help desks" line exist. [C3]
- The monthly versus annual seat price for each plan.
- Revenue by region and by customer size.
- Total equity raised and the last private valuation.
- Current startup program terms (after 29 June 2026).

---

## Sources

| ID | URL | Checked | How read |
|---|---|---|---|
| C1 | https://www.intercom.com/blog/today-intercom-becomes-fin | 2026-11-12 | Fetched |
| C2 | https://www.salesforce.com/news/press-releases/2026/06/15/salesforce-signs-definitive-agreement-to-acquire-fin/ | 2026-11-12 | Fetched |
| C3 | https://www.salesforce.com/news/press-releases/2026/09/10/salesforce-completes-acquisition-of-fin/ | 2026-11-12 | Fetched |
| C4 | https://techcrunch.com/2026/06/15/salesforce-acquires-ai-customer-service-platform-fin-for-3-6b/ | 2026-11-12 | Fetched |
| C5 | https://www.intercom.com/ | 2026-11-12 | Fetched |
| C6 | https://fin.ai/ | 2026-11-12 | Fetched |
| C7 | https://fin.ai/pricing | 2026-11-12 | Fetched |
| C8 | https://www.intercom.com/pricing | 2026-11-12 | Fetched |
| C9 | https://fin.ai/about | 2026-11-12 | Fetched |
| C10 | https://en.wikipedia.org/wiki/Fin_(company) (Products section) | 2026-11-12 | Fetched |
| C11 | https://fin.ai/blueprint | 2026-11-12 | Fetched (partly) |
| C12 | https://fin.ai/integrations | 2026-11-12 | Fetched |
| C13 | https://fin.ai/startups | 2026-11-12 | Fetched |
| C14 | https://www.siliconrepublic.com/business/salesforce-buys-fin-formerly-intercom-for-3-6bn | 2026-11-12 | Fetched |
| C14b | https://www.salesforceben.com/salesforce-acquires-fin-formerly-intercom-adding-30k-ai-customers/ | 2026-11-12 | Fetched |
| C15 | https://siliconangle.com/2026/04/24/intercoms-customer-service-agent-takes-new-sales-role/ | 2026-11-12 | Search |
| C16 | https://en.wikipedia.org/wiki/Fin_(company) (redirected from /Intercom,_Inc.; last edited 30 Oct 2026) | 2026-11-12 | Fetched |
| C17 | https://fin.ai/careers | 2026-11-12 | Fetched |
