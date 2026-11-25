# Maketrail visual mockup register

**Status:** Initial concept reference — not final-approved  
**Register version:** 1.7  
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
- **Approval status:** APPROVED / FROZEN — visual reference v1 approved on 2026-11-25. Use this mockup as the authoritative desktop visual target for `MT-BUY-IMPL-001`; responsive layouts, interaction states, accessibility behavior, and implementation specifications must still be documented before coding.
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
- **Approval status:** **APPROVED / FROZEN** — approved 2026-11-25.
- Desktop only; order permissions, cancellation/refund/dispute states, status transitions, responsive behavior, empty/error/loading states, audit history, and exact design tokens remain to be specified.

## 2.8 Standalone page mockup — Buyer Workspace: My Products

**Mockup ID:** `MT-BUY-PROD-001-v1`  
**Parent screen ID:** `MT-BUY-PROD-001`  
**Asset filename:** `a_clean_modern_marketplace_ui_maketrail_buyer_wor.png`  
**Format:** PNG  
**Scope:** Standalone desktop buyer product library.

**Current source asset:** [Open Buyer Workspace My Products mockup](sandbox:/mnt/data/a_clean_modern_marketplace_ui_maketrail_buyer_wor.png)

**Screen sections shown:**
1. Buyer workspace shell with My Products navigation active.
2. Library summary metrics: total products, active licenses, implementation projects and available updates.
3. Product state tabs: all, active, in implementation and archived.
4. Grid/list view affordance.
5. Product cards with preview, product/creator identity, license version/update metadata and status.
6. Contextual actions: Open, Resources, View Progress, View Update and Changelog.

**Design review notes:**
- This is a new buyer-surface screen for accessing acquired software and related resources.
- The product library is distinct from the order history: it represents access/entitlements and current product versions, not the original transaction record.
- Sample product names, creator names, product counts, license counts, implementation counts, version numbers, dates, update states and progress percentages are illustrative placeholders, not real buyer entitlements or release data.
- Access must be derived from a valid entitlement and checked server-side for every product artifact/resource. A visible library card alone must never grant access.
- Updates must respect the buyer's purchased license terms and supported version policy; do not imply lifetime updates unless that entitlement was explicitly purchased.
- **Delivery status:** COMPLETED — standalone concept produced and registered.
- **Approval status:** APPROVED / FROZEN — visual reference v1 approved on 2026-11-25. Use this mockup as the authoritative desktop visual target for `MT-BUY-ACC-001`; responsive layouts, interaction states, accessibility behavior, and implementation specifications must still be documented before coding.
- Desktop only; entitlement/expiry states, revoked/refunded access, update compatibility, download security, empty/error/loading states, responsive behavior and exact design tokens remain to be specified.

## 2.9 Standalone page mockup — Buyer Workspace: Inquiries

**Mockup ID:** `MT-BUY-INQ-001-v1`  
**Parent screen ID:** `MT-BUY-INQ-001`  
**Asset filename:** `a_clean_modern_ui_dashboard_screenshot_for_maketra.png`  
**Format:** PNG  
**Scope:** Standalone desktop buyer inquiry management and conversation view.

**Current source asset:** [Open Buyer Workspace Inquiries mockup](sandbox:/mnt/data/a_clean_modern_ui_dashboard_screenshot_for_maketra.png)

**Screen sections shown:**
1. Buyer workspace shell with Inquiries navigation active.
2. Inquiry summary metrics: total, awaiting response, quotes received and converted to orders.
3. Inquiry status tabs and new inquiry action.
4. Searchable inquiry list with product, creator, reference, recency and status.
5. Selected inquiry conversation with message history and attachment.
6. Conversation tabs for quotation, details and activity.
7. Inquiry summary and latest quotation panel.
8. Actions to view quotation, convert to order and continue discussion.

**Design review notes:**
- This screen provides the buyer-side workflow for clarifying product fit, requesting implementation scope, receiving a quote and deciding whether to proceed.
- The conversation is tied to an inquiry record and must not become an unrestricted general-purpose chat system by implication.
- Sample inquiry IDs, creator names, message text, timestamps, quotation amount, timeline and counts are illustrative placeholders, not real communications or commercial offers.
- A quote must have explicit scope, price/currency, validity, deliverables, exclusions, provider identity and acceptance state. “Convert to Order” must only be available when a valid quote/offer is accepted and the transaction terms are recorded.
- Message and attachment access must be limited to authorized inquiry participants and platform operators with an appropriate support/moderation reason.
- **Delivery status:** COMPLETED — standalone concept produced and registered.
- **Approval status:** **APPROVED / FROZEN** — approved 2026-11-25.
- Desktop only; unread/read states, message delivery failures, attachments, quote expiry/revision, inquiry closure, participant permissions, responsive behavior, and exact design tokens remain to be specified.

