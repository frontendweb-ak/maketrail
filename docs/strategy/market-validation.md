# 30-day market validation plan

**Status:** Proposed experiment  
**Last updated:** 2026-11-24  
**Decision this plan supports:** whether to proceed, iterate, or change the initial marketplace wedge.

## Objective

Test whether development agencies have urgent willingness to pay for reusable software modules and whether independent creators can supply legitimate, usable products with implementation support.

Do not build the full marketplace during this experiment.

## Target participants

### Buyers
Development agency owners, CTOs, engineering managers, and technical leads. Prioritize teams that repeatedly deliver similar application capabilities.

### Creators
Independent developers and small software studios with reusable software they own and can legally distribute.

## Interview principles

- Ask about past behavior, not hypothetical enthusiasm.
- Request a recent concrete example.
- Quantify engineering time, costs, delays, defects, and maintenance burden.
- Ask what was purchased, reused, or built internally and why.
- Do not pitch the concept before understanding the current workflow.
- Record permissioned notes and anonymize sensitive customer or project details.

## Buyer interview prompts

1. What kinds of software projects did your team deliver in the last six months?
2. Which modules or capabilities did you rebuild across projects?
3. Tell me about the most recent example. How much engineering time did it take?
4. What existing libraries, templates, vendors, or marketplaces did you evaluate?
5. Have you bought third-party code or software before? What happened after purchase?
6. What made evaluation, licensing, compatibility, or integration difficult?
7. What is an upcoming project requirement where you might reuse or buy a solution?
8. What budget and approval process would apply?
9. Would implementation from the original creator reduce risk? What evidence would you require?
10. What would make you reject a solution immediately?

Capture actual upcoming requirements and permission to follow up. Do not count general interest as qualified demand.

## Creator interview prompts

1. What reusable software have you built that you own?
2. Can you show a demo, documentation, repository, or working example?
3. What license and third-party dependencies does it use?
4. Have you sold, distributed, or maintained it before?
5. Who uses it, and what support do they need?
6. Which versions, frameworks, and environments does it support?
7. Would you publish it commercially or as open source? Under what terms?
8. Would you offer integration or customization services?
9. What would make you trust a marketplace with your product and customers?
10. What commercial terms and support expectations would be acceptable?

Do not claim a creator is qualified until product ownership, rights, and basic usability have been checked.

## Workstreams

### A. Buyer discovery
- Build a list of 30 target agencies.
- Complete 15 buyer interviews.
- Identify recurring requirements and approximate cost of current approaches.
- Obtain at least 5 specific, qualified requirements.

### B. Creator supply
- Build a list of 30 potential creators.
- Complete 20 creator interviews.
- Recruit 10 qualified founding creators.
- Collect 20 genuine product candidates with ownership and license information.

### C. Competitor and alternative research
Study CodeCanyon/Envato, GitHub Marketplace, AWS Marketplace, Gumroad, and Contra. Also document internal builds, open-source packages, direct creator sales, and agencies' existing vendor relationships.

Compare discovery, listing quality, demos, licensing, verification, compatibility, payments, refunds, updates, support, and integration services. Deliver a comparison sheet with at least 20 observations. Competitor claims must include source links and access dates.

### D. Concierge transactions
Operate a small manually curated catalog and match actual buyer requirements to products. For each match:
1. Clarify stack, versions, requirements, constraints, and budget.
2. Shortlist two or three plausible products.
3. Check creator identity/ownership, license, documentation, compatibility evidence, and availability.
4. Arrange a demo or technical review.
5. Facilitate purchase using an appropriate existing payment/invoicing arrangement and written terms.
6. Arrange implementation by the creator or a qualified developer.
7. Record outcome, support effort, and buyer feedback.

Do not hold customer funds or describe the process as escrow unless a compliant, approved provider and legal structure support it.

## Candidate catalog experiment

Target 20 real product candidates across categories identified by interviews. Initial hypotheses to test include authentication/RBAC, billing, notifications, admin dashboards, file management, and business workflows.

