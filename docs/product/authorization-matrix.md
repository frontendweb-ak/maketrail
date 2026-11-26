# MVP authorization and action matrix

**Status:** Working proposal — not approved or frozen  
**Version:** 0.1  
**Last updated:** 2026-11-26  
**Scope:** Inquiry-first productized MVP; commerce and organization permissions are excluded unless separately approved.

This document translates the proposed workflows in [User journeys](user-journeys.md) into resource-level access rules. It is a product/security handoff, not an implementation-specific RBAC design. Every rule must be enforced server-side; hiding a button or route is not authorization.

## 1. Authorization principles

1. Deny by default. Grant the minimum action on the minimum resource for the minimum time.
2. A role is not blanket access. Check both role and relationship to the specific resource.
3. Public access applies only to the currently published listing revision and explicitly public creator fields.
4. Buyers see only inquiries they submitted and responses intended for them.
5. Creators see only their own profile/listings and inquiries explicitly routed to their products.
6. Review, support, and platform administration are distinct duties. Support access does not imply publication authority.
7. No creator may approve, independently verify, or moderate their own listing.
8. Every privileged decision and sensitive access records actor, timestamp, target, action, reason where applicable, and outcome.
9. Client-supplied IDs, role names, status values, or organization claims are never trusted without server-side checks.
10. Guest inquiry, organization workspaces, checkout, order, payout, and entitlement permissions are not part of this baseline.

## 2. Actors

| Actor | Meaning | Baseline access |
|---|---|---|
| Visitor | Unauthenticated public user | Published catalog and public listing/profile fields; may start an inquiry only if guest inquiry is later approved |
| Buyer | Authenticated user who submitted an inquiry | Own inquiries and buyer-visible responses |
| Creator | User authorized for a creator profile/listing | Own creator resources and inquiries routed to those listings |
| Listing reviewer | Explicitly assigned reviewer permission | Assigned listing submissions, rights evidence, review decisions |
| Support operator | Explicitly assigned support permission | Assigned inquiries/support cases and minimum context needed to resolve them |
| Platform administrator | Restricted platform-level operator | Account/role administration and emergency controls; not routine content reviewer by default |

A person may hold more than one role, but conflicting duties must be blocked for the same resource. In particular, a creator cannot review their own listing.

## 3. Resource/action matrix

Legend: **Yes** = allowed within stated relationship; **No** = denied; **Limited** = only specified fields/actions.

| Resource / action | Visitor | Buyer | Creator | Reviewer | Support | Platform admin |
|---|---:|---:|---:|---:|---:|---:|
| Read published listing | Yes | Yes | Yes | Yes | Yes | Yes |
| Read unpublished listing | No | No | Own only | Assigned | Case-limited | Exceptional |
| Read public creator profile | Yes | Yes | Yes | Yes | Yes | Yes |
| Edit creator profile | No | No | Own only | No | No | Exceptional |
| Create/edit listing draft | No | No | Own only | No | No | No |
| Submit own listing | No | No | Yes | No | No | No |
| Read rights/review evidence | No | No | Own submitted evidence/status only | Assigned | Case-limited | Exceptional |
| Request changes / approve / reject | No | No | No | Assigned; conflict check | No | Exceptional audited override |
| Suspend / unpublish listing | No | No | Request only | Authorized reviewer | Escalate only | Emergency authority |
| Create product inquiry | Not in baseline pending guest decision | Yes | Yes, only as buyer | No | No | No |
| Read inquiry | No | Own only | Routed to own listing | No by default | Assigned case only | Exceptional |
| Respond to inquiry | No | Own buyer response | Routed inquiry only | No | Only as operator, visibly attributed | Exceptional |
| Change inquiry routing/status | No | Withdraw/close own inquiry within policy | Respond/request clarification/decline | No | Assigned case actions | Exceptional |
| Read private operator notes | No | No | No | Assigned review notes | Assigned case notes | Exceptional |
| Manage roles/permissions | No | No | No | No | No | Yes, audited |
| Read audit records | No | No | Own action history where exposed | Assigned review audit | Assigned case audit | Restricted |

**Interpretation:** “Exceptional” is not a normal user-interface capability. It requires a documented reason, elevated authorization, audit logging, and review. Platform administrators should not routinely browse private user content.

## 4. Listing lifecycle permissions

| Transition/action | Authorized actor | Required controls |
|---|---|---|
| Draft → Submitted | Listing creator | Creator relationship verified; required fields and rights declaration complete; submitted revision captured |
| Submitted → Changes requested | Assigned reviewer | Reason and actionable feedback required |
| Submitted → Approved / Published | Assigned reviewer other than listing creator | Rights/license review outcome recorded; publication applies only to reviewed revision |
| Submitted → Rejected | Assigned reviewer other than listing creator | Reason and policy basis recorded; appeal/escalation route defined |
| Published → Suspended | Authorized reviewer or emergency operator | Scope, reason, effective time, affected inquiries, and notice decision recorded |
| Suspended → Published | Authorized reviewer | Restriction resolved; fresh review where material changes occurred |
| Any active state → Archived / Unpublished | Creator may request; authorized reviewer executes where policy requires | Existing inquiry handling and public discoverability addressed |

Approval means the listing passed the defined publication review. It does not mean the software was executed, security-certified, independently compatibility-tested, or guaranteed production-safe.

## 5. Inquiry lifecycle permissions

The following transition rules apply to the proposed inquiry states in [User journeys](user-journeys.md). Exact labels can be finalized in feature specifications.

