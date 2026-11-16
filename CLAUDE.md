# Intercom GTM Context OS

## Company
Intercom, renamed Fin in May 2026 and owned by Salesforce since 10 Sept 2026, sells the Fin AI Agent ($0.99 per outcome, runs on any helpdesk) and the Intercom helpdesk to 30,000+ companies, mostly software, fintech and AI businesses (sources: `context/docs/research/company.md` C1, C3, C7, C9).

## Files
Root
- `.mcp.json`: project MCP servers (Notion, https://mcp.notion.com/mcp)
- `CLAUDE.md`: this map. `README.md`: what the repo is. `.gitignore`: keeps secrets, lead lists and local files out of Git. `.env`: local secrets, ignored and never committed

Context
- `context/docs/research/company.md`: what Fin sells, pricing, scale, funding, team, leadership
- `context/docs/research/customers.md`: named customers, results, case studies, quotes
- `context/docs/research/competitors.md`: competing vendors and how each positions itself
- `context/docs/research/market.md`: regulation and market changes that create urgency
- `context/docs/research/signals.md`: public evidence of what makes a company need Fin now
- `context/docs/research/voice.md`: how Fin and Intercom describe themselves, in their own words
- `context/icp/icp.md`: ICP in five layers plus not a fit and open questions
- `context/icp/personas.md`: champion, economic buyer, influencer
- `context/icp/exclusion-list.md`: who we never approach (hard filters, not-a-fit, suppression), with sources
- `context/icp/signal-matrix.md`: segments by persona with angles, signals scored on the four tests, top four to build, workflow tracker
- `context/docs/gtm-system.md`: outbound system end to end, with tools, decisions, the weekly feedback loop and the four-pillar check
- `context/positioning/value-proposition.md`: job, pain, gain and proof for each persona
- `context/positioning/positioning.md`: category, target customer, current alternatives, unique value, proof, positioning statement
- `context/positioning/competitors.md`: main competitors, where Fin wins and loses, how to respond
- `context/messaging/messaging.md`: core message, four pillars with proof, persona angles, words to use and avoid
- `context/messaging/facts.md`: the only source of names, claims and numbers allowed in outbound copy, plus banned angles and the sender
- `context/docs/case-studies.md`: every customer story found, with size, industry, problem, result, quote and source
- `context/brand-kit/brand.md`: tone of voice and exact key phrases from Fin's own copy

Output
- `output/campaigns/campaign-strategy.md`: 19 ranked campaign ideas with mother intent, signal, angle, volume band, difficulty and tier
- `output/campaigns/hiring-support-agents-in-bulk/workflow-spec.md`: workflow spec for W1 with the full copy (3 emails, 2 LinkedIn DMs), COPY-APPROVED

Diagrams
- `diagrams/gtm-system.json` and `gtm-system.svg`: flowchart spec and layout for gtm-system.md, drawn on the Miro board "intercom GTM System" (https://miro.com/app/board/uXjVEO-4bOI=/)

Knowledge base (from the GTM Starter Kit)
- `knowledge-base/playbooks/signal-matrix-framework.md`: method for segment and signal matrices
- `knowledge-base/playbooks/workflow-anatomy.md`: workflow layers and the Mother Intent Catalog
- `knowledge-base/playbooks/copy-frameworks.md`, `copy-iron-laws.md`, `copy-bans.yaml`, `linkedin-dm-frameworks.md`: copy rules and frameworks
- `knowledge-base/playbooks/clay/`: `actions-data-credits.md`, `expert.md`, `formulas.md`, `iron-laws.md`, `prompts.md` (Clay how-tos)
- `knowledge-base/playbooks/templates/facts-template.md`: template for `context/messaging/facts.md`
- `knowledge-base/learnings/`: empty until the first campaign runs

Tracking
- `weekly-priorities/2026-W46.md`: this week's steps and their status
- `work-log/2026-W46.md`: everything done this week
- `meetings/`: empty

Skills and tools: see the two sections below (18 skill folders in `.claude/skills/`, 3 tools in `tools/`).

## How this folder works
- `.claude/skills/`: project-specific skills. Read when a task matches a skill.
- `context/icp/`: ideal customer profiles and segments. Read before any targeting or list work.
- `context/positioning/`: positioning statements and competitive alternatives. Read before strategy or messaging work.
- `context/messaging/`: approved messaging, value props, proof points. Read before writing any copy.
- `context/brand-kit/`: voice, tone, visual guidelines. Read before writing or designing anything external.
- `context/docs/research/`: raw company and market research with sources. Read when you need a fact and its citation.
- `knowledge-base/playbooks/`: repeatable how-tos for this team. Read before starting a known type of task.
- `knowledge-base/learnings/`: what worked and what did not. Read before planning a campaign; add after each one.
- `meetings/`: meeting notes and transcripts. Read when a task references a past conversation or decision.
- `output/campaigns/`: one subfolder per campaign with specs, copy and results. Write here; read to resume a campaign.
- `tools/`: scripts and tool configs for this project. Read when a task needs a tool.
- `weekly-priorities/`: one file per ISO week (YYYY-Www.md). Read at the start of every session.
- `work-log/`: one file per ISO week matching weekly-priorities. Append an entry after every change.

## Rules
- Cite a source for every company fact.
- Never invent numbers. If a number is unknown, say so.
- No em dashes in any copy.
- Ask before sending or publishing anything.
- Log every change in this week's work log (`work-log/YYYY-Www.md`).
- This is a public repo built from public sources only. I do not work at Intercom, so nothing is "Source: internal".

## Skills
In `.claude/skills/` (from the GTM Starter Kit). Paths like `knowledge-base/...` and `tools/...` resolve inside this repo.
- Strategy: `/signal-matrix` (ICP and signal matrices), `/campaign-strategy` (15 to 25 ranked campaign ideas)
- Workflow: `/build-workflow-spec` (structure, STRUCTURE-APPROVED), `/campaign-copy` (copy on an approved spec), `/campaign-contract` (Clay build sheet)
- Clay build: `/design-clay-table-json`, `/import-clay-table`, `/build-clay`, `/prompt-builder`, `/save-clay-schema`
- Clay cost and data: `/calculate-costs`, `/workspace-cost-audit`, `/export-tables`
- QA and deliverability: `/campaign-qa`, `/inbox-placement-test`
- Research and visuals: `/crawl4ai`, `/agent-browser`, `/miro-gtm-flowchart`

## Tools
- In `tools/`: rex (unofficial Clay API client), crawl4ai (site crawler to Markdown), agent-browser (browser automation)
- Claude Code, VS Code, Git and GitHub (repo: https://github.com/Eniola-OG/intercom-gtm-os)
- GTM stack: Clay (account not set up yet)
- Notion: read-only mirror of `context/` and `output/` (not research) at "intercom GTM OS" (https://app.notion.com/p/416455fbc30781c2b31ee342f1111399). GitHub is the source of truth; re-sync after changing a mirrored file
