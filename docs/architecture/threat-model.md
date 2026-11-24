# Maketrail threat model

**Status:** Initial qualitative threat model — proposed, not a security assessment  
**Version:** 0.1  
**Last updated:** 2026-11-24  
**Scope:** Conceptual marketplace flows described in the current product and architecture documents

## 1. Purpose and limitations

Identify plausible threats to Maketrail's users, creators, marketplace operations, transactions, and software artifacts so that product scope and future engineering work account for security from the start.

This is a desk-based, architecture-level exercise. It is not based on a deployed system, penetration test, code review, external audit, or confirmed incident data. Likelihood and impact are provisional and must be revised when the MVP, providers, countries, and implementation are known.

## 2. System under consideration

In scope:
- Public marketplace catalog and product pages.
- Buyer and creator accounts and authenticated workflows.
- Creator product listings, ownership declarations, and uploads.
- Listing moderation and independent verification workflows.
- Orders, payment-provider integration, licenses, entitlements, and delivery.
- Admin/support operations and audit records.
- Notifications and external integrations.
- Future implementation-service workflows, where included in MVP.

Out of scope for this first pass:
- Detailed cloud/network architecture, because no provider or topology is selected.
- Specific framework vulnerabilities and implementation-level code paths.
- Provider-specific payment threat analysis.
- Formal legal/privacy impact assessment.
- Dynamic analysis sandbox design.

## 3. Assets to protect

| Asset | Why it matters | Security objective |
|---|---|---|
| Account credentials and sessions | Account takeover and impersonation | Confidentiality, integrity, availability |
| Buyer/creator personal data | Privacy, fraud, trust, legal obligations | Confidentiality and controlled retention |
| Creator ownership and license evidence | IP rights and marketplace legitimacy | Integrity, provenance, access control |
| Product listings and versions | Buyer decisions and creator reputation | Integrity and traceability |
| Uploaded packages and source artifacts | May contain malicious or sensitive content | Isolation, integrity, controlled access |
| Orders and accepted terms | Commercial and legal record | Integrity, availability, auditability |
| Payment events and ledger | Financial loss and reconciliation | Integrity, authenticity, non-duplication |
| Entitlements and download links | Paid access and IP protection | Authorization, integrity, revocability |
| Verification records and reviews | Buyer trust and reputation | Integrity, provenance, transparency |
| Admin permissions and actions | High-impact platform control | Least privilege, accountability |
| Secrets, API tokens, signing keys | Control over platform and providers | Confidentiality, rotation, revocation |
| Backups and logs | Recovery and incident investigation | Confidentiality, integrity, availability |

## 4. Actors and trust boundaries

### Actors
- Anonymous visitor.
- Registered buyer.
- Creator or studio.
- Implementation provider.
- Marketplace reviewer/verifier.
- Support and finance operator.
- Administrator.
- Payment, email, storage, identity, and other external providers.
- Malicious or compromised account holder.
- Malicious uploader or third-party package author.

A legitimate account must not automatically be treated as trustworthy. Creators can make inaccurate claims, accounts can be compromised, and third-party artifacts can be malicious.

### Trust boundaries
1. Browser/mobile client ↔ application API.
2. Public catalog ↔ authenticated buyer/creator data.
3. Creator-submitted content ↔ platform-controlled systems.
4. Quarantined artifacts ↔ any analysis or delivery environment.
5. Marketplace application ↔ payment provider.
6. Application ↔ email, storage, identity, and other providers.
7. Standard user/support role ↔ privileged admin/finance role.
8. Application runtime ↔ production secrets, databases, and backups.

Data crossing a boundary requires validation, authorization, and an explicit trust decision. Client input and creator-supplied artifacts are untrusted.

## 5. Threat analysis (STRIDE-informed)

