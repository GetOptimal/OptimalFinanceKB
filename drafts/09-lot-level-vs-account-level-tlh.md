---
title: "Lot-Level vs Account-Level TLH: The Math Gap Is Bigger Than You Think"
slug: "lot-level-vs-account-level-tlh"
status: draft
voice: open-investigator
last_updated: 2026-05-06
what_id_update_on: "Broker-specific lot selection defaults and how to verify/change them; empirical backtest data on lot-level vs. account-level TLH yield gap; any IRS guidance on specific identification method requirements"
---

# Lot-Level vs Account-Level TLH: The Math Gap Is Bigger Than You Think

## The Claim

"I sell when it's red." Tax-loss harvesting is intuitive — if a position is down, sell it, realize the loss, buy a proxy. As long as you're tracking whether your positions are green or red and acting when they're red, you're doing TLH. FIFO (first-in, first-out) is what most brokers default to, and it works fine for simple portfolios.

This view is common among self-directed investors who have heard of TLH but haven't gone deep on implementation. The instinct — look at the position-level view, sell when red — is directionally correct but operationally incomplete. The gap between this approach and lot-level specific identification can be surprisingly large.

## The Working

### Specific Identification Is Supported, Rarely Defaulted

Every major U.S. broker — Fidelity, Schwab, Vanguard, IBKR, TD Ameritrade (now Schwab) — supports specific lot identification for tax purposes. You can designate which specific lot you're selling at the time of sale, and that designation holds for tax purposes. This is sometimes called "specific ID," "SpecID," or "lot selection."

The problem: almost none of them default to it. The typical default is FIFO (sell oldest shares first). For a long-term investor who has been buying consistently, FIFO means selling the oldest (usually lowest-basis) shares first — which realizes the most gain. That's backwards from a tax-efficiency standpoint.

Switching to specific identification: most brokers allow you to change your default cost basis method, but you typically need to do it at account level and sometimes at lot level at time of sale. The Bogleheads wiki has a good rundown of broker-specific procedures; in general, you need to confirm the lot selection before you execute the sale.

### The Cliff Zone: Don't Harvest a $100 ST Loss When 25 Days Converts $1k ST→LT

The most actionable concept in lot-level TLH is what I call the "cliff zone": the 25-day window before a short-term lot converts to long-term.

If you hold a lot that:
1. Was purchased 340 days ago
2. Has a short-term loss of $100

...you should not harvest that lot today. In 25 days, the loss is the same ($100), but it's now long-term. More importantly: if the stock has recovered partially and the short-term loss is $100 today but would be a $1,000 short-term gain if the stock rallies in the next 25 days, letting the lot "age out" to long-term is valuable — any gain recognized will be taxed at the lower LTCG rate.

Conversely, if you have a lot that:
1. Was purchased 340 days ago
2. Has a large short-term loss ($5,000)

...there's a compelling case to harvest *now* while it's still short-term (STCG rate). A $5,000 short-term loss is worth $5,000 × 37% = $1,850 in a 37% bracket. The same loss in 25 days becomes a $5,000 long-term loss worth $5,000 × 23.8% = $1,190. The 25-day wait costs you $660 in tax value.

The cliff zone rule:
- **Harvest short-term losses > $X before day 365** (where X is your threshold that justifies acting)
- **Do not harvest small short-term losses within 25 days of conversion** unless the position is significantly worse

My working threshold: harvest a short-term loss if the tax value difference between harvesting now vs. waiting 25 days exceeds $200 *and* the position is more than $500 in short-term loss territory. Below those thresholds, the transaction costs and cognitive overhead don't pencil.

### The Four-Way Lot Matrix

When you have a position with multiple lots (from periodic purchases), here's the decision matrix:

| Lot Type | Gain/Loss State | Action |
|---|---|---|
| Long-term, loss | Harvest candidate | Best: locks in LTCG loss, no cliff zone risk |
| Short-term, large loss | Harvest if > 25 days old (cliff zone applies if < 25 days to LT) | Good: STCG rate is higher, so loss is worth more |
| Short-term, small loss | Usually wait for LT conversion | Cliff zone: wait unless truly large |
| Long-term, gain | Do not harvest | Defer this gain as long as possible |

### Backtest Sketch: Account-Level vs. Lot-Level vs. Lot+Cliff

I want to be upfront: I don't have a fully rigorous 10-year backtest using real broker lot data. What I can offer is a structural argument and some rough numbers from published research.