## 2.10 Standalone page mockup — Buyer Workspace: Implementation

**Mockup ID:** `MT-BUY-IMPL-001-v1`  
**Parent screen ID:** `MT-BUY-IMPL-001`  
**Asset filename:** `a_clean_modern_web_ui_dashboard_in_white_and_soft.png`  
**Format:** PNG  
**Scope:** Standalone desktop buyer implementation-project overview.

**Current source asset:** [Open Buyer Workspace Implementation mockup](sandbox:/mnt/data/a_clean_modern_web_ui_dashboard_in_white_and_soft.png)

**Screen sections shown:**
1. Buyer workspace shell with Implementation navigation active.
2. Summary metrics for active projects, in-progress, completed and at-risk projects.
3. Project status tabs and request-implementation action.
4. Searchable implementation project list with creator, status, progress and due date.
5. Selected project overview with order reference and workflow tabs for overview, tasks, files, communication and updates.
6. Project progress timeline with milestones from order confirmation through go-live.
7. Current phase checklist and recent activity feed.
8. Project team and buyer next-action panel.

**Design review notes:**
- This is a buyer-side view of separately agreed implementation work, not a claim that every product purchase includes implementation.
- Example project names, creators, order IDs, progress percentages, dates, milestones, activity and checklist states are illustrative placeholders, not real delivery commitments.
- Project progress and due dates must be derived from an agreed scope, milestone plan and authorized provider updates. Avoid fabricated percentages or implied guarantees.
- Implementation service scope, deliverables, acceptance criteria, change requests, payment terms and dispute handling must be explicit and distinct from the product license/order.
- **Delivery status:** COMPLETED — standalone concept produced and registered.
- **Approval status:** APPROVED / FROZEN — visual reference v1 approved on 2026-11-25. Use this mockup as the authoritative desktop visual target for `MT-CRT-OVW-001`; responsive layouts, interaction states, accessibility behavior, and implementation specifications must still be documented before coding.
- Desktop only; milestone editing, task ownership, file permissions, change requests, delayed/blocked states, buyer/provider communication rules, responsive behavior and exact design tokens remain to be specified.

## 2.11 Standalone page mockup — Buyer Workspace: Support Center

**Mockup ID:** `MT-BUY-SUP-001-v1`  
**Parent screen ID:** `MT-BUY-SUP-001`  
**Asset filename:** `a_clean_modern_ui_dashboard_screenshot_white_lig.png`  
**Format:** PNG  
**Scope:** Standalone desktop buyer support request and ticket conversation view.

**Current source asset:** [Open Buyer Workspace Support Center mockup](sandbox:/mnt/data/a_clean_modern_ui_dashboard_screenshot_white_lig.png)

**Screen sections shown:**
1. Buyer workspace shell with Support navigation active.
2. Support metrics: open tickets, awaiting buyer reply and resolved requests.
3. Support request filters and searchable ticket list.
4. Selected ticket conversation with message history and attachments.
5. Ticket tabs for conversation, attachments and activity.
6. Related product and order context.
7. Support scope and entitlement summary.
8. Helpful documentation and support resources.
9. Reply composer and create-support-request action.

**Design review notes:**
- This screen is for post-purchase help with product access, licensing, downloads and separately agreed implementation support.
- Sample ticket IDs, products, order references, messages, timestamps, attachment names, support coverage and status counts are illustrative placeholders, not actual tickets or policy commitments.
- Support eligibility, duration, response expectations and included/excluded work must come from the buyer's actual license or service agreement. Do not hard-code the sample “90 days” or imply implementation support is included by default.
- Attachments and logs must warn users not to submit passwords, tokens, private keys, personal data or production secrets. Access to tickets and files is restricted to authorized participants and support staff.
- **Delivery status:** COMPLETED — standalone concept produced and registered.
- **Approval status:** **APPROVED / FROZEN** — approved 2026-11-25.
- Desktop only; ticket creation validation, priority/severity rules, SLA policy, secure attachment handling, redaction, escalation, responsive behavior and exact design tokens remain to be specified.

