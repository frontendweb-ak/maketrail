# Maketrail MVP scope proposal

**Status:** Active MVP definition draft — not approved or frozen  
**Version:** 0.2  
**Last updated:** 2026-11-25  
**Decision owner:** Product (to be assigned)

## 1. Executive summary

Maketrail should not begin by building a broad multi-sided marketplace. The proposed first release should prove one narrow outcome:

> A development agency can find a legitimate reusable software solution, evaluate whether it fits a real project, acquire clearly defined rights, and reach a successful integration with accountable support.

The primary buyer remains a hypothesis. The initial product category, country coverage, commercial model, payment flow, and delivery method remain unvalidated.

This document separates two stages:
1. **Concierge validation pilot:** manually deliver the buyer outcome using a curated catalog and compliant existing arrangements. This is the immediate recommended activity; it does not require a full marketplace application.
2. **Productized MVP:** a small software product that supports the repeated, validated parts of that workflow. It may proceed only after the evidence and launch gates in this document are met.

No engineering work is authorized by this proposal.

## 2. Target users and roles

### Primary buyer hypothesis
Development agency owner, delivery lead, or technical lead who has a concrete upcoming project need and has previously spent engineering time or budget solving a similar problem.

### Supply-side user hypothesis
Independent developer or small software studio that can demonstrate control of a reusable product and the right to distribute it under stated terms.

### Operations role
A Maketrail operator who manually qualifies buyer requirements, reviews creator/product information, coordinates matching, and records outcomes during the pilot.

### Explicitly out of initial scope
- General consumers and hobbyist buyers.
- Broad freelance hiring unrelated to a listed software product.
- Enterprise procurement teams and multi-entity organizations.
- Large agencies with complex private-catalog requirements unless interviews show this is the first urgent use case.

## 3. Narrow product wedge

**Working wedge hypothesis:** reusable software modules that reduce repeat implementation work for development agencies.

Candidate categories to investigate—not a preselected launch catalog:
- Authentication, roles, and organizations.
- Payments, subscriptions, and billing.
- Notifications and messaging.
- Admin and business-operation modules.
- File management and reporting.

Select one category, or at most two closely related categories, from observed buyer requirements. Do not launch all categories simply because they appear in the feature map.

## 4. Concierge validation pilot — immediate scope

The pilot is a human-operated service, supported by lightweight documentation/spreadsheets or existing tools where appropriate.

### In scope
- Interview buyers about recent, specific software needs.
- Qualify a real requirement: use case, stack/version, constraints, timeline, budget, decision-maker, and acceptance outcome.
- Identify genuine creator products and obtain evidence of ownership, license, documentation, compatibility claims, price, and support availability.
- Curate a small shortlist for a qualified requirement.
- Arrange a creator demo or technical review.
- Facilitate a purchase through a compliant existing provider or direct invoicing arrangement with clear written terms.
- Coordinate creator or qualified partner implementation where separately agreed.
- Record purchase, integration, support effort, refund/dispute, and repeat-purchase outcomes.
- Keep buyer and creator data permissioned and access-controlled.

### Out of scope
- Building a custom checkout, wallet, escrow, or payout system.
- Holding buyer funds.
- Automated product execution or automated security certification.
- Public self-serve creator publishing at scale.
- AI recommendations, real-time chat, mobile apps, subscriptions, and enterprise features.

### Pilot completion evidence
The pilot is complete only when the experiment outputs in [the market validation plan](../strategy/market-validation.md) are recorded, including actual outcomes and limitations. Interview counts and target transactions are goals, not claims that they have occurred.

## 5. Productized MVP — conditional scope

The following is a candidate first software release if the concierge pilot demonstrates repeatable demand and legal/payment review permits the selected transaction flow.

### A. Public discovery
- Public catalog containing only reviewed and published listings.
- Product detail page with a consistent minimum set of problem, creator, version, stack, license, price/quote, documentation/demo, maintenance, limitations, delivery, and support information.
- Basic category and technology filters based on the selected wedge.
- Clear labels distinguishing creator declarations, community-published status, and independently verified evidence.
- A direct inquiry or request-to-buy action.

### B. Buyer workflow
- Buyer can submit a structured product/integration inquiry.
- Buyer can see the inquiry status and the relevant product/creator response through a controlled channel.
- Buyer can review the commercial terms and license before committing.
- If direct checkout is approved for the launch corridor, buyer can complete provider-hosted checkout and view a server-confirmed order state.
- Buyer can access order, accepted license terms, and delivery instructions after the required confirmed state.

If payment-provider or legal review is not complete, use a clearly disclosed, compliant concierge/invoice flow. Do not simulate an in-app payment or show false payment confirmation.

### C. Creator workflow
- Creator can create a profile and submit a product listing for review.
- Listing captures minimum ownership/right declaration, license, product/version, supported stack, price or quote basis, docs/demo, delivery method, maintenance, known limitations, and support terms.
- Creator can see review status and respond to change requests.
- Only approved listings become public.
- Creator can respond to qualified inquiries and receive relevant order/fulfillment notifications.

