# Maketrail feature map

**Status:** Proposed feature inventory — not an approved engineering scope  
**Version:** 0.1  
**Last updated:** 2026-11-24

## 1. Purpose

This document is the master inventory of proposed Maketrail capabilities. It organizes the product into functional domains, assigns stable feature IDs, records dependencies, and proposes delivery priorities.

The current project stage remains market validation and product definition. Priority labels below are planning hypotheses. They do not authorize implementation or mean every P0 item belongs in the first release. The first MVP must be narrowed after buyer/creator evidence, payment-provider review, and legal assessment.

## 2. Priority definitions

- **P0 — Core candidate:** likely necessary to deliver and operate a narrow, trustworthy marketplace transaction. Still subject to MVP selection.
- **P1 — Next:** useful after the core buyer-to-creator transaction is proven.
- **P2 — Later:** expansion capability; do not build before a demonstrated need.
- **Research:** requires discovery, policy, legal, or provider decisions before it can be specified.

## 3. Product domains

| Domain | Purpose | Primary users | Initial priority |
|---|---|---|---|
| Identity and access | Accounts, profiles, roles, and permissions | All users | P0 candidate |
| Marketplace discovery | Browse, search, filter, and evaluate products | Buyers | P0 candidate |
| Creator publishing | Submit and maintain legitimate product listings | Creators | P0 candidate |
| Commerce and licensing | Purchase, order, entitlement, and license records | Buyers, creators, operations | P0 candidate / Research |
| Implementation services | Connect buyers with product integration providers | Buyers, creators, partners | P1 candidate |
| Trust and verification | Ownership, moderation, verification evidence, reporting | Buyers, creators, operations | P0 candidate |
| Operations and administration | Listing review, support, disputes, audit | Operations | P0 candidate |
| Notifications and communication | Transactional updates and buyer/creator contact | All users | P0/P1 candidate |
| Analytics and reporting | Measure discovery, conversion, quality, and economics | Creators, operations | P1 candidate |
| Organization and enterprise | Team purchasing, private catalogs, procurement | Agencies, businesses | P2 |

## 4. Feature inventory

### A. Identity and access

| ID | Feature | Priority | Dependencies / notes |
|---|---|---:|---|
| IDN-001 | Account registration and sign-in | P0 | Authentication approach and supported regions TBD |
| IDN-002 | Email verification and account recovery | P0 | Delivery provider and abuse controls |
| IDN-003 | User profile and public creator profile | P0 | Profile visibility and privacy rules |
| IDN-004 | Buyer, creator, and operations permissions | P0 | Define authorization matrix before implementation |
| IDN-005 | Creator onboarding and eligibility status | P0 / Research | Separate listing access from payout eligibility where lawful |
| IDN-006 | Organization accounts and team membership | P2 | Validate multi-user buyer workflows |
| IDN-007 | Multi-factor authentication and elevated admin controls | P1 / Research | Risk assessment and account recovery design |

### B. Marketplace discovery and product evaluation

| ID | Feature | Priority | Dependencies / notes |
|---|---|---:|---|
| MKT-001 | Public product catalog and listing pages | P0 | Published listings only |
| MKT-002 | Product detail page with structured metadata | P0 | Listing schema and content policy |
| MKT-003 | Category and technology taxonomy | P0 | Validate initial category wedge |
| MKT-004 | Search by product, problem, and creator | P0 | Search technology deferred |
| MKT-005 | Filters for stack, versions, price, license, and verification | P0 | Data completeness and taxonomy |
| MKT-006 | Product demo, documentation, changelog, and media links | P0 | Safe external-link and content handling |
| MKT-007 | Compare or shortlist products | P1 | Buyer research |
| MKT-008 | Saved products and buyer collections | P1 | Account feature |
| MKT-009 | Compatibility guidance based on declared metadata | P1 | Must distinguish declared from tested compatibility |
| MKT-010 | AI-assisted discovery and recommendations | P2 | Requires quality data and evaluation; no invented claims |

### C. Creator publishing and catalog management

| ID | Feature | Priority | Dependencies / notes |
|---|---|---:|---|
| CRT-001 | Creator profile and capabilities | P0 | Identity/profile domain |
| CRT-002 | Create and edit product listing drafts | P0 | Listing schema |
| CRT-003 | Product ownership and distribution-rights declaration | P0 | Legal wording and evidence process |
| CRT-004 | License, price, delivery, and support metadata | P0 | License policy and product type |
| CRT-005 | Submit listing for review | P0 | Moderation workflow |
| CRT-006 | Listing status and review feedback | P0 | Admin review domain |
| CRT-007 | Product version and changelog management | P1 | Versioning and buyer notification design |
| CRT-008 | Direct file delivery configuration | P0 / Research | Storage, scanning, limits, and secure delivery design |
| CRT-009 | GitHub-connected product/repository linking | P1 / Research | OAuth scopes, ownership checks, repository access model |
| CRT-010 | Creator listing performance analytics | P1 | Metric definitions and privacy |
| CRT-011 | Creator subscription and premium tools | P2 | Validate willingness to pay; free publishing remains available |