## 2.12 Standalone page mockup — Buyer Workspace: Account & Settings

**Mockup ID:** `MT-BUY-ACC-001-v1`  
**Parent screen ID:** `MT-BUY-ACC-001`  
**Asset filename:** `a_clean_modern_saas_dashboard_ui_screenshot_for_ma.png`  
**Format:** PNG  
**Scope:** Standalone desktop buyer account and settings overview.

**Current source asset:** [Open Buyer Workspace Account & Settings mockup](sandbox:/mnt/data/a_clean_modern_saas_dashboard_ui_screenshot_for_ma.png)

**Screen sections shown:**
1. Buyer workspace shell with Account navigation active.
2. Settings navigation for profile, security, organization, notifications, billing/payments and privacy/account actions.
3. Profile summary and editable personal/contact fields.
4. Organization and team membership summary.
5. Security summary with password, two-factor authentication and login activity.
6. Notification preference controls.
7. Billing and payment method, invoices and billing details entry points.
8. Privacy controls including data export and account deletion entry points.

**Design review notes:**
- This is a consolidated settings overview; sensitive workflows such as password changes, 2FA recovery, payment method management, tax details, data export and account deletion should use dedicated confirmation and verification flows.
- Names, email addresses, phone numbers, company, location, verification marks, team size, 2FA state and payment method details shown are illustrative placeholders, not user data or implemented account states.
- Do not imply that email, phone, identity or organization is verified without a real verification process and stored evidence. Never expose full payment credentials.
- Organization membership and role changes require explicit authorization and clear impact messaging. Account deletion must explain effects on orders, licenses, financial records and legal retention before confirmation.
- **Delivery status:** COMPLETED — standalone concept produced and registered.
- **Approval status:** APPROVED / FROZEN — visual reference v1 approved on 2026-11-25. Use this mockup as the authoritative desktop visual target for `MT-CRT-PROD-001`; responsive layouts, interaction states, accessibility behavior, and implementation specifications must still be documented before coding.
- Desktop only; field validation, security challenge flows, recovery, organization role permissions, billing provider behavior, notification defaults, data export/deletion lifecycle, responsive behavior and exact design tokens remain to be specified.

## 2.13 Standalone page mockup — Creator Studio: Overview

**Mockup ID:** `MT-CRT-OVW-001-v1`  
**Parent screen ID:** `MT-CRT-OVW-001`  
**Asset filename:** `a_clean_modern_saas_dashboard_ui_for_maketrail_cr.png`  
**Format:** PNG  
**Scope:** Standalone desktop creator workspace overview.

**Current source asset:** [Open Creator Studio Overview mockup](sandbox:/mnt/data/a_clean_modern_saas_dashboard_ui_for_maketrail_cr.png)

**Screen sections shown:**
1. Creator Studio shell and creator-specific navigation.
2. Summary metrics for published products, pending reviews, buyer inquiries and monthly earnings.
3. Creator product list with category, listing status and last-updated date.
4. Creator profile completion checklist.
5. Action-required review feedback card.
6. Recent product, inquiry and order activity.
7. Creator education and policy resources.

**Design review notes:**
- This is the creator's operational home: it prioritizes listing status, buyer demand, required actions and publishing guidance over generic analytics.
- Product names, counts, inquiry volume, earnings, profile completion, creator identity, activity and dates are illustrative placeholders, not real creator performance or financial data.
- Earnings must distinguish gross sales, platform fees, refunds, pending amounts and settled payouts. Never present a sample total as withdrawable balance.
- Profile completion is a guidance indicator, not proof of identity, rights ownership, payout eligibility or creator verification.
- **Delivery status:** COMPLETED — standalone concept produced and registered.
- **Approval status:** **APPROVED / FROZEN** — approved 2026-11-25.
- Desktop only; permission-aware navigation, earnings definitions, empty states, listing status transitions, responsive behavior, accessibility and exact design tokens remain to be specified.

## 2.14 Standalone page mockup — Creator Studio: Products