Academic work on TLH efficiency (Israel & Moskowitz, Israelov & Tummala 2018) suggests that lot-level specific identification, combined with proactive cliff-zone filtering, can improve TLH yield by **20–40% relative** compared to FIFO on the same portfolio. The variance is large because it depends heavily on purchase timing — a portfolio of well-spread purchases benefits more from lot-level TLH than a portfolio of lump-sum purchases.

A rough illustration for a $500k portfolio with 12 years of accumulated lots:

| Method | Estimated Annual TLH Yield | Tax Value (37%) | Annual Tax Savings |
|---|---|---|---|
| Account-level (FIFO, sell when red) | 0.4–0.6% AUM | ~37% | $740–$1,110 |
| Lot-level specific ID | 0.7–1.0% AUM | ~37% | $1,295–$1,850 |
| Lot-level + cliff zone filter | 0.8–1.2% AUM | ~37% | $1,480–$2,220 |

*Very rough estimates; portfolio volatility and purchase history dominate actual results.*

The gap between FIFO and lot-level TLH isn't "negligible rounding error." It's potentially $500–$1,000/year on a $500k portfolio — money that compounds in the portfolio as a deferred tax benefit.

### The Broker Data Problem

There's a structural reason this gap exists: most portfolio aggregation tools (Mint, Personal Capital/Empower, Copilot budget) see only **positions**, not lots. They show you "VTI: $120,000" without showing you that you have seven different lots purchased over three years at seven different prices. The lot data lives inside your broker's system.

The Optimal extension reads lot-level data directly from brokers where API access supports it. This is different from what most aggregators do — they read position-level data from statement imports. The difference is exactly the gap described above: position-level data lets you know when a *position* is red; lot-level data lets you know when a specific *lot* is red and whether it's in the cliff zone.

### Setting Your Broker Default Today

Regardless of whether you use any automation:
1. Log into each taxable brokerage account
2. Find the "cost basis method" or "tax lot" setting
3. Change it from FIFO to "Specific Identification" or equivalent
4. For each taxable account with existing lots, verify the per-lot cost basis records are correct (especially for positions with dividend reinvestment or corporate actions)

This is a one-time 20-minute task per broker. The alternative is leaving money on the table in every future TLH transaction.

## What Optimal Is Building

The **Optimal extension** reads lot-level data directly from connected brokers (where supported), runs the cliff-zone filter against every lot, and surfaces only the harvests that pencil — the ones where harvesting today is clearly superior to waiting. The output is a ranked list of harvest candidates with the estimated tax value of each harvest, the cliff zone status, and the recommended proxy swap. You confirm; the extension stages the two-leg order.

This eliminates the most error-prone part of manual TLH: tracking 50+ lots across multiple purchase dates, calculating the STCG vs. LTCG tax value of each lot, and applying the cliff-zone filter. Even motivated self-directed investors make errors here; the extension doesn't.

## What I Might Be Missing

1. **Broker lot selection UI differences**: The specific procedure for designating lots varies by broker and can change with platform updates. My description above is general; actual steps may differ. If you've found a particularly cumbersome or counterintuitive UI for lot selection at a specific broker, that's worth documenting.

2. **The wash sale interaction with lot selection**: When you harvest a lot and buy a proxy, the wash sale window applies to that specific lot, not the whole position. If you have multiple lots and harvest the loss lot while retaining a gain lot, the gain lot's presence doesn't cause a wash sale — only a repurchase of the *same* security within 30 days causes a wash sale on the harvested lot. This is a nuance worth being explicit about.

3. **Dividend reinvestment creating unintended wash sales**: If you have DRIP enabled on a position and you harvest a loss in that position, the DRIP reinvestment in the 30-day window after the harvest is a wash sale. Most brokers don't warn you. If you're running TLH, disable DRIP on positions you're actively harvesting.

**Open an issue at [GetOptimal/OptimalFinanceKB](https://github.com/GetOptimal/OptimalFinanceKB/issues)** labeled `lot-level-tlh` with your broker's actual cost basis method options, any UI quirks for lot selection, and — if you have empirical data — your actual TLH yield improvement after switching from FIFO to specific ID.

---

*Not legal, tax, or investment advice. The yield estimates are based on published academic literature and are illustrative approximations; your results will vary significantly based on portfolio composition, purchase history, and market conditions. Specific identification of lots for tax purposes requires proper designation at time of sale; consult your broker's documentation and a tax advisor to ensure proper implementation.*

*Last updated: 2026-05-06 | What I'd update on: Broker-specific lot selection documentation; empirical yield improvement data | Open questions: see issues labeled `lot-level-tlh`*
