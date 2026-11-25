# Maketrail architecture readiness assessment

**Status:** Working assessment — not an architecture approval  
**Version:** 0.1  
**Last updated:** 2026-11-25  
**Working branch:** `develop`  
**Purpose:** Identify the decisions and evidence needed to move from product definition into formal architecture without duplicating existing strategy, requirements, or design documents.

## 1. Executive assessment

Maketrail has enough documented groundwork to begin **bounded architecture discovery**: validate domain boundaries, map critical flows, identify trust boundaries, compare plausible technology options, and expose constraints.

It is **not ready for an architecture freeze or implementation authorization**. The most consequential inputs are still hypotheses or unanswered questions: the launch buyer problem and product category, launch jurisdictions, seller/merchant responsibilities, transaction and payout model, and the exact productized MVP workflow.

This assessment is an index and readiness control, not a replacement for the linked source documents. Requirements and proposals remain in their existing documents; decisions belong in ADRs; validation evidence belongs in the market-validation record.

### Current recommendation

- Proceed with bounded MVP definition and architecture discovery in parallel, using the active MVP scope draft as the workflow input.
- Keep market validation proportional: obtain minimum credible buyer, supply, rights, and transaction evidence; the full interview/transaction targets are not prerequisites to define the MVP.
- Do not select a production stack, commit to a payment provider, procure infrastructure, design a final physical schema, or start application implementation yet.
- Do not treat the 23 registered screen concepts as an approved product scope. The mockup register remains the source of truth for each screen's approval status.
- Reassess readiness when the blocking evidence below has been recorded and reviewed.

## 2. Readiness snapshot

| Area | Existing source of truth | Current assessment | Blocks architecture freeze? |
|---|---|---|---|
| Product vision and target users | [Vision](../product/vision.md), [PRD](../product/prd.md), [personas](../product/personas.md) | Documented hypotheses; not validated | Yes — launch workflow must be grounded |
| Market demand and supply | [Market validation plan](../strategy/market-validation.md) | Experiment proposed; no results are recorded in the plan | Yes |
| MVP workflow and boundaries | [MVP scope](../product/mvp-scope.md), [user journeys](../product/user-journeys.md) | Conditional proposal; not approved | Yes |
| Commerce and legal operating model | [Business model](../strategy/business-model.md), [transaction lifecycle](../product/transaction-lifecycle.md) | Commercial and payment assumptions unresolved | Yes |
| Launch jurisdictions | [MVP scope — unresolved decisions](../product/mvp-scope.md) | Countries and applicable obligations not selected | Yes |
| Domain concepts and invariants | [Domain model](domain-model.md) | Conceptual model exists; physical schema intentionally deferred | No for discovery; yes for schema freeze |
| Identity, organization and authorization | [Organization/access model](tenancy-model.md), [security baseline](security.md) | Principles proposed; permission matrix not approved | Yes before detailed access design |
| Logical architecture | [Architecture strategy](architecture-strategy.md), [system design](system-design.md) | Reversible direction proposed; no stack or deployment selected | No for discovery; yes for architecture freeze |
| Threats and operational risks | [Threat model](threat-model.md), [risk register](risk-register.md) | Initial qualitative drafts; not validated assessments | Yes before public launch; material threats before design freeze |
| Design system and screen behavior | [Foundations](../design-system/foundations.md), [mockup register](../design-system/mockup-register.md) | Visual concepts in progress; responsive and interaction specifications incomplete | No for domain discovery; yes for implementation readiness |
| Team, budget and operating constraints | Not yet captured in one approved source | Unknown | Yes for stack, hosting and delivery decisions |

**Interpretation:** “Blocks architecture freeze” does not mean all discovery must stop. It means the team must not convert an assumption into an irreversible technical commitment.

## 3. Required decision register

Use these IDs in planning and review. Do not copy the full requirements from linked documents into this assessment.

| ID | Required decision or evidence | Current state | Required output | Gate |
|---|---|---|---|---|
| AR-01 | Confirm the repeated buyer problem and initial buyer segment | Hypothesis | Evidence-backed problem statement with real examples and alternatives used | Product gate |
| AR-02 | Select the first product category/wedge | Candidate categories only | One narrow launch wedge supported by buyer demand and credible supply | Product gate |
| AR-03 | Confirm creator supply and product legitimacy | No validated supply results recorded here | Qualified candidate set with ownership, license, documentation and creator availability evidence | Product gate |
| AR-04 | Define the first end-to-end buyer outcome | Journey and MVP proposal exist | Approved workflow, including evaluation, rights acquisition, delivery and integration outcome | Product gate |
| AR-05 | Select launch countries and participant jurisdictions | Unresolved | Launch corridor and jurisdiction matrix reviewed by qualified counsel | Commerce gate |
| AR-06 | Define seller, platform and merchant responsibilities | Unresolved | Written operating model covering contracting party, invoicing, tax responsibilities, refunds and disputes | Commerce gate |
| AR-07 | Validate collection and payout feasibility | Provider and flow unselected | Provider capability review, supported countries/currencies, fees, onboarding, payout, refund and dispute flow | Commerce gate |
| AR-08 | Approve product license and service agreement boundaries | Principles documented; terms unresolved | Commercial terms model distinguishing software license, implementation service and support | Commerce gate |
| AR-09 | Approve the conditional productized MVP | Proposal only | Prioritized scope, exclusions, measurable acceptance criteria and named decision owner | Scope gate |
| AR-10 | Approve resource authorization and role matrix | Principles documented; detailed matrix missing | Action/resource matrix for buyers, creators, optional organization members and platform operators | Security/design gate |
| AR-11 | Confirm team and delivery constraints | Unknown | Team skills/capacity, operating budget, launch timeline, support coverage and risk tolerance | Technical gate |
| AR-12 | Select technology and deployment approach | Options only | Comparative ADRs based on approved workflow, team capability, cost, security and operational burden | Architecture gate |
| AR-13 | Define service-level and recovery requirements | No usage profile or launch commitment | Initial availability, recovery, backup, monitoring and incident objectives appropriate to launch | Architecture/launch gate |
| AR-14 | Complete implementation-ready screen specifications | Mockups registered; states/specifications incomplete | Approved screen specs for the actual MVP, including responsive, interaction, accessibility and error states | Implementation gate |