| ID | Threat scenario | Primary risk | Required design response |
|---|---|---|---|
| TM-01 | Attacker steals credentials or abuses account recovery to take over a buyer/creator account | Account takeover, unauthorized purchases, listing changes, private data exposure | Strong session controls, secure recovery, MFA for privileged users, rate limits, anomaly monitoring |
| TM-02 | User changes an object ID to access another buyer's order, artifact, profile, or private inquiry | Broken object-level authorization and data disclosure | Server-side ownership/permission checks on every resource operation; negative authorization tests |
| TM-03 | Creator uploads a malicious archive/package that exploits a parser or is accidentally executed | Platform compromise, malware distribution, reviewer workstation compromise | Quarantine, strict parsing limits, isolated scanning, no execution on app/primary workstations |
| TM-04 | Malicious archive uses path traversal, decompression bombs, or oversized content | Storage exhaustion, arbitrary overwrite, worker denial of service | Generated object keys, safe archive handling, quotas, expansion limits, time/resource bounds |
| TM-05 | Creator lists third-party code without distribution rights or uses a misleading license | IP claims, takedowns, buyer loss, legal exposure | Rights declaration, evidence review, license/dependency checks, complaint/takedown process |
| TM-06 | Creator claims compatibility, verification, or security not supported by evidence | Buyer harm, reputational damage, disputes | Separate declared claims from tested facts; version-scoped evidence and precise public labels |
| TM-07 | Attacker forges, replays, duplicates, or reorders payment events | Fraudulent order state, duplicate fulfillment/refund, ledger mismatch | Provider signature verification, event ID deduplication, idempotent state transitions, reconciliation |
| TM-08 | Buyer manipulates browser success URL or client payload to obtain paid access | Unauthorized entitlement/download | Grant access only from server-verified provider state and policy-approved order state |
| TM-09 | Attacker guesses or reuses download URL or obtains leaked object key | Unauthorized artifact access | Private storage, short-lived scoped access, entitlement checks, revocation and access logging |
| TM-10 | Compromised admin/support account changes listing, payout, refund, or account state | High-impact fraud and abuse | Least privilege, strong authentication, step-up/dual approval for selected actions, immutable audit |
| TM-11 | Insider or compromised operator accesses buyer/creator data without a support need | Privacy breach and trust loss | Scoped support permissions, access audit, data minimization, periodic access review |
| TM-12 | Search, inquiry, review, or registration endpoints are abused for scraping, spam, enumeration, or denial of service | Service degradation, privacy leakage, creator harassment | Rate limits, anti-automation controls, abuse reporting, safe public data boundaries |
| TM-13 | Malicious listing content or external links deliver phishing, XSS, or SSRF payloads | Account compromise, internal service access, browser compromise | Output encoding, safe URL policy, server-side request restrictions, content sanitization |
| TM-14 | API key, webhook secret, signing key, or deployment credential leaks | Full or partial platform/provider compromise | Managed secret storage, narrow scopes, rotation, environment separation, access audit |
| TM-15 | Vulnerable dependency or compromised build pipeline introduces malicious code | Supply-chain compromise | Dependency review, lockfile integrity, automated scanning, protected CI, artifact provenance |
| TM-16 | Backup or log contains credentials, payment data, or unnecessary personal information | Secondary data breach | Data minimization, redaction, encryption, restricted access, retention and restore controls |
| TM-17 | Refund/chargeback is processed but entitlement remains active, or access is revoked incorrectly | Financial loss, unfair denial, dispute escalation | Explicit state-transition policy, reconciliation, idempotent revocation, support recovery |
| TM-18 | Provider outage or delayed webhook leaves payment and order states inconsistent | Duplicate action, delayed fulfillment, support burden | Durable event records, retry/backoff, pending states, reconciliation and operator tooling |
| TM-19 | Creator or buyer disputes service scope, deliverables, or acceptance | Commercial disputes and reputational harm | Separate service agreement, explicit scope/acceptance terms, evidence and escalation |
| TM-20 | Personal data is retained, transferred, or exposed without a defined basis or process | Regulatory and user harm | Jurisdiction review, purpose limitation, retention schedule, rights handling, processor review |

## 6. Abuse cases and security requirements

### Buyer account
- A buyer must not access another buyer's orders, invoices, inquiries, or downloads by changing an identifier.
- A buyer must not obtain paid access by replaying a checkout URL or editing client state.
- A buyer must be able to identify the product version, license, seller/provider, and terms associated with an order.

### Creator account
- A creator must not edit another creator's listings or view their private sales/customer data.
- A creator must not publish a listing before required review is complete.
- A creator must not self-award independent verification or alter reviewer evidence.
- A creator must not access buyer data beyond what is required to fulfill a legitimate transaction.

### Admin and support
- Support staff must not automatically receive finance, payout, or security-administration permissions.
- Privileged actions must be attributable to an authenticated actor and have a recorded reason where appropriate.
- High-impact actions need explicit authorization and a recovery/escalation path.

### Artifact handling
- Uploads must remain quarantined until the defined checks are complete.
- Artifact processing must not inherit production credentials or unrestricted network access.
- Download access must be checked server-side and should be revocable under defined order/license rules.

### Payment processing
- Duplicate or out-of-order events must not create duplicate orders, ledger entries, refunds, or entitlements.
- The application must distinguish provider-reported state from internal processing state.
- Manual corrections must preserve the original record and an auditable adjustment.

## 7. Highest-priority control themes

1. **Authorization:** resource-level checks for every private object and privileged action.
2. **Payment integrity:** verified provider events, idempotency, and reconciliation.
3. **Artifact isolation:** quarantine and safe handling; never execute submissions in trusted environments.
4. **Admin security:** least privilege, strong authentication, and complete audit.
5. **IP and verification integrity:** evidence-backed rights and version-scoped claims.
6. **Privacy:** collect less, restrict access, and define retention and jurisdictional obligations.
7. **Operational recovery:** backups, incident response, webhook/job retries, and abuse monitoring.

## 8. Launch-blocking questions

Do not launch the relevant capability until these are answered and evidenced:
- What are the launch countries, legal seller roles, and payment-provider responsibilities?
- What personal data is collected, why, where processed, and for how long?
- What exact roles and permissions exist for support, reviewers, finance, and administrators?
- How are uploads quarantined, scanned, retained, and removed?
- How are payment events authenticated, deduplicated, retried, and reconciled?
- What conditions grant, suspend, or revoke entitlements?
- How are ownership complaints, malware reports, vulnerabilities, and takedowns handled?
- Who owns incident response, customer communications, and provider escalation?

## 9. Validation plan

Before implementation:
- Map the actual MVP data flows and trust boundaries.
- Assign an owner and evidence requirement to every high-priority control.
- Convert threats into feature acceptance criteria and negative tests.
- Review payment and privacy flows with relevant providers and qualified professionals.
- Obtain an implementation-specific security review before public launch.

After implementation:
- Test authorization across roles and resource IDs.
- Test webhook forgery, replay, duplication, delay, and out-of-order delivery.
- Test upload size, archive, parser, and quarantine boundaries without executing malicious samples in trusted environments.
- Test admin privilege separation and audit completeness.
- Test backup restoration, incident response, and entitlement recovery.

## 10. Related documents

- [System design](system-design.md)
- [Security baseline](security.md)
- [Risk register](risk-register.md)
- [Transaction lifecycle](../product/transaction-lifecycle.md)
- [Market validation plan](../strategy/market-validation.md)
