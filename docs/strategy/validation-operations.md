# Market validation operating kit

**Status:** Proposed operating procedure; not evidence of fieldwork  
**Last updated:** 2026-11-25  
**Parent strategy:** [30-day market validation plan](market-validation.md)  
**Purpose:** Turn the approved research plan into repeatable, privacy-conscious fieldwork records without restating its hypotheses, targets, interview prompts, calendar, or decision framework.

> **Execution status:** No interviews, creator qualifications, buyer requirements, product verifications, transactions, or integrations are recorded by this template. Populate records only after the corresponding activity has actually happened.

## 1. Operating rules

1. Assign a stable research ID before outreach. Use IDs such as `BUY-001`, `CRT-001`, `REQ-001`, `PRD-001`, and `OPP-001`.
2. Keep this public repository free of names, email addresses, phone numbers, personal social profiles, private repository URLs, customer names, credentials, payment details, and confidential commercial information.
3. Store contact details, consent evidence, raw recordings, transcripts, private links, and supporting documents in an access-controlled private system. The public tracker may contain only anonymized IDs and non-sensitive status.
4. Obtain explicit permission before recording or quoting. A person agreeing to an interview does not automatically agree to recording, attribution, or public quotation.
5. Ask about specific past behavior and actual projects. Separate observed/documented behavior from recollection, opinion, and hypothetical intent.
6. Record negative evidence, rejected matches, failed transactions, and limitations. Do not silently discard inconvenient results.
7. Never store passwords, API keys, access tokens, payment-card data, bank details, or other secrets in research records.
8. Do not access private repositories or customer materials without explicit authorization and a defined review scope. Do not execute submitted code on a workstation or production environment.
9. Keep proposed targets from the parent plan as targets. Update progress only when supported by dated records.
10. Use `Unknown` or `Not asked` rather than guessing. Use `Not applicable` only when the field genuinely does not apply.

## 2. Status vocabulary

| Area | Allowed statuses |
|---|---|
| Outreach | Not started · Contacted · Replied · Declined · No response · Follow-up due |
| Interview | Not scheduled · Scheduled · Completed · Cancelled |
| Consent | Not requested · Granted · Declined · Withdrawn |
| Evidence review | Not reviewed · In review · Supported · Partially supported · Contradicted · Insufficient |
| Creator/product qualification | Not assessed · Needs evidence · Qualified for pilot · Not qualified · On hold |
| Buyer requirement | Unqualified · Needs clarification · Qualified · Matched · Closed · Withdrawn |
| Opportunity | Discovery · Shortlisting · Demo/review · Terms discussion · Purchased · Delivered · Integrated · Failed · Refunded · Closed |

A status is an administrative state, not proof that a claim is true. Qualification must cite the evidence record that supports it.

## 3. Participant tracker

Use one row per person or organization. Keep identity and contact information in the private contact vault; the public row uses only the research ID.

| Research ID | Segment | Role band | Source/channel | Outreach status | Interview status | Consent status | Interview date (ISO) | Private notes reference | Follow-up date | Owner | Notes (anonymized) |
|---|---|---|---|---|---|---|---|---|---|---|---|
| BUY-___ | Buyer |  |  | Not started | Not scheduled | Not requested |  |  |  |  |  |
| CRT-___ | Creator |  |  | Not started | Not scheduled | Not requested |  |  |  |  |  |

**Field guidance**
- Segment: Buyer or Creator; use a separate record if one person participates in both roles.
- Role band: e.g. agency owner, delivery lead, technical decision-maker, independent developer, studio lead. Avoid identifiable job-title detail where unnecessary.
- Source/channel: referral, direct outreach, community, event, inbound, or other broad category.
- Private notes reference: opaque identifier in the approved private system; never a public URL or access token.
- Consent status: track interview, recording, attribution, and quotation permissions separately in the private consent record.

## 4. Interview evidence record

Create one record per interview, linked to a participant ID. Do not publish raw transcripts. Store anonymized, concise findings and private source references.

