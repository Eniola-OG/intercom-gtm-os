# Workflow Spec: Hiring support agents in bulk

**Status:** STRUCTURE-APPROVED 2026-11-12 · COPY-APPROVED 2026-11-12 · second review edits 2026-11-12

- Workflow W1 in `context/icp/signal-matrix.md` Matrix 3 (signal #1, scored 19/20). This run targets segment S2 (self-serve B2B SaaS).
- Built with `/build-workflow-spec` from `context/icp/icp.md`, `personas.md`, `signal-matrix.md`, `context/docs/gtm-system.md` and `context/docs/research/`.
- `context/messaging/facts.md` doesn't exist yet. `/campaign-copy` will create it, and any specific fact not in it is a `{{placeholder}}`.
- [ENGINE] sections are reused when this workflow is replicated. [ICP] sections change per segment.

---

## 1. Mother Intent (Trigger) [ENGINE]

**A self-serve B2B SaaS company that has posted 3 or more customer support agent roles in the last 30 days.**

- Catalog match (workflow-anatomy.md): Hiring specific roles, plus Hypergrowth (hiring velocity).
- Evidence: "When support volume gets that high, your only option is throwing bodies at the problem." (Lightspeed, customers.md K8)
- The 3+ threshold is a starting setting (signal-matrix.md #1), tuned in the weekly loop.

## 2. Inclusion / Exclusion [ICP]

**Include**

| Filter | Rule | Source |
|---|---|---|
| Segment | S2 self-serve B2B SaaS: B2B software with online signup or a free trial, and a public help center | signal-matrix.md Matrix 1 |
| Size floor | More than 15 employees and more than $10M total funding | icp.md Not a fit |
| Size ceiling | `{{size_ceiling}}`: not set. Every pass is logged so the weekly loop can set it | icp.md Open question 1 |
| Region | HQ or a major office in the US, UK, Ireland, EU or Australia | icp.md Layer 1 |
| Trigger | 3+ open roles matching the support-agent title regex (signal 1), posted in the last 30 days, at the same company domain | Section 4 |
| Recipient | **Champion first:** Director, Head or VP of Customer Support; Head of CX; Head of Customer Operations. **If there's no champion:** economic buyer (Director or VP of Operations, COO). **If neither:** hold and re-run in 30 days | personas.md; gtm-system.md step 6 |

**Exclude**

| Who | Why | How it's read |
|---|---|---|
| Intercom widget on the site | Probably already a customer, so this is expansion, not outbound | BuiltWith technology list contains "Intercom" |
| Salesforce Service Cloud users | Same owner as Agentforce; they go to the channel list | Technology list contains "Salesforce Service Cloud" or "Salesforce Live Agent" |
| Startup-program companies | 15 or fewer employees, or $10M or less raised | Employee count and total funding fields |
| Staffing, outsourcing and support agencies | They post support roles for their clients (INFERRED risk) | Industry is "Staffing and Recruiting" or "Outsourcing", or the description matches `outsourc|BPO|staffing|contact cent(er|re) services` |
| Competitors and the owner | Zendesk, HubSpot, Freshworks, Decagon, Sierra, Ada, Kustomer, Gorgias, Forethought, Salesforce, Fin | Domain blocklist |
| Segments S1, S3, S4, S5 | Covered by later runs of this workflow | Segment classification is not S2 |
| Contacted in the last 90 days, open CRM opportunity, unsubscribed | Suppression rules | gtm-system.md steps 2 and 9 |

## 3. Sources [ENGINE]

| What | Source | Tool / action |
|---|---|---|
| Trigger: open support roles | LinkedIn Jobs, Indeed, company career pages | Clay "Find Jobs at Company"; Apify LinkedIn Jobs scraper for gaps |
| Firmographics: employees, HQ country, industry, description | Company enrichment | Clay company enrichment (waterfall) |
| Total funding, last round and date | Crunchbase | Crunchbase via Clay |
| Helpdesk widget, AI-agent widget, Intercom and Salesforce exclusion | BuiltWith | BuiltWith via Clay "Find Technology Stack" |
| 6-month headcount growth | Headcount snapshots | Clay "Company Headcount" |
| Segment classification (S1 to S5, or none) | Company description and website | Clay Use AI column with a fixed list of allowed outputs (`/prompt-builder`) |
| Contacts | People profiles | Clay "Find People at Company" |
| Emails | Email providers | Clay email waterfall plus a verifier |

## 4. Signals table [ENGINE]

| # | Signal | Role | How it's read | Output |
|---|---|---|---|---|
| 1 | Open support agent roles | **trigger** | Count of job posts at the company domain, posted in the last 30 days, where the title matches `(customer\|technical)?\s*support (agent\|specialist\|representative\|associate\|advocate\|engineer)\|customer (experience\|care) (associate\|agent\|specialist)\|help ?desk`. Fires at 3 or more | `open_support_roles` (count) |
| 1a | Hiring scale (cluster of #1) | context-clause | **3-4** = "adding to the team"; **5-9** = "growing the team fast"; **10+** = "a large hiring push". The raw count never goes to copy | `hiring_scale` (one of the three labels) |
| 1b | Example role title | context-clause | Title of the most recent matching post, cleaned (seniority and location suffix removed) | `example_role_title` (text) |
| 2 | Helpdesk detected | **router** | BuiltWith list contains "Zendesk" leads to `zendesk`. Contains "HubSpot Conversations" or "HubSpot Messages" leads to `hubspot`. Anything else leads to `none_detected` (this includes Freshdesk until its detection is verified) | `helpdesk_route` (zendesk / hubspot / none_detected) |
| 3 | AI agent already on site | **router** | BuiltWith list contains "Decagon" leads to true. Ada and Sierra are unverified, so they're not read | `ai_agent_present` (true / false) |
| 4 | Recent funding | context-clause | Last round's announced date is within 12 months, AND the round is Series A or later | `recent_round` (round name, or empty) |
| 5 | Headcount growth | context-clause | 6-month headcount growth of 25% or more leads to true; otherwise false | `fast_growth` (true / false) |

1 trigger, 2 routers, 4 context-clauses. Funding and growth never route.

## 5. Routing matrix with angles [ENGINE]

- Axis 1, helpdesk route: 3 values (zendesk, hubspot, none_detected).
- Axis 2, AI agent present: 2 values (true, false).
- Stacked: **3 × 2 = 6 cells.**

**Branch coverage:** every cell has `open_support_roles`, `hiring_scale` and `example_role_title`. Only C1 to C4 can name a helpdesk. Only C2, C4 and C6 can mention an existing AI agent. `recent_round` and `fast_growth` may be empty in any cell, so no angle depends on them.

| Cell | Deterministic read | What it tells us (inferred situation) | The angle it earns |
|---|---|---|---|
| **C1** | helpdesk_route = zendesk, ai_agent_present = false | They run Zendesk, show no separate AI agent, and are adding 3+ support agents. Zendesk includes its own AI agents in every Suite and Support plan (competitors.md P1), so they use Zendesk's AI or none. Either way, they're meeting volume with headcount | **Put Fin in front of Zendesk instead of the next hires, and keep Zendesk.** Fin resolves Zendesk tickets "keeping Zendesk as your system of record" (company.md C12). Proof: Lightspeed runs Fin on Zendesk, "72%Fin resolution rate" (customers.md K8). Supporting: Birdie Care tried a move to Zendesk and "pivoted back" (K11) |
| **C2** | helpdesk_route = zendesk, ai_agent_present = true | They run Zendesk plus a standalone AI agent, and are still adding 3+ human agents. The automation they bought is in place, and they're still hiring for volume | **Test Fin against the AI agent you already have, on your own conversations.** Vanta's head-to-head on 400 real conversations: Fin about 73% vs the incumbent's about 49% (customers.md K9). Plus the Zendesk no-migration line |
| **C3** | helpdesk_route = hubspot, ai_agent_present = false | They run HubSpot Service Hub, show no separate AI agent, and are adding 3+ support agents. HubSpot sells its own Customer Agent at "$0.50" per resolution (competitors.md P10), so price is the comparison they'll make | **Resolution rate, not price per resolution.** Fin's published average is 76% across 12,000+ customers (company.md C6); HubSpot's published average is "70%" (competitors.md P10). Both are vendor claims. Fin keeps HubSpot "as your system of record" (company.md C12). Weakness: no Fin customer story on HubSpot (icp.md Open question 7) |
| **C4** | helpdesk_route = hubspot, ai_agent_present = true | They run HubSpot plus a standalone AI agent, and are still hiring 3+ agents. Same situation as C2 on a different helpdesk. INFERRED: likely the smallest cell | **Test Fin against your current AI agent, and keep HubSpot.** Vanta head-to-head proof (K9) with the HubSpot system-of-record line (C12). No price comparison, because the incumbent is the AI vendor |
| **C5** | helpdesk_route = none_detected, ai_agent_present = false | They're adding 3+ support agents, and no helpdesk or AI widget is visible. Support may run through email, a form, Freshdesk or another tool, so the angle can't name one | **Fin works on whatever you run today, with no migration.** "Deploy Fin on any helpdesk over API. No migration required." (company.md C12). Proof: Vanta started Fin on its existing ticketing system first (customers.md K9) |
| **C6** | helpdesk_route = none_detected, ai_agent_present = true | They have a standalone AI agent, no detected helpdesk, and are still adding 3+ agents. Same situation as C2 and C4 without a known helpdesk | **Test Fin against your current AI agent, on your own conversations.** Vanta head-to-head proof (K9). No helpdesk named |

**Recipient note:** when the economic buyer gets the sequence instead of the champion (section 2), they get the same cell angle. The cost framing comes from the personas.md economic buyer column ("Measured on" cost to serve and headcount). It isn't a new routing axis.

## 6. Variables contract [ENGINE]

| Variable | Source field | Exists in branches |
|---|---|---|
| `{{first_name}}` | Clay Find People: first name | All |
| `{{company_name}}` | Clay company enrichment: name, cleaned (legal suffix removed) | All |
| `{{example_role_title}}` | Signal 1b | All |
| `{{hiring_scale}}` | Signal 1a (one of the three labels) | All |
| `{{helpdesk_name}}` | Formula from `helpdesk_route`: zendesk leads to "Zendesk", hubspot leads to "HubSpot" | C1, C2, C3, C4 only |
| `{{ai_agent_vendor}}` | Formula: "Decagon" when `ai_agent_present` = true | C2, C4, C6 only |
| `{{recent_round}}` | Signal 4 (may be empty) | Any cell, optional. Copy must read fine without it |
| `{{fast_growth}}` | Signal 5 (true or false) | Any cell, optional. Copy uses it only as a condition, never as printed text |
| `{{recipient_persona}}` | Set at step 6: champion or economic_buyer | All |
| `{{route_id}}` | Formula: C1 to C6 from signals 2 and 3 | All (picks the template; never printed) |
| `{{proof_point}}` | Per cell, from `context/messaging/facts.md` | All. **Placeholder until facts.md exists** |
| `{{sender_name}}`, `{{sender_title}}` | Sequencer sender settings | All. **Placeholder until a sender is set up** |

Nothing outside this table may appear in copy.

## 7. Cadence and channel [ENGINE]

| | |
|---|---|
| Periodicity | **Always-on.** The Clay jobs table refreshes weekly (workflow-anatomy.md: job postings are high velocity, so weekly) |
| Signal window | Posts from the last 30 days only. Older ones drop, since the timing hook is gone |
| Channel | **Both.** 3 emails plus 2 LinkedIn touches (gtm-system.md step 8): Email 1 on day 1, LinkedIn connection on day 2, Email 2 on day 4, LinkedIn DM on day 7 only if accepted, Email 3 on day 10. Days are starting settings |
| Email-less contacts | LinkedIn-only track (gtm-system.md step 7) |
| Stop rule | Any reply on any channel stops all touches and goes to reply handling (gtm-system.md step 9) |
| Suppression and re-entry | 90 days after the last touch. Re-entry only on a new trigger (gtm-system.md step 2) |
| Tools | Clay (not set up yet), Instantly and HeyReach (proposed), Salesforce CRM (proposed). Run `/campaign-qa` before launch |

---

## Definition of done

- [x] Mother intent: one sentence, signal-led, matched to the catalog
- [x] Inclusion: ICP box, trigger definition and recipient, tagged [ICP]
- [x] Exclusion: who's out and why
- [x] Sources: trigger and every enrichment
- [x] Signals table: every read deterministic, every role declared
- [x] Count clusters declared (signal 1a; the count is a context-clause, not a router)
- [x] Routing matrix with every angle filled (6 cells)
- [x] Branch coverage checked
- [x] Variables contract: every variable mapped to its source field
- [x] Engine/ICP markers on every section
- [x] Cadence and channel declared

**Next:** `/campaign-copy` on this file. It creates `context/messaging/facts.md` first.

---

## Copy

Facts source: `context/messaging/facts.md` (approved 2026-11-12). Variables: only those in section 6. Register: signal play.

**Subject (static, kept for the whole thread):** `{support hiring question|before the next support hire|a support team question}`

### Email 1 (day 1, new thread). Approved 2026-11-12

```
{{first_name}},

{{company_name}} is hiring for several support roles right now, including a {{example_role_title}}.

{My guess is|Could be off, but my guess is} support volume is growing {faster than the team|ahead of the team}, and hiring is how you're keeping pace.

{{e1l3}}

{{social_proof}}

{Worth testing Fin on a sample of your own conversations before the next hire?|Would a test on a sample of your own conversations help before the next hire?}

{{sender_name}}
{{sender_title}}
```

**`{{e1l3}}` (value prop).** Routes are exhaustive, so there's no fallback.
- + helpdesk_route = zendesk AND ai_agent_present = false (C1): no line. The proof line carries it.
- + helpdesk_route = zendesk AND ai_agent_present = true (C2): Fin is an AI agent that resolves support conversations on top of Zendesk, keeping Zendesk as your system of record.
- + helpdesk_route = hubspot (C3, C4): Fin is an AI agent that resolves support conversations on top of HubSpot, keeping HubSpot as your system of record.
- + helpdesk_route = none_detected (C5, C6): Fin is an AI agent that resolves support conversations on the helpdesk you already run, with no migration.

**`{{social_proof}}`.** Routes are exhaustive, so there's no fallback.
- + ai_agent_present = true (C2, C4, C6): You already have an AI agent on your site, so the closest comparison is Vanta: on 400 real conversations, Fin resolved about 73%, its existing agent about 49%.
- + helpdesk_route = zendesk AND ai_agent_present = false (C1): Lightspeed runs Fin, an AI agent, on Zendesk, and 72% of the conversations Fin handles are resolved without a person.
- + helpdesk_route = hubspot AND ai_agent_present = false (C3): Fin's published average resolution rate is 76% across 12,000+ customers.
- + helpdesk_route = none_detected AND ai_agent_present = false (C5): Vanta started Fin on the ticketing system it already had, before changing anything else.

Word counts: C1 66, C2 93, C3 75, C4 93, C5 78, C6 92.

**Sample (C1), as received:**

> **Subject:** before the next support hire
>
> Sam,
>
> Acme is hiring for several support roles right now, including a Customer Support Specialist.
>
> My guess is support volume is growing faster than the team, and hiring is how you're keeping pace.
>
> Lightspeed runs Fin, an AI agent, on Zendesk, and 72% of the conversations Fin handles are resolved without a person.
>
> Worth testing Fin on a sample of your own conversations before the next hire?
>
> Gbadamosi Eniola
> GTM

("Sam" and "Acme" are made-up names to show the rendering.)

### Email 2 (day 4, same thread, subject "Re:"). Approved 2026-11-12

Static for every cell. Spintax on the opener and CTA only.

```
{{first_name}},

{One more thought|Another thought} on the support hiring at {{company_name}}, this time on cost.

Fin is priced at $0.99 per outcome, and you're not charged when a conversation is simply passed to your team.

Synthesia handled more than 275k additional monthly queries with the same headcount.

{Would it help to see what that looks like against your own volume?|Useful to see that against your own volume?}

{{sender_name}}
{{sender_title}}
```

Word count: 61. New value vs Email 1: cost and headcount (Email 1 was about resolution).

### Email 3 (day 10, same thread, subject "Re:"). Approved 2026-11-12

Static for every cell. A final touch with a referral CTA.

```
{{first_name}},

{Last note from me on this.|I'll leave it here after this one.}

Fin works 24 hours a day, every day, so the people you're hiring can spend their time on the conversations that need a person.

{If someone else at {{company_name}} owns support tooling, who should I talk to?|Is someone else at {{company_name}} the right person for support tooling?}

{{sender_name}}
{{sender_title}}
```

Word count: 41. New value vs Emails 1 and 2: around-the-clock coverage, plus the referral ask.

### LinkedIn. Approved 2026-11-12

**Connection request (day 2):** empty, no note.

**DM 1 (if accepted, about day 7).** Routes are exhaustive, so there's no fallback.
- + ai_agent_present = true (C2, C4, C6): {{first_name}}, with the support roles you're hiring for, is the plan to grow your AI agent's share of conversations too, or mostly the team?
- + ai_agent_present = false (C1, C3, C5): {{first_name}}, with the support roles you're hiring for, is AI part of the support plan, or is it mostly team growth for now?

**DM 2 (3 to 5 days after DM 1, if there's no reply).** Static. It uses Personio, so no lead sees the same proof by email and LinkedIn.

```
{Asking because|Reason I ask:} Personio has Fin resolving 30k support conversations a month. {Happy to show what that could look like at your volume if useful.|Can share what that might look like at your volume if that helps.}
```

### Persona review and human test. Done 2026-11-12

Reviewed as a Director of Customer Support at a self-serve SaaS company that is hiring 3+ support roles. One change: the Email 1 proof line for C2, C4 and C6 was reworded for clarity ("Fin resolved about 73%, the existing agent about 49%"). Facts unchanged. Before launch: a final manual read against `knowledge-base/playbooks/copy-iron-laws.md`, then `/campaign-qa`.

### Second persona review and human test. Done 2026-11-12

Six fixes, all wording only. Facts and routes are unchanged.
1. Email 1 opener: dropped the repeated "role" ("is hiring for several support roles right now, including a {{example_role_title}}").
2. Email 1 C1 proof: "Fin conversations" became "the conversations Fin handles".
3. Email 1 C2, C4, C6 proof: now says why Vanta's test matters ("You already have an AI agent on your site, so the closest comparison is Vanta"). This uses the `ai_agent_present` read that defines these cells.
4. Email 1 C3 proof: added "resolution rate" so the 76% is clear.
5. Email 2 opener: "One more thought on the support hiring at {{company_name}}, this time on cost."
6. DM 1, AI-agent cells: "the AI agent's share" became "your AI agent's share".
