# Architecture documentation

**Status:** Proposed architecture baseline — not approved for implementation  
**Last updated:** 2026-11-24

## Purpose

This directory captures system boundaries, major data flows, security requirements, and technical options for Maketrail. It is intended to support validation and future engineering decisions, not to authorize infrastructure procurement or implementation.

## Documents

- [System design](system-design.md) — proposed logical architecture, trust boundaries, data domains, integrations, and unresolved choices.
- [Security baseline](security.md) — minimum security and operational controls to design for.

## Decision policy

- Formal decisions live in [the decision log](../decisions/README.md).
- A proposal is not an accepted decision.
- Select technologies only when a validated product requirement, operational constraint, and cost/risk comparison support the choice.
- Keep early architecture reversible. Avoid distributed infrastructure and premature scale optimization.
- Payment, payout, tax, privacy, and marketplace legal roles require provider and professional review before launch.

## Current status

No production stack, cloud provider, database, payment provider, or deployment topology has been approved.
