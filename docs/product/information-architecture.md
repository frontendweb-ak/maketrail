# Maketrail information architecture

**Status:** Proposed information architecture — validate before screen design or route implementation  
**Version:** 0.1  
**Last updated:** 2026-11-24

## 1. Purpose

Define how people enter, navigate, and move between Maketrail's public marketplace, buyer experience, creator studio, and operations console.

This is a product/navigation model, not a final sitemap, URL contract, or approved MVP. The concierge validation pilot does not require these application surfaces to exist. Build only routes needed by a validated productized workflow.

## 2. IA principles

1. Marketplace first: public discovery and evaluation are the center of the product, not a login wall.
2. Intent-led navigation: organize around user tasks, not internal teams or database entities.
3. One human identity, multiple contexts: do not force separate accounts for buyer and creator roles.
4. Separate public and private information: public product/creator pages are indexable; inquiries, orders, drafts, and operational evidence are private.
5. Progressive complexity: expose only navigation needed by the current user and release.
6. Put trust near the decision: license, compatibility, version, maintenance, verification scope, delivery, and support belong in product evaluation.
7. Keep operations distinct: privileged queues and case handling must not be mixed into customer navigation.
8. Design responsive experiences for their tasks, not merely shrunken desktop layouts.
9. No dead ends: empty, pending, rejected, suspended, and failed states explain the next safe action.
10. Keep public product and creator URLs durable and shareable.

## 3. Audiences and surfaces

| Surface | Audience | Primary job | Access |
|---|---|---|---|
| Public marketplace | Visitors, buyers, creators | Discover, evaluate, compare | Public |
| Buyer area | Signed-in buyers | Manage inquiries, purchases, licenses, delivery, support | Authenticated and resource-authorized |
| Creator studio | Creators and authorized collaborators | Publish products, manage listings, respond to demand | Authenticated and creator-resource-authorized |
| Operations console | Reviewers, support, finance, security operators | Review, investigate, resolve, audit | Privileged and explicitly permissioned |

These are experience boundaries, not necessarily separate applications or deployments. One person can move between public marketplace and authorized workspaces using one account.

## 4. Navigation model

### Public header

Primary navigation candidates:
- Explore — catalog and category discovery.
- How it works — buyer process and trust/verification approach.
- For creators — publishing proposition and onboarding information.
- Sign in — authentication.
- Publish a product — creator entry point when onboarding is open.

Provide prominent product search. Keep detailed categories and filters inside discovery rather than filling the global header. Footer links should include About, policies, support, terms, privacy, and relevant buyer/creator guidance.

### Account menu

After sign-in, provide profile/account settings, eligible workspace entry points, help/support, and sign out. Show a workspace switcher only when the user has multiple active contexts. Preserve the intended return destination after authentication where safe. Do not redirect everyone into an irrelevant dashboard.

### Workspace navigation

Buyer and creator workspaces may use a desktop sidebar and compact task-oriented mobile navigation. Label the active surface clearly. Do not combine buyer and creator links into one universal sidebar. The operations console has its own restricted shell.

## 5. Proposed sitemap and route hierarchy

Routes below are illustrative, not frozen URL contracts.

### A. Public marketplace

