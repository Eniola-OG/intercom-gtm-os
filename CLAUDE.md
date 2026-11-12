# Intercom GTM Context OS

## Company
Intercom, renamed Fin in May 2026 and owned by Salesforce since 10 Sept 2026, sells the Fin AI Agent ($0.99 per outcome, runs on any helpdesk) and the Intercom helpdesk to 30,000+ companies, mostly software, fintech and AI businesses (sources: `context/docs/research/company.md` C1, C3, C7, C9).

## Key files
- `context/docs/research/`: company.md, customers.md, competitors.md, market.md, signals.md, voice.md (raw research, every fact sourced)
- `context/icp/icp.md`: ICP in five layers plus not a fit and open questions
- `context/icp/personas.md`: champion, economic buyer, influencer
- `context/icp/signal-matrix.md`: segments by persona with angles, signals scored on the four tests, top four to build, workflow tracker
- `context/docs/gtm-system.md`: outbound system end to end, with tools, decisions, the weekly feedback loop and the four-pillar check
- `output/campaigns/hiring-support-agents-in-bulk/workflow-spec.md`: workflow spec for W1, STRUCTURE-APPROVED, copy pending

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
