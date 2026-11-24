# Maketrail design system

**Status:** Design direction and system proposal — visual identity and tokens not yet approved  
**Version:** 0.1  
**Last updated:** 2026-11-24

## 1. Purpose

Create a consistent, accessible interface language across Maketrail without forcing every surface into the same layout. The design system should support the public marketplace, buyer experience, creator workspace, and operations console.

This is not a finished visual identity, Figma library, or implementation specification. Brand colors, typography, logo, and detailed component visuals require deliberate design exploration and review.

## 2. Design position

Maketrail should feel like a **credible technical marketplace**, not a generic admin template, crypto exchange, or source-code repository clone.

The interface should communicate:
- Confidence through transparent evidence, licensing, compatibility, and support information.
- Technical depth without overwhelming non-specialist decision-makers.
- Commercial clarity around price, terms, delivery, and service scope.
- Creator credibility without turning listings into promotional noise.
- Operational precision in moderation and transaction workflows.

Recommended visual direction:
- Light-first, content-led public marketplace.
- Restrained neutral foundation with one distinctive brand accent selected after visual exploration.
- Strong typography and clear information hierarchy.
- Product media and technical metadata presented consistently.
- Color used semantically for state, not decoration.
- Dense data tables only in operations contexts where they improve throughput.
- Dark theme considered later if research shows a real need; do not design two themes before the first is coherent.

## 3. Experience surfaces

| Surface | Primary job | Design character |
|---|---|---|
| Public marketplace | Discover, evaluate, compare, trust | Editorial, open, search-friendly, product-led |
| Buyer area | Manage inquiries, orders, licenses, delivery and support | Calm, clear, reassuring |
| Creator studio | Publish products, respond to buyers, maintain listings | Productive, structured, feedback-rich |
| Operations console | Review, investigate, moderate and audit | Precise, information-dense, cautious |

Share foundations and reusable components. Do not force the public site to use the same navigation, density, or page shell as the admin console.

## 4. System layers

1. **Brand layer:** name, logo, voice, visual identity, illustration and imagery rules.
2. **Foundation layer:** color roles, typography, spacing, sizing, radius, elevation, motion, breakpoints.
3. **Primitive layer:** buttons, links, inputs, icons, surfaces, typography, focus treatment.
4. **Pattern layer:** forms, filters, listing cards, metadata groups, status labels, tables, review panels, confirmation flows.
5. **Template layer:** catalog, product detail, creator profile, buyer order/inquiry, creator listing workflow, operations review.
6. **Guidance layer:** accessibility, responsive behavior, content style, usage and anti-patterns.

## 5. Component principles

- Prefer semantic, accessible HTML and native behavior.
- Components expose variants for meaningful states, not arbitrary styling knobs.
- Keep domain-specific components composed from shared primitives.
- Every interactive component has keyboard, focus, disabled, loading, error, and relevant empty states.
- Status is never conveyed by color alone; pair it with text and, where useful, an icon.
- Forms explain requirements, validation, and consequences near the field.
- Destructive, financial, publication, and rights decisions require clear confirmation and feedback.
- Product cards show decision-making information, not just an image and a title.
- Avoid creating a component for a one-off layout unless reuse or consistency warrants it.

## 6. Accessibility and quality bar

Target WCAG 2.2 AA for product interfaces:
- Keyboard access and visible focus.
- Semantic headings, landmarks, labels, and table structure.
- Sufficient text and non-text contrast.
- Screen-reader names and state announcements.
- No color-only status.
- Reduced-motion support.
- Responsive reflow and usable touch targets.
- Accessible validation and error summaries.

Accessibility is part of component acceptance, not a final audit task.

## 7. Governance

Each component or pattern should document purpose, anatomy, variants, states, responsive behavior, accessibility behavior, content guidance, and examples of correct/incorrect use.

Promote a pattern to the shared system when it appears across multiple surfaces or carries a high-risk interaction. Keep experimental components local until proven.

Do not choose a component framework or token implementation until the application stack is selected. The conceptual token names should remain portable.

## 8. Next design work

1. Confirm target user tasks and information architecture for each surface.
2. Explore 2–3 distinct visual directions before selecting brand color/type/logo.
3. Define semantic tokens and typography scale.
4. Design core journeys in low-fidelity before polishing components.
5. Build and test the highest-value patterns: product card, product detail metadata, filters, inquiry form, listing editor, moderation decision panel, order state.
6. Test with buyers, creators, and operators; revise based on task success, not aesthetic preference alone.

## 9. Related documents

- [Design foundations](foundations.md)
- [Architecture strategy](../architecture/architecture-strategy.md)
- [MVP scope](../product/mvp-scope.md)
- [User journeys](../product/user-journeys.md)
