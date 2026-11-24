# Maketrail risk register

**Status:** Initial qualitative register — proposed, not evidence-ranked  
**Last updated:** 2026-11-24  
**Owner:** To be assigned

## 1. Purpose

Track product, market, trust, security, legal, financial, and operational risks that could invalidate the Maketrail proposition or make a launch unsafe.

This is an initial planning register. Ratings are hypotheses based on the proposed product model, not measured likelihoods or confirmed incidents. Re-score risks as buyer/creator interviews, provider discussions, legal review, and technical testing produce evidence.

## 2. Rating method

Use a simple qualitative scale:

- **Likelihood:** Low / Medium / High — estimated chance within the next 12 months if the relevant capability launches.
- **Impact:** Low / Medium / High — potential user, financial, legal, operational, or reputation harm.
- **Priority:** Critical / High / Medium / Low — a planning judgment; any High impact risk involving account takeover, payment integrity, untrusted code, IP, or privacy requires explicit mitigation before the related feature launches.

Ratings are provisional. Do not calculate false precision from qualitative labels.

## 3. Risk register

| ID | Risk | Likelihood | Impact | Priority | Mitigation / evidence required | Owner |
|---|---|---|---|---|---|---|
| R-01 | Agencies do not have a frequent enough problem or willingness to pay for third-party software modules | Medium | High | High | Buyer interviews based on recent projects, qualified requirements, paid concierge tests | Product |
| R-02 | Buyers prefer established open-source libraries, internal builds, or existing marketplaces | High | Medium | High | Compare real alternatives and document why buyers reject or choose them | Product |
| R-03 | Creators cannot establish ownership or distribution rights for submitted products | Medium | High | Rights declaration, evidence review, license/dependency checks, takedown process | Trust/Operations |
| R-04 | Product quality, maintenance, or compatibility is inconsistent | High | High | High | Versioned metadata, scoped verification evidence, explicit limitations, update policy | Product/Trust |
| R-05 | Marketplace cannot reliably support buyer and creator countries or payout arrangements | Medium | High | High | Provider eligibility confirmation and country-by-country legal/payment review before checkout | Business/Legal |
| R-06 | Commission revenue does not cover payment, support, verification, refunds, and acquisition costs | Medium | High | High | Measure actual transaction economics and manual effort during concierge validation | Business |
| R-07 | Account takeover or broken authorization exposes private data or enables fraud | Medium | High | High | Threat-modelled access matrix, resource-level authorization tests, privileged MFA and monitoring | Security/Engineering |
| R-08 | Malicious or malformed uploaded artifact compromises platform or reviewer environment | Medium | High | Critical | Quarantine, isolated processing, strict resource limits, no execution in trusted environments | Security/Engineering |
| R-09 | Forged, replayed, or misordered payment events create incorrect orders, refunds, or entitlements | Medium | High | Critical | Signed event verification, idempotency, durable event records, reconciliation and tests | Engineering/Finance |
| R-10 | Entitlement or download controls allow unauthorized access or fail to revoke access appropriately | Medium | High | High | Server-side entitlement checks, scoped links, explicit refund/dispute policy, access tests | Engineering |
| R-11 | Admin misuse or account compromise causes high-impact listing, account, or financial changes | Low/Medium | High | High | Least privilege, strong authentication, audit, step-up/dual approval for sensitive actions | Security/Operations |
| R-12 | Privacy obligations, cross-border processing, or retention practices are not addressed for launch markets | Medium | High | High | Data inventory, purpose/retention policy, processor review, qualified jurisdictional advice | Legal/Privacy |
| R-13 | Verification labels are misunderstood as a guarantee of security or production readiness | Medium | High | High | Plain-language scope, version/date/environment/evidence/limitations, review of marketing claims | Product/Trust |
| R-14 | Refunds, chargebacks, service disputes, or IP complaints exceed operational capacity | Medium | High | High | Written policies, case workflows, escalation ownership, support-cost measurement | Operations |
| R-15 | Spam, scraping, fake listings, fake reviews, or creator impersonation reduce trust | Medium | Medium | Medium | Account friction proportional to risk, moderation, verified-purchase rules, rate limits | Trust/Operations |
| R-16 | External provider outage or integration change interrupts checkout, notifications, or delivery | Medium | Medium | Medium | Provider abstraction where useful, retry/reconciliation, outage messaging, documented fallback | Engineering |
| R-17 | Scope expands into enterprise, mobile, subscriptions, chat, or microservices before core demand is proven | High | Medium | High | MVP gate, feature lifecycle, decision records, evidence-based prioritization | Product |
| R-18 | Team lacks capacity to operate verification, support, compliance, and incident response | Medium | High | High | Estimate manual effort, define service levels/owners, limit launch regions and catalog size | Leadership |
| R-19 | Dependency or build pipeline compromise introduces malicious code into platform | Low/Medium | High | High | Protected CI, secret isolation, dependency review, provenance and patch process | Engineering/Security |
| R-20 | Backup failure or poor recovery process causes permanent loss or prolonged outage | Low/Medium | High | High | Backup policy, restore tests, recovery objectives, restricted backup access | Engineering/Operations |

## 4. Immediate launch gates

The following are launch blockers for the corresponding capabilities, not necessarily blockers for a no-payment discovery prototype:

### Public catalog and creator publishing
- Ownership and license review process exists.
- Abuse reporting, moderation, suspension, and takedown process has an accountable owner.
- Public claims distinguish creator declarations from independently verified evidence.
- Uploads are not executed in trusted application or developer environments.

### Accounts and private workspaces
- Resource-level authorization is tested across roles and object identifiers.
- Account recovery, session revocation, rate limits, and privileged access controls are defined.
- Privacy notice, data inventory, and retention rules are reviewed for launch jurisdictions.

### Checkout and payouts
- Provider approves the business model and supported countries.
- Seller/merchant roles, tax/invoice responsibilities, refunds, disputes, and payout terms are reviewed.
- Server-side payment verification, idempotency, reconciliation, and audit are tested.
- No unsupported escrow or custody claims are made.

### Artifact delivery
- Private storage, quarantine, scanning policy, access authorization, and revocation behavior are tested.
- Artifact processing is isolated from production secrets and trusted workloads.
- Incident and takedown procedures are documented.

### Independent verification
- Reviewer competence, evidence standards, version scope, reproducibility, and limitations are defined.
- Verification claims do not imply a security guarantee.

## 5. Evidence tracking

For each risk, future updates should record:
- Evidence source and date.
- What was observed versus inferred.
- Current rating and rationale.
- Mitigation owner and due date.
- Residual risk and acceptance authority.
- Review date and trigger.

Do not mark a risk resolved merely because a policy or design document exists. Resolution requires evidence that the control is implemented and effective for the relevant scope.

## 6. Review cadence

- Review market and business risks after each interview/concierge validation cycle.
- Review security and operational risks at each MVP scope change and before each public launch gate.
- Revisit provider, privacy, and legal risks when launch countries, payment model, or data flows change.
- Review open High/Critical risks at every release decision.

## 7. Related documents

- [Threat model](threat-model.md)
- [System design](system-design.md)
- [Security baseline](security.md)
- [Market validation plan](../strategy/market-validation.md)
- [Business model](../strategy/business-model.md)
