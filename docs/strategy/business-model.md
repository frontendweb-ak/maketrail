# Maketrail business model

**Status:** Proposed model — pending buyer/creator validation and legal/payment review  
**Last updated:** 2026-11-24

## 1. Executive summary

Maketrail is proposed as a commission-based hybrid marketplace for creator-built software products and related implementation services.

The initial model should let creators publish without a mandatory subscription, let buyers purchase products with clear license terms, and allow creators or qualified third parties to provide optional implementation services.

Maketrail earns revenue primarily when successful transactions occur. Recurring subscriptions, enterprise plans, sponsored placement, and other monetization should be considered only after the core marketplace demonstrates repeat demand.

This is a business-model hypothesis. Commission rates, payment flows, payout timing, tax treatment, and legal roles are not approved until validated with users and reviewed for each supported market.

## 2. Participants and value exchange

### Buyers
- Discover reusable software relevant to a real project.
- Evaluate product fit, ownership, license, maintenance, and verification evidence.
- Purchase the rights described by the license.
- Optionally hire the creator or another qualified implementation partner.

### Creators
- Publish products they own or are authorized to distribute.
- Set product price and license terms within marketplace policy.
- Receive buyer demand and product revenue, subject to agreed fees and provider terms.
- Optionally offer integration, customization, and maintenance.

### Implementation partners
- Offer scoped services for products they are qualified and authorized to implement.
- Agree deliverables, milestones, price, acceptance criteria, and support boundaries with buyers.

### Maketrail
- Operates discovery, listing workflows, trust signals, transaction coordination, and marketplace governance.
- Provides clear terms and auditable transaction records.
- Earns an agreed fee for transactions facilitated through the platform.

## 3. Revenue streams

| Revenue stream | How it works | Initial priority |
|---|---|---:|
| Product transaction commission | Percentage of eligible product sale value | P0 |
| Implementation service commission | Percentage of eligible service transaction value | P0/P1 |
| Optional creator subscription | Paid tools, analytics, or enhanced workflow features | Later |
| Enterprise plans | Team purchasing, private catalogs, procurement and administration | Later |
| Sponsored placements | Clearly labeled paid visibility subject to quality rules | Later |
| Verification services | Potential paid, scoped review service with conflict-of-interest safeguards | Later; validate carefully |

Do not charge creators merely to publish a basic listing in the initial model. Do not let paid placement imply independent verification or better product quality.

## 4. Commission hypothesis

Initial ranges to test—not final pricing:
- Product sales: 10–15% marketplace commission.
- Implementation services: 8–12% marketplace commission.

The actual fee should be tested against buyer willingness to pay, creator economics, payment provider costs, refunds, disputes, taxes, support, verification effort, and acquisition costs.

### Illustrative transaction

Assume a $100 product license, a $200 implementation service, a 12% product commission, and a 10% service commission.

| Item | Amount |
|---|---:|
| Product sale | $100 |
| Product marketplace fee | $12 |
| Product creator gross before other costs | $88 |
| Implementation service | $200 |
| Service marketplace fee | $20 |
| Service provider gross before other costs | $180 |
| Total buyer spend before applicable taxes/fees | $300 |
| Total Maketrail gross marketplace revenue | $32 |
| Total creator/provider gross before other costs | $268 |

This example is arithmetic only. It is not a price recommendation, forecast, payout promise, or statement of tax treatment. Payment processing, refunds, chargebacks, withholding, currency conversion, and applicable taxes may change actual settlements.

## 5. Free, open-source, and paid products

Maketrail should support free products with a clearly identified license, open-source products where the creator has rights to publish and the license is accurately represented, paid commercial products with explicit usage rights, and freemium or paid-support arrangements where terms are clear.

A free/open-source listing should not imply that implementation, support, hosting, or maintenance is also free. Maketrail must not rewrite, obscure, or override an upstream open-source license. Listing terms and marketplace terms must be reviewed for compatibility with the underlying license.

## 6. Product licensing and delivery

The buyer purchases the rights described by the product's license, not automatic ownership of the creator's intellectual property.

Each paid listing must explain what the buyer receives; which license applies; permitted use, project/client limits, seats, redistribution and modification rights as applicable; whether source code, binaries, hosted access, or another delivery method is included; update and support entitlements; refund terms; and third-party/open-source components and notices.

Creators remain responsible for ensuring they have the rights to distribute the product. Maketrail needs a documented takedown and dispute process.

## 7. Implementation services

Product and service transactions must be understandable as separate commercial items, even when bundled.

A service offer should specify provider identity and relevant experience; product and version being integrated; scope and exclusions; deliverables and acceptance criteria; buyer responsibilities and required access; price, currency, taxes where applicable, and payment milestones; timeline and dependencies; support, warranty, and maintenance boundaries; and ownership of custom work and resulting intellectual property.

The original creator should be discoverable as an implementation option, but buyers may choose another qualified provider. Do not imply that a third party is endorsed by the creator unless authorized.

## 8. Payment, fees, and payouts

Use a marketplace-capable payment provider that supports the relevant countries, currencies, seller onboarding, identity/business verification, split payments or platform fees, refunds, disputes, and payouts.

