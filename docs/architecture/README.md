# Architecture documentation

**Status:** Proposed architecture baseline — not approved for implementation  
**Last updated:** 2026-11-24

## Purpose

This directory captures system boundaries, major data flows, security requirements, and technical options for Maketrail. It is intended to support validation and future engineering decisions, not to authorize infrastructure procurement or implementation.

## Readiness

- [Architecture readiness assessment](readiness-assessment.md) — current readiness, required decisions, exit criteria, and work order. This is an index/control document; detailed requirements remain in their source documents.

## Documents

- [Architecture strategy](architecture-strategy.md) — recommended product and technical architecture, trade-offs, and deferred decisions.
- [Conceptual domain model](domain-model.md) — business concepts, relationships, ownership classes, and lifecycle invariants.
- [System design](system-design.md) — proposed logical architecture, trust boundaries, data domains, integrations, and unresolved choices.
- [Organization and resource-access model](tenancy-model.md) — optional organization model; Maketrail is not assumed to be tenant-first.
- [Security baseline](security.md) — minimum security and operational controls to design for.
- [Threat model](threat-model.md) — initial STRIDE-informed threats, abuse cases, trust boundaries, and launch-blocking questions.
- [Risk register](risk-register.md) — provisional market, business, security, legal, and operational risks.

## Decision policy

- Formal decisions live in [the decision log](../decisions/README.md).
- A proposal is not an accepted decision.
- Select technologies only when a validated product requirement, operational constraint, and cost/risk comparison support the choice.
- Keep early architecture reversible. Avoid distributed infrastructure and premature scale optimization.
- Payment, payout, tax, privacy, and marketplace legal roles require provider and professional review before launch.
- Risk ratings are provisional until supported by real validation, provider review, or technical evidence.

## Current status

No production stack, cloud provider, database, payment provider, or deployment topology has been approved.
