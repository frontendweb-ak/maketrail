# Maketrail design foundations

**Status:** Proposed foundations — no final visual tokens approved  
**Version:** 0.1  
**Last updated:** 2026-11-24

## 1. Token strategy

Use semantic tokens rather than styling components directly with raw colors or arbitrary values. Token names should express purpose and remain independent of a particular CSS/UI framework.

### Color roles

Define roles before choosing exact color values:

| Token family | Examples of semantic roles |
|---|---|
| Background | canvas, surface, surface-raised, surface-muted |
| Text | primary, secondary, muted, inverse |
| Border | default, subtle, strong, focus |
| Brand | brand, brand-hover, brand-pressed, on-brand |
| Action | primary-action, secondary-action, destructive-action |
| Status | success, warning, danger, info, neutral |
| Data visualization | chart series roles with accessible differentiation |

Rules:
- Choose one brand accent only after comparing visual directions and testing contrast.
- Status colors must have text labels and must not be the only signal.
- Do not use brand color for every button, badge, border, and link.
- Verify text and control contrast against every surface.
- Keep marketplace verification labels visually distinct from generic success states.

## 2. Typography

Use a restrained type system with roles for:
- Display/marketing heading.
- Page title.
- Section heading.
- Body and long-form description.
- UI label and form helper.
- Metadata and compact table text.
- Numeric/financial values.

Typography should prioritize legibility of product descriptions, license terms, compatibility details, and transaction amounts. Use tabular numerals for prices, quantities, dates, and financial tables where the chosen font supports them. Final font families and scale are open until brand exploration.

## 3. Spacing and layout

Use a consistent spacing scale based on a small base unit (a 4px or 8px-derived scale can be tested). Avoid one-off spacing values in shared components.

Define:
- Content max-widths for marketing/catalog pages.
- Reading width for long descriptions and legal/license text.
- Grid rules for product discovery.
- Form widths and section spacing for creator workflows.
- Table density options for operations.
- Responsive breakpoints based on content fit, not device brand names.

The public catalog should not inherit the narrow content width of a dashboard. Operations pages may use more horizontal space for review queues and audit tables.

## 4. Shape, elevation, and motion

- Use a small radius scale: control, card, and overlay.
- Use elevation sparingly; prefer borders and surface contrast over nested shadows.
- Establish overlay layers for menus, dialogs, popovers, and toasts.
- Motion should clarify state changes, not decorate routine navigation.
- Respect reduced-motion preferences and avoid motion that blocks task completion.

Exact values are intentionally deferred until visual prototypes exist.

## 5. Responsive behavior

Design for mobile, tablet, and desktop, but prioritize based on user tasks:
- Public browsing and product evaluation must work well on mobile.
- Creator listing creation may be easier on desktop but must remain usable on smaller screens.
- Complex operations tables can use responsive prioritization, row detail views, or controlled horizontal scrolling; never simply shrink text until unreadable.
- Forms preserve field order, labels, and validation context across breakpoints.

## 6. Core component inventory

### Primitives
- Button, icon button, link.
- Text input, textarea, select, checkbox, radio, switch.
- Label, helper text, validation message.
- Badge/status indicator, avatar, icon, divider.
- Card/surface, tooltip, popover, dialog, toast.
- Skeleton/loading indicator, empty state, error state.

### Marketplace patterns
- Product card and product result row.
- Creator identity block.
- Product metadata list: stack, version, license, price, maintenance, support.
- Verification evidence panel.
- Category and technology filter.
- Sort control and pagination.
- Product media/demo section.
- License and commercial terms summary.
- Related products and implementation offer.

### Buyer patterns
- Inquiry composer and conversation thread (if validated).
- Order summary and lifecycle timeline.
- License/terms acceptance record.
- Delivery/access panel.
- Support case summary.

### Creator patterns
- Listing editor with draft autosave only if reliability is designed.
- Version and compatibility editor.
- Rights/license declaration.
- Submission checklist and review feedback.
- Listing status and publication history.
- Buyer inquiry response panel.

### Operations patterns
- Review queue and filters.
- Evidence viewer and provenance details.
- Approve/request-changes/reject decision panel.
- Takedown and report case view.
- Order/payment event timeline.
- Restricted action confirmation and audit history.

## 7. Content and status language

Use plain, precise status labels. Avoid vague labels such as “trusted,” “safe,” “certified,” or “approved” without a defined policy and evidence.

Examples of status distinctions to design:
- Draft / Submitted / Changes requested / Published / Suspended.
- Creator-declared / Evidence reviewed / Independently tested (with exact scope).
- Payment pending / Confirmed / Failed / Refunded / Disputed.
- Entitlement active / Suspended / Revoked.

A status label should explain what happened, what it means, and what action is available next.

## 8. Component acceptance checklist

Before a shared component is accepted:
- It solves a repeated user need.
- Anatomy, variants, and state behavior are documented.
- Keyboard and screen-reader behavior are tested.
- Contrast and focus states meet the target.
- Responsive behavior is defined.
- Loading, disabled, empty, and error behavior are defined where relevant.
- Content guidance prevents misleading or ambiguous language.
- It has usage examples and anti-patterns.
