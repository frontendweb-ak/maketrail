# Transaction lifecycle

**Status:** Conceptual workflow — pending payment provider, legal, and MVP scope decisions  
**Last updated:** 2026-11-24

## 1. Purpose

Describe the expected lifecycle for product and implementation-service transactions. This is a product/operations model, not a payment integration specification or authorization to hold customer funds.

See [business model](../strategy/business-model.md) for revenue, commission, licensing, and unit economics.

## 2. Transaction types

### Product license
Buyer pays for rights defined by a specific product license and receives the delivery or access described in the listing.

### Implementation service
Buyer engages a creator or qualified third party for a defined scope of work.

### Product plus implementation
A buyer may acquire both, but the product license and service agreement must remain separately identifiable with their own deliverables, terms, and dispute conditions.

## 3. Product purchase states

Proposed high-level states:

- draft — buyer has not completed checkout.
- pending_payment — checkout initiated; payment not yet confirmed.
- paid — trusted provider confirmation received and validated.
- fulfillment_pending — paid order requires delivery or access provisioning.
- fulfilled — delivery/access made available as contracted.
- refund_pending — refund requested or being processed.
- partially_refunded — partial refund confirmed.
- refunded — full refund confirmed.
- disputed — payment dispute or chargeback opened.
- cancelled — order cancelled under applicable rules.
- failed — payment failed or expired before confirmation.

Exact state names and transitions must be finalized during technical design.

## 4. Product purchase flow

1. Buyer reviews product details, license, delivery method, price, taxes/fees, refund terms, and support entitlements.
2. Buyer confirms purchase intent.
3. Checkout is created with the selected provider.
4. Provider processes payment.
5. Maketrail validates a signed webhook or retrieves status from a trusted provider API.
6. Payment processing is idempotent; duplicate or delayed events do not create duplicate orders or entitlements.
7. After required confirmation, order and license entitlement are recorded.
8. Delivery is authorized through a controlled mechanism.
9. Buyer receives a receipt/order record and access instructions.
10. Creator receives the appropriate order notification and fulfillment information.
11. Settlement and payout follow provider terms and applicable compliance checks.

A client-side success URL is not sufficient evidence of payment.

## 5. Implementation service flow

1. Buyer describes the required outcome and technical environment.
2. Provider confirms capability, product/version fit, scope, exclusions, and availability.
3. Parties agree price, currency, milestones, deliverables, acceptance criteria, timeline, access, and support boundaries.
4. Payment arrangement is agreed using a supported provider or compliant direct invoicing flow.
5. Work begins when agreed prerequisites are satisfied.
6. Provider submits deliverables or milestone evidence.
7. Buyer accepts or raises a documented issue under the agreed terms.
8. Payment settlement, refund, or dispute follows the approved commercial arrangement.
9. Final documentation and handover are recorded.

Do not imply escrow or milestone custody unless the payment provider and legal structure explicitly support it.

## 6. Commission calculation

For each eligible transaction, store a reproducible fee calculation: transaction type; gross amount and currency; discount and tax treatment; marketplace fee rate and amount; provider processing fees when available; refunds, reversals, and adjustments; creator/provider payable amount; and rule/version used to calculate the fee.

The fee base must be defined in terms before checkout. Do not silently change fee calculation for an order after purchase.

## 7. Refunds and disputes

- Record request, reason, supporting evidence, timestamps, and responsible reviewer.
- Confirm payment provider status before issuing a second refund action.
- Prevent duplicate refund execution through idempotency and reconciliation.
- Update entitlements and delivery access according to license, policy, and legal advice.
- Preserve an auditable record of partial/full refunds and chargebacks.
- Escalate IP, fraud, safety, and legal claims through defined procedures.

## 8. Reconciliation and operational controls

A future transaction system should reconcile internal records with provider records: payments initiated/succeeded/failed/reversed; fees and settlement amounts; refunds and disputes; payouts and payout failures; currency conversion and adjustments.

Every financial state change should have a source reference, timestamp, and audit record. Manual adjustments require a reason and authorized actor.

## 9. Security and reliability requirements

- Verify provider webhook signatures.
- Use idempotency keys for checkout, payment, refund, and payout-related actions where supported.
- Do not trust client-submitted payment status or amounts.
- Enforce authorization for order, download, and license access.
- Use short-lived or otherwise controlled download access where appropriate.
- Avoid exposing sensitive payment data; use provider-hosted/tokenized payment collection.
- Log state transitions without logging secrets or full payment credentials.
- Provide retry, dead-letter, and reconciliation procedures for asynchronous failures.
- Apply least privilege to financial and administrative operations.

## 10. Open questions

- Which provider supports the first launch countries and creator payout needs?
- Who is contractual seller and merchant of record for each transaction?
- Does the provider support platform fees, connected accounts, refunds, and cross-border payouts?
- What taxes and invoices are required in each market?
- What service payment milestones can be supported without Maketrail custody?
- What is the refund and access-revocation policy for each product license?
- What reconciliation frequency and operational owner are required?