### Interview metadata

| Field | Value |
|---|---|
| Interview ID | INT-___ |
| Participant ID | BUY-___ or CRT-___ |
| Date (ISO) |  |
| Interviewer |  |
| Duration |  |
| Interview type | Buyer / Creator |
| Consent and recording reference (private) |  |
| Anonymized notes reference (private) |  |

### Evidence capture

| Topic | Record |
|---|---|
| Recent concrete project/example and timeframe |  |
| Capability/module involved |  |
| Frequency across projects (observed/reported) |  |
| Existing approach or workaround |  |
| Alternatives evaluated or used |  |
| Engineering time, delay, defect, or maintenance impact |  |
| Actual spend or budget evidence (currency and period; no confidential detail) |  |
| Purchase/reuse/build decision and outcome |  |
| Decision authority and approval process |  |
| Technical, legal, procurement, or operational constraints |  |
| What would cause rejection |  |
| Specific follow-up permission and action |  |
| Contradictory or disconfirming evidence |  |
| Researcher interpretation (clearly labeled) |  |

### Claim-level evidence log

| Claim ID | Claim (one testable statement) | Evidence type | Source reference (private/anonymized) | Direct observation or participant report? | Confidence | Contradictory evidence | Limitation |
|---|---|---|---|---|---|---|---|
| CLM-___ |  |  |  |  | Low / Medium / High |  |  |

Do not convert a participant's statement into an independently verified fact. Attribute it as a report unless documentary or observed evidence supports it.

## 5. Creator and product supply record

Create a creator record and one or more product records. Qualification is product-specific; one qualified product does not automatically qualify every product from the same creator.

### Creator record

| Field | Value |
|---|---|
| Creator ID | CRT-___ |
| Public display reference (if approved) |  |
| Creator type | Individual / Studio |
| Identity check method and private evidence reference |  |
| Distribution-rights declaration reference |  |
| Commercial participation interest |  |
| Support capacity and availability (with date checked) |  |
| Implementation service offered? | Yes / No / Conditional / Unknown |
| Service scope, capacity, and constraints |  |
| Creator status | Not assessed |
| Reviewer and review date |  |
| Open questions / limitations |  |

### Product record

| Field | Value |
|---|---|
| Product ID | PRD-___ |
| Creator ID | CRT-___ |
| Product name / anonymized label |  |
| Problem solved and intended buyer |  |
| Product category (observed need; not assumed) |  |
| Ownership evidence and private reference |  |
| Distribution rights and license |  |
| Third-party dependencies and notices |  |
| Supported stack, versions, runtime, and environment |  |
| Latest release/version and date checked |  |
| Documentation reviewed (reference kept private if needed) |  |
| Demo or working example reviewed? |  |
| Delivery method |  |
| Price and included usage rights |  |
| Maintenance status and last maintainer activity checked |  |
| Known limitations and security considerations |  |
| Support terms and response expectations |  |
| Implementation availability and provider |  |
| Verification level | Not assessed / Community Published / Independently Verified |
| Verification evidence record ID |  |
| Qualification status | Not assessed |
| Reviewer, date, and next review trigger |  |

### Verification evidence checklist

| Check | Status | Evidence reference | Scope / limitation |
|---|---|---|---|
| Creator identity reasonably checked | Not reviewed |  |  |
| Ownership or authority to distribute checked | Not reviewed |  |  |
| License and usage rights reviewed | Not reviewed |  |  |
| Material third-party dependencies/notices reviewed | Not reviewed |  |  |
| Documentation and advertised claims reviewed | Not reviewed |  |  |
| Supported versions and environment stated | Not reviewed |  |  |
| Build/tests reviewed in isolated environment (if applicable) | Not reviewed |  |  |
| Security checks and their scope recorded (if applicable) | Not reviewed |  |  |
| Known limitations recorded | Not reviewed |  |  |
| Support and maintenance availability checked | Not reviewed |  |  |

