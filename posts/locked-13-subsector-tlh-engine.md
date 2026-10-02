---
title: "DIY: the subsector TLH engine - lower-effort direct indexing."
slug: "subsector-tlh-engine"
status: published
voice: optimal
last_updated: 2026-10-02
---

# DIY: the subsector TLH engine - lower-effort direct indexing.

Direct indexing is the tax-loss-harvesting trick the industry charges for: instead of one index fund, own the pieces, so the pieces that are down can be sold at a loss while the whole keeps tracking the market. Wealthfront and Parametric do it with hundreds of individual stocks, armies of software, and a fee. The retail version does it with subsector ETFs - and it's nearly as good.

The construction. Take the market apart by subsector: electric utilities, banks, semiconductors, software, healthcare, industrials, consumer discretionary, energy, and so on. Buy one ETF per bucket, weighted to roughly match the market. Together they ARE the market - they track the S&P within an error you won't feel. Individually, they zigzag. And zigzag is the raw material of tax-loss harvesting: at any given moment, something is down.

The harvest. When a subsector drops below your cost, sell it, bank the loss, and immediately buy a substitute in the same space. This is where the structure shines: every subsector comes with two, three, sometimes more equivalent ETFs - large, liquid, low-expense-ratio funds from different issuers tracking different indexes. Same exposure, not substantially identical. Sell the semiconductor ETF tracking one index, buy the one tracking another, and your exposure never leaves the market while the loss is real. The wash-sale rule cares about substantially identical securities, not correlated ones. And in 31 days, if you miss the original, you can rotate back.

Why subsectors instead of stocks? The stock version harvests deeper - more line items, more dispersion, more losses - but it takes hundreds of positions, daily monitoring, and automation to run. That's the meticulous-execution trap. The subsector version gets most of the benefit with 12 positions and a scheduled check. The losses per dollar run lower. The odds you actually do it run a lot higher. A strategy you'll execute beats a strategy you won't.

The losses are the fuel. Banked losses offset gains anywhere: the concentrated stock you're selling down, the box spread's Section 1256 losses stacking alongside, a future liquidity event. Whatever you can't use carries forward indefinitely. You're building a tax asset one red month at a time.

The honest caveats. The engine is most productive when it's young and when markets are choppy - a long smooth bull run starves it. Substitute ETFs never track perfectly, so you eat small tracking differences. And the harvest needs discipline: check on a schedule, not on vibes, and let automation do the watching where you can. But the barrier was never intelligence or even effort. It's that nobody packages this, because the packaging is where the fee lives.

## Assumptions

The engine trades precision for fewer positions. Its tax value depends on the portfolio you actually build and the losses you can actually use.

- **Position count:** Twelve positions is an illustrative implementation size, not a validated minimum or a claim of a measured percentage of direct-indexing benefit. The "hundreds" comparison describes the individual-stock approach. No backtest here quantifies "nearly as good," tracking error or loss yield.
- **Replacement choices:** Two or three candidate ETFs per bucket is a design goal, not proof every subsector has interchangeable, liquid, low-cost and tax-safe alternatives. Indexes, holdings, weights, spreads and expenses need to be checked for each pair. Correlated does not automatically mean substantially identical, but different tickers or issuers alone do not establish safety.
- **Wash sales:** [IRS Schedule D instructions](https://www.irs.gov/instructions/i1040sd) test substantially identical purchases within 30 days before or after a loss sale. Day 31 is outside that forward window only if no other relevant purchase creates a wash sale; review other accounts, automatic reinvestment and related transactions too.
- **Loss use:** Allowable losses offset gains under applicable netting rules, with carryforwards subject to tax rules. A harvested loss is not a dollar-for-dollar tax saving. Value depends on gain character, rate, timing and subsequent sale of the replacement, whose lower basis can defer tax rather than eliminate it. ETF losses do not "offset" another loss; financing losses, if eligible, add to the loss pool rather than becoming gains for ETF losses to offset.
- **Return and risk:** Specify bucket weights, benchmark, rebalancing, harvest threshold, trading costs, tracking error and monitoring cadence. These inputs are not supplied as a reproducible portfolio here. No schedule guarantees something is always below your basis or that the whole portfolio exactly tracks the market.

Have better inputs, a missing cost or evidence that changes the result? [Share it](https://github.com/GetOptimal/OptimalFinanceKB/issues). We will update our assumptions and conclusions to reflect the most accurate representation.
