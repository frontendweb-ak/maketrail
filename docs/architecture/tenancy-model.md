# Maketrail organization and resource-access model

**Status:** Proposed domain guidance — organization features unvalidated  
**Version:** 0.2  
**Last updated:** 2026-11-24

## 1. Correct framing

Maketrail is a multi-sided marketplace. It should not be treated as a tenant-first SaaS application by default.

The platform has global marketplace resources, individual users, creator identities, optional organizations, transaction participants, and privileged platform operators. Organization workspaces are a possible feature for agencies and studios—not the universal boundary for all data.

This document supersedes the earlier framing that described the recommendation as a tenant-aware architecture. It does not authorize organization workspace implementation.

## 2. Core concepts

- **Platform:** global marketplace, catalog policy, moderation, and operator environment.
- **User:** an individual human account.
- **Creator profile:** public creator identity for an individual or, if validated, a studio.
- **Organization:** optional business/team identity.
- **Membership:** relationship between a user and an organization, with role and status.
- **Buyer context:** whether a specific inquiry/order is personal or made on behalf of an organization.
- **Platform role:** permission to perform a restricted Maketrail operation; unrelated to organization membership.

A user may eventually belong to multiple organizations. A creator may be an individual or studio. Both require validation.

## 3. Resource classes

| Class | Examples | Access principle |
|---|---|---|
| Marketplace-global | Taxonomy, public policies, public search configuration | Platform-managed |
| Public | Published product listings, public creator profiles | Public read, controlled publication |
| User-owned | Account settings, personal inquiries | User and narrowly authorized operations |
| Creator-owned | Drafts, product management, creator settings | Creator owner/collaborators and reviewers as required |
| Organization-scoped (optional) | Shared inquiries, collections, team orders, membership | Active membership plus resource-specific permission |
| Transaction-scoped | Orders, accepted terms, payment references, entitlements | Explicit transaction participants and restricted operations |
| Platform-restricted | Moderation evidence, fraud signals, audit, finance operations | Explicit operator permission and audit |

A resource can involve multiple parties without being owned by all of them. A creator's access to one inquiry does not grant access to the buyer's other activity.

## 4. Authorization rules

1. Authenticate the human account, then authorize each action and resource separately.
2. Apply least privilege and deny by default.
3. Check resource ownership and relationship to the specific transaction or inquiry.
4. If an organization-scoped feature exists, validate active membership and permission server-side on every request and background job.
5. Do not trust a client-supplied organization ID or role.
6. Keep platform operator permissions separate from creator, buyer, and organization roles.
7. Make sensitive support/admin access attributable and auditable.
8. Test denied access, identifier tampering, membership removal, role changes, exports, caches, and background jobs.

## 5. Architecture implications

- Do not add an organization/tenant key to every entity.
- Do not choose database-per-tenant or schema-per-tenant.
- Do not require an organization to register, publish, inquire, or buy unless the validated legal/commercial workflow requires it.
- Record buyer context on the relevant transaction rather than assuming all user activity belongs to an organization.
- Define ownership and access for each resource before schema design.
- Select database-level row security or application authorization only after stack and threat analysis; regardless, enforce authorization in trusted server-side code.

## 6. Validation questions

- Do multiple agency team members actually evaluate and purchase together?
- Who can see an inquiry, order, license, or invoice?
- Are purchases made personally, by a company, or both?
- Is shared visibility sufficient, or are approval/budget controls needed?
- Do creator studios need multiple collaborators?
- What happens to access when a member leaves or a company relationship ends?

If the first validated workflow is individual, keep organization workspaces out of the MVP and preserve the ability to add them later.

## 7. Related documents

- [Architecture strategy](architecture-strategy.md)
- [Domain model](domain-model.md)
- [MVP scope](../product/mvp-scope.md)
- [Threat model](threat-model.md)
