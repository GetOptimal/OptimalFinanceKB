---
title: "Are tax-aware funds like AQR a tax-deferred bridge to nowhere?"
slug: "aqr-tax-deferred-bridge"
status: published
voice: optimal
last_updated: 2026-10-02
---

# Are tax-aware funds like AQR a tax-deferred bridge to nowhere?

The pitch: hand a manager your concentrated stock problem. They build a diversified long/short book around it, engineered to realize capital losses while keeping market exposure. The losses offset your gains as you sell slices of the concentrated position. You diversify without the tax bill. AQR built a business on this, and the mechanics are real.

How it works: the long side owns a diversified basket. The short side shorts against it. Markets zigzag, and both sides throw off realized losses at a healthy clip while the combined book tracks the market. Those losses are the product. Everything else is packaging.

Now the pitfalls.

The fee stack is three layers deep. The management fee is the one they quote. Under it sit financing costs on the short book and the leverage. Under those sits the broker or platform fee you pay to access the strategy at all - anywhere from zero to a full point depending on your custodian. Our comparison uses 85 to 90 basis points all-in, every year, on the whole book. That is a modeling assumption, not a current AQR quote. The question is whether the full fee stack and exit taxes offset enough of the tax benefit to make the strategy worth less than the alternatives over 20 years.

The losses decay. A fresh book harvests aggressively. A seasoned book has already banked its easy losses and generates less incremental benefit each year. The fee does not decay.

The exit has a price. In a full cash liquidation, closing positions can realize deferred gains, and appreciated longs can carry low basis. That tax bill offsets part of the benefit the AQR-style strategy delivered to begin with; it does not erase every benefit of keeping more capital invested along the way. Leaving a manager is not always the same as liquidating the book: a manager change, in-kind transfer or gradual unwind can lead to a different bill. Know which exit you are buying.

The SMA versus pooled distinction matters. In a separately managed account you own the securities and can in principle move the longs in kind. In a pooled fund you own shares of the fund, and your exit is a redemption on their terms.

And the quietest pitfall: the benchmark. Compare the strategy with more than 'sell everything and pay the tax bill.' Include holding the concentrated stock to a potential stepped-up basis at death, while recognizing that holding leaves you exposed to the concentrated stock. Our original 20-year estimate puts the strategy at $36.4 million against $38.3 million for holding - about $2 million behind. Those figures depend on the model inputs and exit assumptions; they are not a universal verdict. The appendix sets out the working assumptions and what is needed to reproduce the comparison.

What they sell is real: speed, completeness, and delegation. You get to zero concentration without learning what a box spread is. For some people that's worth the toll. Just know the toll is not the advertised management fee. It's the full fee stack and the exit-tax cost that offsets part of the benefit, measured against the value of diversification and keeping more capital invested. The bridge goes somewhere. Just make sure the toll is buying an outcome you actually want.

## Assumptions

Our argument is about the full bill: fees, financing and exit taxes versus the value of diversification and tax deferral. These are the working assumptions behind our comparison. Better evidence should improve the model, not end the conversation.

- **Fees:** Our illustration uses 85-90bp a year (0.85%-0.90%) on the whole book - $900 per $100,000 annually at 90bp. Modeling assumption, not a current AQR quote. Platform range is 0%-1% by provider. Reproducible comparison needs management, platform, financing and short-borrow separated, no double counting. Original cost breakdown not included with this article.
- **Taxes:** 37% combined rate is the illustration. Your rate depends on year, state, income, gain type, NIIT. Basis, sale schedule and usable losses determine the benefit. A loss on paper is not cash saved today.
- **The 20-year comparison:** $36.4m strategy vs $38.3m holding; gap $1.9m, rounded to $2m. Model inputs (starting wealth, returns, dividend taxes, leverage, harvesting schedule, reinvestment, liquidation calc) not published here. Estimate, not a universal ranking.
- **Exit and benchmark:** Holding assumes no sale 20 years + step-up at death; retains concentration risk. Same endpoint both paths. Full liquidation, manager change, in-kind transfer, gradual unwind are different exits; SMA vs pooled fund differ. Exit tax offsets part of the benefit - it does not mean all benefits disappear.
- **AQR's counterclaim:** [Their liquidation analysis](https://www.aqr.com/Insights/Research/Tax-Aware-Investing/The-Impact-of-Liquidation-Taxes-on-the-Lifecycle-Benefits-of-Tax-Aware-Long-Short-Strategies) finds benefits can exceed the liquidation tax under their assumptions, and describes alternatives to full unwind. Competing model worth examining - not a fee quote or a reproduction of ours. The useful test: same starting portfolio, full costs, usable losses, risk and exit plan on both sides.

Have better inputs or a fuller fee schedule? AQR and readers are welcome to [share it](https://github.com/GetOptimal/OptimalFinanceKB/issues). We will update our assumptions and conclusions to reflect the most accurate representation.