| Page | Illustrative route | Purpose | Release status |
|---|---|---|---|
| Marketplace home | / | Explain value and guide discovery | Candidate |
| Product catalog | /products | Browse published products | Conditional MVP candidate |
| Search results | /search | Search by problem, product, creator | Search scope TBD |
| Category landing | /categories/{slug} | Browse a validated category | Conditional candidate |
| Product detail | /products/{slug} | Evaluate product and terms | Conditional MVP candidate |
| Creator directory | /creators | Discover creators, if useful | Validate |
| Creator profile | /creators/{slug} | Review identity and published work | Candidate |
| How it works | /how-it-works | Explain buyer process | Candidate |
| For creators | /creators/join | Explain publishing and creator value | Candidate |
| Trust and verification | /trust | Explain labels, evidence and limitations | Candidate |
| Help | /help | Resolve common questions | Candidate |
| Legal pages | /legal/* | Explain applicable policies | Required before relevant launch |

Product detail is a high-value decision page. Organize it in buyer evaluation order:
1. What the product does and who it is for.
2. Demo/media and core capabilities.
3. Technical compatibility: stack, versions, dependencies, environment.
4. License and permitted use.
5. Price or quote process and what is included.
6. Verification label with exact scope, date, version, and limitations.
7. Maintenance, changelog, known issues, and support.
8. Creator identity and optional implementation service.
9. Buyer question/inquiry or purchase action.

Do not hide license, version, limitations, or delivery terms behind low-visibility tabs.

### B. Buyer area

| Page | Illustrative route | Purpose | Release status |
|---|---|---|---|
| Buyer overview | /buyer | Next actions and recent activity | Only if useful |
| Inquiries | /buyer/inquiries | Track questions and requests | Conditional candidate |
| Inquiry detail | /buyer/inquiries/{id} | Context, responses, quote and status | Conditional candidate |
| Orders | /buyer/orders | Purchase history and state | If transactions supported |
| Order detail | /buyer/orders/{id} | Terms, payment state, delivery, support | If transactions supported |
| Library | /buyer/library | Acquired products/entitlements | Validate recurring need |
| Saved products | /buyer/saved | Shortlist products | Later / validate |
| Support | /buyer/support | Product/order support cases | Conditional |
| Account | /account | Personal profile and preferences | As needed |

Do not assume the buyer overview is the first page after sign-in. Route users to the resource or action they intended to reach.

### C. Creator studio

| Page | Illustrative route | Purpose | Release status |
|---|---|---|---|
| Creator overview | /studio | Listing and inquiry actions | Only if useful |
| Creator profile | /studio/profile | Manage public identity | Conditional candidate |
| Products | /studio/products | View products and statuses | Conditional candidate |
| New product | /studio/products/new | Create listing draft | Conditional candidate |
| Edit product | /studio/products/{id}/edit | Maintain listing details | Conditional candidate |
| Submission status | /studio/submissions/{id} | Review status and requested changes | Conditional candidate |
| Inquiries | /studio/inquiries | Respond to qualified buyer inquiries | Conditional candidate |
| Inquiry detail | /studio/inquiries/{id} | Respond to a product requirement | Conditional candidate |
| Services | /studio/services | Manage implementation offers | Later / validate |
| Earnings/payouts | /studio/earnings | Financial activity | Only after provider/legal model |
| Settings | /studio/settings | Creator preferences | As needed |

Creator publishing should be a guided workflow, not one overwhelming form. Candidate steps: product identity, technical fit, license/commercial terms, documentation/demo, ownership declaration, review and submit. Required fields depend on product type and policy.

### D. Operations console

| Page | Illustrative route | Purpose | Access |
|---|---|---|---|
| Operations overview | /ops | Assigned queues and urgent exceptions | Privileged |
| Listing review queue | /ops/listings | Triage submissions | Reviewer |
| Listing review detail | /ops/listings/{id} | Inspect listing, rights, evidence and decide | Reviewer |
| Creators/accounts | /ops/creators | Restricted account support | Specific role |
| Reports/takedowns | /ops/reports | Manage abuse/IP cases | Authorized reviewer |
| Inquiries/support | /ops/support | Case-specific assistance | Support |
| Orders | /ops/orders | Investigate transaction issues | Support/finance as permitted |
| Payments/refunds | /ops/finance | Restricted financial operations | Finance role |
| Verification records | /ops/verification | Manage scoped evidence | Authorized reviewer |
| Audit log | /ops/audit | Review sensitive actions | Restricted |
| Policies/configuration | /ops/settings | Manage approved platform settings | Platform admin |

Operations navigation is permission-aware, but hiding links is only a usability measure. APIs must independently enforce every permission. Avoid one unrestricted admin role for routine tasks.

## 6. Cross-surface entry and handoff

- Publish a product: explain creator value, authenticate if needed, then return to creator setup.
- Ask a question: authenticate only when required; return to the same product and preserve safe form context.
- Buy: show price, license, seller identity, and transaction terms before commitment.
- Creator inquiry response: expose only the relevant inquiry and data needed to respond.
- Operator review: open the relevant case in the restricted operations console.
- Dual-role user: switching surfaces must not discard unsaved work.
- Organization context, if introduced: show the active organization at the point of action; never silently mix personal and organization activity.

## 7. Authentication and access states

Design explicitly for:
- Signed-out public browsing.
- Sign-in and account recovery.
- Buyer capability only.
- Creator capability only.
- Both buyer and creator capabilities.
- Optional organization membership.
- Restricted or suspended account.
- Creator onboarding pending or rejected.
- Operations access denied or elevated authentication required.

Authentication success does not imply creator approval, payout eligibility, organization membership, or operations permission.

## 8. Search and content structure

Search should reflect buyer language, not only internal product labels. Candidate intents include product/creator name, problem/capability, technology and supported version, license/price, and verification/maintenance state.

Start with a narrow validated taxonomy. Do not create empty category pages or filters without enough quality listings. Public product pages should be indexable and shareable; private workspace and operations pages must not be indexed.

## 9. Responsive navigation

- Public: compact header, prominent search, category discovery, simple account access.
- Buyer: prioritize active inquiry/order and delivery tasks.
- Creator: clear listing-creation steps and easy access to drafts/submissions.
- Operations: prioritize queue triage and case detail; do not simply compress dense desktop tables.
- Preserve page titles, back navigation, focus position, and unsaved form state where practical.

Responsive design does not imply a native mobile app is required.

## 10. Conditional MVP route cut

If the productized MVP is approved, the likely smallest route set is:

**Public:** home, catalog, product detail, creator profile only if it improves buyer confidence, and required help/legal pages.

**Buyer:** sign-in/recovery as needed, product-specific inquiry and status, order detail only if a platform-supported transaction is included.

**Creator:** profile setup, product list/draft editor/submission status, and inquiry response only if inquiry is included.

**Operations:** listing review queue/detail and restricted case/support access required by the actual operating model.

Do not build overview dashboards, saved collections, creator analytics, payout screens, enterprise workspaces, or complex settings unless the validated workflow needs them.

## 11. Open questions

1. Is public catalog discovery the primary acquisition channel, or will early buyers arrive through curated matching and referrals?
2. Does a buyer need an account to inquire, or can verified email inquiry be sufficient?
3. Should creators self-publish at launch, or should listings remain operator-curated?
4. Does the first release support direct checkout, quote/request, or both?
5. Does a creator profile materially increase trust for the chosen category?
6. Which buyer details can a creator access, and for how long?
7. Are organization workspaces required for the first buyer workflow?
8. Which pages need search indexing at launch?

## 12. Validation and design handoff

Before high-fidelity UI:
- Test representative buyers finding a suitable product for a real requirement.
- Test whether buyers can identify license, compatibility, support, and verification limits.
- Test creator comprehension of listing submission.
- Test reviewer ability to find rights evidence and make a defensible decision.
- Test whether users understand when acting personally versus for an organization.
- Remove or defer routes that do not support the validated workflow.

Design each page around a user task and acceptance criteria. Do not design every proposed route as approved scope.

## 13. Related documents

- [MVP scope](mvp-scope.md)
- [User journeys](user-journeys.md)
- [Product requirements](prd.md)
- [Architecture strategy](../architecture/architecture-strategy.md)
- [Domain model](../architecture/domain-model.md)
- [Design system](../design-system/README.md)