A checklist completion does not imply production safety. Any independent verification statement must identify the exact version, date, environment, checks, results, reviewer, and limitations. Never label a product Independently Verified solely because it builds or passes automated scans.

## 6. Qualified buyer requirement record

Create one record per distinct real requirement, not per general expression of interest.

| Field | Value |
|---|---|
| Requirement ID | REQ-___ |
| Buyer participant ID | BUY-___ |
| Anonymized organization/segment |  |
| Project context and intended outcome |  |
| Capability required |  |
| Current workaround / alternative |  |
| Stack, versions, runtime, and environment |  |
| Required integrations and dependencies |  |
| Must-have acceptance criteria |  |
| Constraints (security, data, hosting, license, procurement) |  |
| Deadline and consequence of delay |  |
| Budget range, currency, and basis |  |
| Evidence of existing spend or approved budget |  |
| Decision-maker / approval path (role only) |  |
| Technical evaluator and procurement owner (role only) |  |
| Willingness to evaluate a named solution? Evidence |  |
| Implementation required? Scope |  |
| Qualification status | Unqualified |
| Supporting interview/claim IDs |  |
| Disqualifying gaps or unknowns |  |
| Next action, owner, and due date |  |

**Qualification rule:** mark Qualified only when there is a concrete use case, identifiable acceptance outcome, sufficiently clear technical constraints, a credible timeline, and a reachable decision/approval path. Record budget evidence separately; enthusiasm alone is not budget.

## 7. Concierge match and transaction outcome log

Use one opportunity ID to connect a requirement, shortlisted products, commercial terms, and outcome. Keep this log free of payment credentials, bank information, invoices containing personal data, and confidential contract text.

| Field | Value |
|---|---|
| Opportunity ID | OPP-___ |
| Requirement ID | REQ-___ |
| Buyer ID | BUY-___ |
| Shortlisted product IDs |  |
| Match rationale and rejected alternatives |  |
| Demo / technical review outcome |  |
| Quoted product price and currency |  |
| Quoted implementation price and currency |  |
| Written terms / license reference (private) |  |
| Agreed scope and acceptance criteria |  |
| Payment route/provider category (no account details) |  |
| Payment status and date (evidence reference private) |  |
| Product delivery method and date |  |
| Implementation provider and scope |  |
| Integration result | Not started / Successful / Partial / Failed |
| Acceptance evidence and date |  |
| Support effort (hours) and issues |  |
| Refund / dispute status and reason |  |
| Actual marketplace revenue/fee (if any) |  |
| Payment, refund, verification, support variable costs |  |
| Matching/sales effort (hours) |  |
| Integration effort (hours) |  |
| Repeat use or follow-up behavior observed |  |
| Outcome status | Discovery |
| Blockers, lessons, and next action |  |

Record actual collected amounts separately from quotes, proposals, and unpaid invoices. Calculate contribution using actual revenue and attributable costs; do not treat gross transaction value as marketplace revenue. Do not describe payment-provider processing or delayed settlement as escrow.

## 8. Evidence quality and confidence rubric

### Evidence type

| Type | Meaning | Typical strength |
|---|---|---|
| Direct observation | Researcher observed the workflow, artifact, demo, or behavior with permission | Strong for the exact observed scope |
| Contemporaneous documentation | Dated invoice, contract excerpt, ticket, project artifact, analytics, or other permitted record | Strong when provenance and scope are clear |
| Specific participant recollection | Detailed account of a past event, with timeframe and concrete details | Moderate; still self-reported |
| General recollection | Broad memory without a specific example or supporting detail | Weak |
| Opinion or preference | Belief, prediction, or stated preference without behavior | Weak for demand validation |
| Hypothetical intent | What someone says they might do in a future scenario | Very weak; not purchase evidence |

### Confidence

- **High:** multiple independent, relevant sources or strong direct/documentary evidence; scope and limitations are clear; no material contradiction remains unexplained.
- **Medium:** one specific credible source or partial corroboration; some important uncertainty remains.
- **Low:** opinion, vague recollection, hypothetical intent, indirect evidence, or unresolved contradiction.

