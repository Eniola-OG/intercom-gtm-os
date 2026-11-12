# Competitors: where Fin wins, loses, and how to respond

Every claim traces to `context/docs/research/competitors.md` (tags P0 to P18) unless another file is named. Stats are each vendor's own claims. INFERRED marks my reading.

## Main competitors

| Vendor | Type | Pricing on its site | Scale claim | Who it says it serves |
|---|---|---|---|---|
| **Zendesk** (owns Forethought) | Helpdesk with built-in AI | AI agents "included in every Suite and Support plan", outcome-based, no figures (P1) | "Trusted by 32,000+ customers"; "22K+ AI customers" (P1) | "From startups to enterprises" (P1) |
| **HubSpot Service Hub** | CRM and helpdesk with built-in AI | "$0.50" per resolution; seats from "$0/month" (P10) | "TRUSTED BY 306,000 CUSTOMERS WORLDWIDE."; "70%" average resolution (P10) | Small business to enterprise tiers (P10) |
| **Freshdesk** | Helpdesk with built-in AI | No figures; "Free AI onboarding included" (P9) | "Trusted by 50,000+ businesses worldwide" (P9) | Not named (P9) |
| **Salesforce Agentforce** | CRM AI platform, now Fin's sister product | "Flex Credits, Resolutions, or per-user licensing", no figures (P2) | "Over 18K companies" (P2) | "enterprise scale" (P2) |
| **Decagon** | Standalone AI agent | Not shown (P3) | Customer stats only (P3) | "the world's leading enterprises" (P3) |
| **Sierra** | Standalone AI agent | "Pay for a job well done." (P4) | No numbers (P4) | "great companies of the world" (P4) |
| **Ada** | Standalone AI agent | Not shown (P5) | "350+" global businesses (P5) | "Enterprise CX" (P5) |
| **Gorgias** | Ecommerce helpdesk with AI | Not shown (P7) | "17,000+ ecommerce brands" (P7) | Ecommerce and Shopify brands (P7) |
| **Kustomer** | AI-native CX platform | Not shown (P8) | "600+ B2C & B2B companies" (P8) | "B2C & B2B companies" (P8) |

## Where Fin wins

| Win | Evidence |
|---|---|
| Runs on the competitor's helpdesk, so the deal needs no migration | "Deploy Fin on any helpdesk over API. No migration required." (P12); Lightspeed on Zendesk (customers.md K8) |
| Head-to-head proof against an incumbent AI vendor | Vanta: about 73% vs about 49% on 400 conversations (customers.md K9) |
| Published price and results; most rivals publish neither | "$0.99 per outcome" (P0) vs no figures from Zendesk, Agentforce, Decagon, Sierra, Ada (table above). "averaging 76% across 12,000+ customers" (P0) |
| A helpdesk and AI agent from one vendor, for teams that want it | "the only helpdesk with a natively integrated AI Agent" (voice.md V3) |
| Speed to live | Anthropic "In under a week" (customers.md K10); "Set up in under an hour on your current helpdesk" (company.md C8) |

## Where Fin loses, or is exposed

| Loss | Evidence |
|---|---|
| **Price per resolution** | HubSpot "$0.50" and "half the price of leading competitors" (P10) vs Fin's $0.99 (P0) |
| **AI bundled into the helpdesk plan** | Zendesk AI agents "included in every Suite and Support plan" (P1). INFERRED: buyers ask why they should pay twice |
| **Salesforce ownership** | "Fin is getting acquired. Is now the time to switch?" (Bland, P17). The main worry is roadmap independence (P18) |
| **Model choice** | Ada: "Orchestrate multiple LLMs" (P5). Fin runs on its own Apex models (company.md section 2) |
| **Large enterprise and voice** | Decagon, Sierra and Ada lead with enterprise logos (P3 to P5). Fin Voice is a "custom pricing plan" for "select customers" (company.md C7) |
| **Ecommerce** | Gorgias "17,000+ ecommerce brands" (P7). Few Fin ecommerce stories were found (customers.md section 3) |
| **No proof on HubSpot or Freshdesk** | No Fin customer story on either was found (customers.md section 2) |

## How to respond

| When they say | Respond with |
|---|---|
| "HubSpot is half the price" | Compare resolutions, not price: Fin's published 76% vs HubSpot's published "70%" (P0, P10). Both are vendor numbers. INFERRED: price per resolution only matters if the bot resolves |
| "Our helpdesk AI is already included" | Offer a test on their own conversations, as Vanta did: 73% vs 49% (customers.md K9). Fin keeps their helpdesk "as your system of record" (P12) |
| "You're Salesforce now" | Quote the close release: Fin "will continue to serve its customers" and "works seamlessly with the help desks and systems companies already use" (company.md C3) |
| "We want to pick our own model" | Fin claims "+15%" "Confirmed resolutions vs Sonnet 5" (P0), a vendor benchmark. Anthropic itself runs Fin (customers.md K10) |
| "We'll build it ourselves" | Anthropic, a model maker, bought instead (customers.md K10). Lightspeed tried its own assistant first (K8) |
| Enterprise voice or a deeply customised build | INFERRED: not Fin's sweet spot. Salesforce points those to Agentforce (company.md C2). Qualify out |
