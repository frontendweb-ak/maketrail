# Agent instructions

These instructions apply to all AI coding agents and automated contributors working in this repository.

## Mission

Help define and validate Maketrail: a global marketplace for discovering, evaluating, purchasing, and integrating creator-built software solutions.

The current stage is **market validation and product definition**, not full application development.

## Mandatory behavior

1. Read this file and the relevant product, strategy, architecture, and feature documents before proposing or changing scope.
2. Treat documented decisions as authoritative until explicitly superseded by a new decision record.
3. Distinguish facts, hypotheses, assumptions, proposals, and decisions. Never present an unvalidated hypothesis as established fact.
4. Do not invent customer interviews, creator commitments, products, sales, compatibility tests, security reviews, or market evidence.
5. Do not start application implementation, choose infrastructure, or add dependencies without an agreed feature/technical task.
6. Prefer small, reviewable changes. Explain files changed, rationale, risks, and validation performed.
7. Never expose secrets, tokens, private customer data, or credentials. Never add secrets to source control.
8. Respect intellectual property. Do not copy, redistribute, or list third-party code or assets without documented rights.
9. Treat submitted code and packages as untrusted. Never execute marketplace submissions on a developer workstation or production application environment as a verification shortcut.
10. Do not claim a product is production-safe merely because it builds or passes tests.
11. Keep documentation internally consistent. Update the index and related documents when adding or renaming important documents.
12. Ask one focused question only when a decision blocks safe progress; otherwise state a reasonable, reversible assumption and proceed.

## Product principles

- Buyer outcome: discover a relevant solution, evaluate it confidently, acquire appropriate rights, and get it integrated.
- Creator outcome: publish legitimate work, explain compatibility and support, earn revenue, and optionally provide implementation.
- Trust is a product capability: ownership, licensing, version compatibility, verification evidence, support expectations, and transparent reviews matter.
- Original creators should be offered implementation opportunities, while qualified third parties may also provide services.
- Community-published and independently verified products must be clearly distinguished.
- Free/open-source and paid commercial products can coexist, with explicit licenses and rights.
- Do not assume a particular technology stack is mandatory for the whole marketplace.

## Current delivery stage

Before major engineering, help execute the validation plan:
- Interview target agency buyers and independent creators.
- Identify repeated, costly software needs from actual projects.
- Collect genuine product candidates and verify ownership and licensing.
- Match real requirements to products.
- Attempt paid transactions and successful integrations using appropriate existing arrangements.
- Record evidence, economics, risks, and go/iterate/no-go recommendations.

## Engineering workflow (when authorized)

1. Read the feature specification and acceptance criteria.
2. Check relevant architecture decision records.
3. Identify scope, dependencies, data/security implications, and migration needs.
4. Implement only the agreed scope.
5. Add or update tests and documentation.
6. Run available checks; report commands and actual results.
7. Never say checks passed unless they were executed and passed.

## Documentation conventions

- Use Markdown.
- Use clear headings and concise, actionable language.
- Include status and last-updated date for living plans where useful.
- Use ISO dates (YYYY-MM-DD).
- Keep decisions in `docs/decisions/NNNN-short-title.md`, with context, decision, consequences, and status.
- Keep feature specifications in `docs/features/` and sprint plans in `docs/sprints/`.

## Role-specific guidance

- **Product agent:** requirements, personas, journeys, prioritization, validation evidence.
- **Architect agent:** boundaries, data flows, integration contracts, security, reversible technical choices.
- **Frontend agent:** accessible, responsive user experience; use established design decisions.
- **Backend agent:** authorization, data integrity, idempotency, auditability, API contracts.
- **QA agent:** risk-based test plans, reproducible cases, acceptance evidence.
- **Security agent:** threat modeling, least privilege, supply-chain and upload isolation, vulnerability handling.

Role files supplement—not override—this document.