### D. Operations workflow
- Restricted operations access with role-based permissions.
- Review queue to approve, reject, request changes, or suspend listings.
- Record rights/ownership review outcome and supporting evidence references.
- Manage buyer inquiries and manually coordinate the pilot's selected fulfillment model.
- View order and provider status where transactions are enabled.
- Record support, refund, dispute, abuse, and takedown cases appropriate to launch scope.
- Audit sensitive actions and status changes.

### E. Trust and security minimum
- Server-side resource authorization and role checks.
- Secure account recovery and session controls.
- Ownership declaration and license information required before publication.
- Report/takedown path and accountable operator.
- No untrusted package execution in production or on primary developer workstations.
- Private artifact storage and entitlement-controlled delivery only if platform-managed downloads are included.
- Payment state based only on trusted provider confirmation, with idempotent event handling, if checkout is included.
- Data minimization, privacy notice, retention rules, secrets management, logging redaction, and backup/recovery procedures before public launch.

## 6. Explicitly deferred

Do not include these in the first productized MVP unless validation demonstrates a critical dependency:
- Native iOS/Android apps.
- Real-time chat or community/social features.
- AI product matching or code analysis.
- Advanced full-text search infrastructure and complex recommendation ranking.
- Product comparison workspaces, collections, and wishlists.
- Automated independent verification or execution of submitted software.
- General-purpose code hosting, CI/CD, package registry, or runtime hosting.
- Creator subscriptions, premium listing plans, coupons, and recurring billing.
- Enterprise organizations, approvals, budgets, private catalogs, SSO, and procurement.
- Multi-currency automated payouts across many countries.
- Escrow, wallet, or platform-held milestone funds.
- Complex milestone/project management for implementation services.
- Broad analytics dashboards; capture only the events and economics needed to evaluate the MVP.

## 7. End-to-end acceptance criteria

A productized MVP is not accepted merely because individual screens exist. The selected launch workflow must pass the relevant end-to-end criteria below.

### Discovery and evaluation
- A visitor can find and open a published product in the selected category.
- The listing clearly identifies creator, product/version, supported environment, license, price or quote process, delivery, support, and known limitations.
- Missing or unverified claims are not presented as established facts.
- A visitor cannot access drafts, rejected listings, private creator data, or unpublished evidence.

### Creator publishing and moderation
- A creator can submit a listing with the required fields and rights declaration.
- A reviewer can request changes, approve, reject, or suspend the listing.
- Only an authorized reviewer can change publication status.
- Every decision records actor, timestamp, reason, and relevant evidence reference.
- A suspended or unpublished listing is no longer discoverable through public catalog routes.

### Inquiry and communication
- A buyer can submit a product-specific inquiry with enough context for qualification.
- Only authorized parties can view the inquiry and its attachments/details.
- Rate limits and abuse reporting exist.
- Communication does not expose private buyer contact data beyond the approved workflow.

### Purchase and delivery (only if checkout is approved)
- Buyer sees the applicable license and commercial terms before purchase and the accepted terms are retained with the order.
- Client redirects or client-submitted status cannot mark an order paid.
- Forged, duplicate, delayed, and out-of-order provider events do not create duplicate orders, ledger entries, refunds, or entitlements.
- Delivery is unavailable before the required server-confirmed payment state.
- Refund/dispute status follows an explicit policy and affects access consistently.
- Reconciliation can identify mismatches between provider and internal records.

### Operations and security
- Buyer, creator, support, reviewer, finance, and admin permissions are tested for both allowed and denied actions.
- A user cannot access another user's orders, inquiries, or downloads by changing an identifier.
- Sensitive admin actions are auditable.
- Uploads are quarantined and are never executed in trusted production environments.
- Secrets and sensitive payment/personal data do not appear in logs or source control.
- Backup restoration and incident escalation are documented and tested before a paid public launch.

### Buyer outcome
- A real buyer can identify a suitable solution for a qualified requirement.
- A purchase or agreed acquisition arrangement is completed under clear terms.
- The buyer reaches the agreed integration outcome or a documented reason why it failed.
- Support effort, time-to-integration, costs, and buyer feedback are recorded.

## 8. Release gates

| Gate | Required evidence | Outcome if not met |
|---|---|---|
| G0 — Problem validation | Repeated concrete buyer problem, qualified requirements, evidence of current cost or spend | Continue discovery or change wedge |
| G1 — Supply validation | Real candidate products, credible ownership/license evidence, documentation, creator availability | Do not open creator self-publishing |
| G2 — Transaction feasibility | Compliant purchase/invoice arrangement, clear seller roles, refunds/support terms, country/provider review | Run non-custodial concierge only; no custom checkout |
| G3 — Trust operations | Moderation, takedown, verification language, support owner, incident escalation | Do not publish open submissions |
| G4 — Technical readiness | Threat controls implemented and tested for included features; restore/recovery and monitoring | Do not launch affected capability |
| G5 — Outcome validation | Paid or otherwise evidenced acquisition and successful integrations with acceptable economics | Iterate or stop before expansion |

Passing a gate requires documented evidence and an accountable reviewer. A target count alone is not proof.

## 9. Success metrics

