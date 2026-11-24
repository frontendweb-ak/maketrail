# Proposed user journeys

**Status:** Draft hypotheses  
**Last updated:** 2026-11-24

These journeys describe the intended end-to-end outcome. They are not final UI specifications.

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
