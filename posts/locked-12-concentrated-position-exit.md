---
title: "The best way out of a concentrated position isn't for sale."
slug: "concentrated-position-exit"
status: published
voice: optimal
last_updated: 2026-10-02
---

# The best way out of a concentrated position isn't for sale.

Say you've got $10 million, $3 million of it in one stock with a $1 million basis. You want out. There are three roads. Two are products - [tax-aware funds like AQR](/blog/aqr-tax-deferred-bridge/) and [exchange funds like Cache](/blog/cache-exchange-funds/) - and I've taken apart each one's pitfalls separately (linked). The third is a strategy, not a product. Nobody sells it, which is the first clue it's good. Here's how it actually works.

Step one: borrow like an institution. A box spread is an options construction that behaves like a loan. Sell the box and you get cash today against a fixed payment at expiration, at an effective rate near Treasuries - cheaper than any margin loan, no sale of your stock, no taxable gain. Start small: against a $10 million portfolio, borrow $400,000.

Step two: build the loss engine. The borrowed cash doesn't go into one S&P fund. It goes into a basket of subsector ETFs - utilities, banks, semis, software, healthcare, energy - that together track the market but move independently. That's the point: independent movement means something is always down. When a subsector drops, you sell it, bank the loss, and immediately buy a sufficiently different substitute in the same space. Your market exposure never changes. Your tax losses accumulate.

Step three: the flywheel. Each harvested loss lets you sell a slice of the concentrated stock tax-free. Those proceeds buy more subsector ETFs, which create more harvesting surface, which frees the next slice. Each cycle is smaller than the last - an echoing flywheel - but it runs on one rule: never realize a gain without an offsetting loss. A strict $0 tax budget.

Two details make the math sing. First, the leverage isn't a cost center - it's a second loss engine. Borrowed at roughly 5.5% and invested at 7%, the carry is positive on its own. But the box spread's financing cost also comes back as Section 1256 losses, and those feed the same flywheel: they offset gains and unlock more tax-free stock sales, exactly like the harvested ETF losses do. Over 20 years, $910,000 of gross financing cost nets out to a $648,000 benefit. The loan pays you, twice. Second, taxes paid early are compounding capital removed: holding the $0 budget beat an unconstrained path by $2.6 million.

Now the comparison. I ran all three roads for 20 years at 7% market returns, top California rates, death and a basis step-up at the end. And I included the benchmark nobody includes: doing nothing.

Both products do their job - fully diversified, tax-managed, professional. And both leave you poorer than the guy who never touched his stock. The long/short fund finishes at $36.4 million. The exchange fund finishes at $37.0 million. Doing nothing finishes at $38.3 million. The fee drag outruns the tax alpha: every year, the meter quietly eats the benefit you paid for.

The flywheel is the only road that beats inertia. It finishes at $39.3 million, with 89% of the position recycled into diversified assets along the way - about a million dollars ahead of doing nothing. Not because it found a loophole, but because it keeps the two things the products take: the fees and the early taxes.

Is it fragile? A thousand simulated futures say no: the flywheel beats holding 63% of the time, versus 61% for the exchange fund and 59% for the long/short fund. Not a guarantee. But the base case isn't close.

So what are the products actually for? Speed, completeness, and delegation. Both get you to zero concentration without you learning what a box spread is, and for some people that's worth a million or two of terminal wealth. But that's a luxury purchase, not a financial decision. And doing nothing deserves its own honesty: the $4 million of tax you "save" by dying with the stock is the reward for holding risk you didn't want for 20 years. The flywheel's real competitor was never the products. It was inertia.

The caveat is execution. An individual can run this - no manager, no fee layer - but even the subsector TLH harvesting is easier said than done: it needs meticulous execution and benefits enormously from automation, and the box spread leverage doubly so. That doesn't change the direction of the math: for the concentrated, the riskiest position is the one you're already in, and sometimes the way out runs through more borrowing, not less.

## Assumptions

These are the inputs and checks behind the flywheel comparison. The strategy should be judged on reproducible after-tax wealth and risk, not the appeal of its name.

- **Starting wealth:** $10 million total, with $3 million in one stock and $1 million of basis, means 30% concentration and $2 million of embedded gain. Borrowing $400,000 is 4% of initial portfolio value. The remaining $7 million, its basis and its treatment must also be specified.
- **Returns and financing:** The base case uses 20 years, 7% market returns, roughly 5.5% borrowing and a death/step-up endpoint. The simple expected spread is 1.5 percentage points before costs and taxes; on a constant $400,000 balance that is $6,000 per year, not guaranteed profit. Future borrowing rates, rollover, cash flows and the compounding convention matter.
- **Financing benefit:** The $910,000 gross cost and $648,000 net benefit require the full annual debt schedule, contract proceeds/payoffs, Section 1256 tax character, usable offsets and reinvestment assumptions. They cannot be reconstructed from $400,000 and 5.5% alone. A financing loss is not itself income. Do not double count it as both a capital-loss benefit and an interest deduction.
- **Tax budget and harvesting:** The $0 realized-tax budget is a policy constraint, not a guarantee losses are available. The $2.6 million advantage requires the unconstrained path's sale and tax schedule. The 89% diversification figure needs the starting-position denominator, prices, sale dates, harvested losses and remaining shares.
- **Terminal wealth:** $36.4 million, $37.0 million, $38.3 million and $39.3 million are the original modeled outcomes. The flywheel-holding gap is $1 million; the product-holding gaps are $1.9 million and $1.3 million. The original annual return, fee, loss and tax schedules are not published here. The comparison needs the same endpoint, step-up treatment and cash-flow rules across paths. Concentrated holding is not risk-equivalent to diversification. Exit tax offsets part of a tax-aware strategy's benefit; it does not mean all benefits disappear.
- **Simulation:** 1,000 futures with 63%, 61% and 59% win rates require the return distribution, correlations, volatility, random seed, borrowing/margin rules, loss-harvesting algorithm, comparison metric and treatment of failed paths. None is supplied here. These are reported simulation estimates, not independently reproducible probabilities or guarantees. "$4 million saved" also needs the final gain and applicable tax rate, not starting wealth alone.
- **Product comparison:** The [AQR](../aqr-tax-deferred-bridge/) and [exchange-fund](../cache-exchange-funds/) appendices distinguish modeling fees from current terms and outline competing evidence. Updated product fees and exit choices can change these results.

Have better inputs, a missing cost or evidence that changes the result? [Share it](https://github.com/GetOptimal/OptimalFinanceKB/issues). We will update our assumptions and conclusions to reflect the most accurate representation.