**Mockup ID:** `MT-CRT-PROD-001-v1`  
**Parent screen ID:** `MT-CRT-PROD-001`  
**Asset filename:** `a_clean_modern_web_dashboard_ui_for_maketrail_c.png`  
**Format:** PNG  
**Scope:** Standalone desktop creator product management list and selected-product detail panel.

**Current source asset:** [Open Creator Studio Products mockup](sandbox:/mnt/data/a_clean_modern_web_dashboard_ui_for_maketrail_c.png)

**Screen sections shown:**
1. Creator Studio shell with Products navigation active.
2. Product summary metrics: all, published, in review and drafts.
3. Product status tabs and add-new-product action.
4. Search, category, technology and sort filters.
5. Product table with title, description, category/technology, status and last-updated date.
6. Selected product summary with listing completeness checklist.
7. Review feedback panel.
8. Quick actions to edit, preview, view analytics and duplicate a listing.

**Design review notes:**
- This is the creator's product portfolio management screen; product listing state is distinct from individual submission/review case history.
- Product names, counts, categories, technology stacks, statuses, dates, completeness percentages and feedback are illustrative placeholders, not actual creator inventory or review outcomes.
- A completeness score is a content-readiness aid, not an approval or verification score. Published status does not mean the software has been independently security-tested.
- Duplicate actions must create a new draft with clearly defined handling for license, version, media, ownership declarations and unique listing identity; never duplicate an active entitlement or transaction.
- **Delivery status:** COMPLETED — standalone concept produced and registered.
- **Approval status:** APPROVED / FROZEN — visual reference v1 approved on 2026-11-25. Use this mockup as the authoritative desktop visual target for `MT-CRT-SUB-001`; responsive layouts, interaction states, accessibility behavior, and implementation specifications must still be documented before coding.
- Desktop only; bulk actions, archive/delete rules, listing ownership, version lifecycle, review history, filter behavior, responsive behavior and exact design tokens remain to be specified.

## 2.15 Standalone page mockup — Creator Studio: Submissions

**Mockup ID:** `MT-CRT-SUB-001-v1`  
**Parent screen ID:** `MT-CRT-SUB-001`  
**Asset filename:** `a_clean_modern_saas_dashboard_ui_screenshot_for.png`  
**Format:** PNG  
**Scope:** Standalone desktop creator submission review and feedback workspace.

**Current source asset:** [Open Creator Studio Submissions mockup](sandbox:/mnt/data/a_clean_modern_saas_dashboard_ui_screenshot_for.png)

**Screen sections shown:**
1. Creator Studio shell with Submissions navigation active.
2. Submission summary metrics: all, in review, action required and approved.
3. Submission status tabs and filters for product, category, status and date.
4. Submission table with product, submission ID, submitted date, version, review stage, status and last update.
5. Selected submission detail with product/version/category and submission date.
6. Review progress timeline from submission through initial review, technical/rights review and decision.
7. Reviewer feedback with requested corrections.
8. Actions to view submission, update and resubmit, or withdraw.
9. Submission activity timeline.

**Design review notes:**
- A submission is a versioned review case, distinct from the creator's canonical product listing. Resubmission should preserve prior review history and link the new submitted version to the same case or a clearly traceable revision.
- Sample submission IDs, product names, versions, reviewer feedback, dates, counts and statuses are illustrative placeholders, not actual review decisions or policy.
- Review stages and required evidence must be defined by operations policy. Technical review and rights review are separate dimensions; approval must not imply security certification or legal advice.
- Withdrawal behavior must explain whether the creator can withdraw during each review stage and what happens to an already published listing or existing buyer entitlements.
- **Delivery status:** COMPLETED — standalone concept produced and registered.
- **Approval status:** **APPROVED / FROZEN** — approved 2026-11-25.
- Desktop only; reviewer identity/permissions, revision comparison, evidence uploads, feedback resolution, resubmission rules, withdrawal consequences, responsive behavior and exact design tokens remain to be specified.

## 2.16 Standalone page mockup — Creator Studio: Inquiries

**Mockup ID:** `MT-CRT-INQ-001-v1`  
**Parent screen ID:** `MT-CRT-INQ-001`  
**Asset filename:** `a_clean_modern_creator_inquiries_dashboard_for_ma.png`  
**Format:** PNG  
**Scope:** Standalone desktop creator inquiry and quotation workspace.

**Current source asset:** [Open Creator Studio Inquiries mockup](sandbox:/mnt/data/a_clean_modern_creator_inquiries_dashboard_for_ma.png)

