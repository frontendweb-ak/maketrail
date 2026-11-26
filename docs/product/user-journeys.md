# Maketrail MVP end-to-end workflows

**Status:** Working workflow definition — proposed, not approved or frozen  
**Version:** 0.2  
**Last updated:** 2026-11-26  
**Scope source:** [MVP scope](mvp-scope.md)  
**Decision owner:** Product (to be assigned)

These workflows refine the existing journey hypotheses into a candidate first-release operating model. They are not route contracts, UI specifications, API contracts, or authorization implementation. Conditional commerce steps remain excluded until the payment and seller model is approved.

## 1. Buyer discovers and evaluates a product

**Actor:** Agency owner, technical lead, or SaaS engineering lead.

1. Buyer arrives with a concrete problem or searches the catalog.
2. Buyer filters by category, stack, supported versions, price, license, and verification level.
3. Buyer opens a product detail page.
4. Buyer reviews demo, documentation, changelog, compatibility, dependencies, license, maintenance, limitations, and support.
5. Buyer compares shortlisted products.
6. Buyer asks a technical question or requests a demo.
7. Buyer decides whether to purchase, reject, or request implementation help.

**Success outcome:** Buyer can make an informed decision without relying on unsupported quality claims.

**Failure cases:** Missing license, unclear ownership, unsupported stack, stale product, no demo/docs, creator unresponsive, unclear price.

## 2. Creator submits a product

**Actor:** Independent developer or studio.

1. Creator creates an account and profile.
2. Creator starts a product listing.
3. Creator enters product description, supported stack, versions, dependencies, demo, docs, license, pricing, delivery method, maintenance status, and support terms.
4. Creator declares ownership and distribution rights.
5. Creator submits the listing.
6. Operations reviews completeness, policy, and rights information.
7. Listing is approved, rejected, or returned with requested changes.
8. Approved listing becomes visible with an accurate publication/verification label.

**Success outcome:** A legitimate, understandable listing is available to buyers.

**Failure cases:** Rights cannot be established, license conflicts, prohibited content, missing required details, misleading claims.

## 3. Buyer purchases a product

**Actor:** Buyer with a qualified requirement.

1. Buyer selects a product and reviews its commercial terms.
2. Buyer confirms license, price, taxes/fees where applicable, delivery, and refund terms.
3. Buyer completes checkout or the approved purchase process.
4. Payment provider confirms the transaction through a trusted server-side event or reconciliation process.
5. Order and entitlement records are created idempotently.
6. Buyer receives authorized download access or delivery instructions.
7. Creator receives the order notification and applicable fulfillment details.
8. Buyer can access order and license information later.

**Success outcome:** Payment, order, license entitlement, and delivery state are consistent and auditable.

**Critical controls:** Never grant paid access based only on a client redirect. Handle duplicate, delayed, failed, and out-of-order payment events. Do not promise payouts or escrow until provider/legal arrangements are approved.

## 4. Buyer gets implementation help

**Actor:** Buyer and creator or qualified implementation partner.

1. Buyer identifies implementation needs.
2. Buyer reviews service provider, scope, deliverables, indicative price, and availability.
3. Buyer and provider agree technical requirements, access, milestones, acceptance criteria, and support responsibilities.
4. Work proceeds under an explicit agreement.
5. Buyer reviews the result against agreed acceptance criteria.
6. Support and maintenance obligations continue only as contracted.

**Success outcome:** Product purchase and implementation responsibilities are clear and the buyer reaches a working integration.

**Failure cases:** Unclear scope, incompatible environment, missing access, IP dispute, missed deliverables, ambiguous support boundary.

## 5. Operations reviews a listing

**Actor:** Marketplace moderator or verifier.

1. Reviewer opens a submitted listing and creator declaration.
2. Reviewer checks completeness, rights evidence, license, claims, and policy compliance.
3. If independent verification is requested, reviewer records the exact version, environment, checks, results, and limitations.
4. Reviewer approves, rejects, or requests changes.
5. System records reviewer, timestamp, status transition, and reason.
6. Public listing displays only the claims supported by recorded evidence.

