---
title: "Self-Liquidating Leverage: Borrow to Harvest, Harvest to Exit, Exit to Repay"
slug: "self-liquidating-leverage"
status: draft
voice: open-investigator
last_updated: 2026-05-06
what_id_update_on: "Real execution data on the four-stage cycle from readers who've run it; edge cases where the box spread loss isn't sufficient to cover concentrated position tax; better break-even modeling for multi-year cycles"
---

# Self-Liquidating Leverage: Borrow to Harvest, Harvest to Exit, Exit to Repay

## The Claim

Using leverage alongside tax-loss harvesting is dangerous. Adding debt to a portfolio that's already volatile amplifies your downside. If you're trying to exit a concentrated position, just do it slowly — sell a little each year, pay the capital gains tax, and diversify. Adding box spread debt to the equation turns a straightforward tax management problem into something with multiple moving parts that can go wrong.

I want to steelman this fully: the concern is legitimate. Leverage is an amplifier, and most of the time people describe "self-liquidating" leverage in the context of sophisticated strategies, they're using it to *add* risk, not reduce it. If you're borrowing to buy more of your concentrated position, or to speculate on the market while you wait to sell, the "amplifier" critique is exactly right.

What I'm describing is structurally different. The purpose of the leverage here is **de-risking**, not amplification. Let me show the cycle.

## The Working

### The Four-Stage Cycle

**Stage 1 — Borrow**: Execute a box spread loan (or margin, or SBLOC) against your existing liquid portfolio. Borrow $X at an implied APR of Y% for Z months. You have cash.

**Stage 2 — Harvest**: Deploy the borrowed cash (or use the loan as a replacement for cash you were holding) to fund systematic tax-loss harvesting purchases. The key mechanic: you buy proxies *before* harvesting the underlying, ensuring you never leave the market during the transition and thus avoiding the problem of trying to time a 30-day out-of-market window.

Wait. Why does borrowing help here? Because TLH requires you to *buy* a proxy before or simultaneously with the harvest sale (to avoid being out of the market), and if you're already fully invested, you need capital to fund the proxy purchase before you receive the sale proceeds. The box spread loan provides that capital. It's not leverage-as-amplifier; it's leverage-as-timing-bridge.

