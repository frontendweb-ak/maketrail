# Product requirements document (PRD)

**Product:** Maketrail  
**Version:** 0.1  
**Status:** Draft — hypothesis-led, pending market validation  
**Last updated:** 2026-11-24  
**Owner:** Product

## 1. Purpose

Define the product problem, intended users, proposed experience, requirements, boundaries, and evidence needed before committing to implementation.

This document is not authorization to build every capability described. Requirements marked as hypotheses must be validated before MVP scope is frozen.

## 2. Product summary

Maketrail is a proposed marketplace where buyers discover, evaluate, purchase, and integrate reusable software products created by independent developers and software studios.

A listing may offer:
- A software product with a clear license and delivery method.
- Evidence about compatibility, maintenance, documentation, and verification.
- Optional implementation, customization, or maintenance services.

**Core buyer journey:** Discover → Evaluate → Purchase → Integrate.

## 3. Problem statement (hypothesis)

Development agencies and software teams repeatedly need common software capabilities. They may find code through repositories, communities, marketplaces, or direct contacts, but evaluating ownership, license, quality, compatibility, maintenance, and integration effort can be difficult.

Creators may have reusable software but lack effective distribution, buyer access, and a clear route to implementation revenue.

Validation must establish which part of this problem is frequent, costly, and sufficiently painful to support a marketplace.

## 4. Goals

### Validation-stage goals
- Identify one narrow, recurring buyer problem.
- Confirm buyers already spend money or engineering time solving it.
- Recruit creators with genuine products and distribution rights.
- Complete real product-to-buyer matches.
- Observe paid purchases and successful integrations.
- Understand unit economics and operational risks.

### Eventual product goals
- Make legitimate software products discoverable.
- Help buyers assess fit before purchase.
- Make licensing and product status understandable.
- Connect buyers to creators or qualified implementers.
- Give creators a sustainable way to distribute and support products.

## 5. Non-goals for the initial launch

- Replacing GitHub or package registries.
- A general-purpose freelance job marketplace.
- Hosting or executing arbitrary customer-submitted code.
- A universal marketplace for every digital asset category.
- Complex enterprise procurement, private catalogs, or multi-entity billing before demand is demonstrated.
- Claims that every listing is secure, production-ready, or independently audited.
- Building escrow or holding buyer funds without an approved legal and payment structure.

## 6. Target users

### Primary buyer hypothesis: development agency
Needs reusable capabilities across client projects, cares about delivery time, compatibility, license rights, support, and predictable integration.

### Secondary buyer hypothesis: SaaS startup / product team
Needs to accelerate delivery without taking on excessive maintenance or vendor risk.

### Primary creator hypothesis: independent developer
Owns reusable software, wants distribution and revenue, and may offer setup or customization.

### Secondary creator hypothesis: small software studio
Has maintained modules or starter products and can provide documentation and implementation support.

### Implementation partner
A creator or qualified third party who integrates, customizes, or maintains a purchased solution.

Detailed personas: [personas.md](personas.md).

## 7. Product principles

1. Trust and evidence before catalog volume.
2. Buyer outcomes over downloads.
3. Respect creator ownership and licensing.
4. Make compatibility and limitations explicit.
5. Distinguish community-published from independently verified.
6. Do not confuse automated checks with a security guarantee.
7. Keep the first release narrow and evidence-led.
8. Keep the marketplace usable across supported regions while complying with payment and legal requirements.

## 8. Proposed experience areas

These are conceptual product areas, not a finalized application architecture.

### Public marketplace
- Browse and search published products.
- Filter by category, technology, supported versions, license, price, and verification level.
- View creator profiles and product details.
- Access demos and documentation where available.

### Creator workspace
- Create and manage creator profile.
- Submit product listing and required metadata.
- Declare ownership and distribution rights.
- Provide license, price, version, dependencies, documentation, and support terms.
- Manage listing status, versions, and service availability.

### Buyer workspace
- Save or shortlist products.
- Ask product questions or contact the creator through an approved channel.
- Purchase a license where supported.
- Access purchased files or delivery instructions.
- View order, license, update, and support information.

### Operations/admin workspace
- Review creator and product submissions.
- Moderate listings and reports.
- Record verification evidence and review status.
- Handle disputes, refunds, abuse, and policy escalations.
- Maintain auditable administrative actions.

### Implementation services
- Show optional integration/customization offers.
- Identify provider, scope, deliverables, price, and support boundaries.
- Allow buyers to engage the creator or a qualified third party.
- Keep service contracts and product licenses clearly distinguished.

## 9. Functional requirements

Priority key:
- **P0:** required for a validated narrow marketplace MVP.
- **P1:** useful after the core transaction works.
- **P2:** later expansion.
- **TBD:** depends on validation, legal review, or provider capability.

