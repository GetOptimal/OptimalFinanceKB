---
title: "Subsector Direct Indexing Without Paying Wealthfront 0.25%"
slug: "subsector-direct-indexing"
status: draft
voice: open-investigator
last_updated: 2026-05-06
what_id_update_on: "Empirical yield studies on position-fragmentation-only vs. full tranching; any degradation in proxy pair ETF tracking over multi-year periods; Wealthfront/Frec fee changes"
---

# Subsector Direct Indexing Without Paying Wealthfront 0.25%

## The Claim

Direct indexing — owning the individual stocks in an index rather than an ETF — requires Wealthfront, Frec, Parametric, or another managed platform. The automation, the rebalancing, the lot-level tracking: it's too complex to do yourself at meaningful scale. The platforms charge 0.25% or more of AUM for this service, and for the tax-loss harvesting yield they generate, it's worth it.

I want to be precise about what I'm agreeing with and what I'm disputing here. The platforms are doing something real. Lot-level rebalancing and systematic harvesting at scale do require automation. What I'm challenging is the claim that you need *their* automation — and the implicit claim that paying 0.25% AUM indefinitely is the only path to that automation.

I also want to be transparent about what I'm *not* doing: I'm not claiming we've fully replicated tranching (time-fragmentation of purchases). We haven't yet, and saying so is the brand.

## The Working

### Two Fragmentation Sources in Direct Indexing

Direct indexing generates tax-loss harvesting opportunities from two structural sources:

**1. Position fragmentation (across positions)**: When you hold 50 individual securities instead of one ETF, individual stocks will have losses even when the index is up. On any given day, the Nasdaq might be +1.2% while three of your tech holdings are down 2–5%. If you held QQQ, there's nothing to harvest. If you hold the individual components, you can harvest the losers and buy a proxy.

**2. Time fragmentation (tranching)**: When you purchase shares across multiple time periods rather than all at once, you create lots with different cost bases. Lots purchased at peaks have losses available during the subsequent dip; lots purchased at troughs have gains you might want to let ride. Platforms like Parametric explicitly use tranching — dripping purchases over weeks or months — to maximize the number of lots with harvestable losses.

Position fragmentation delivers the majority of the value. Based on the academic literature (Shim et al. 2023, Vanguard Research 2022 white paper on direct indexing), position fragmentation alone captures approximately **70–80% of the total TLH yield** available from a full direct indexing program, with tranching providing the remaining 20–30%.

**We build the position-fragmentation layer. We do not currently do tranching.** Tranching requires execution automation we haven't landed yet — specifically, the ability to automatically split a purchase across dates and track the intent of each lot. It's on the roadmap. In the meantime, I'd rather be explicit about this gap than oversell the yield.

### The 11 SPDR Sector ETF Framework

Instead of replicating 500+ S&P 500 stocks, I use 11 SPDR sector ETFs as the "basket" that approximates a broad index exposure. The sectors:

| ETF | Sector | Approx. Weight in SPX |
|---|---|---|
| XLK | Technology | ~31% |
| XLV | Health Care | ~13% |
| XLF | Financials | ~13% |
| XLY | Consumer Discretionary | ~10% |
| XLC | Communication Services | ~9% |
| XLI | Industrials | ~9% |
| XLP | Consumer Staples | ~6% |
| XLE | Energy | ~4% |
| XLB | Materials | ~3% |
| XLRE | Real Estate | ~2% |
| XLU | Utilities | ~2% |

By holding all 11 in market-cap proportions, I track the S&P 500 with a tracking error roughly comparable to a multi-factor ETF blend (expect 1.5–3% annual tracking error, versus < 0.1% for SPY). That tracking error is the price of harvesting opportunities across 11 positions instead of one. Whether that trade-off is worth it depends on your tax rate and the TLH yield you achieve.

### Proxy Pair Table for Sector TLH