**Success outcome:** Buyers see accurate publication and verification information.

**Critical controls:** Reviewer actions are auditable. Submitted code is untrusted and must not be executed in production or on primary application infrastructure.

## 6. Refund, dispute, or takedown

**Actor:** Buyer, creator, operations, or payment provider.

1. A report or dispute is received.
2. Operations classifies the issue: payment, delivery, license/ownership, quality claim, abuse, or support.
3. Relevant listing/order evidence is preserved.
4. Access or listing status is restricted when necessary to reduce harm.
5. The issue is handled under published terms and payment-provider rules.
6. Parties receive a clear outcome and next steps.
7. Repeated or serious violations may lead to listing removal or account restrictions.

**Success outcome:** Issues are handled consistently with evidence and an auditable record.

## Cross-journey requirements

- Clear identity and role permissions.
- Explicit product status and commercial terms.
- Versioned and traceable listing changes.
- Audit trail for moderation, verification, order, and entitlement events.
- Accessible, understandable error and recovery states.
- No unsubstantiated verification, security, compatibility, or production-readiness claims.


## 7. Proposed first-release workflow boundary

The first release should prove the repeatable path from a visitor's software need to a legitimate product inquiry and an accountable next step. It should not require a custom checkout, wallet, escrow, automated payout, or platform-hosted code delivery.

### Included in the inquiry-first baseline

- Public visitors can browse published listings and open product details.
- Product detail pages expose creator, product/version, supported environment claims, license, price or quote basis, demo/docs, delivery method, maintenance, support, and known limitations.
- A visitor can submit a product-specific inquiry with project context and contact/follow-up details appropriate to the approved privacy model.
- An authenticated buyer can review their own submitted inquiries and their status. Whether anonymous inquiry is allowed remains a product/privacy decision; do not expose inquiry data publicly.
- A creator can create and maintain a creator profile, draft a product listing, submit it for review, and see review feedback.
- A creator can respond to inquiries routed to that creator, subject to platform policy and controlled disclosure of buyer information.
- An authorized operator can review listing completeness, rights declarations, licensing information, and policy compliance; request changes, approve, reject, suspend, or unpublish a listing; and manage inquiry/support cases.
- Publication and moderation decisions are auditable.

### Explicitly conditional, not assumed baseline

- Custom checkout, payment collection, refunds, chargebacks, commission calculation, seller onboarding, and payouts.
- Order/entitlement records and automated artifact downloads.
- Platform-managed file storage or code hosting.
- Paid implementation-service checkout or milestone management.
- Buyer organizations, team seats, approval workflows, and shared procurement.

A manually agreed acquisition outside the software workflow may be used only under a reviewed, compliant arrangement with clear contracting parties and terms. The application must not represent an inquiry as an order, an invoice as paid, or a payment as confirmed without trusted evidence.

## 8. Detailed buyer workflow

**Primary actor:** visitor or buyer evaluating a reusable software product for a real project.

1. **Enter discovery:** arrive through the marketplace home, a category/search result, or a shared product URL.
2. **Find candidates:** browse the curated published catalog. MVP filters should be limited to validated fields such as category and supported technology; do not add advanced ranking or comparison tools by default.
3. **Evaluate:** open product detail and inspect the problem solved, creator, product/version, compatibility claims, license, price/quote basis, docs/demo, delivery method, maintenance, known limitations, and support.
4. **Resolve uncertainty:** submit a product-specific question or request a demo. The form asks only for information needed to route and answer the inquiry: project context, relevant stack/version, intended use, timeframe (optional), and a safe reply channel.
5. **Receive acknowledgement:** see a clear confirmation and reference. The inquiry enters a visible status such as Submitted, Awaiting creator, Response received, Needs buyer information, Closed, or Withdrawn. Exact labels may change during UI specification.
6. **Continue privately:** buyer can view their own inquiry and authorized responses. No other buyer can discover it by changing an identifier or URL.
7. **Decide next step:** buyer may continue discussion, decline, or proceed under separately agreed commercial terms. The MVP does not imply checkout unless that capability passes its own approval gate.
8. **Close:** buyer or authorized operator closes/withdraws the inquiry; history and relevant audit events remain available according to retention policy.

