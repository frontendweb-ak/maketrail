# Maketrail security baseline

**Status:** Proposed baseline — requires threat modeling and implementation-specific review  
**Last updated:** 2026-11-24

## 1. Security objectives

Protect:
- Buyer and creator accounts and personal information.
- Product ownership, license, version, and verification records.
- Orders, payment state, fee calculations, entitlements, and delivery.
- Creator-uploaded artifacts and external integrations.
- Admin operations, moderation decisions, and audit records.

Security is a product and operational requirement. A checklist or automated scan alone does not establish that a product or platform is secure.

## 2. Identity and authorization

- Deny access by default and enforce authorization on every server-side operation.
- Separate buyer, creator, support, reviewer, finance, and administrator permissions.
- Check resource ownership and organization membership for every private resource.
- Require stronger authentication for privileged roles and sensitive actions.
- Protect account recovery and email-change workflows against takeover.
- Rate-limit authentication, recovery, inquiry, upload, and other abuse-prone endpoints.
- Revoke sessions and access tokens after account restriction or relevant security events.
- Avoid relying on client-side route guards or hidden UI controls as security boundaries.

## 3. Admin and operations controls

- Use separate admin access policies and least-privilege roles.
- Require MFA or equivalent strong authentication for privileged access.
- Record actor, action, target, timestamp, reason, and relevant before/after state for sensitive operations.
- Require explicit confirmation and, where justified, dual review for high-impact financial or account actions.
- Restrict support access to the minimum data needed and audit access to sensitive records.
- Define reviewer training, escalation, appeals, and emergency access procedures.

## 4. Upload and software supply-chain risks

Threats include malware, malicious packages, archive/path traversal, oversized files, parser exploits, dependency confusion, typosquatting, and deceptive ownership or license claims.

Minimum controls to design:
- Private quarantine storage and generated object keys.
- File size/type limits, archive expansion limits, and path normalization.
- Signature-based file identification and malware scanning where appropriate.
- Dependency and license metadata review with clear limits on what automated tools establish.
- Checksums and immutable version records.
- No execution of submitted artifacts in production or on developer machines.
- Isolated analysis only after a dedicated sandbox threat model and operational review.
- Defined quarantine, rejection, takedown, and incident procedures.

## 5. Payments and financial integrity

- Use hosted/tokenized provider collection; never store raw payment card details.
- Validate provider webhook signatures and event authenticity.
- Make payment, refund, and entitlement processing idempotent.
- Do not trust browser redirects or client-provided payment status.
- Store immutable provider references and auditable financial adjustments.
- Enforce strict permissions for refunds, payout changes, and ledger adjustments.
- Reconcile internal records with provider statements/events.
- Avoid logging credentials, full payment data, or unnecessary personal information.

## 6. Application and API security

Threat-model and test for:
- Broken object-level and function-level authorization.
- Injection, cross-site scripting, cross-site request forgery where relevant, and server-side request forgery.
- Unsafe file handling and path traversal.
- Session fixation, token leakage, and insecure account recovery.
- Rate-limit bypass, enumeration, scraping, spam, and denial of service.
- Insecure direct object references in product, order, artifact, and admin APIs.
- Misconfigured CORS, security headers, cookies, and transport encryption.
- Dependency, build pipeline, and secret-management compromise.

Use secure defaults, parameterized data access, output encoding, input validation, and reviewed dependency updates.

## 7. Privacy and data governance

- Document purpose and lawful basis for personal data processing in each launch jurisdiction.
- Collect the minimum data necessary and define retention periods.
- Provide appropriate access, correction, export, and deletion processes where required.
- Separate public profile information from private account, order, and support data.
- Restrict analytics and logs to necessary fields; avoid sensitive payloads.
- Review third-party processors, data location, cross-border transfer, and breach obligations.
- Establish a process for legal holds and records that cannot be deleted immediately.

## 8. Operational readiness

Before launch, define:
- Security contact and vulnerability-reporting channel.
- Incident severity levels, escalation owner, and response playbooks.
- Credential rotation and emergency revocation.
- Backup encryption, restore testing, and recovery objectives.
- Monitoring for account takeover, suspicious downloads, upload abuse, payment anomalies, and privileged actions.
- Patch and dependency vulnerability response targets.
- Provider outage and webhook backlog procedures.
- Customer/creator notification and legal escalation responsibilities.

## 9. Verification language

Use precise labels:
- **Community Published:** listing passed the stated publication checks; no independent technical verification is implied.
- **Independently Verified:** only when a documented reviewer performed defined checks on a specific version in a stated environment, with date, results, and limitations.

Do not claim “secure,” “safe,” “production-ready,” or “vulnerability-free” from a build, test suite, static scan, or limited review alone.

## 10. Required follow-up

Create a threat model and risk-based test plan once the first MVP flows and architecture choices are approved. This baseline is not a substitute for professional security review, legal review, or implementation-specific testing.
