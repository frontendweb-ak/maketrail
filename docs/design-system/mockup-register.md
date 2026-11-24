# Maketrail visual mockup register

**Status:** Initial concept reference — not final-approved  
**Register version:** 0.1  
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

## 6. Approval status

| Mockup ID | Current status | Next action |
|---|---|---|
| `MT-MKT-001` | Concept only | Refine and review Marketplace Home |
| `MT-PDP-001` | Concept only | Refine and review Product Detail |
| `MT-CRT-001` | Concept only | Refine and review Creator Studio |
| `MT-OPS-001` | Concept only | Refine and review Operations Console |

No screen in this register is currently approved as a pixel-perfect implementation reference.

## 7. Related documents

- [Visual identity directions](visual-directions.md)
- [Design foundations](foundations.md)
- [Design system overview](README.md)
- [Information architecture](../product/information-architecture.md)