**Screen sections shown:**
1. Creator Studio shell with Inquiries navigation active.
2. Inquiry metrics for new, awaiting creator response, quoted and converted.
3. Inquiry status tabs, search and filters.
4. Inquiry list with buyer/organization, requested product or service, reference, date and status.
5. Selected inquiry detail with buyer request, requirements and conversation history.
6. Quote summary with scope, deliverables, price, validity and response actions.
7. Actions to ask for clarification, decline, prepare quote or continue discussion.

**Design review notes:**
- This is the creator-side counterpart to the buyer inquiry experience; each inquiry must be a shared, permission-controlled record with participant-specific views.
- Buyer names, organizations, inquiry references, message content, quote values, dates and status counts are illustrative placeholders, not real customer requests or offers.
- Quotes must explicitly separate product license terms from optional implementation/service scope. Include currency, deliverables, exclusions, validity, support, payment milestones where applicable, and acceptance state.
- A creator must not see another creator's inquiries or buyer-private data. Declining or closing an inquiry must preserve an auditable history and explain any impact on an existing offer.
- **Delivery status:** COMPLETED — standalone concept produced and registered.
- **Approval status:** APPROVED / FROZEN — visual reference v1 approved on 2026-11-25. Use this mockup as the authoritative desktop visual target for `MT-CRT-INQ-001`; responsive layouts, interaction states, accessibility behavior, and implementation specifications must still be documented before coding.
- Desktop only; quote revision/expiry, negotiation states, attachments, notifications, response-time policy, organization access, responsive behavior and exact design tokens remain to be specified.

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
| `MT-MKT-001` | **APPROVED / FROZEN** — standalone visual v1 | Preserve the approved desktop visual; specify responsive and interaction behavior before implementation |
| `MT-PDP-001` | **APPROVED / FROZEN** — standalone visual v1 | Preserve the approved desktop visual; specify responsive and interaction behavior before implementation |
| `MT-CRT-001` | **APPROVED / FROZEN** — standalone visual v1 | Preserve the approved desktop visual; specify responsive and interaction behavior before implementation |
| `MT-OPS-001` | **APPROVED / FROZEN** — standalone visual v1 | Preserve the approved desktop visual; specify responsive and interaction behavior before implementation |
| `MT-BUY-001` | Standalone concept v1 completed; approval pending | Review this page, then specify responsive and interaction states |
| `MT-BUY-ORD-001` | Standalone concept v1 completed; approval pending | Review this page, then specify responsive and interaction states |
| `MT-BUY-PROD-001` | Standalone concept v1 completed; approval pending | Review this page, then specify responsive and interaction states |
| `MT-BUY-INQ-001` | Standalone concept v1 completed; approval pending | Review this page, then specify responsive and interaction states |
| `MT-BUY-IMPL-001` | **APPROVED / FROZEN** — standalone visual v1 | Preserve the approved desktop visual; specify responsive and interaction behavior before implementation |
| `MT-BUY-SUP-001` | Standalone concept v1 completed; approval pending | Review this page, then specify responsive and interaction states |
| `MT-BUY-ACC-001` | **APPROVED / FROZEN** — standalone visual v1 | Preserve the approved desktop visual; specify responsive and interaction behavior before implementation |
| `MT-CRT-OVW-001` | **APPROVED / FROZEN** — standalone visual v1 | Preserve the approved desktop visual; specify responsive and interaction behavior before implementation |
| `MT-CRT-PROD-001` | **APPROVED / FROZEN** — standalone visual v1 | Preserve the approved desktop visual; specify responsive and interaction behavior before implementation |
| `MT-CRT-SUB-001` | **APPROVED / FROZEN** — standalone visual v1 | Preserve the approved desktop visual; specify responsive and interaction behavior before implementation |
| `MT-CRT-INQ-001` | **APPROVED / FROZEN** — standalone visual v1 | Preserve the approved desktop visual; specify responsive and interaction behavior before implementation |

The four initial desktop screens are approved and frozen as visual references. They are not complete implementation specifications: responsive behavior, interaction states, accessible behavior, and final design tokens remain separate deliverables.

## 8. Related documents

- [Visual identity directions](visual-directions.md)
- [Design foundations](foundations.md)
- [Design system overview](README.md)
- [Information architecture](../product/information-architecture.md)
