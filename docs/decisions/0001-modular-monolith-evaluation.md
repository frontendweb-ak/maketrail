# ADR-0001: Evaluate a modular application as the initial architecture

- **Status:** Proposed — not accepted
- **Date:** 2026-11-24
- **Decision owner:** To be assigned

## Context

Maketrail is at the market-validation and product-definition stage. Its initial transaction volume, team size, product wedge, operating countries, payment model, and hosting constraints are not yet established.

The system will likely need distinct capabilities for identity, catalog, creator publishing, moderation, commerce, entitlements, delivery, notifications, and operations. Those logical boundaries do not automatically require separate deployable services.

The project needs an architecture that supports clear ownership and security boundaries without introducing operational complexity before it is justified.

## Proposal

Evaluate a modular monolith as the default starting hypothesis:
- One primary application deployment initially, if validated requirements permit.
- Explicit domain modules with clear ownership of business rules and data access.
- Well-defined interfaces for payment providers, storage, email, and other external systems.
- Separate client experiences where user and security needs justify them, without assuming separate backend services.
- A documented path to extract a module into a service only when there is a measurable reason.

This is not an accepted implementation decision and does not authorize choosing a framework, database, cloud, or hosting provider.

## Alternatives considered

### Microservices from the beginning

Potential benefits:
- Independent deployment and scaling.
- Stronger process-level isolation for selected workloads.

Costs and risks:
- Distributed transactions and eventual consistency.
- More deployment, observability, networking, and on-call complexity.
- Larger operational burden before product-market evidence exists.

### Unstructured single application

Potential benefits:
- Low initial setup overhead.

Costs and risks:
- Domain rules and permissions can become coupled.
- Sensitive payment, admin, and delivery logic may be harder to isolate and audit.
- Later change becomes riskier without explicit module boundaries.

### Separate services only for high-risk workloads

Potential benefits:
- Upload scanning or isolated analysis can be separated where a specific threat model requires it.
- External integrations can be isolated behind narrow interfaces.

Costs and risks:
- More infrastructure and integration complexity.
- Requires evidence that process or environment isolation materially reduces risk.

## Evaluation criteria

Revisit this proposal after:
1. The first buyer problem and MVP workflows are selected.
2. Team size, deployment ownership, and operational capability are known.
3. Security review identifies workloads that require stronger isolation.
4. Expected workload and availability requirements are documented.
5. Hosting and cost comparisons are available.

## Consequences if later accepted

- Domain boundaries and authorization rules should be explicit from the beginning.
- Modules should not mutate each other's data directly.
- External provider integrations should have clear contracts and idempotent handling.
- Extraction into a separate service remains possible but is not a goal by itself.

## Revisit triggers

Revisit if a module needs independent scaling, a distinct security boundary, separate release cadence, specialized runtime, or independently owned operational lifecycle.

## Related documents

- [System design](../architecture/system-design.md)
- [Security baseline](../architecture/security.md)
- [Transaction lifecycle](../product/transaction-lifecycle.md)