## 4. What can proceed in parallel now

These activities are useful before every business decision is settled, provided they remain exploratory and reversible:

1. **Domain walkthrough:** trace one hypothetical product purchase from creator submission through buyer evaluation, rights acquisition, payment confirmation, entitlement and delivery. Mark every unresolved business rule rather than inventing one.
2. **Trust-boundary mapping:** identify sensitive data, untrusted uploads, privileged operations, external payment events and resource ownership using the existing threat model.
3. **Architecture option comparison:** compare a modular monolith with credible alternatives against the actual team and workflow once those constraints are known. Do not assume microservices or a specific framework.
4. **Technology evaluation criteria:** define criteria before scoring vendors or frameworks: team familiarity, security support, deployment/rollback, observability, data integrity, regional support, cost and exit/portability.
5. **Mockup reconciliation:** resolve the remaining screen approvals in the mockup register and specify only screens that survive MVP scope selection. Do not design every future feature in detail.

These are discovery tasks, not permission to create production infrastructure or application code.

## 5. Architecture freeze exit criteria

Formal architecture may be considered for approval only when all of the following have evidence or an explicitly accepted risk:

- [ ] A validated initial buyer problem and selected launch wedge are recorded.
- [ ] Real creator/product supply has credible rights, licensing and delivery evidence.
- [ ] The MVP's first end-to-end workflow and explicit exclusions are approved.
- [ ] Launch jurisdictions and the seller/platform/merchant operating model have been reviewed.
- [ ] Payment collection, payout, refunds and disputes are feasible for the launch corridor, or the MVP explicitly excludes online checkout.
- [ ] Product license, implementation service and support obligations are separately defined.
- [ ] The domain model and lifecycle invariants match the approved workflow.
- [ ] Resource ownership and authorization rules are explicit and testable.
- [ ] Team, budget, delivery and operational constraints are known.
- [ ] Technology and deployment choices are supported by documented comparisons and ADRs.
- [ ] Material security, privacy, supply-chain and operational risks have owners and mitigations.
- [ ] Architecture diagrams, integration boundaries, data flows, recovery approach and deployment model have been reviewed.

Passing this checklist authorizes an architecture review, not automatically an implementation launch. Implementation additionally requires feature specifications, acceptance tests, operational ownership and an explicit build decision.

## 6. Suggested work order — no duplicate documentation

| Order | Work item | Update the existing source | Completion evidence |
|---|---|---|---|
| 1 | Run buyer and creator validation | [Market validation plan](../strategy/market-validation.md) | Dated, permissioned evidence and go/iterate/stop recommendation |
| 2 | Reconcile MVP and transaction workflow to observed evidence | [MVP scope](../product/mvp-scope.md), [PRD](../product/prd.md), [transaction lifecycle](../product/transaction-lifecycle.md) | Approved scope and workflow; unresolved items remain visible |
| 3 | Resolve jurisdiction and commerce feasibility | [Business model](../strategy/business-model.md) and MVP unresolved decisions | Reviewed launch corridor and viable transaction model |
| 4 | Finalize domain and authorization rules | [Domain model](domain-model.md), [organization/access model](tenancy-model.md), [security baseline](security.md) | Reviewed lifecycle invariants and permission matrix |
| 5 | Capture delivery constraints and compare technology options | [Architecture strategy](architecture-strategy.md), then ADRs in `docs/decisions/` | Evidence-backed, accepted architecture decisions |
| 6 | Specify only MVP screens and interaction states | [Mockup register](../design-system/mockup-register.md), [design foundations](../design-system/foundations.md) | Approved implementation-ready specifications |
| 7 | Conduct architecture review | This assessment plus linked sources | Recorded approval, accepted risks and explicit implementation authorization |

## 7. Governance and status changes

- The product owner must be assigned before scope and market gates can be approved.
- Legal/compliance review must be performed by appropriately qualified professionals for the selected launch jurisdictions; this document is not legal advice.
- Technical decisions must identify an accountable reviewer and link to an ADR.
- A gate changes to **Passed** only when its evidence is linked and reviewed. Interview targets, mockups, diagrams or proposed provider lists are not proof by themselves.
- Record the date, evidence, reviewer and decision. If evidence changes, reopen the affected gate rather than silently rewriting history.
- This assessment must remain an index and readiness control. Detailed requirements, validation notes, threat scenarios, screen mappings and technical decisions stay in their existing source documents.

## 8. Related source documents

- [Product requirements](../product/prd.md)
- [MVP scope proposal](../product/mvp-scope.md)
- [Market validation plan](../strategy/market-validation.md)
- [Business model](../strategy/business-model.md)
- [Transaction lifecycle](../product/transaction-lifecycle.md)
- [Architecture strategy](architecture-strategy.md)
- [Conceptual domain model](domain-model.md)
- [Organization and resource-access model](tenancy-model.md)
- [System design](system-design.md)
- [Security baseline](security.md)
- [Threat model](threat-model.md)
- [Risk register](risk-register.md)
- [Design foundations](../design-system/foundations.md)
- [Mockup register](../design-system/mockup-register.md)
- [Architecture decision log](../decisions/README.md)
