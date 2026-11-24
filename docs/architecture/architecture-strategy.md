# Maketrail architecture strategy

**Status:** Architecture recommendation for review — not an implementation approval  
**Version:** 0.1  
**Last updated:** 2026-11-24

## 1. Executive recommendation

Maketrail should be designed as a **marketplace product with modular business domains**, not assumed to be a multi-tenant SaaS platform.

Recommended starting shape, subject to validation:
- One shared global marketplace and one coherent product experience.
- A modular monolith for the transactional application rather than microservices.
- Responsive, search-engine-friendly web experiences first; native mobile is not a starting requirement.
- Explicit domain ownership and server-side authorization.
- A relational transactional data model as the leading option, with database choice deferred.
- Private object storage only if platform-managed product delivery is proven necessary.
- Provider-hosted payment collection and verified asynchronous payment events if/when checkout is approved.
- A shared design system with distinct experience patterns for public marketplace, buyer, creator, and operations surfaces.

This is a set of reasoned defaults, not a stack selection. Validate the buyer workflow, creator workflow, transaction model, launch jurisdictions, team capability, and cost before freezing implementation choices.

## 2. Start with the business, not the tenancy pattern

Maketrail's core is a multi-sided marketplace:
- Buyers discover and evaluate products.
- Creators publish and maintain products.
- Marketplace operators review listings, handle trust issues, and support transactions.
- A creator or a third-party provider may deliver implementation services.
- Payment providers and other external parties participate in transaction fulfillment.

This does not automatically make every record tenant-owned. The global catalog, taxonomy, verification policy, platform moderation, and marketplace rules are platform-wide. Some personal records belong to a user. Some creator records belong to an individual or studio. Some future buyer workflows may belong to an organization.

Therefore:
- Model users, creator identities, organizations, and platform roles as distinct concepts.
- Treat organization context as optional and explicit.
- Do not require an organization for a buyer or creator to participate.
- Do not add an organization/tenant key mechanically to every table.
- Do not promise shared purchasing, team approvals, private catalogs, or organization billing until validated.
- Enforce resource-level authorization regardless of whether an organization feature exists.

The earlier tenancy proposal should be read as an optional organization and isolation model, not a decision to make Maketrail a tenant-first SaaS product.

## 3. Product surfaces

### Public marketplace
The public experience is a primary acquisition and discovery surface. It needs indexable product pages, creator pages, category pages, clear licensing/compatibility information, fast performance, and accessible browsing.

### Buyer experience
Start with the smallest authenticated capability proven necessary: inquiries, purchase/order visibility, license records, delivery instructions, and support context. Do not assume a full buyer portal with teams, collections, approvals, or budgets.

### Creator experience
Support creator identity, listing drafts, submission/review feedback, and responses to qualified inquiries. Add version management, analytics, team collaboration, and payout dashboards only when needed.

### Operations console
Treat operations as a first-class product surface because trust, moderation, rights review, support, and financial exceptions are central to marketplace quality. Keep it separately permissioned and visually distinct from customer experiences. It may initially share application infrastructure; it does not need a separate microservice architecture.

## 4. Domain boundaries

Keep these business capabilities separate in code and ownership, even if they initially run in one application:

| Domain | Responsibility | Important invariants |
|---|---|---|
| Identity and access | Human accounts, sessions, authentication, authorization | Authentication is not authorization; deny by default |
| Creator identity | Individual/studio creator presence and public profile | A creator profile is not necessarily an organization |
| Catalog | Product, version, category, listing metadata and publication | Only approved public listing versions are discoverable |
| Trust and moderation | Rights declarations, evidence, review cases, reports, takedowns | Claims and verification evidence are distinct and traceable |
| Buyer engagement | Inquiries, product questions, shortlist/intent if validated | Private conversations are visible only to involved parties |
| Commerce | Orders, accepted license/terms snapshots, fee calculation | Historical commercial terms are preserved |
| Payment integration | Provider sessions, events, refunds, reconciliation | Provider-confirmed state; idempotent event processing |
| Fulfillment | Entitlements, delivery instructions, artifact access | Access is derived from an authorized order and policy |
| Services | Implementation offers, quotes, agreements, deliverables | Service agreement is distinct from product license |
| Platform operations | Support, admin actions, policy configuration, audit | Least privilege and attributable sensitive actions |
| Notifications | Delivery of transactional and workflow messages | Retry-safe; source business record remains authoritative |

Do not turn each row into a deployable service. A boundary is first a rule about ownership, APIs, and invariants—not a deployment unit.

## 5. Application topology

### Recommended default: modular monolith

A modular monolith is the best current default because:
- The team and validated workload are not yet known to justify distributed operations.
- Marketplace transactions require consistency across orders, accepted terms, payment events, entitlements, and audit records.
- A single deployable reduces deployment, observability, networking, and incident complexity.
- Clear module boundaries preserve the option to extract a domain later if scale, team ownership, isolation, or release cadence demands it.

Required discipline:
- Modules own their business rules and write operations.
- Avoid arbitrary cross-module database writes.
- Expose explicit application interfaces between modules.
- Keep external provider adapters at integration boundaries.
- Keep domain logic independent from UI and vendor SDKs where practical.
- Add module-level tests for invariants and integration tests for critical journeys.

A modular monolith is not a large unstructured codebase. It needs enforced dependency direction and ownership.

### When to split a service

Extract a service only when evidence shows a concrete need such as independent scaling, separate team ownership, distinct security/isolation requirements, independent availability, or a release cadence that cannot be managed within the application. Define data ownership and failure behavior before extraction.

