# Maketrail visual mockup register

**Status:** Initial concept reference — not final-approved  
**Register version:** 0.8  
**Created:** 2026-11-24  
**Branch:** `develop`

## 1. Purpose

This register is the index for Maketrail visual mockups. It assigns a stable reference ID to each screen, records where it appears in its source image, and defines how the reference must be used during design refinement and implementation.

A mockup ID identifies a screen concept, not a route contract or a promise that the screen is approved for production.

## 2. Source image

**Mockup set ID:** `MT-VIS-001`  
**Title:** Maketrail — Four-Surface Visual Concept  
**Asset filename:** `a_clean_modern_ui_concept_collage_for_maketrail.png`  
**Canvas:** 1536 × 1024 px  
**Format:** PNG  
**Composition:** Four screen concepts in a 2 × 2 collage.

**Current source asset:** [Open the original mockup image](sandbox:/mnt/data/a_clean_modern_ui_concept_collage_for_maketrail.png)

> Asset hosting note: this link points to the image attachment in the originating ChatGPT conversation. The image binary has not yet been committed to this Git repository, so the sandbox link is not a permanent public GitHub asset URL. Before sharing this register outside the originating conversation or using it as a durable repository asset, copy the original image into the repository (recommended location: `docs/design-system/mockups/MT-VIS-001.png`) and replace this link with its GitHub URL.

## 2.1 Consolidated reference board (new concept)

**Reference board ID:** `MT-BOARD-002`  
**Title:** Maketrail — Consolidated UI Reference Board  
**Asset filename:** `a_clean_flat_maketrail_design_reference_final.png`  
**Canvas:** 1536 × 1024 px  
**Format:** PNG  
**Composition:** Four screen concepts plus a right-side design-token/implementation reference panel.

**Current source asset:** [Open consolidated reference board](sandbox:/mnt/data/a_clean_flat_maketrail_design_reference_final.png)

This board consolidates the four existing screen IDs and introduces visual token suggestions. The generated token values and typography shown in the board are **conceptual proposals only**; they are not approved design-system tokens. The board's “Final” label is artwork text, not an approval status. The screen approval statuses below remain unchanged until explicit review and approval.

## 2.2 Standalone page mockup — Marketplace Home

**Mockup ID:** `MT-MKT-001-v1`  
**Parent screen ID:** `MT-MKT-001`  
**Asset filename:** `a_high_quality_ui_screenshot_of_maketrail_marketpl.png`  
**Format:** PNG  
**Scope:** Standalone desktop public marketplace homepage concept.

**Current source asset:** [Open Marketplace Home standalone mockup](sandbox:/mnt/data/a_high_quality_ui_screenshot_of_maketrail_marketpl.png)

**Screen sections shown:**
1. Global public navigation and account actions.
2. Hero proposition, primary search, and popular topic shortcuts.
3. Marketplace trust/value proposition strip.
4. Category discovery.
5. Featured solution cards with preview, summary, indicative price, license type, and category tags.

**Design review notes:**
- This is the first page-by-page standalone refinement and supersedes the top-left quadrant of `MT-VIS-001` as the current Marketplace Home visual reference.
- The visual direction follows the hybrid editorial-tech proposal: editorial hero, technical marketplace language, and structured commerce cards.
- Product names, category counts, ratings, download counts, prices, and claims are sample content for layout exploration. They are not validated marketplace inventory or real performance evidence.
- The image represents a desktop concept only. Responsive tablet/mobile layouts, menu behavior, search states, loading/empty/error states, accessibility checks, and exact design tokens remain to be specified.
- **Delivery status:** COMPLETED — standalone concept produced and registered.
- **Approval status:** APPROVED / FROZEN — visual reference v1 approved on 2026-11-25. Use this mockup as the authoritative desktop visual target for `MT-MKT-001`; responsive layouts, interaction states, accessibility behavior, and implementation specifications must still be documented before coding.