A listing record should capture:
- Product name and creator.
- Problem solved and intended buyer.
- Demo and documentation.
- Repository or delivery method.
- Supported stack, versions, dependencies, and environment.
- License and third-party dependency notices.
- Price and included usage rights.
- Maintenance status and last tested version/date.
- Known limitations and security considerations.
- Support expectations and creator availability.
- Implementation service availability.
- Verification status and evidence.

Never fabricate products, demos, reviews, ownership, sales, or verification results.

## Verification levels (proposed)

**Community Published**
- Creator submitted the listing.
- Ownership and distribution-rights declaration collected.
- License and basic metadata reviewed.
- Not represented as independently tested.

**Independently Verified**
- Creator/repository ownership checked using reasonable evidence.
- License and material third-party dependencies reviewed.
- Build and relevant tests executed in an isolated environment.
- Documentation and supported-version claims reviewed.
- Appropriate automated security checks performed.
- Tested version, date, environment, results, limitations, and reviewer recorded.

A successful build or automated scan does not prove production safety. Verification scope must be explicit. Submitted code must not run on the primary application infrastructure.

## 30-day calendar

### Week 1 — Discovery setup
- Build lists of 30 agencies and 30 creators.
- Complete 10 buyer and 10 creator interviews.
- Begin competitor comparison.
- Identify the top three recurring buyer problems.

### Week 2 — Evidence and supply
- Complete remaining interviews.
- Recruit 10 qualified creators.
- Collect 20 real product candidates.
- Review ownership, licenses, documentation, and basic usability.
- Select the strongest buyer requirements.

### Week 3 — Concierge catalog
- Publish a simple landing page and curated catalog.
- Contact 15–20 relevant agencies with specific matching products.
- Obtain 5 qualified buyer requests.
- Arrange product demos and technical compatibility reviews.

### Week 4 — Transactions and decision
- Target 3 paid purchases and 2 successful integrations.
- Record buyer and creator experience.
- Calculate transaction economics and manual operating effort.
- Write a go/iterate/no-go recommendation supported by evidence.

## Metrics and unit economics

For every opportunity, track:
- Buyer segment and source.
- Requirement, urgency, and qualification.
- Products shortlisted and reason for selection/rejection.
- Product price and implementation price.
- Total transaction value.
- Marketplace revenue or proposed fee.
- Payment processing, refunds, chargebacks, and taxes where applicable.
- Verification and support cost.
- Matching and sales time.
- Integration hours and outcome.
- Repeat-purchase intent and observed follow-up.

**Contribution margin** = marketplace revenue minus variable transaction, payment, refund, verification, support, and other directly attributable costs.

Separate actual cash collected from proposals and expressions of interest.

## Decision framework

**Proceed to a narrow MVP** when evidence supports recurring buyer demand, real supply, paid transactions, successful integrations, repeat potential, and workable legal/payment operations.

**Iterate** when demand exists but product quality, compatibility, trust, pricing, support, or matching creates friction.

**Change the wedge or stop** when buyers consistently prefer internal builds or existing alternatives, creators cannot supply legitimate products, willingness to pay is absent, or economics/compliance are untenable.

Thresholds are proposed decision aids, not universal rules. Explain the evidence behind the recommendation and any small sample limitations.

## Risk controls

- Never list another party's repository or code without rights.
- Use clear commercial terms, licenses, support boundaries, and refund rules.
- Distinguish community-published from independently verified products.
- Do not promise compatibility without testing the relevant version and environment.
- Do not claim production-safe based on a build or scan alone.
- Do not hold funds without suitable legal/payment arrangements.
- Keep personal and customer information permissioned and access-controlled.

## Experiment output

At the end of the 30 days, produce:
1. Buyer interview synthesis.
2. Creator interview synthesis.
3. Competitor comparison.
4. Qualified buyer requirements.
5. Curated product candidate catalog.
6. Transaction and integration outcomes.
7. Unit economics and operational effort.
8. Risks and unresolved questions.
9. Go/iterate/no-go recommendation.