## 6. Data and integration strategy

### Transactional data
A relational database is the leading candidate because products, versions, listings, creators, orders, licenses, payment events, and entitlements have meaningful relationships and integrity constraints. This is not a vendor decision. Compare team expertise, managed operations, regional availability, backup/restore, security, and cost before selection.

Use explicit foreign-key relationships, unique constraints, and transactional state transitions for critical records. Store money as integer minor units with currency; preserve immutable snapshots of accepted terms and commercial facts.

### Search
Begin with structured catalog data and database-backed search if it meets the selected catalog's relevance and filtering needs. Introduce a dedicated search service only when measured relevance, scale, language, or faceting needs justify the operational cost. The catalog remains the source of truth.

### Files and artifacts
Do not build an artifact hosting pipeline by default. The concierge pilot can use creator-managed delivery where appropriate. If platform-managed downloads become essential, use private quarantine storage, safe metadata handling, scanning, checksums, access authorization, and revocation. Never execute submissions in the application or on a developer workstation.

### Asynchronous work
Use background jobs for work that genuinely needs retry or delay: email, provider events, reconciliation, and scanning if included. Persist the source event/state first. Use idempotency and bounded retries. A transactional outbox may be appropriate when committing a database change and reliably publishing an external event must be atomic; do not introduce a general event bus preemptively.

### External integrations
Keep payment, email, identity, storage, and analytics integrations behind small, explicit adapters. Do not build a generic plugin framework. Preserve provider-specific constraints rather than hiding important differences behind an over-general abstraction.

## 7. Authorization and ownership model

Use a combination of:
- Platform roles for operations capabilities.
- Resource ownership and relationship checks for personal and creator resources.
- Organization membership and role checks only for organization-scoped features that are validated.
- Explicit permissions for sensitive actions such as refunds, suspensions, rights decisions, and payout changes.

Every request and background job must authorize the target resource. Never rely only on a client-supplied organization ID, role name, route guard, or unguessable identifier. Test denied access across user, creator, organization, and platform boundaries.

## 8. Frontend and experience architecture

Use a shared component foundation but preserve distinct information architecture:
- Public marketplace: SEO, discovery, editorial product content, conversion.
- Buyer: orders, licenses, inquiries, delivery, support.
- Creator: listings, review feedback, product lifecycle, buyer leads.
- Operations: queues, evidence, case handling, audit, restricted actions.

Prefer responsive web first. Separate applications or deployments are decisions to make from team/security needs, not an automatic consequence of separate surfaces. Keep public pages server-renderable/indexable where the selected framework supports it.

## 9. Quality attributes to design and test

| Attribute | Why it matters | Early design response |
|---|---|---|
| Security | Money, IP, personal data, uploaded code | Threat-led authorization, quarantine, audit, least privilege |
| Integrity | Orders, licenses, payments, entitlements | Transactional invariants, idempotency, immutable history |
| Discoverability | Marketplace acquisition depends on public pages | SEO, canonical URLs, structured content, fast pages |
| Usability | Buyers need to assess technical fit and terms | Consistent listing schema, plain language, comparison-ready metadata |
| Accessibility | Buyers and creators use varied devices and abilities | Keyboard support, semantic HTML, WCAG 2.2 AA target |
| Reliability | Provider events and delivery may be delayed | Durable states, retries, reconciliation, visible exceptions |
| Operability | Small team cannot run complex infrastructure | Managed services, few deployables, useful audit/monitoring |
| Portability | Early provider decisions may change | Avoid leaking vendor SDKs into domain logic |

Do not set numerical scale, latency, or availability SLOs until there is a real usage profile and launch commitment.

## 10. Deliberately avoid for now

- Microservices, Kubernetes, service mesh, and a distributed event platform.
- Database-per-tenant or schema-per-tenant.
- Mandatory organization workspaces or universal tenant IDs.
- Native mobile apps before mobile-specific demand is established.
- Dedicated search clusters before catalog needs justify them.
- General-purpose artifact hosting, package registry, or code execution.
- AI recommendations and automated security certification.
- Complex enterprise procurement, SSO, private catalogs, or budget approvals.
- Multi-region active-active deployment and premature high-scale optimization.

These may become valid later. They are not current requirements.

## 11. Decisions still open

1. Validated first buyer problem and product category.
2. Whether the first productized workflow needs accounts or can remain concierge.
3. Launch countries, seller/merchant roles, and compliant payment flow.
4. Creator-managed versus platform-managed product delivery.
5. Whether buyers need organization workspaces at launch.
6. Framework, database vendor, hosting, identity provider, and payment provider.
7. Team capability, operating budget, and support capacity.

## 12. Recommended sequence

1. Validate the concierge workflow and actual purchase/integration behavior.
2. Confirm the minimum product surfaces and launch transaction model.
3. Review the domain model and permission matrix against those workflows.
4. Select technology through a short architecture decision record comparing viable options.
5. Prototype the highest-risk flows: listing review, authorization, payment event integrity if checkout is included, and delivery.
6. Freeze only the narrow MVP and its measurable acceptance criteria.
7. Implement and test in vertical slices.

## 13. Related documents

- [Domain model](domain-model.md)
- [Tenancy and organization model](tenancy-model.md)
- [System design](system-design.md)
- [Security baseline](security.md)
- [Threat model](threat-model.md)
- [MVP scope](../product/mvp-scope.md)
- [Feature map](../features/feature-map.md)
