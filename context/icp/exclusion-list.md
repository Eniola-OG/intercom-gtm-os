# Exclusion list

Who we never approach through outbound, why, and how each rule is checked. One place for every exclusion. Built 2026-11-16 from the three files below; if a rule changes, change it there and here.

Sources:
- `output/campaigns/hiring-support-agents-in-bulk/workflow-spec.md` section 2 (STRUCTURE-APPROVED 2026-11-12)
- `context/icp/icp.md` "Not a fit"
- `context/docs/gtm-system.md` steps 2, 9 and 10

## 1. Hard filters (applied before any outreach)

From the W1 workflow spec, section 2. These run as filters in the list build.

| Who | Why | How it's checked |
|---|---|---|
| Sites with the Intercom widget | Probably already a customer, so this is expansion, not outbound | BuiltWith technology list contains "Intercom" |
| Salesforce Service Cloud users | Same owner as Agentforce; they go to the channel list | Technology list contains "Salesforce Service Cloud" or "Salesforce Live Agent" |
| Startup-program companies | 15 or fewer employees, or $10M or less raised. Fin gives them "1 year of Fin free + 93% off Intercom" (icp.md, company.md C13) | Employee count and total funding fields |
| Staffing, outsourcing and support agencies | They post support roles for their clients (INFERRED risk) | Industry is "Staffing and Recruiting" or "Outsourcing", or the description matches `outsourc\|BPO\|staffing\|contact cent(er\|re) services` |
| Competitors and the owner | Zendesk, HubSpot, Freshworks, Decagon, Sierra, Ada, Kustomer, Gorgias, Forethought, Salesforce, Fin | Domain blocklist |
| Segments S1, S3, S4, S5 (W1 only) | Covered by later runs of the workflow | Segment classification is not S2 |
| Contacted in the last 90 days, open CRM opportunity, unsubscribed | Suppression rules (section 3 below) | gtm-system.md steps 2 and 9 |

## 2. Not a fit (judgement calls, not yet automated filters)

From `context/icp/icp.md` "Not a fit". Rows marked INFERRED are reasoning from research, not stated facts.

| Who | Why | Evidence |
|---|---|---|
| Current Fin customers | Existing customers. INFERRED: Intercom helpdesk customers not yet on Fin are an expansion motion, not cold outbound | company.md section 4 |
| Large enterprises wanting a deeply customised build | Salesforce positions Agentforce as the "deeply customizable platform" and Fin as fast time to value for SMB and commercial | company.md C2. INFERRED split |
| Companies whose volume is mainly voice in a contact centre | Fin Voice is a "custom pricing plan" for "select customers" | company.md C7. INFERRED weaker fit |
| Teams with no help content and no APIs | They fail Fin's own readiness checks | signals.md G10 |
| Companies that refuse a vendor tied to Salesforce or want to choose their own model | This is the main pitch of the "switch from Fin" vendors | competitors.md P17, P18. INFERRED: disqualify only if stated |
| Businesses with very low conversation volume | They can't clear the 50-outcome minimum on another helpdesk | company.md C7. INFERRED |

## 3. Suppression (after contact)

From `context/docs/gtm-system.md`. The 90-day window is a starting setting, tuned in the weekly loop.

| Event | Rule | Source |
|---|---|---|
| Contacted in the last 90 days | Suppress, unless the signal is new since the last touch; then allow re-entry | gtm-system.md step 2 |
| Reply: already a Fin or Intercom customer | Add to suppression. Pass to the account team. Fix the Intercom-widget check if it missed them | gtm-system.md step 9 |
| Unsubscribe or hostile reply | Suppress permanently across all channels | gtm-system.md step 9 |
| No reply after the last touch | Close the contact. The company can re-enter only on a new signal after the 90-day suppression | gtm-system.md step 9 |
| Opportunity closed lost | Log the reason. Suppress for 90 days, then allow re-entry on a new signal | gtm-system.md step 10 |