**Buyer success:** the buyer can identify a plausible product, understand the important constraints and rights, get a useful response, and know the next step without misleading purchase or verification claims.

**Buyer failure/recovery cases:** no suitable listing; missing or unclear license; unsupported stack; stale or incomplete listing; creator does not respond; invalid/abusive inquiry; email delivery failure; account recovery issue; inquiry withdrawn; product unpublished while inquiry is open. Each case needs a clear message and safe next action.

## 9. Detailed creator workflow

**Primary actor:** individual developer or small studio authorized to distribute a reusable product.

1. **Create account and creator profile:** establish the human account and creator identity. Organization/studio membership remains optional and requires a separately approved model.
2. **Start draft:** create a product listing that is private to its authorized creator until submission and approval.
3. **Provide listing information:** enter problem/use case, description, product/version, supported stack and versions, dependencies, demo/docs, license and distribution-rights declaration, price/quote basis, delivery method, maintenance status, known limitations, and support terms.
4. **Save and resume:** incomplete drafts remain private; validation errors identify missing or inconsistent required fields.
5. **Submit:** creator confirms accuracy and submits the selected listing version. Submitted content becomes read-only or revision-controlled while under review; the exact edit model is a UI/technical decision.
6. **Review outcome:** creator sees Pending review, Changes requested, Approved/Published, Rejected, or Suspended as applicable, with a reason and safe remediation path.
7. **Revise:** when changes are requested, creator edits a new draft/revision and resubmits. Prior review decisions remain auditable.
8. **Respond to inquiries:** creator receives only inquiries assigned to their product and may respond, request clarification, or decline. Contact details are disclosed only as needed by the approved communication policy.
9. **Maintain listing:** creator can submit version/compatibility/documentation updates. Material changes may trigger re-review and must not silently overwrite historical order/license terms if commerce is later enabled.

**Creator success:** a legitimate creator can explain their product accurately, submit it for review, understand decisions, and respond to genuine buyer interest.

**Creator failure/recovery cases:** incomplete draft; rights evidence insufficient; license conflict; misleading or prohibited claim; reviewer requests changes; listing rejected/suspended; creator loses distribution rights; creator account compromised; creator cannot respond. Suspension/unpublishing must stop new discovery while preserving appropriate historical records and open-case handling.

## 10. Detailed operations workflow

**Actors:** reviewer/moderator and support operator. Finance/security responsibilities require separate permissions if payment or sensitive cases are introduced.

### Listing review

1. Reviewer opens a queued submission and sees the creator, listing revision, declarations, and evidence references needed for review.
2. Reviewer checks completeness, ownership/distribution-rights basis, license, third-party dependency notices, product claims, demo/docs, supported versions, delivery/support terms, and policy eligibility.
3. Reviewer records a decision: request changes, approve for publication, reject with reason, or escalate/hold.
4. Approval publishes only the reviewed revision. A later material change may require another review.
5. Reviewer records actor, timestamp, reason, decision, and evidence reference. Public labels describe publication/review status accurately and do not imply code verification.
6. If a bounded independent verification is performed, it is a separate record with version, date, environment, checks, results, limitations, and reviewer. It is not implied by listing approval.

### Inquiry and support handling

1. Operator opens an inquiry/case queue and accesses only the records permitted by their role.
2. Operator classifies the case, assigns an owner, and records status/next action.
3. Operator may request clarification, route a product question to the relevant creator, restrict unsafe content, or close the case with a reason.
4. Operator does not silently alter buyer/creator messages or make commercial commitments on their behalf.
5. Sensitive access and high-impact actions are audited.

