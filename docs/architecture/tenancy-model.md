# Maketrail tenancy model

**Status:** Proposed domain model — not an approved implementation decision  
**Version:** 0.1  
**Last updated:** 2026-11-24

## 1. Purpose

Define how Maketrail should model users, organizations, creator identities, and data boundaries before detailed feature or database design. This is a logical product model, not a database schema or authorization implementation.

## 2. Recommendation

Design for a **shared global marketplace with optional organization workspaces**.

- Maketrail is one global marketplace with a shared public catalog.
- An organization is a workspace boundary for a business or team using Maketrail.
- A user is a human account and may act personally or as a member of one or more organizations.
- A creator profile is a marketplace identity; it is not automatically the same thing as an organization.
- Public listings are marketplace resources. Private drafts, team inquiries, orders, billing details, and workspace settings need explicit access rules.

Do not create a separate deployment, database, or marketplace instance for every organization by default.

## 3. Core concepts

| Concept | Meaning |
|---|---|
| Platform | Maketrail's global marketplace and operator environment |
| User | Individual authenticated person |
| Organization | Optional workspace representing a business or team |
| Membership | Relationship between a user and an organization, including role and status |
| Creator profile | Public-facing creator identity, belonging to an individual or potentially a studio |
| Product | Reusable software solution offered in the marketplace |
| Listing | A product's marketplace publication and commercial presentation |
| Buyer context | Whether an action is performed personally or on behalf of an organization |

A user may belong to multiple organizations. An organization may have multiple users. These are proposed capabilities to validate, not confirmed requirements.

## 4. Resource ownership and visibility

| Resource | Likely owner/context | Default visibility |
|---|---|---|
| Public product listing | Marketplace / creator | Public after approval |
| Public creator profile | Creator | Public fields only |
| Creator listing draft | Creator or creator organization | Private to authorized collaborators |
| Personal profile and settings | User | User and authorized platform operations |
| Organization profile and membership | Organization | Members according to role |
| Organization inquiry or collection | Organization, if validated | Authorized members only |
| Personal inquiry | User | User and explicitly involved parties |
| Order and accepted license | Buyer context recorded at purchase | Buyer, relevant creator/seller, authorized operations |
| Payment and payout records | Marketplace transaction / relevant account | Strictly restricted |
| Moderation and audit records | Maketrail operations | Restricted by operational role |

Do not give a creator access to an organization's unrelated workspace data merely because the creator is involved in one inquiry or order.

## 5. Authorization principles

1. Authenticate the person; authorize the action and resource. A valid session alone grants no organization or resource access.
2. Organization-scoped actions require active membership and a role permitted to perform the action.
3. When a user belongs to multiple organizations, the acting organization context must be explicit and validated server-side.
4. Deny by default when ownership, membership, or permission evidence is missing.
5. Enforce authorization at every API/service boundary and in background jobs; hiding UI controls is not access control.
6. Prevent cross-organization reads and writes, including identifier-guessing and parameter-tampering attacks.
7. Keep platform operations separate from organization roles. Support, moderation, finance, and security access must be least-privileged and audited.
8. Expose only explicitly published public fields through public catalog endpoints.
9. Limit creator access to buyer information to the specific inquiry/order and agreed fulfillment purpose.
10. Keep personal and organization activity distinguishable. A user's personal purchase does not automatically belong to every organization they join.

## 6. Candidate role model

These are role hypotheses, not a final permission matrix.

**Organization roles**
- Owner: manages organization settings, membership, and ownership transfer.
- Admin: manages members and workspace settings within delegated authority.
- Buyer/member: performs permitted buyer actions for the organization.
- Finance/billing: accesses approved billing and transaction information, if needed.
- Viewer: read-only access to selected workspace resources.

**Platform roles**
- Support: limited case-specific support access.
- Catalog reviewer: listing and rights review.
- Finance operations: restricted transaction/refund/payout operations.
- Security administrator: security and incident response controls.
- Platform administrator: tightly restricted platform configuration.

An organization owner is not a Maketrail platform administrator. Avoid one all-powerful admin role for routine operations.

## 7. Conceptual data implications

If organization workspaces are validated, likely concepts include users, organizations, organization memberships, creator profiles, and explicit organization or buyer-context references on private workspace resources.

Do not mechanically add an organization identifier to every table. Public catalog data, global taxonomies, platform moderation records, and marketplace-wide configuration do not automatically belong to a tenant.

For every resource, document its owner/context, visibility, read/write/export permissions, membership-removal behavior, organization-deletion behavior, and audit/retention obligations.

The database schema, row-level security strategy, and enforcement mechanism remain undecided.

## 8. Isolation and test expectations

Before organization features launch, test that:
- A user with no membership cannot access an organization resource.
- A member of Organization A cannot access Organization B's private resources.
- Removed or suspended membership loses access promptly.
- Role changes take effect on subsequent actions.
- Users in multiple organizations cannot mix contexts.
- Public endpoints expose only published public fields.
- Creators can access only inquiries/orders they are authorized to fulfill.
- Background jobs, exports, caches, and download links enforce the same boundaries.
- Support/admin access is permissioned and audited.

Use negative authorization tests, not only successful-path tests.

## 9. What not to do yet

- Do not implement database-per-tenant or schema-per-tenant isolation without a demonstrated requirement.
- Do not build organization workspaces solely because agencies are the initial buyer hypothesis.
- Do not assume every creator must be an organization.
- Do not equate membership with product ownership, seller status, or payout eligibility.
- Do not expose all organization purchases to every member without an explicit policy.
- Do not select a database vendor or row-level security mechanism in this document.

## 10. Validation questions

Validate whether multiple people need to discover, evaluate, approve, or purchase together; who should see inquiries, orders, licenses, and invoices; whether purchases are personal or business purchases; whether agencies need shared collections or approvals; whether users act for multiple organizations; and whether creator studios need shared profiles and listings.

If one person can complete the first validated workflow, organization workspaces may remain deferred while the domain model preserves a path to add them later.

## 11. Related documents

- [System design](system-design.md)
- [Feature map](../features/feature-map.md)
- [MVP scope](../product/mvp-scope.md)
- [Threat model](threat-model.md)
- [Risk register](risk-register.md)