When I harvest a loss in one sector ETF, I need to swap into a proxy that:
1. Maintains roughly equivalent market exposure (to avoid disrupting the portfolio's sector weights)
2. Is not "substantially identical" to the harvested ETF (wash sale avoidance — see Post #3)
3. Has sufficient liquidity for my position size

| Harvest | Proxy | Index Difference | Substantially Identical Risk |
|---|---|---|---|
| XLK | VGT | MSCI Tech vs. S&P Tech | Low — different index, weights differ |
| XLF | VFH | MSCI Financials vs. S&P Financials | Low |
| XLV | VHT | MSCI Health Care vs. S&P Health Care | Low |
| XLY | VCR | MSCI Cons. Disc. vs. S&P Cons. Disc. | Low |
| XLC | VOX | MSCI Comm. vs. S&P Comm. | Low-Moderate |
| XLI | VIS | MSCI Industrials vs. S&P Industrials | Low |
| XLP | VDC | MSCI Cons. Staples vs. S&P Cons. Staples | Low |
| XLE | VDE | MSCI Energy vs. S&P Energy | Low |
| XLB | VAW | MSCI Materials vs. S&P Materials | Low |
| XLRE | VNQ | MSCI Real Estate (broader) | Low |
| XLU | VPU | MSCI Utilities vs. S&P Utilities | Low |

The MSCI vs. S&P index methodology difference provides the most defensible wash sale protection. VGT and XLK, while both "tech ETFs," track different indexes with meaningfully different constituent lists and weights. The largest constituent overlap is high (both hold AAPL, MSFT, NVDA), but the index definitions diverge on what counts as "technology" — for example, Alphabet is in XLC (S&P Communication Services) but was historically in tech under MSCI.

### Honest Yield Estimate: 0.7–1.5% AUM

I want to be specific about what yield to expect. Position-fragmentation-only TLH across 11 sector ETFs should generate approximately:

- **Bull market year (low volatility, sectors correlated)**: 0.3–0.7% AUM — few positions diverge enough to create harvestable losses
- **Normal year (moderate volatility)**: 0.7–1.2% AUM — sectors take turns underperforming; 3–5 harvest events per year
- **Volatile year (high cross-sector dispersion)**: 1.2–2.0% AUM — multiple sectors down > 5% from purchase price; significant harvest opportunities

Central estimate: **~0.9% AUM** in a normal year, with meaningful downside in calm bull markets and upside in volatile ones.

Compare that to Wealthfront's ~0.25% AUM fee. At $500k AUM, that's $1,250/year in fees. The net TLH benefit (at a 32% tax rate on deferred gains) from 0.9% TLH yield is approximately 0.9% × 32% = **0.29% of AUM annually in tax beta** — roughly $1,450/year at $500k. After Wealthfront's fee, the net benefit is ~$200/year. Marginal.

At $2M AUM:
- Wealthfront fee: $5,000/year
- TLH benefit (32% × 0.9%): ~$5,760/year
- Net after fee: ~$760/year

The ratio improves with AUM because the fee is proportional and the TLH yield in absolute dollars grows, but the cost of the fee also grows. The real question is whether the platform's execution (including tranching) outperforms DIY by enough to justify the ongoing cost.

My honest answer: at $500k, maybe not, especially if you're competent to execute the sector ETF strategy yourself. At $2M+, the tranching layer and execution automation at Wealthfront/Parametric probably adds enough yield to justify the fee if you're in a high tax state. At $10M+, Parametric's full direct indexing probably wins outright.

### What We're Not Doing (Yet)

To be clear: we do not currently automate tranching. If you want to add position fragmentation yourself, you can buy all 11 sector ETFs at market today and begin harvesting. If you want tranching, either:
1. Do it manually: spread your purchases across 3–5 dates over the next few weeks
2. Use a platform: Wealthfront and Frec both automate tranching in their direct indexing products
3. Wait: tranching automation is on our roadmap for when execution automation is ready

We're not going to pretend this limitation doesn't exist to close a sale. The most compelling reason people *don't* do TLH themselves is operational — it's tedious and error-prone, not conceptually hard. We remove the operational friction; where we can't yet fully remove it, we say so.

## What Optimal Is Building

The **Optimal extension** generates the sector ETF basket allocation based on your target AUM, monitors lot-level loss thresholds across all 11 ETFs, and surfaces harvest+proxy swap opportunities as single execution plans. You see: "XLK is down 7.3% from your Jan 15 purchase. Harvest $12,400 loss, swap to VGT. Confirm?" — rather than manually tracking 11 positions, calculating loss percentages, and routing two orders. The execution is still yours to confirm, but the monitoring and staging are automated.

Tranching is on the roadmap when execution automation lands.

## What I Might Be Missing

1. **Tracking error tolerance**: I've assumed 1.5–3% tracking error is acceptable for the TLH benefit. For investors with benchmark-sensitive objectives (endowments, some institutional accounts), this might not be acceptable. If you have a hard tracking error constraint, the 11-ETF approach may not work for you.

2. **ETF-level wash sales from fund rebalancing**: When a sector ETF rebalances its underlying index (adds/removes constituents), you don't trigger a wash sale because you own the ETF, not the underlying stocks. This is an advantage over stock-level direct indexing. But I haven't fully modeled whether the proxy ETF's rebalancing events could create any substantially identical issue over long holding periods. This is probably not a concern in practice, but I flag it.

3. **The 70–80% yield capture estimate**: I'm citing a Vanguard Research white paper and secondary academic work. If you have access to empirical data from a real direct indexing program (Parametric or Wealthfront statements) showing position-only vs. full program yields, please share — even anonymized numbers would help calibrate this estimate.

**Open an issue at [GetOptimal/OptimalFinanceKB](https://github.com/GetOptimal/OptimalFinanceKB/issues)** labeled `direct-indexing-yield` with your empirical TLH yield data, your AUM range, the year, and whether you used tranching. I'll aggregate what comes in and update this estimate.

---

*Not legal, tax, or investment advice. The yield estimates in this post are based on published academic research and author analysis, not audited performance data. Your results will vary significantly based on market conditions, purchase timing, tax rates, and portfolio size. The "substantially identical" analysis for ETF proxy pairs is the author's working interpretation; consult a tax advisor before relying on any specific pair for wash sale purposes.*

*Last updated: 2026-05-06 | What I'd update on: Empirical yield data from readers; proxy pair wash-sale rulings; tranching research | Open questions: see issues labeled `direct-indexing-yield`*