### Moderation, suspension and takedown

1. Receive a report, rights complaint, safety issue, policy breach, or credible abuse signal.
2. Preserve relevant evidence and open a case.
3. Apply proportionate temporary restriction where needed to prevent ongoing harm; record the reason and scope.
4. Investigate using authorized evidence only. Do not execute submitted software in production or on primary developer machines.
5. Decide restore, request changes, restrict, suspend, or remove; notify affected parties as appropriate.
6. Record appeal/escalation path, retention obligations, and any downstream impact on open inquiries or future orders.

**Operations success:** publication, inquiry routing, moderation and support are consistent, permissioned, explainable, and auditable.

## 11. Cross-workflow state and access rules

These are proposed business rules to validate before technical design:

- A listing is publicly visible only when its current revision is approved and published.
- Drafts, review evidence, private creator data, inquiries, and operator notes are never public.
- A creator may manage only their own profile/listings and inquiries explicitly routed to them.
- A buyer may access only their own inquiries and responses authorized for them.
- A reviewer may make listing decisions only within assigned reviewer permissions; support access does not automatically grant approval or financial authority.
- Suspension/unpublishing blocks new discovery and inquiry creation for that listing. Existing inquiries move to a controlled state with a clear explanation.
- A listing approval is not independent code verification, security certification, compatibility guarantee, or production-safety claim.
- Product license, implementation-service agreement, and support obligations remain distinct.
- If commerce is introduced later, order, payment attempt, provider event, refund, license snapshot, entitlement, and delivery are separate records with explicit transitions. Client-side status never establishes payment.
- Every privileged state change records actor, timestamp, reason, and relevant before/after state.

### Proposed inquiry states

| State | Meaning | Typical next states |
|---|---|---|
| Submitted | Buyer has sent the inquiry; routing/acknowledgement is pending | Awaiting creator, Needs operator review, Withdrawn |
| Awaiting creator | Routed to creator for response | Response received, Needs buyer information, Closed |
| Response received | Creator/operator has responded | Needs buyer information, Closed, Withdrawn |
| Needs buyer information | A safe clarification is required | Awaiting creator, Closed, Withdrawn |
| Needs operator review | Requires moderation/support intervention | Awaiting creator, Closed, Withdrawn |
| Closed | Conversation concluded | Reopen only through an explicit support path |
| Withdrawn | Buyer withdrew the inquiry | Closed |

Exact state names, transition permissions, and notification behavior must be finalized in the feature specifications.

## 12. Decisions still required before workflow freeze

1. Whether buyer inquiry requires an account, supports verified email/guest submission, or both.
2. Which buyer contact fields are necessary and when creators can see them.
3. Whether creator-to-buyer communication is in-product, email-mediated, or operator-mediated for the first release.
4. Whether creators can publish only individual listings or require an operator-assisted onboarding step.
5. Which listing fields are mandatory for the first selected product category.
6. Whether price is fixed, quote-based, or both for the first release.
7. Who can review, approve, suspend, and handle appeals; whether reviewer and support roles are separate at launch.
8. Which public verification/publication labels can be operationally supported.
9. Which exact mockup screens correspond to the included workflows and which pending mockups should be deferred.
10. Whether any order/payment/delivery capability is actually required for the first launch corridor.

## 13. Workflow acceptance criteria for the next review

The workflow definition can be considered ready for product approval when:
- Buyer, creator, and operator happy paths are unambiguous.
- Every private resource has an explicit owner/authorized audience.
- Listing and inquiry states, transitions, and failure paths are documented.
- Listing approval and independent verification are clearly separated.
- Inquiry-first baseline is distinguished from conditional commerce.
- The minimum screen set is mapped to existing mockup IDs without changing their approval statuses.
- Open decisions have an owner and a clear resolution gate.
- Product, security, and operations owners have reviewed the workflow.

This document remains a proposed workflow until the decision owner explicitly approves it.