### D. Commerce, licensing, and entitlements

| ID | Feature | Priority | Dependencies / notes |
|---|---|---:|---|
| COM-001 | Product purchase intent and checkout | P0 / Research | Provider, seller/merchant role, supported countries |
| COM-002 | Payment status verification through trusted provider API/webhook | P0 | Provider integration and signature validation |
| COM-003 | Order record and lifecycle | P0 | Transaction lifecycle specification |
| COM-004 | License terms presented and accepted at purchase | P0 | License model and legal review |
| COM-005 | Buyer entitlement and authorized product delivery | P0 | Secure storage/delivery design |
| COM-006 | Marketplace fee calculation and transaction ledger | P0 / Research | Approved fee base and provider capabilities |
| COM-007 | Creator payout onboarding and payout status | Research | Provider and country eligibility |
| COM-008 | Refund and cancellation workflow | P0 / Research | Provider, consumer law, policy |
| COM-009 | Dispute and chargeback case tracking | P0 / Research | Provider responsibilities and operations policy |
| COM-010 | Tax, invoice, and currency handling | Research | Country-by-country professional review |
| COM-011 | Coupons, promotions, and discounts | P2 | Not required to validate initial value |
| COM-012 | Subscriptions or recurring product billing | P2 | Only if product category supports it and demand exists |

### E. Implementation services

| ID | Feature | Priority | Dependencies / notes |
|---|---|---:|---|
| SVC-001 | Creator indicates implementation availability | P1 | Creator profile and service policy |
| SVC-002 | Service listing with scope, deliverables, price, and terms | P1 | Service taxonomy and contracting terms |
| SVC-003 | Buyer requests an implementation quote | P1 | Buyer-to-provider contact workflow |
| SVC-004 | Buyer selects creator or qualified third-party provider | P1 | Provider eligibility and conflict disclosures |
| SVC-005 | Service agreement and acceptance criteria record | P1 / Research | Legal review and scope template |
| SVC-006 | Milestone and delivery tracking | P2 / Research | Do not imply escrow or fund custody |
| SVC-007 | Service reviews after verified engagement | P2 | Moderation and review integrity |
| SVC-008 | Maintenance and support plans | P2 | Service obligations and recurring billing |

### F. Trust, safety, and verification

| ID | Feature | Priority | Dependencies / notes |
|---|---|---:|---|
| TRU-001 | Community-published status and label | P0 | Clear definition and public explanation |
| TRU-002 | Independently verified status and evidence record | P0 candidate | Verification scope, version, date, environment, limitations |
| TRU-003 | Creator ownership evidence review | P0 | Rights policy and reviewer workflow |
| TRU-004 | License and dependency disclosure review | P0 | Policy and expertise requirements |
| TRU-005 | Product report and takedown request | P0 | Abuse/IP process and response ownership |
| TRU-006 | Prohibited content and creator conduct policy | P0 | Policy and appeals process |
| TRU-007 | Isolated product analysis and security scanning | Research | Threat model, sandbox, resource limits, supply-chain controls |
| TRU-008 | Vulnerability disclosure and incident response | P1 / Research | Security operations and escalation |
| TRU-009 | Verified-purchase reviews and moderation | P1 | Transaction linkage and anti-abuse controls |
| TRU-010 | Product freshness and maintenance indicators | P1 | Define measurable freshness signals |

### G. Operations and administration

| ID | Feature | Priority | Dependencies / notes |
|---|---|---:|---|
| OPS-001 | Admin access with least-privilege roles | P0 | Identity and access matrix |
| OPS-002 | Listing review queue and decisions | P0 | Creator submission workflow |
| OPS-003 | Review notes and creator change requests | P0 | Audit trail |
| OPS-004 | Creator/account restrictions and listing suspension | P0 | Policy, notice, and appeal process |
| OPS-005 | Report, IP claim, and takedown case management | P0 | Legal/operations procedures |
| OPS-006 | Order lookup and support case record | P0 candidate | Privacy-aware support access |
| OPS-007 | Refund/dispute operations view | P0 / Research | Provider capabilities and permissions |
| OPS-008 | Audit log for sensitive administrative actions | P0 | Retention and tamper-resistance requirements |
| OPS-009 | Marketplace health and operational dashboard | P1 | Metrics and access controls |

### H. Notifications and communication

| ID | Feature | Priority | Dependencies / notes |
|---|---|---:|---|
| COMMS-001 | Transactional email for account and order events | P0 candidate | Email provider and consent/legal requirements |
| COMMS-002 | Creator notification for listing review and order events | P0 candidate | Notification preferences |
| COMMS-003 | Buyer-to-creator product inquiry | P0 candidate | Abuse controls and contact privacy |
| COMMS-004 | In-app notification center | P1 | Notification event model |
| COMMS-005 | Product update notifications to entitled buyers | P1 | Versioning and preference controls |
| COMMS-006 | Real-time chat | P2 | Do not build until messaging demand is proven |

### I. Analytics and reporting