| ID | Requirement | Priority | Notes |
|---|---|---:|---|
| PR-001 | Public can browse and view published product listings | P0 | Search/filter depth depends on catalog |
| PR-002 | Product detail explains problem, stack, versions, license, price, delivery, maintenance, limitations, and support | P0 | Required fields may vary by product type |
| PR-003 | Creator can submit a product listing | P0 | Draft and review states required |
| PR-004 | Creator declares ownership and distribution rights | P0 | Evidence and policy review required |
| PR-005 | Admin can approve, reject, suspend, or request changes to listings | P0 | Audit trail required |
| PR-006 | Listing shows community-published or independently verified status accurately | P0 | No implied guarantees |
| PR-007 | Buyer can express purchase intent or place an order through an approved flow | P0/TBD | Exact checkout depends on legal/payment provider |
| PR-008 | Buyer receives authorized access or delivery instructions after confirmed payment | P0/TBD | Secure delivery and entitlement checks |
| PR-009 | Order, license, fee, refund, and creator payable records are auditable | P0/TBD | Payout availability depends on provider |
| PR-010 | Buyer can contact creator about product or integration | P0 | Avoid building broad chat before need |
| PR-011 | Creator can offer implementation services | P1 | Validate service demand and contracting |
| PR-012 | Buyer can submit a review after a verified transaction | P1 | Abuse and moderation controls |
| PR-013 | Buyer can view purchased products and updates | P1 | Version/update delivery design |
| PR-014 | Creator analytics for views, conversion, revenue, and support | P1 | Define metrics carefully |
| PR-015 | Organization accounts and team purchasing | P2 | Validate buyer workflow |
| PR-016 | Subscription plans and private catalogs | P2 | Not required for free publishing or initial validation |
| PR-017 | AI-assisted discovery and compatibility suggestions | P2 | Must not invent compatibility claims |

## 10. Core product data requirements

A product listing should be able to represent:
- Identity: name, slug, summary, description, category.
- Creator: account, public profile, ownership declaration.
- Product type: module, package, template, application, or another explicitly supported type.
- Technical fit: languages, frameworks, runtime, supported versions, dependencies, deployment model.
- Evaluation: screenshots, demo, docs, changelog, test instructions, known limitations.
- Commercial terms: free/paid, price, currency, license, permitted use, delivery method.
- Lifecycle: draft, submitted, changes requested, published, suspended, archived.
- Maintenance: maintained/unmaintained status, latest version, last updated.
- Support: included support, response expectations, support duration, contact path.
- Verification: level, scope, tested version, environment, date, reviewer, results, limitations.
- Services: provider, scope, availability, indicative price, deliverables.

Do not require every field for every product type until listing taxonomy is defined.

## 11. Trust, safety, and governance requirements

- Collect an ownership and rights declaration before publication.
- Require clear license terms and third-party dependency disclosures.
- Provide a reporting and takedown process.
- Preserve an audit trail for moderation and verification.
- Label verification scope, date, version, and limitations.
- Never execute submitted code in production or on the primary application environment.
- Use isolated environments and least privilege for any future automated analysis.
- Protect downloads and entitlements from unauthorized access.
- Define refund, dispute, prohibited-content, and creator suspension policies before transactions.
- Avoid promising escrow, guaranteed quality, security certification, or compatibility without evidence and appropriate legal arrangements.

## 12. Non-functional requirements (initial expectations)

These are design constraints to refine before engineering:
- **Security:** least privilege, secure sessions, input validation, safe file handling, auditability, and a documented threat model.
- **Privacy:** collect only necessary data; define retention, deletion, and access policies.
- **Reliability:** payment and order operations must be idempotent and recoverable.
- **Accessibility:** semantic, keyboard-accessible interfaces and readable contrast.
- **Performance:** establish measurable budgets after target experience and stack are selected.
- **Internationalization:** English-first initially; avoid assumptions that prevent future localization.
- **Observability:** structured logs, actionable errors, and operational monitoring for critical workflows.

## 13. Key journeys

See [user journeys](user-journeys.md) for proposed end-to-end flows.

## 14. MVP boundary

The MVP is not frozen. The detailed [MVP scope proposal](mvp-scope.md) separates the immediate concierge validation pilot from a conditional productized MVP. Neither is an approved engineering scope.

After validation, select:
- One buyer segment.
- One or two high-frequency product categories.
- One primary purchase/delivery model.
- One supported payment and payout approach.
- A minimum viable verification policy.
- A small set of buyer and creator workflows.

The MVP should prove a complete transaction and integration outcome, not maximize feature count.

## 15. Success metrics

### Marketplace funnel
- Qualified buyer requirements.
- Search-to-product-detail engagement.
- Product-detail-to-contact or purchase-intent conversion.
- Purchase conversion and time to purchase.
- Refund and dispute rates.

### Supply quality
- Qualified active creators.
- Listings with complete licensing and compatibility data.
- Listing approval time.
- Product freshness and support responsiveness.

### Outcome
- Successful integrations.
- Time from requirement to working integration.
- Buyer satisfaction and repeat purchases.
- Creator earnings and repeat creator participation.

### Economics
- Gross transaction value.
- Marketplace revenue.
- Payment and payout costs.
- Refunds, disputes, verification and support costs.
- Contribution margin and manual matching effort.

Do not optimize vanity traffic before successful buyer outcomes.

## 16. Open decisions

- Which initial category has the strongest buyer demand?
- Which product types and delivery models are in scope at launch?
- Which jurisdictions and payment corridors can be supported?
- Will the first purchase be a direct product license, creator invoice, or provider-hosted checkout?
- What are the commission, refund, and payout rules?
- What minimum evidence qualifies a product for independent verification?
- What support obligations belong to creators versus Maketrail?
- What are the first required account roles and organization capabilities?

## 17. Release gates

Do not freeze MVP engineering scope until:
1. Buyer and creator interviews have been synthesized.
2. A narrow, repeated buyer problem is supported by evidence.
3. Genuine product supply exists with documented rights.
4. At least some real buyer-to-product matches have been attempted.
5. Transaction, integration, payment, and legal risks have been reviewed.
6. MVP acceptance criteria and operational ownership are documented.