| From | To | Who may initiate | Conditions |
|---|---|---|---|
| Submitted | Awaiting creator | System/operator | Product is still eligible; inquiry passes abuse checks and is routed |
| Submitted | Needs operator review | System/support | Moderation, routing, or policy issue requires intervention |
| Submitted | Withdrawn | Buyer | Buyer owns inquiry |
| Awaiting creator | Response received | Routed creator | Creator is authorized for the product; response is attributable |
| Awaiting creator | Needs buyer information | Routed creator or assigned support | Specific clarification requested |
| Awaiting creator | Closed | Buyer or assigned support | Buyer may close own inquiry; support records reason |
| Response received | Needs buyer information | Routed creator or assigned support | Clarification is needed |
| Response received | Closed | Buyer or assigned support | Closure reason captured where operator closes |
| Needs buyer information | Awaiting creator | Buyer | Buyer supplies requested information; re-route to authorized creator |
| Needs buyer information | Closed | Buyer or assigned support | Closure reason captured where operator closes |
| Needs operator review | Awaiting creator | Assigned support | Issue resolved and creator routing remains valid |
| Needs operator review | Closed | Assigned support | Resolution and reason recorded |
| Closed | Reopened | Support only | Explicit support request and reason; preserve prior history |
| Withdrawn | Closed | System/support | Terminal housekeeping; no further creator response |

A creator must not silently close or erase a buyer inquiry. A buyer cannot change routing, operator notes, or another party's response. A support operator cannot impersonate a buyer or creator.

## 6. Field-level visibility and disclosure

| Information | Visitor | Buyer | Routed creator | Reviewer | Support |
|---|---|---|---|---|---|
| Published listing content | Public fields | Public fields | Own listing | Review fields | Case-relevant |
| Creator private contact/account data | No | No | Own data | Only if necessary for assigned review | Only if necessary for assigned case |
| Buyer project context | No | Own | Only inquiry fields needed to respond | No by default | Assigned case only |
| Buyer email/contact channel | No | Own | Only if approved communication model requires it | No | Assigned case only |
| Rights evidence and private documents | No | No | Own submitted evidence | Assigned review | Case-limited |
| Internal review/support notes | No | No | Creator-visible feedback only | Assigned review | Assigned case |
| Other buyers' inquiries | No | No | No | No by default | No, unless separately assigned and justified |

Prefer platform-mediated replies or a controlled relay until the product/privacy decision on direct contact disclosure is made. Do not expose buyer contact information merely because a creator owns the listing.

## 7. Minimum audit events

At minimum, record:
- Listing submitted, resubmitted, approved, rejected, suspended, restored, or unpublished.
- Rights/evidence review opened and decision recorded.
- Inquiry created, routed, assigned, responded to, withdrawn, closed, or reopened.
- Support/reviewer access to sensitive inquiry or evidence records, including the access purpose.
- Role grant/revocation and emergency administrative action.
- Failed authorization attempts for sensitive resources at a rate suitable for security monitoring.

Audit records should be append-only to ordinary application roles. Define retention and access policy before launch; do not store message bodies, credentials, or unnecessary personal data in audit metadata.

## 8. Required authorization test cases

1. Buyer A cannot read, update, close, or export Buyer B's inquiry by changing an identifier.
2. Creator A cannot read inquiries routed to Creator B or another product.
3. Creator cannot approve, reject, or independently verify their own listing, even if they also hold reviewer permissions.
4. A reviewer cannot access unassigned private evidence or perform finance/payout actions.
5. Support cannot publish, approve, or change rights-review outcomes.
6. An unpublished, rejected, or suspended listing is absent from public catalog, direct public detail routes, and public search results.
7. A creator loses inquiry access when routing is removed or listing access is revoked, subject to documented case-retention needs.
8. A buyer cannot see internal notes, private rights evidence, or another party's contact details.
9. A user cannot gain permissions by editing client state, request payloads, URLs, or cached role data.
10. Revoked roles and expired sessions stop granting access on subsequent server-authorized requests.
11. Emergency admin actions require elevated authorization, a reason, and an audit event.
12. Every denied case is tested as deliberately as each allowed case.

## 9. Decisions required before authorization freeze

| Decision | Current proposal | Must be resolved by |
|---|---|---|
| Buyer inquiry identity | Require authenticated account for private inquiry history; evaluate verified-email guest inquiry separately | Product/privacy |
| Contact disclosure | Keep buyer contact private; use controlled communication first | Product/privacy |
| Reviewer/support separation | Separate permissions, even if one small team member holds both roles | Product/operations |
| Creator onboarding | Creator profile and listing ownership relationship must be explicit; studio/team access deferred | Product |
| Review conflict handling | No self-review; define assignment and escalation | Operations/security |
| Admin override | Exceptional, reasoned, audited, and reviewable | Security/operations |
| Retention and deletion | Define by record type and applicable law | Legal/privacy |
| Appeals | Define creator appeal path for rejection/suspension | Operations |

## 10. Handoff

This matrix is the input to:
1. Feature specifications for identity, listing submission/review, inquiry, and support.
2. API/resource authorization design and negative security tests.
3. Screen specifications for only the included MVP routes.
4. Architecture discovery for identity boundaries, audit events, notification delivery, and private data handling.

It does not approve checkout, orders, entitlements, payouts, organizations, or implementation. Those remain separately gated.

## Related documents

- [MVP scope](mvp-scope.md)
- [End-to-end workflows](user-journeys.md)
- [Information architecture](information-architecture.md)
- [Conceptual domain model](../architecture/domain-model.md)
- [Security baseline](../architecture/security.md)
- [Threat model](../architecture/threat-model.md)
