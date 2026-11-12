# Fin (formerly Intercom): Authorized Copy Facts

**Status: APPROVED 2026-11-12 by Gbadamosi Eniola** (repo owner) for this exercise. Drafted from `context/docs/research/`. Every entry cites its research file and tag.

This is a public portfolio project built from public sources. "Approved by" means approved by the repo owner for this exercise, not by Fin. Nothing here will be sent to anyone (CLAUDE.md: ask before sending).

**Last updated:** 2026-11-12

---

## Sender identity

| Field | Value |
|---|---|
| Sender name(s) | Gbadamosi Eniola (resolves `{{sender_name}}`) |
| Title | GTM (resolves `{{sender_title}}`) |
| Signature format | `{{sender_name}}` on one line, `{{sender_title}}` on the next. No company line, so this public repo doesn't suggest the sender works at Fin |
| Sender persona notes | First person singular, peer to a support leader |

## What we do (locked value prop)

- **Variant A:** "Fin is an AI agent that resolves support conversations on the helpdesk you already run, with no migration." Sources: company.md C12, "Deploy Fin on any helpdesk over API. No migration required."
- **Variant B:** "Fin resolves support conversations end to end, and you pay per outcome, not per seat." Sources: company.md C7 "$0.99 per outcome"; company.md C8 "No seats required".

Product one-liner (context, not copy): the Fin AI Agent, on Zendesk, HubSpot, Freshdesk, Salesforce or any helpdesk over API, priced per outcome (company.md C7, C12).

## Approved claims and numbers (use these exact phrasings)

| Claim | Approved phrasing | Source |
|---|---|---|
| Average resolution rate | "Fin's published average resolution rate is 76% across 12,000+ customers" | company.md C6 ("averaging 76% across 12,000+ customers", stated as resolution rates) |
| Price | "$0.99 per outcome" | company.md C7 |
| Billing rule | "you're not charged when a conversation is simply passed to your team" | company.md C7 |
| No migration | "no migration" / "on the helpdesk you already run" | company.md C12 |
| Zendesk | "keeping Zendesk as your system of record" | company.md C12 |
| HubSpot | "keeping HubSpot as your system of record" | company.md C12 |
| Around the clock | "works 24 hours a day, every day" | voice.md V2 |

**Formatting rules for proof:**
- Customer names exactly as written in the table below.
- Fin's numbers are Fin's published figures. Say "published", never present them as independent.
- Hiring counts come from scraped job posts. Use the `{{hiring_scale}}` label, never a raw number.

## Numbers to keep fuzzy (never quote as hard numbers)

- Total customer count. Sources disagree: 30,000+ for all products, 12,000+ for Fin (company.md section 4).
- Anthropic and Lightspeed results, which differ between stories (case-studies.md, conflicts).
- Any ROI or dollar figure outside the table above.

## Authorized social-proof names

| Name | What it proves | Matches | Caveat |
|---|---|---|---|
| **Lightspeed** | Runs Fin on Zendesk; "72%" of Fin conversations resolved without a human; "More than 43,000" requests resolved a month (customers.md K8) | Zendesk route (C1). Large software company | Bigger than most S2 targets. Use it as proof that Fin works on Zendesk, not as a size match |
| **Vanta** | A head-to-head on 400 real conversations: Fin about 73% vs the incumbent's about 49%. Started on its existing ticketing system (customers.md K9) | S2 self-serve SaaS. AI-agent routes (C2, C4, C6) and the no-migration route (C5) | Don't name the incumbent vendor. It isn't named in the source |
| **Personio** | "30k" monthly Fin resolutions (customers.md section 2) | S2 SaaS | Volume only; no resolution rate published |
| **Synthesia** | More than 275k additional monthly queries handled with the same headcount (customers.md section 2) | S2 and S1 software | Headcount angle only |

Everyone else in case-studies.md stays out of copy until added here.

## Proof caveats

- No Fin customer story on HubSpot exists (icp.md Open question 7). The HubSpot routes (C3, C4) carry no HubSpot-specific customer proof.
- Birdie Care's Zendesk story is about a migration that was reversed. It's too easy to read as a knock on Zendesk, so it's not authorized for copy.
- All customer results are published by Fin (customers.md caveat).

## Banned

### Banned angles
- Price comparisons with HubSpot or any competitor (spec C3: resolution rate, not price).
- Criticising any competitor by name.
- Leading with Salesforce ownership (messaging.md: use it only to answer the objection).
- "Replace your team" or anything implying people lose jobs.
- Diagnosing their support team as failing (iron law 14 and the insult test).

### Banned words and phrasing (company-specific)
- "perfect", "highest performing", "provably superior": Fin's own brand claims, not ours to make (messaging.md).
- "chatbot": Fin doesn't use it (voice.md section 7).
- "deflection": don't mix it with "resolution" (messaging.md).
- "free trial": "free" is globally banned (copy-bans.yaml).

### Never in copy, under any circumstance
- Neo Financial's homepage quote, which duplicates Anthropic's (case-studies.md).
- Any customer quote not in this file.

## Voice notes

- Register: direct, peer-to-peer, plain. Fin's category words: "AI agent", "resolution", "outcome" (brand.md).
- Hedges about the prospect: "my guess is", "could be off", "not sure if".
- Subjects: lowercase, 3 to 5 words, the same subject across the thread.

## CTA ladder

- **Primary:** an offer to test Fin on a sample of their own conversations, asked as a question.
- **Secondary (final email):** a referral ask: who owns support tooling?
- **Never:** "book a call", calendar links, "free".

## Internal only (never in prospect copy)

- Signal-matrix scores, tiers, volume bands, ICP fail reasons.