## 2.3 Standalone page mockup — Product Detail

**Mockup ID:** `MT-PDP-001-v1`  
**Parent screen ID:** `MT-PDP-001`  
**Asset filename:** `a_clean_modern_high_detail_ui_mockup_of_maketrai.png`  
**Format:** PNG  
**Scope:** Standalone desktop product detail page concept.

**Current source asset:** [Open Product Detail standalone mockup](sandbox:/mnt/data/a_clean_modern_high_detail_ui_mockup_of_maketrai.png)

**Screen sections shown:**
1. Global public navigation and breadcrumb trail.
2. Product media gallery with preview and demo affordance.
3. Product identity, summary, indicative rating/download metadata, price and license label.
4. Primary purchase and secondary implementation actions.
5. Product assurances and support/licensing summary.
6. Overview, features, technical details, license and reviews tabs.
7. Creator profile and marketplace trust panel.
8. Feature highlights and technology stack.

**Design review notes:**
- This is the standalone refinement of the top-right quadrant in `MT-VIS-001`.
- The hierarchy emphasizes product evaluation before purchase: preview, fit, license, creator and support context are visible together.
- Product name, rating, review count, download count, price, license, update promise, support duration, verification marker, and trust claims are illustrative placeholders. They must not become real claims without evidence, defined policy, and operational capability.
- The “verified” visual treatment must only be used when a corresponding verification process and evidence record exist; a creator identity or listing approval is not equivalent to code-quality certification.
- **Delivery status:** COMPLETED — standalone concept produced and registered.
- **Approval status:** APPROVED / FROZEN — visual reference v1 approved on 2026-11-25. Use this mockup as the authoritative desktop visual target for `MT-PDP-001`; responsive layouts, interaction states, accessibility behavior, and implementation specifications must still be documented before coding.
- Desktop only; responsive behavior, tab interaction, gallery states, checkout/inquiry states, accessibility, and exact design tokens remain to be specified.

## 2.4 Standalone page mockup — Creator Studio: Product Publishing

**Mockup ID:** `MT-CRT-001-v1`  
**Parent screen ID:** `MT-CRT-001`  
**Asset filename:** `a_clean_modern_dashboard_ui_for_maketrail_creator.png`  
**Format:** PNG  
**Scope:** Standalone desktop creator workspace page, first step of product publishing.

**Current source asset:** [Open Creator Studio standalone mockup](sandbox:/mnt/data/a_clean_modern_dashboard_ui_for_maketrail_creator.png)

**Screen sections shown:**
1. Creator Studio top bar and account controls.
2. Creator navigation sidebar with product, order, implementation, earnings, verification, profile and team areas.
3. Four-step publishing progress: Basic Info, Product Details, Pricing & License, Support & Publish.
4. Basic product information form: name, short description, category and primary technology tags.
5. Contextual publishing tips panel.
6. Save as Draft and Continue to Product Details actions.

**Design review notes:**
- This is the standalone refinement of the bottom-left quadrant in `MT-VIS-001`.
- The screen intentionally uses a creator-focused workspace shell distinct from public marketplace navigation.
- Example product text and technology selections are illustrative content, not a real creator submission or approved field specification.
- The four-step sequence is a proposed workflow; required rights declarations, licensing details, versioning, compatibility, documentation, media, support terms and review requirements need product-policy validation.
- **Delivery status:** COMPLETED — standalone concept produced and registered.
- **Approval status:** APPROVED / FROZEN — visual reference v1 approved on 2026-11-25. Use this mockup as the authoritative desktop visual target for `MT-CRT-001`; responsive layouts, interaction states, accessibility behavior, and implementation specifications must still be documented before coding.
- Desktop only; responsive sidebar behavior, form validation, draft persistence, upload handling, step navigation, accessibility, and exact design tokens remain to be specified.

## 2.5 Standalone page mockup — Operations Console: Listing Review