Before enabling transactions in a country, confirm provider availability and the platform's legal, tax, consumer, privacy, and reporting obligations there.

### Payment lifecycle
1. Buyer reviews product/service terms and total price.
2. Buyer starts checkout through the approved provider.
3. Provider processes payment and sends a signed server-to-server event or makes transaction status available through a trusted API.
4. Maketrail verifies the event and records payment state idempotently.
5. Order and entitlement are created only after required payment confirmation.
6. Delivery or service fulfillment begins according to agreed terms.
7. Provider settlement and payout follow provider rules and applicable risk/compliance requirements.
8. Refunds, disputes, reversals, and chargebacks update the order and financial ledger with an audit trail.

A browser redirect alone must never be treated as proof of payment.

### Custody and escrow boundary

Maketrail must not independently hold, pool, or transmit customer funds unless the legal structure and regulated payment arrangements explicitly permit it. Do not market a provider's standard settlement delay or risk review as Maketrail escrow. No payout timing should be promised until provider capabilities and terms are confirmed.

### Financial records

Maintain auditable records for order gross amount and currency; tax and fee components where known; marketplace commission; provider processing fees where available; creator/provider payable amount; refunds, reversals, disputes, and adjustments; payout references and status; and exchange rates/conversion costs where applicable.

Keep marketplace revenue, gross transaction value, creator earnings, and cash settlement distinct in reporting.

## 9. Refunds, disputes, and cancellations

Publish separate rules for digital product delivery and implementation services.

Potential product refund considerations include duplicate charge; payment without delivery or entitlement; materially misrepresented product; license or ownership issue; corrupt or inaccessible delivery; and statutory consumer rights/provider rules.

Potential service dispute considerations include scope not delivered; milestone disagreement; missed deliverable; unauthorized scope change; and access, dependency, or buyer-caused delay.

The policy must explain reporting, evidence, response windows, remedies, and escalation. It must not waive mandatory consumer rights. Do not promise automatic refunds or chargeback outcomes before provider and legal review.

## 10. Creator onboarding and eligibility

Before a creator can receive eligible transaction proceeds, the marketplace/payment provider may need to collect and verify identity, business, tax, bank, and other information.

Requirements vary by country and provider. Collect only necessary information, explain why it is needed, restrict access, and rely on provider-supported onboarding where appropriate. A creator's ability to publish free listings may be separated from eligibility to receive payouts, subject to legal and policy review.

## 11. Unit economics

**Gross transaction value (GTV):** total value of eligible buyer transactions before marketplace fees and adjustments, using a documented definition.

**Marketplace gross revenue:** marketplace fees and other recognized marketplace revenue, not the full GTV.

**Contribution margin per transaction:** marketplace revenue attributable to the transaction minus variable costs such as payment processing, refunds, chargebacks, verification, support, incentives, and other directly attributable costs.

Also track buyer/creator acquisition effort, manual matching time, verification time/cost, support time per order, integration outcome/rework, repeat purchase, and repeat creator activity.

Do not scale a transaction type that has negative contribution margin without an explicit learning rationale and budget.

## 12. Pricing experiments

During concierge validation, test buyer preference for product-only versus product-plus-integration; ask creators what commission they would accept and why; record actual willingness to pay rather than stated preference alone; compare the proposed fee with the value and operating work Maketrail provides; test fixed versus percentage service fees only with real examples; and record payment/currency costs for each supported corridor.

Avoid changing several pricing variables simultaneously when trying to understand behavior.

## 13. Risks and controls

| Risk | Initial control |
|---|---|
| Creator lacks distribution rights | Ownership declaration, evidence review, takedown process |
| Misleading quality/security claims | Evidence-based verification labels and moderation |
| Payment fraud or chargebacks | Provider risk tools, idempotent payment handling, audit trail |
| Regulatory/payment restrictions | Country-by-country launch review and approved provider |
| Tax obligations misunderstood | Professional tax/legal review before cross-border launch |
| Creator payout failure | Provider onboarding and explicit payout status |
| Buyer disputes service quality | Written scope, milestones, acceptance criteria, dispute process |
| Commission economics fail | Track variable costs and contribution margin |
| Paid placement damages trust | Clear labels and no influence on verification status |
| Platform assumes excessive liability | Clear terms, careful claims, appropriate legal/insurance review |

## 14. Decisions still open

1. Which payment provider and countries are supported first?
2. Are product and service transactions both in the first MVP?
3. What exact commission applies to each transaction type?
4. Who is merchant of record or contractual seller in each supported flow?
5. How are taxes, invoices, refunds, chargebacks, and currency conversion handled?
6. What is the payout schedule and what risk controls are provider-managed?
7. What license templates or license metadata are supported?
8. What happens when a creator stops maintaining a purchased product?
9. What support is included in the product price versus separately purchased?
10. What evidence qualifies a creator and product for publication?

## 15. Validation required before approval

- Interview at least 15 target buyers and 20 creators, as set out in the validation plan.
- Test real product and service pricing with qualified opportunities.
- Facilitate paid transactions only through an appropriate existing provider or compliant invoicing arrangement.
- Record actual fees, refunds, support, verification, and manual effort.
- Obtain legal/accounting review for intended launch markets and payment model.
- Approve final rates and terms only after the evidence is reviewed.
