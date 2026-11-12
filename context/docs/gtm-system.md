# GTM System: Fin (formerly Intercom) outbound

The end-to-end outbound system, from signal to CRM and back into the Context OS.
- Built from `context/icp/icp.md`, `personas.md` and `signal-matrix.md`. Citations look like `signal-matrix.md #1`.
- **Tool status:** "Live" means it is in the repo and usable. "Proposed" means it hasn't been chosen or set up yet (CLAUDE.md Tools lists only Clay, rex, crawl4ai and agent-browser, and Clay isn't set up yet).
- **Settings marked "start at"** are starting values to tune in the weekly loop. They are not research facts.
- **Visual version:** [intercom GTM System on Miro](https://miro.com/app/board/uXjVEO-4bOI=/), drawn from this file with `/miro-gtm-flowchart`. Source spec: `diagrams/gtm-system.json`.

## Flow at a glance

```
 0 Context OS (GitHub repo, Claude Code)
   │
 1 Buying signals ── Clay Find Jobs / Find People / Crunchbase / Headcount
   │
 2 Find companies ── signal rows → company domain, dedupe, suppression check
   │
 3 Enrich ── Clay: firmographics, BuiltWith helpdesk + AI widget, funding, headcount
   │
 4 ICP fit check ──fail──▶ drop (reason logged)
   │ pass            └─unknown──▶ hold, recheck in 30 days
 5 Route by segment ── S1/S2/S3 × helpdesk route × AI-widget route
   │
 6 Find people ── champion → economic buyer → influencer
   │
 7 Find + verify email ──invalid──▶ LinkedIn-only track
   │ valid
 8 Sequence ── 3 emails (Instantly) + 2 LinkedIn touches (HeyReach)
   │
 9 Reply handling ── classify → meeting / objection / nurture / suppress
   │
10 CRM ── Salesforce: account, contact, opportunity, signal source
   │
11 Weekly feedback loop ──▶ back to 0 (learnings, matrix scores, ICP)
```

---

## Step 0: Context OS

| | |
|---|---|
| **What happens** | Every run starts from the repo. Claude Code reads `CLAUDE.md`, then `context/icp/` (who to target and why), `context/docs/research/` (facts and proof), and this week's `weekly-priorities` file |
| **Tool** | GitHub repo plus Claude Code (Live). Skills: `/build-workflow-spec`, `/campaign-copy`, `/campaign-contract`, `/design-clay-table-json`, `/import-clay-table` (Live) |
| **Output** | One approved workflow spec per signal in `output/campaigns/<slug>/workflow-spec.md`, with status STRUCTURE-APPROVED, before anything is built in Clay |

| Decision | Answer leads to |
|---|---|
| Does a STRUCTURE-APPROVED spec exist for this workflow? | **Yes:** build it in Clay (step 1). **No:** run `/build-workflow-spec` first. Nothing is built without a spec |
| Does the claim we want to use in copy have a source in `context/docs/research/`? | **Yes:** allowed in copy. **No:** cut it, or add it to research with a source first |

## Step 1: Buying signals

| | |
|---|---|
| **What happens** | Always-on searches detect the four priority signals. Each signal is one Clay table that refreshes on a schedule |
| **Tool** | Clay (Proposed: account not set up). Actions from signal-matrix.md Matrix 2 |

| Workflow | Signal | Clay action | Refresh (workflow-anatomy.md periodicity) |
|---|---|---|---|
| W1 | Hiring support agents in bulk (signal-matrix.md #1) | Find Jobs at Company; Apify for boards Clay misses | Weekly |
| W2 | Hiring AI-support or CX-automation roles (#2) | Find Jobs at Company | Weekly |
| W3 | New support leader in the last 90 days (#3) | Find People at Company, by title and start date | Monthly |
| W4 | Hiring multilingual or new-region support (#4) | Find Jobs at Company, language or location keywords | Weekly |

| Decision | Answer leads to |
|---|---|
| Does the job or person match the title keywords in signal-matrix.md? | **Yes:** new row moves to step 2. **No:** discarded by a Clay filter |
| W1 only: does the company have at least the starting threshold of open support roles (start at 3, signal-matrix.md #1)? | **Yes:** continue. **No:** stay in the table and re-check next week, since the count may rise |
| Is the signal older than its window (30 days for jobs, 90 days for leaders)? | **Yes:** drop, because the timing hook is gone. **No:** continue |

## Step 2: Find companies

| | |
|---|---|
| **What happens** | Turn signal rows into one row per company: take the domain, dedupe across W1 to W4, check suppression lists |
| **Tool** | Clay (Proposed): formulas and lookups across tables |

| Decision | Answer leads to |
|---|---|
| Is the domain already in another active workflow? | **Yes:** merge. Keep the strongest signal as the mother intent (W2 > W1 > W3 > W4, from the signal-matrix.md scores) and the others as supporting lines. **No:** new company row |
| Was it contacted in the last 90 days (start at 90, workflow-anatomy.md "Suppress for X days")? | **Yes:** suppress, unless the signal is new since the last touch. Then re-enter (workflow-anatomy.md "Allow re-entry if new signal detected"). **No:** continue |
| Is it on the do-not-contact list (current Fin customers, unsubscribes, open opportunities in the CRM)? | **Yes:** drop. **No:** step 3 |

## Step 3: Enrichment

| | |
|---|---|
| **What happens** | Add the data the ICP check and routing need. Run cheap fields first and expensive ones only on rows that survive ("Filter before enriching", clay/actions-data-credits.md) |
| **Tool** | Clay (Proposed): company enrichment, BuiltWith via Clay, Crunchbase via Clay, Company Headcount |

| Order | Field | Why | Source |
|---|---|---|---|
| 1 | Employee count, HQ country, industry, description | ICP firmographics | icp.md Layer 1 |
| 2 | Total funding raised | Startup-program cut-off "Up to $10M in funding" | icp.md Not a fit |
| 3 | Helpdesk widget: Zendesk, HubSpot, Freshdesk or Intercom | Routing, plus the existing-customer check | signal-matrix.md #7 |
| 4 | AI-agent widget: Decagon (Ada and Sierra unverified) | Displacement route | signal-matrix.md #8 |
| 5 | Last funding round and date | Supporting line | signal-matrix.md #5 |
| 6 | 6-month headcount growth | Supporting line | signal-matrix.md #6 |

| Decision | Answer leads to |
|---|---|
| Did fields 1 and 2 come back empty? | **Yes:** try a second provider (Clay waterfall). Still empty: mark "unknown" and go to step 4's unknown path. **No:** continue |
| Is an Intercom widget detected? | **Yes:** drop. They're likely already a customer, which is expansion, not outbound (icp.md Not a fit). **No:** run fields 4 to 6 |

## Step 4: ICP fit check

| | |
|---|---|
| **What happens** | A pass or fail check against icp.md, so no one is contacted on a guess |
| **Tool** | Clay (Proposed): formula columns, plus a Use AI column only for the segment classification (built with `/prompt-builder`) |

| Check | Pass | Fail leads to |
|---|---|---|
| Employees more than 15 and funding more than $10M | Continue | Drop with reason "startup program" (icp.md Not a fit) |
| Size ceiling | Not set yet (icp.md Open question 1). Log every pass so the weekly loop can set it from real data | n/a |
| HQ or major office in the US, UK, Ireland, EU or Australia | Continue | Drop with reason "region" |
| Segment classified as S1 to S5 (signal-matrix.md Matrix 1) | Continue | "None" leads to a drop with reason "segment" |
| Helpdesk is Salesforce Service Cloud | n/a | Leave the cold flow. Hand off to the Salesforce channel list (icp.md Not a fit) |

| Decision | Answer leads to |
|---|---|
| All checks pass? | **Yes:** step 5. **No:** drop, and write the fail reason to a column (counted in the weekly loop). **Unknown on any check:** hold and re-enrich in 30 days (start at 30). Never send to an unknown |
| Segment is S4 or S5 (lower priority)? | **Yes:** hold, until the S1 to S3 results justify opening them (signal-matrix.md assessment). **No:** step 5 |

## Step 5: Route by segment

| | |
|---|---|
| **What happens** | Each company gets three labels, and together they pick the copy template |
| **Tool** | Clay (Proposed): formula columns that output a route ID |

| Label | Values | Leads to |
|---|---|---|
| Segment | S1 AI-native / S2 Self-serve SaaS / S3 Consumer fintech | Angle and proof from signal-matrix.md Matrix 1. For example, S1 uses Anthropic and S2 uses Vanta |
| Helpdesk route | Zendesk / HubSpot / Freshdesk / Unknown | **Zendesk:** "keep Zendesk as your system of record", with Birdie Care and Fathom proof. **HubSpot:** lead on resolution rate, never on price, since HubSpot is $0.50 (icp.md Layer 2). **Freshdesk:** no-migration line, no proof story. **Unknown:** generic no-migration line |
| AI-widget route | Decagon or another agent detected / none | **Detected:** "beat the bot you already have" angle, with Vanta's 73% vs 49%. **None:** default angle for the segment |

| Decision | Answer leads to |
|---|---|
| Does a template exist for this route ID? | **Yes:** step 6. **No:** use the segment fallback template (workflow-anatomy.md "Create fallback for prospects without secondary signals") |

## Step 6: Find people

| | |
|---|---|
| **What happens** | Find up to three contacts per company in persona order |
| **Tool** | Clay (Proposed): Find People at Company. Titles from personas.md |

| Order | Persona | Titles to search (personas.md) |
|---|---|---|
| 1 | Champion | Director, Head or VP of Customer Support; Head of CX; Head of Product Support; Head of Customer Operations |
| 2 | Economic buyer | Director or VP of Operations, COO, Chief Digital Officer |
| 3 | Influencer | VP of Information Systems, RevOps lead, Head of AI Support |

| Decision | Answer leads to |
|---|---|
| Is a champion found? | **Yes:** the champion gets the main sequence. The economic buyer, if found, gets a shorter cost-angle sequence starting 7 days later (start at 7). **No:** go to the next persona |
| No champion, but an economic buyer is found? | **Yes:** the economic buyer gets the main sequence with the cost angle (signal-matrix.md Matrix 1, economic buyer column). **No:** influencer |
| Nobody found at all? | Hold the company. Re-run in 30 days, because W1 often means the support team is being hired right now |
| W3 row (new leader)? | The leader from the signal is the contact. Skip the search |

## Step 7: Find and verify emails

| | |
|---|---|
| **What happens** | Waterfall email finding across providers in Clay, then verification. Only verified addresses go to the sender |
| **Tool** | Clay email waterfall plus a verifier inside Clay (Proposed: providers picked at build) |

| Decision | Answer leads to |
|---|---|
| Is the email found and verified as valid? | **Valid:** email sequence, plus LinkedIn |
| Catch-all domain? | Send only if the contact is a champion, and cap it at a small share of each send (start at 10%, to protect deliverability). Otherwise LinkedIn-only track |
| Invalid or not found? | LinkedIn-only track |
| No LinkedIn URL either? | Drop the contact and try the next persona at the same company (back to step 6) |
| Contact is in the EU or UK? | INFERRED compliance check, not legal advice: confirm a lawful basis before sending (the framework flags "GDPR constraints on enrichment"). Unsure leads to LinkedIn-only |

## Step 8: Sequence (email and LinkedIn)

| | |
|---|---|
| **What happens** | One sequence per route, written with `/campaign-copy` on the approved spec, using only facts from `context/messaging/facts.md`. Shape from the build brief: 3 emails and 2 LinkedIn touches |
| **Tool** | Email: Instantly (Proposed; supported by `/campaign-qa`). LinkedIn: HeyReach (Proposed). QA: `/campaign-qa`. Deliverability test: `/inbox-placement-test` (Live skills) |

| Day (start at) | Channel | Touch | Content |
|---|---|---|---|
| 1 | Email 1 | Signal plus segment angle | The signal line, for example "hiring 4 support agents", plus one proof point for the segment |
| 2 | LinkedIn | Connection request, no pitch | none |
| 4 | Email 2 | Helpdesk route | The Zendesk, HubSpot or Freshdesk line, or the AI-widget line |
| 7 | LinkedIn DM | Only if the connection was accepted | Short proof point |
| 10 | Email 3 | Soft close | Persona objection pre-empted (personas.md) |

| Decision | Answer leads to |
|---|---|
| Has the campaign passed `/campaign-qa`? | **Yes:** launch. **No:** fix and re-run. Never launch unchecked |
| Is inbox placement healthy? | **Yes:** keep sending. **No:** pause the sender pool and run `/inbox-placement-test` (KILL, MARGINAL or KEEP for each pool) |
| Did the prospect reply on any channel? | **Yes:** stop all touches and go to step 9. **No:** next touch |
| Did the LinkedIn connection get accepted? | **Yes:** send the day-7 DM. **No:** skip the DM, email continues |

## Step 9: Reply handling

| | |
|---|---|
| **What happens** | Every reply gets one label within one business day (start at one business day) |
| **Tool** | Instantly Unibox and the HeyReach inbox (Proposed). Labels by a person at first. Later, possibly a Claude prompt built with `/prompt-builder` |

| Reply type | Leads to |
|---|---|
| **Positive or meeting request** | Book a meeting. Create the opportunity in the CRM with the signal and route ID |
| **Objection** | Answer from the objection list in personas.md (Salesforce ownership, price vs HubSpot, build vs buy, content not ready). Then back to waiting for a reply |
| **"Not now" or not ready** (for example "our content isn't ready", signals.md G10) | Nurture track using Fin Blueprint content (icp.md Layer 5). Re-enter outbound only on a new signal |
| **Wrong person, with a referral** | Add the referred contact and start at step 7 |
| **Wrong person, no referral** | Try the next persona (step 6) |
| **Already a Fin or Intercom customer** | Add to suppression. Pass to the account team. Fix the Intercom-widget check if it missed them |
| **Unsubscribe or hostile** | Suppress permanently across all channels |
| **Out of office** | Pause and resume after the return date |
| **No reply after the last touch** | Close the contact. The company can re-enter only on a new signal after the 90-day suppression |

## Step 10: CRM

| | |
|---|---|
| **What happens** | Every contacted company and every reply is written to the CRM with where it came from, so results can be traced to a signal |
| **Tool** | Salesforce Sales Cloud (Proposed. INFERRED fit, since Fin is part of Salesforce, company.md C3). Synced from Clay and the sender |

| Field written | Example values |
|---|---|
| Signal source | W1, W2, W3 or W4 |
| Route ID | Segment, helpdesk route, AI-widget route |
| Persona | Champion, economic buyer or influencer |
| Status | Contacted, replied (with label), meeting, opportunity, closed won or lost, nurture |
| ICP fail reason (dropped rows, kept in Clay) | Startup program, region, segment, unknown |

| Decision | Answer leads to |
|---|---|
| Does the account already exist in the CRM? | **Yes:** attach the activity to it, and check the owner before sending (back to the step 2 do-not-contact check). **No:** create it |
| Is the opportunity closed lost? | Log the reason. Suppress for 90 days, then allow re-entry on a new signal |

## Step 11: Weekly feedback loop back into the Context OS

| | |
|---|---|
| **What happens** | Every week, results move from the CRM and sender back into the repo, and the matrix and ICP are updated |
| **Tool** | Claude Code plus the repo (Live). Exports from Instantly and Salesforce (Proposed). Clay costs via `/calculate-costs` (Live skill) |

| Weekly check | Decision | Leads to (file updated) |
|---|---|---|
| Reply and meeting rate per signal (W1 to W4) | A workflow is clearly below the others after enough sends (start at 200 sends before judging) | Rewrite the angle first. If it's still low after the next round, cut it. Update the scores in `signal-matrix.md` and the Matrix 3 status |
| Results per route (segment by helpdesk route) | One route underperforms | Change that route's template only. Log it in Matrix 3 Changelog |
| ICP fail reasons | One reason dominates, for example "unknown" | Fix the enrichment (step 3) or the filter (step 4) |
| Headcount of companies that passed and booked meetings | A clear size band shows up | Set the size ceiling and close icp.md Open question 1 |
| Objections heard | A new objection appears twice or more | Add it to `personas.md` with the best answer so far |
| Wins and losses | A pattern emerges | Write it to `knowledge-base/learnings/` |
| Clay spend per workflow | Cost per meeting is too high for a workflow | Reorder enrichments or drop the expensive one |
| Every week | Always | Log a summary in `work-log/YYYY-Www.md` and set next week's `weekly-priorities` |

---

## Check against the four pillars

| Pillar | How the system meets it | Weak spot today |
|---|---|---|
| **Clean data** | Dedupe on domain (step 2). Suppression lists (steps 2 and 9). Waterfall enrichment with "unknown" holds instead of guesses (steps 3 and 4). Verified emails only (step 7). Signal and route stored on every CRM record (step 10) | Freshdesk, Ada and Sierra detection unverified (signal-matrix.md open item 3). No size ceiling yet |
| **Always-on signals** | W1, W2 and W4 refresh weekly, W3 monthly (step 1), and re-entry is allowed on a new signal (step 2) | Clay isn't set up yet, so nothing runs today |
| **Composable workflows** | One Clay build per signal serves S1 to S3 with keyword swaps (signal-matrix.md: 9 of 9 universal). Shared enrichment, ICP check, routing, people and email steps are reused by every workflow | Templates per route have to be written for each route ID |
| **Tight feedback loops** | Weekly review per signal and per route, with set actions and named files updated (step 11). Closed-lost reasons and objections flow back into personas.md and learnings | Sender and CRM not chosen, so exports aren't defined yet. Starting thresholds (200 sends, 90 days, 30 days) are untested |

## Open items

1. Choose and set up the sender (Instantly proposed), LinkedIn tool (HeyReach proposed) and CRM (Salesforce proposed). Then list them in CLAUDE.md Tools.
2. Set up Clay and run the test pull (signal-matrix.md open item 1).
3. Tune every "start at" setting in the weekly loop.
4. Create `context/messaging/facts.md` before any copy is written (`/campaign-copy` requires it).