**Mockup ID:** `MT-OPS-001-v1`  
**Parent screen ID:** `MT-OPS-001`  
**Asset filename:** `a_clean_modern_web_dashboard_ui_maketrail_operat.png`  
**Format:** PNG  
**Scope:** Standalone desktop operations listing-review workspace.

**Current source asset:** [Open Operations Console standalone mockup](sandbox:/mnt/data/a_clean_modern_web_dashboard_ui_maketrail_operat.png)

**Screen sections shown:**
1. Operations-specific application shell and privileged navigation.
2. Listing review queue with pending, in-review, approved and rejected states.
3. Category and recency filters.
4. Selected listing summary, creator identity and submission metadata.
5. Product preview and technical/commercial metadata.
6. Verification evidence checklist covering ownership, license, documentation/demo, compatibility and optional security scan.
7. Review actions: Request Changes, Reject and Approve Listing.

**Design review notes:**
- This is the standalone refinement of the bottom-right quadrant in `MT-VIS-001`.
- The design separates queue triage from detailed evidence assessment and gives reviewers a visible basis for a decision.
- Sample creator names, products, timestamps, statuses, evidence outcomes and counts are illustrative placeholders, not actual submissions or completed checks.
- A missing optional security scan must not automatically imply a product is unsafe; required checks and approval criteria must be defined in policy. Creator declarations, platform moderation, and independent technical verification are distinct evidence types.
- Approval must not imply that submitted software is secure or production-safe unless the platform has a clearly scoped, documented verification process supporting that claim.
- **Delivery status:** COMPLETED — standalone concept produced and registered.
- **Approval status:** APPROVED / FROZEN — visual reference v1 approved on 2026-11-25. Use this mockup as the authoritative desktop visual target for `MT-OPS-001`; responsive layouts, interaction states, accessibility behavior, and implementation specifications must still be documented before coding.
- Desktop only; role permissions, reviewer audit trail, evidence viewing, decision confirmation, escalation, responsive behavior, accessibility, and exact design tokens remain to be specified.

## 2.6 Standalone page mockup — Buyer Workspace: Overview

**Mockup ID:** `MT-BUY-001-v1`  
**Parent screen ID:** `MT-BUY-001`  
**Asset filename:** `a_clean_modern_ui_dashboard_screenshot_for_maketra.png`  
**Format:** PNG  
**Scope:** Standalone desktop authenticated buyer workspace overview.

**Current source asset:** [Open Buyer Workspace standalone mockup](sandbox:/mnt/data/a_clean_modern_ui_dashboard_screenshot_for_maketra.png)

**Screen sections shown:**
1. Buyer workspace shell, global search, notifications and account controls.
2. Buyer navigation: Overview, Inquiries, Orders, My Products, Implementation, Support and Account.
3. Summary metrics for open inquiries, active orders, products in library and implementation projects.
4. Recent activity across inquiries, orders and implementation requests.
5. Contextual pending actions with direct links to the relevant workflow.
6. Stack-relevant product recommendations.
7. Implementation services discovery call-to-action.

**Design review notes:**
- This is a new buyer-surface screen, extending the four initial representative concepts into the authenticated buyer journey.
- The overview is task-oriented: it surfaces pending work and recent transaction activity rather than acting as a generic analytics dashboard.
- User name, counts, product names, activity, order references, statuses, prices and recommendations are illustrative placeholders. They are not real buyer data or validated recommendations.
- Summary metrics must be derived from authorized buyer-owned or buyer-accessible records; do not expose organization or other users' private transactions.
- Recommendations must not imply personalized compatibility unless the buyer's stack/preferences and product compatibility data are actually available.
- **Delivery status:** COMPLETED — standalone concept produced and registered.
- **Approval status:** PENDING — not frozen and not yet an implementation-ready source of truth.
- Desktop only; responsive navigation, empty states, permissions, data freshness, loading/error behavior, and exact design tokens remain to be specified.

## 2.7 Standalone page mockup — Buyer Workspace: My Orders