Measure a small set tied to the buyer outcome:
- Number of qualified buyer requirements.
- Time from requirement to relevant shortlist.
- Shortlist-to-demo/inquiry and inquiry-to-purchase conversion.
- Paid transactions and successful integrations.
- Time from purchase to working integration.
- Refund, dispute, and failed-integration reasons.
- Creator response and fulfillment time.
- Verification, support, and matching hours per transaction.
- Actual marketplace revenue and contribution margin where applicable.
- Repeat buyer behavior and repeat creator participation.

Separate actual results from targets, estimates, and expressions of interest.

## 10. Dependencies and unresolved decisions

- Validated buyer problem and initial product category.
- Evidence from buyer and creator interviews.
- Creator ownership and distribution rights.
- Launch countries and jurisdiction-specific legal/privacy requirements.
- Seller/merchant-of-record responsibilities.
- Payment provider capabilities, fees, refunds, disputes, and payout eligibility.
- Whether the first software release needs direct checkout or can continue with a concierge arrangement.
- Whether platform-managed artifact delivery is necessary.
- Verification scope and available reviewer capability.
- Support capacity and incident ownership.

## 11. Current working direction — MVP definition and architecture discovery

**Status of this direction:** proposed working approach; not a final product, architecture, or launch approval.

The project is moving from research preparation into bounded MVP definition and architecture discovery. The 30-day interview and transaction targets remain useful validation goals, but completing every target is not a prerequisite to define the MVP, begin reversible architecture discovery, or prepare implementation specifications.

Do not confuse these milestones:
- **MVP definition:** decide the smallest coherent buyer/creator/operator workflow and its acceptance criteria.
- **Architecture discovery:** map domains, data, permissions, trust boundaries, integration constraints, and compare reversible technology options.
- **Architecture freeze:** approve the consequential technical and operational decisions required for implementation.
- **Public launch readiness:** satisfy legal, payment, security, support, privacy, recovery, and operational requirements for the actual launch scope.

### Working release shape to evaluate

The following is a starting proposal for product-definition review, not an approved scope:

**Core first-release workflow**
1. Public visitor discovers a small, curated set of genuinely reviewed product listings.
2. Visitor evaluates a product detail page with creator, version, compatibility claims, license, price/quote basis, delivery, support, limitations, and accurately scoped trust information.
3. Buyer submits a product-specific inquiry or request; no custom checkout is assumed.
4. Creator submits a listing for review and can respond to authorized inquiries.
5. Operations reviews rights/licensing declarations, controls publication, handles inquiries, and records moderation/support actions.
6. Buyer and creator can follow the inquiry and agreed next steps through a controlled, auditable workflow.

**Conditional capabilities**
- Buyer account and inquiry history, if anonymous inquiry plus secure follow-up is insufficient.
- Order records, license snapshots, entitlements, and delivery access if the initial acquisition model requires them.
- Provider-hosted checkout only after seller/merchant responsibilities, launch jurisdictions, provider eligibility, refunds, disputes, and payout flow are reviewed and approved.
- Platform-managed artifact storage/downloads only if a real creator/buyer workflow requires them and safe storage, scanning, access control, and takedown operations are designed.

**Not required merely to call the release an MVP**
- Wallet, escrow, platform-held funds, complex payout orchestration.
- Native mobile applications, real-time chat, AI matching, advanced recommendations.
- Enterprise organizations, team approvals, private catalogs, SSO.
- Automated code execution or automated security certification.
- Broad creator analytics, subscriptions, coupons, and complex service project management.

### Validation proportionality

Before implementation authorization, seek enough evidence to establish:
- At least one concrete buyer problem and a credible first use case.
- A small number of real product candidates with credible ownership and license paths.
- A feasible, clearly disclosed acquisition/fulfillment approach for the first release.
- A reachable operational owner for listing review, support, refunds/disputes if applicable, and takedowns.

This is a minimum evidence bar, not a claim that these conditions are already met. The proposed 15 buyer interviews, 20 creator interviews, 10 founding creators, 20 product candidates, 3 paid purchases, and 2 integrations remain experiment targets, not mandatory MVP entry criteria.

### Immediate sequence

1. Approve or revise the first-release workflow and exclusions.
2. Reconcile that workflow against the existing mockup register; only screens needed by the selected workflow receive implementation specifications.
3. Complete the resource/action permission matrix and state transitions for the selected workflows.
4. Conduct architecture discovery for the selected flows: domain boundaries, data ownership, external integrations, trust boundaries, failure handling, and operational requirements.
5. Resolve launch-market, contracting/seller, payment, privacy, and support constraints before freezing affected capabilities.
6. Approve the MVP scope and architecture decisions explicitly before coding.

No application implementation, production stack selection, infrastructure procurement, or payment-provider commitment is authorized by this working direction.

## 12. Related documents

- [Product requirements document](prd.md)
- [Feature map](../features/feature-map.md)
- [Proposed user journeys](user-journeys.md)
- [Market validation plan](../strategy/market-validation.md)
- [System design](../architecture/system-design.md)
- [Threat model](../architecture/threat-model.md)
- [Risk register](../architecture/risk-register.md)
