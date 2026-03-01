---
layout: post
title: "Making Token Distributions Fair: A Structural Approach"
subtitle: "How to level the playing field for investors and insiders alike"
canonical_url: https://themasonic.substack.com/p/making-token-distributions-fair-a
---

Token distribution is one of the most consequential decisions a founding team makes. After processing over $1B in transactions across hundreds of tokens, I've seen nearly every outcome. The standard model — allocating tokens directly to team members and investors subject to vesting schedules — mirrors traditional equity compensation but introduces structural asymmetries that disadvantage the people who actually build projects.

This article proposes an alternative framework that treats token distributions more like dividends than direct holdings, centralizing liquidation decisions to ensure fair execution for all stakeholders.

## The Execution Gap

When tokens unlock, all holders theoretically gain the same right to sell. In practice, execution quality varies dramatically by sophistication.

A venture fund with a material position prepares months in advance: OTC relationships coordinated, block trade counterparties lined up, execution preferences selected to minimize slippage. The moment tokens become transferable, their sell order executes at or near the prevailing price.

An employee with a smaller allocation faces a different reality. They may not track unlock times precisely. They lack OTC relationships. When they attempt to sell through a retail interface, institutional sellers have already moved the market. The employee — who contributed years of work — receives materially worse execution than the investor who contributed capital.

This is a structural disadvantage baked into the distribution model.

## Three Patterns That Make It Worse

**1. Staking Reward Extraction.** Some networks allow locked tokens to be staked, generating liquid rewards that can be sold immediately. Polychain Capital invested approximately $20 million in Celestia's Series A and B. Despite tokens remaining locked, on-chain analysts estimate the firm sold over $240 million worth of TIA through staking rewards alone — a 12x return without selling a single locked token. Employees with smaller allocations, even if aware of this mechanism, lack the infrastructure to execute similar strategies.

**2. Undisclosed Liquidity Mechanisms.** EigenLayer: when EIGEN tokens became transferable in late September 2024, community members discovered that early investors with nominally locked allocations could stake those tokens and sell the resulting rewards immediately. Documentation had been updated shortly before launch to permit this practice. Of the 130 million EIGEN tokens staked at launch, approximately 70 million belonged to early investors earning tradable rewards while their principal remained locked.

**3. Asymmetric Exit Rights.** Berachain's Series B included a supplementary agreement granting Nova Digital Fund (Brevan Howard) the right to demand a full cash refund of its $25 million investment at any time within one year of the token generation event. BERA launched at approximately $15 and declined over 90%. Nova held a put option: upside if the token appreciated, principal protection if it didn't. Other Series B investors stated publicly they were unaware of the arrangement.

These patterns share a common thread: they advantage holders with legal sophistication and negotiating leverage over those whose primary contribution was building the product.

## The Entity-Based Solution

Rather than distributing tokens directly to individuals, structure allocations to flow through an entity — typically the offshore foundation that issues the tokens, or a dedicated vehicle controlled by the operating company.

**Token Custody.** The entity holds tokens on behalf of investors and team members. Individual beneficiaries have contractual rights to the economic value of their allocation, but not direct possession.

**Liquidation Authority.** A board, committee, or defined governance process determines when and how tokens are sold — triggered by periodic schedules, supermajority votes, or board resolution.

**Execution Standards.** Governing documents mandate professional execution through a designated market maker using strategies designed to minimize market impact. A 30-day TWAP distributes selling pressure across weeks rather than concentrating it at unlock moments.

**Cash Distribution.** Proceeds are distributed to beneficiaries as dividends, proportional to allocation. The employee and the venture fund receive the same per-token execution price.

## The Comparison

**Conventional structure:** Institutional investors sell at $15/token via OTC at unlock. Continued selling drives price to $8. Employees sell during this period at an average of $9/token. The investor received 67% more per token for the identical asset.

**Entity-based structure:** All allocations held in a foundation-controlled vehicle. Board authorizes partial liquidation. A 30-day TWAP achieves $12/token for all tranches. Every stakeholder receives $12/token. The execution gap disappears.

## Implementation

This structure must be established at formation, not retrofitted after token issuance.

- Subscription agreements and token purchase agreements must incorporate the entity-based structure explicitly
- Mandate TWAP execution requirements and market maker designation in the subscription agreement
- The offshore foundation structure consolidates custody and liquidation authority in a single governed vehicle
- Pre-determine periodic selling schedules or percentage-based voting thresholds to handle divergent liquidity needs between investors and employees

Note: This structure increases centralization of control over token supply, which may affect securities analysis in certain jurisdictions. Consult counsel on the trade-offs.

## The Bottom Line

The current token distribution paradigm optimizes for simplicity at the cost of fairness. Centralizing custody and liquidation authority in a governed entity eliminates the execution gap that systematically disadvantages employees.

In conventional equity structures, employees don't individually negotiate their exit. They participate in a governed liquidity event. Token distributions should work the same way.