**Mockup ID:** `MT-BUY-ORD-001-v1`  
**Parent screen ID:** `MT-BUY-ORD-001`  
**Asset filename:** `a_clean_modern_ui_dashboard_screenshot_for_maketr.png`  
**Format:** PNG  
**Scope:** Standalone desktop buyer orders list and selected-order detail view.

**Current source asset:** [Open Buyer Workspace My Orders mockup](sandbox:/mnt/data/a_clean_modern_ui_dashboard_screenshot_for_maketr.png)

**Screen sections shown:**
1. Buyer workspace shell with Orders navigation active.
2. Order summary metrics: total, active, completed and pending action.
3. Order status tabs and search/category/status/sort filters.
4. Selectable order list with product, creator, date, price and status.
5. Selected order detail with order identifier and purchase date.
6. Order lifecycle timeline: placed, payment confirmed, implementation and delivery.
7. Implementation progress, current update and next milestone.
8. Deliverables checklist and buyer actions to view details, contact creator or request an update.

**Design review notes:**
- This is a new buyer-surface screen following the Buyer Workspace Overview concept.
- The layout combines order discovery and selected-order progress to reduce navigation between list and detail views.
- Product/creator names, order references, dates, prices, counts, statuses, progress percentage, updates, milestone estimates and deliverables are illustrative placeholders, not actual transactions or service commitments.
- Product purchase and implementation service must remain distinguishable in order data and terms, even when displayed together in one buyer workflow.
- Progress and delivery estimates must be sourced from an agreed implementation plan and provider updates; never fabricate completion percentages or dates.
- **Delivery status:** COMPLETED — standalone concept produced and registered.
- **Approval status:** PENDING — not frozen and not yet an implementation-ready source of truth.
- Desktop only; order permissions, cancellation/refund/dispute states, status transitions, responsive behavior, empty/error/loading states, audit history, and exact design tokens remain to be specified.

## 3. Screen-to-mockup mapping

| Mockup ID | Screen name | Image position | Intended surface | Primary purpose |
|---|---|---|---|---|
| `MT-MKT-001` | Marketplace Home (Public) | Top-left quadrant | Public marketplace | Search, category discovery, value proposition, trust cues |
| `MT-PDP-001` | Product Detail | Top-right quadrant | Public marketplace | Product evaluation, demo, technical fit, license, price, creator and implementation CTA |
| `MT-CRT-001` | Creator Studio — Product Publishing | Bottom-left quadrant | Creator workspace | Guided product submission and publishing workflow |
| `MT-OPS-001` | Operations Console — Listing Review | Bottom-right quadrant | Operations console | Submission queue, evidence/compliance review and moderation decisions |

### 3.1 MT-MKT-001 — Marketplace Home

- **Reference:** `MT-VIS-001`, top-left.
- **Main elements:** brand/navigation header, marketplace proposition, prominent search, popular topic chips, trust/value strip, category cards.
- **Design intent:** editorial discovery experience with a clear route into relevant software solutions.
- **Do not infer:** final category taxonomy, final navigation labels, verified creator claims, or actual marketplace inventory from placeholder content.

### 3.2 MT-PDP-001 — Product Detail

- **Reference:** `MT-VIS-001`, top-right.
- **Main elements:** breadcrumb, product demo/gallery, product summary, price/license, purchase and implementation actions, product information tabs, creator panel.
- **Design intent:** make technical and commercial evaluation possible on one coherent page.
- **Important correction for future refinement:** ratings, download counts, verification badges, support periods, update promises, and license claims shown in the concept are illustrative placeholders. They must not be presented as real product facts without evidence and approved policy.

### 3.3 MT-CRT-001 — Creator Studio: Product Publishing