More importantly: the §1256 loss from the box spread itself is a **down payment on your tax bill**. A $200k box spread at 5% for 14 months generates roughly $11,700 in §1256 losses (as worked in Post #2). Those losses offset gains you'll realize in Stage 3.

**Stage 3 — Exit**: Use the harvested losses *plus* the §1256 losses to offset capital gains as you sell down the concentrated position. The losses you've accumulated determine your annual "exit budget" — how much concentrated stock you can sell without owing net capital gains tax.

Example with $1M concentrated position in NVDA (single-stock, $50k cost basis, current price $1M → $950k unrealized LTCG):

| Year | Losses Harvested | Box Spread §1256 Loss | Annual Exit Budget | Concentration Remaining |
|---|---|---|---|---|
| 1 | $30,000 | $11,700 | ~$41,700 at 23.8% effective LTCG rate | ~$958k |
| 2 | $35,000 | $11,700 | ~$46,700 | ~$911k |
| 3 | $40,000 | $0 (loan repaid) | ~$40,000 | ~$871k |
| 4+ | $35,000 | $0 | ~$35,000 | Declining |

*Numbers illustrative. Annual loss harvest depends on portfolio volatility and TLH yield. Exit budget = losses ÷ effective LTCG rate.*

**Stage 4 — Repay**: As you sell the concentrated position, some of the proceeds repay the box spread loan. The loan term is fixed (typically 6–18 months); you repay at expiration using proceeds from concentration sales and/or from realizing gains on the proxies you bought during harvesting.

**End-state**: Less concentration (the risky single-stock position has been partially diversified), less leverage (the box spread is repaid), and a lower lifetime tax bill (because gains realized during the exit were offset by harvested losses and §1256 losses). The leverage was transient; it bought you time and loss generation to fund the exit.

### Break-Even Reframing

The conventional break-even question is: "What return on the borrowed capital must I earn to cover the borrowing cost?" That's the amplification-framing break-even, and it's the wrong question here.

The right question: **What is the carrying cost of the box spread as a percentage of the tax savings it enables on the concentrated exit?**

Take the first two years of the example above:
- Box spread cost (after-tax, from Post #2): ~$7,400/year × 2 years = **~$14,800 total carrying cost**
- Additional exit enabled by the §1256 losses: ~$23,400 over 2 years
- Tax savings on that incremental exit (assuming 23.8% effective LTCG rate): $23,400 × 23.8% = **~$5,569 incremental tax savings from §1256 alone**

But the bigger driver is the TLH losses that the bridge financing enabled. If the loan-as-bridge allowed you to harvest $65,000 in losses over two years that you otherwise couldn't have timed properly, the tax value is $65,000 × 23.8% = **$15,470** — essentially covering the full carrying cost.

The math works if:
1. You have a meaningful concentrated position (> $500k unrealized gains) where the exit budget matters
2. You can generate TLH losses in your existing portfolio (requires a diversified taxable portfolio alongside the concentrated position)
3. Your tax rate is high enough (combined LTCG rate > 20%) to make loss generation valuable
4. You actually execute all four stages — the cycle only closes if you follow through

### When This Strategy Is Wrong

I want to be direct about the failure modes:

1. **No concentrated position**: If you don't have a single-stock or concentrated-sector position you're trying to exit, the "de-risking" frame doesn't apply. You're just borrowing to invest, which is the amplification strategy — and I'm not endorsing that here.

2. **Low tax bracket**: If your LTCG rate is below 15% (roughly $94k–$583k for MFJ 2025) or zero (below $94k), the losses you're generating are worth less and the carrying cost may exceed the benefit.

3. **Won't execute**: This strategy requires actually selling the concentrated position across Stages 3 and 4. If you're emotionally attached to the concentrated stock and genuinely won't sell it, the harvest-to-exit-to-repay cycle doesn't close, and you're just carrying leverage on a concentrated position — which is the dangerous version.

4. **Duration mismatch**: Box spreads have fixed terms. If your concentrated position becomes illiquid or if the market is down significantly at repayment time, you may need to source repayment capital from somewhere other than the planned concentration sale.

## What Optimal Is Building

The **TLH Calculator** in the Optimal extension runs the full four-stage cycle model. You input: concentrated position size, cost basis, current price, annual gain budget, and your tax profile. The planner outputs: recommended box spread size and term, projected annual TLH loss generation (based on your existing portfolio), years-to-zero on both the concentrated position and the leverage, and the cumulative after-tax cost comparison vs. "pay gains tax directly."

The goal is to make "is this worth it?" a 10-minute analysis, not a 10-hour spreadsheet project.

## What I Might Be Missing

1. **Multi-position concentration**: I've modeled this with one concentrated position. In practice, you might have NVDA plus RSUs from a different company plus appreciated real estate. The multi-position version of this model has more variables and I haven't fully worked through the optimal sequencing of exits when you have gains in multiple places.

2. **The behavioral risk**: Even with a plan, people don't always execute Stage 3 (the exit). If the concentrated stock continues to rise during the two years you're running this strategy, the unrealized gain grows faster than your exit budget, and you end the cycle with more concentration, not less. I think this is the real risk, not the leverage itself — and I don't have a clean solution for it beyond "commit to the exit in advance."

3. **Borrow rate risk on renewal**: A 14-month box spread is fixed-rate. But if you renew it for a second cycle, the new box spread will reflect then-current Treasury rates. Rate increases between cycles increase the carrying cost. I've modeled this at a constant rate; the real world isn't.

**Open an issue at [GetOptimal/OptimalFinanceKB](https://github.com/GetOptimal/OptimalFinanceKB/issues)** labeled `self-liquidating-leverage` if you've run a variant of this strategy. What worked? What forced you off the plan? Specifically: if you tried to execute Stage 3 and found the exit timing harder than expected, what was the friction?

---

*Not legal, tax, or investment advice. The strategy described involves significant complexity and risk, including leverage risk, tax characterization risk, and execution risk. The worked examples use illustrative numbers and assumed tax rates. Consult qualified tax and financial advisors before implementing any leveraged investment or borrowing strategy. Past behavior of financial instruments is not indicative of future results.*

*Last updated: 2026-05-06 | What I'd update on: Multi-position concentration model; behavioral execution data | Open questions: see issues labeled `self-liquidating-leverage`*