Confidence applies to an individual claim, not to an entire participant or market segment. A small convenience sample cannot establish market-wide prevalence. Report sample size, recruitment method, non-response, selection bias, and counterexamples alongside any synthesis.

## 9. Operating cadence

| Cadence | Action | Required record/output |
|---|---|---|
| Before outreach | Assign IDs, identify segment and research purpose, prepare consent approach | Participant tracker |
| After each contact | Update outreach status and next action | Participant tracker |
| Immediately after each interview | Capture concrete examples, claim-level evidence, contradictions, and follow-ups | Interview evidence record |
| After each creator/product review | Record rights, compatibility, docs, support, verification scope, and gaps | Creator/product record |
| After each buyer qualification | Record constraints, acceptance outcome, timeline, budget evidence, and authority | Buyer requirement record |
| After each match or transaction event | Update quote, terms, payment status, delivery, support, outcome, and effort | Opportunity log |
| Weekly | Reconcile tracker counts to underlying records; review disconfirming evidence and overdue follow-ups | Dated internal weekly synthesis |
| At experiment end | Compare evidence with the parent plan's gates and targets; state sample limitations | Go / iterate / no-go recommendation |

Do not mark a workstream complete from tracker status alone. Reconcile counts against interview records, qualified requirement records, reviewed product records, and transaction evidence.

## 10. Privacy and repository boundary

**Suitable for this public repository**
- Empty templates and field definitions.
- Research IDs with non-identifying segment/status metadata.
- Anonymized aggregate findings only after reviewing them for re-identification risk.
- Public competitor observations with source URLs and access dates, where permitted.

**Keep in an access-controlled private system**
- Names, emails, phone numbers, social handles, and contact lists.
- Consent forms, recordings, raw transcripts, and identifiable quotations.
- Private repository links, source archives, customer code, and access instructions.
- Customer names, project names, architecture diagrams, security findings, and confidential requirements.
- Contracts, invoices, tax records, payment references, bank/payout details, and dispute correspondence.
- Any data whose publication could identify a participant or reveal commercially sensitive information.

Use least-privilege access, a defined retention period, and a deletion process for private research material. Honor consent withdrawal and applicable privacy obligations. If a public summary could identify a participant by a rare role, project, location, or combination of details, generalize or omit it.

## 11. Gate evidence handoff

This kit supports the gates in [MVP scope](../product/mvp-scope.md) and [Architecture Readiness Assessment](../architecture/readiness-assessment.md); it does not replace them.

| Gate / decision area | Evidence to hand off | Source record |
|---|---|---|
| Problem and buyer segment | Repeated concrete problems, frequency, impact, current alternatives, actual spend | Interview claims + qualified requirements |
| Creator supply and legitimacy | Real candidates, rights/license evidence, product quality/compatibility, creator availability | Creator/product records |
| First end-to-end buyer outcome | Qualified requirement through match, terms, payment route, delivery, integration, and support | Requirement + opportunity records |
| Launch and commercial feasibility | Jurisdiction constraints, provider/payment route evidence, refund/dispute handling, operational economics | Opportunity records + separately reviewed legal/provider evidence |
| Trust and operating readiness | Review scope, moderation/verification effort, support and incident patterns, privacy controls | Product reviews + opportunity records |
| Productized MVP scope | Which buyer/creator/operations steps were repeatedly necessary to complete a successful outcome | Synthesized evidence linked to source IDs |

A gate is not passed by reaching a numerical target alone. Explain the quality and limitations of the evidence, unresolved risks, and the decision owner. Any legal, tax, payment-provider, or regulatory conclusion requires appropriate qualified review; interview notes are not legal advice.

## 12. Current execution record

**No fieldwork results have been entered in this document.** The targets, hypotheses, and calendar remain those in the parent plan. Start adding dated, anonymized records only when activities occur; keep raw evidence private and link to it by opaque reference.