- **Reference:** `MT-VIS-001`, bottom-left.
- **Main elements:** creator navigation, multi-step publishing progress, basic information form, category/technology inputs, publishing guidance.
- **Design intent:** make creator submission structured and understandable, with rights, technical, pricing, license, and support requirements introduced at the appropriate steps.
- **Do not infer:** final field list, final step count, creator eligibility rules, or approval guarantees.

### 3.4 MT-OPS-001 — Operations Console: Listing Review

- **Reference:** `MT-VIS-001`, bottom-right.
- **Main elements:** separate operations navigation, listing queue, status filters, selected submission details, evidence/compliance context, review actions.
- **Design intent:** support consistent, explainable review decisions and auditable moderation.
- **Do not infer:** final moderation policy, approval authority, evidence standards, or operational SLAs.

## 4. Shared visual direction

The four screens express the proposed **hybrid editorial-tech** direction:

- Light-first surfaces with a restrained purple accent.
- Editorial spacing and clear product storytelling in public discovery.
- Structured technical metadata where buyers evaluate software.
- Guided forms for creator productivity.
- Denser, task-oriented operations layouts.
- Shared foundations with distinct navigation shells and information density.

The image is a direction-setting concept. It does not establish exact color values, typography, spacing tokens, component dimensions, responsive behavior, or interaction states.

## 5. Source-of-truth and implementation rules

1. Use the stable mockup ID when discussing, reviewing, or implementing a screen.
2. Keep the original composite as the provenance reference until individual screen mockups are created.
3. A refined screen receives a new revision identifier (for example, `MT-MKT-001-v2`); do not silently overwrite the original concept.
4. Record approval status and reviewer/date before calling a mockup implementation-ready.
5. Once approved, implementation must match the approved screen's layout, hierarchy, typography, color, spacing, component states, and responsive behavior. Any intentional deviation must be recorded and approved.
6. Do not implement placeholder ratings, sales/download counts, verification claims, product details, or policy promises as real data.
7. If a screen cannot be built exactly because of platform, accessibility, content, or responsive constraints, document the deviation and obtain approval rather than improvising silently.
8. Keep design tokens and reusable components consistent with the approved mockup set; do not treat this first collage as a complete component specification.

## 6. Delivery status and approval status

- Initial four-screen concept set: **COMPLETED** as a concept baseline (`MT-VIS-001`).
- Consolidated reference board: **COMPLETED** as a second visual reference (`MT-BOARD-002`).
- Design freeze: **DESKTOP SCREENS FROZEN** — `MT-MKT-001-v1`, `MT-PDP-001-v1`, `MT-CRT-001-v1`, and `MT-OPS-001-v1` are approved and frozen as desktop visual references. Responsive behavior, interaction states, and shared design tokens are not yet frozen.
- Implementation readiness: **NOT READY** — all four representative desktop screens are approved, but responsive specifications, interaction states, accessible behavior, and token extraction still remain before implementation.

## 7. Approval status

| Mockup ID | Current status | Next action |
|---|---|---|
| `MT-MKT-001` | Concept only | Refine and review Marketplace Home |
| `MT-PDP-001` | **APPROVED / FROZEN** — standalone visual v1 | Preserve the approved desktop visual; specify responsive and interaction behavior before implementation |
| `MT-CRT-001` | **APPROVED / FROZEN** — standalone visual v1 | Preserve the approved desktop visual; specify responsive and interaction behavior before implementation |
| `MT-OPS-001` | **APPROVED / FROZEN** — standalone visual v1 | Preserve the approved desktop visual; specify responsive and interaction behavior before implementation |
| `MT-BUY-001` | Standalone concept v1 completed; approval pending | Review this page, then specify responsive and interaction states |
| `MT-BUY-ORD-001` | Standalone concept v1 completed; approval pending | Review this page, then specify responsive and interaction states |

No screen in this register is currently approved as a pixel-perfect implementation reference.

## 8. Related documents

- [Visual identity directions](visual-directions.md)
- [Design foundations](foundations.md)
- [Design system overview](README.md)
- [Information architecture](../product/information-architecture.md)