| ID | Feature | Priority | Dependencies / notes |
|---|---|---:|---|
| ANA-001 | Funnel events for discovery, product views, and purchase intent | P0 candidate | Privacy and event taxonomy |
| ANA-002 | Transaction and contribution-margin reporting | P0 candidate | Accurate financial ledger and cost inputs |
| ANA-003 | Creator listing and sales reporting | P1 | Privacy and metric definitions |
| ANA-004 | Product quality and freshness reporting | P1 | Verification and maintenance data |
| ANA-005 | Cohort, retention, and repeat-purchase analytics | P1 | Sufficient volume and privacy controls |
| ANA-006 | Enterprise reporting and exports | P2 | Enterprise demand |

### J. Organization and enterprise capabilities

| ID | Feature | Priority | Dependencies / notes |
|---|---|---:|---|
| ENT-001 | Organization profile and membership | P2 | Identity domain |
| ENT-002 | Shared buyer workspace and collections | P2 | Organization authorization |
| ENT-003 | Team purchase approvals and budgets | P2 | Buyer procurement research |
| ENT-004 | Private or invite-only catalogs | P2 | Enterprise demand and access model |
| ENT-005 | Enterprise invoices and procurement workflow | Research | Legal/payment model |
| ENT-006 | Enterprise support and service commitments | P2 | Operational capacity and contracts |

## 5. Candidate MVP capability set

This is a candidate scope to validate, not a commitment to build all listed capabilities.

### Buyer path
- Public catalog and product detail pages.
- Search and a small number of meaningful filters.
- Clear license, price, supported stack/version, delivery, and support information.
- Product inquiry or purchase-intent workflow.
- A supported purchase and delivery path if payment/legal review permits it.
- Order and entitlement visibility for paid products.

### Creator path
- Creator profile.
- Product listing draft and submission.
- Ownership and license declarations.
- Listing review feedback and publication status.
- A practical way to deliver the product and fulfill buyer questions.

### Operations path
- Admin roles and listing review queue.
- Ownership/license review and takedown process.
- Clear community-published versus independently verified status.
- Auditable order/support/refund handling appropriate to the launch model.

### Explicitly defer unless validation proves essential
- Real-time chat.
- AI recommendations.
- Complex creator subscriptions.
- Organization procurement and private catalogs.
- Multi-currency payout automation across many countries.
- Full milestone payment/escrow system.
- Large-scale automated code execution or security certification.

## 6. Cross-domain dependencies

| Capability | Depends on |
|---|---|
| Public product catalog | Listing schema, publication state, taxonomy |
| Product search and filters | Structured product metadata and indexable fields |
| Creator publishing | Identity, creator profile, rights declaration, moderation |
| Independent verification | Ownership evidence, license review, isolated test process, reviewer record |
| Paid checkout | Country/provider approval, commercial terms, order model, fee policy |
| Entitlement delivery | Confirmed payment, license, secure delivery, access control |
| Creator payouts | Provider onboarding, supported countries, financial ledger, tax review |
| Implementation services | Provider profiles, scope/contract templates, dispute/support policies |
| Reviews | Verified transaction or engagement, moderation and anti-abuse controls |
| Analytics | Event taxonomy, privacy rules, trustworthy transaction records |

## 7. Feature specification standard

Before implementation, each selected feature must have a dedicated specification under `docs/features/` containing:

1. Feature ID and title.
2. Status, owner, and priority.
3. Problem and target user.
4. Goals and non-goals.
5. User stories and primary/alternate flows.
6. Functional requirements and business rules.
7. Permissions and data access rules.
8. Error, empty, loading, and recovery states.
9. Security, privacy, and abuse considerations.
10. Analytics/events where relevant.
11. Dependencies and open decisions.
12. Acceptance criteria and test scenarios.
13. Rollout, migration, and operational considerations where relevant.

## 8. Feature lifecycle

Proposed states:
- `proposed` — idea captured, not researched.
- `researching` — discovery or feasibility work in progress.
- `specified` — requirements and acceptance criteria reviewed.
- `approved` — explicitly selected for a release/sprint.
- `in_progress` — implementation started.
- `in_review` — awaiting review or validation.
- `done` — acceptance criteria met and evidence recorded.
- `deferred` — intentionally postponed with reason.
- `rejected` — not proceeding, with rationale.

A priority label alone does not move a feature to approved.

## 9. Open product decisions

1. Which product category and buyer workflow should anchor the first release?
2. Does the first release need direct checkout, or should concierge invoicing validate demand first?
3. Is direct file delivery required initially, or is creator-managed delivery sufficient for the first wedge?
4. Is GitHub connection a launch requirement or a later convenience?
5. What minimum verification can be performed safely and consistently?
6. Are implementation services part of the first paid workflow or a follow-on offering?
7. Which countries and currencies can be supported compliantly?
8. Which metrics can be collected with an appropriate privacy basis?

## 10. Next step

Use the validation plan to select the first buyer problem and product category. Then write detailed specifications only for the smallest end-to-end journey that addresses that evidence. Do not turn this entire inventory into a single implementation sprint.
