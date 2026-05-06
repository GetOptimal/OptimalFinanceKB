---
title: "Engineering a Multi-Year Exit from Concentrated Stock"
slug: "multi-year-concentrated-exit"
status: draft
voice: open-investigator
last_updated: 2026-05-06
what_id_update_on: "Reader data on actual exit timelines for NVDA/FAANG-level positions; better modeling of the interaction between RSU vesting and exit planning; any PLR on eagerness-level elections as a tax planning mechanism"
---

# Engineering a Multi-Year Exit from Concentrated Stock

## The Claim

"I'll diversify slowly." Most people with a large concentrated position — say, $1M+ in NVDA, a tech employer's stock, or shares from a company sale — have said some version of this. The plan is: sell a little each year, pay the capital gains tax as you go, and eventually you're diversified. It's logical, tax-aware, and better than doing nothing.

The problem isn't the intent. It's that "slowly" is not a plan — it's a disposition. Without a specific annual gain budget, a TLH loss offset strategy, and an explicit policy for each position (how aggressive should this exit be?), "slowly" becomes "never" when the stock keeps going up, and then "in a panic" when it doesn't.

I've talked to people who've been "diversifying slowly" for eight years and are still 70%+ in one name. The psychological inertia is real. The tax drag is real. And the volatility risk of running a concentrated single-stock position for a decade is very real.

This post is about converting "slowly" into an actual 5–10 year engineering project.

## The Working

### The Three Knobs

A systematic multi-year exit from concentrated stock has three decision variables:

**Knob 1: Annual gain budget** — How much capital gains (net of any available losses) are you willing to realize per year? This is partly a bracket-management question (you may want to stay below the NIIT threshold at $250k NII for single/$500k MFJ, or below a specific bracket), and partly a cash flow question (you need to pay the resulting tax bill). I typically recommend setting the annual budget as the larger of:
- The amount you can pay in capital gains tax without disrupting cash flow (e.g., "I can write a $60k check to the IRS without strain")
- The amount of losses you're generating through TLH (which offsets gains dollar-for-dollar)

**Knob 2: Loss generation rate** — How many losses can you generate per year through TLH, box spread §1256 losses, and other strategies? This is a function of your taxable portfolio composition, your TLH discipline, and whether you're using leverage instruments like box spreads. A well-run TLH program on a $500k diversified portfolio might generate $20k–$50k in losses per year. These losses directly increase your exit budget without increasing your tax bill.

**Knob 3: Eagerness per position** — For each concentrated position, you set an explicit exit policy:
- **Tax-Neutral**: Sell only the amount offset by available losses. Never realize a net gain. Exit is slow but tax bill is near zero each year.
- **Bleed It Out**: Sell enough each year to stay within a specific bracket (e.g., fill up the 20% LTCG bracket before crossing into NIIT territory). Steady, predictable, takes 7–15 years for large positions.
- **Rip the Band-Aid**: Sell as aggressively as cash flow allows regardless of bracket, accepting the full tax bill in exchange for faster diversification and reduction of single-stock risk.

The eagerness setting should match your actual risk tolerance for the position, not your general investment philosophy. A position in a single tech company with massive unrealized gains warrants different eagerness than a position in a diversified ETF you've held for years.

### Worked Example: $1M NVDA, $100k Annual Gain Budget

Assumptions:
- Current NVDA position: $1M market value, $50k cost basis → $950k unrealized LTCG
- Filing status: MFJ
- Federal LTCG rate at this income: 23.8% (20% + 3.8% NIIT)
- CA state tax on LTCG: 13.3% (CA taxes LTCG as ordinary income)
- Combined LTCG rate: ~37.1%
- Annual gain budget: $100k (comfortable writing $37,100 check per year)
- TLH loss generation: $25k/year from existing diversified portfolio
- Eagerness: Bleed It Out

Year-by-year projection:

| Year | Available Losses | Net Exit Budget | Shares Sold (approx.) | After-Tax Proceeds | Remaining Position |
|---|---|---|---|---|---|
| 1 | $25,000 | $125,000 | ~12.5% | ~$125k − $37k tax = $88k net | ~$875k |
| 2 | $25,000 | $125,000 | ~12.5% of remainder | ~$88k net | ~$766k |
| 3 | $25,000 | $125,000 | ~12.5% of remainder | ~$88k net | ~$670k |
| 4 | $25,000 | $125,000 | ~12.5% of remainder | ~$88k net | ~$586k |
| 5 | $25,000 | $125,000 | ~12.5% of remainder | ~$88k net | ~$513k |

*Assumes NVDA price stays flat for simplicity — in reality, if the stock continues to appreciate, the % sold each year represents fewer shares and the absolute position may not decline. This is the "stock keeps going up" problem.*

At this pace, it takes approximately 9–11 years to reduce the position below $200k (at flat stock price). If the stock appreciates significantly, the timeline extends indefinitely — which is the behavioral trap of "slowly."

### The Stock-Keeps-Going-Up Problem

The single hardest challenge in systematic exit planning is that if the stock is going up, every year you delay selling looks like the right call in hindsight, and every year you do sell looks like you "left money on the table." This dynamic explains why so many engineers and early employees at high-growth companies end up with 10-year positions that only get liquidated at a large loss or at estate.

I don't have a perfect behavioral fix for this. But I can point at what the model says: if you have $1M in a single stock, the expected loss from the concentration itself (excess variance vs. a diversified portfolio) costs you roughly 1–2% per year in risk-adjusted terms based on empirical concentrated portfolio studies (see Bessembinder 2018 on stock return dispersion). On a $1M position, that's $10k–$20k/year in risk you're carrying for free — and that cost rises as the position grows with the stock price.

The rational response to a rising concentrated position is to sell *faster*, not slower, because the risk exposure grows. That's counterintuitive but mathematically supported.

### Interaction with RSU Vesting

Many people accumulate concentrated positions through RSU vesting, not through a single purchase. This complicates the plan:

1. **New high-basis shares vesting annually**: If you continue to receive RSUs in the same company, new shares vest each year at current market price. These shares have a high cost basis (ordinary income was recognized at vest). Selling them quickly after vest recognizes only the gain since vest — often a small amount. This is the easiest part of the exit.

2. **Old low-basis shares**: The shares accumulated over years of vesting have low bases and large unrealized gains. These are the exit challenge.

The optimal RSU exit strategy: **sell new vest immediately** (low tax cost, reduces concentration) and **sell old shares systematically** under the exit plan above. Don't let the new-vest-hold decision bleed into the old-share strategy.

### Three-Position Household

Complexity multiplies when you have multiple concentrated positions (NVDA from employer, AAPL from prior employer, AMZN from an early investment). In that case, the three-knob framework applies per position, and you need a household-level view of:
- Total unrealized gains across all positions
- Available losses per year
- Optimal sequencing (which position to exit first based on risk, return expectation, and tax efficiency)

General heuristic: exit the highest-risk, lowest-expected-return positions first, regardless of tax cost. Concentration risk is real; don't let tax-aversion override basic diversification.

## What Optimal Is Building

The **Concentration Exit add-on** in Optimal lets you flag concentrated positions, set an eagerness level per position (Tax-Neutral / Bleed It Out / Rip the Band-Aid), and set an annual gain budget. The planner then pairs exit sales with available losses across the household — including TLH harvests from the diversified portion of the portfolio — and generates a year-by-year projection. You see: "At current pace, NVDA position reaches < $200k in 2033. Want to accelerate to 2030? Here's what that costs in additional taxes."

## What I Might Be Missing

1. **AMT interaction for ISOs**: If the concentrated position includes ISOs exercised in prior years, the AMT basis may differ from the regular tax basis. The exit math changes significantly and I've simplified this away. If you have a meaningful ISO position, work through the dual-basis math before setting your exit plan.

2. **The gift/DAF option**: For the highest-gain lots, donating to a donor-advised fund or gifting to low-income-bracket family members may be more efficient than selling. I've excluded this from the main analysis because it assumes capital disposition, not charitable intent.

3. **Step-up in basis at death**: "Die holding it" is a real strategy for concentrated positions in an estate context. If you're near end-of-life planning, the stepped-up basis at death eliminates the LTCG entirely. I've modeled this for a wealth-building investor with a long time horizon, not an estate planner. The analysis differs significantly for estate planning.

**Open an issue at [GetOptimal/OptimalFinanceKB](https://github.com/GetOptimal/OptimalFinanceKB/issues)** labeled `concentrated-exit` with your situation. Specifically: if you've run a multi-year exit plan and can share the timeline and how it deviated from projections, that would help calibrate the behavioral model.

---

*Not legal, tax, or investment advice. The examples use illustrative numbers, assumed tax rates, and simplified growth assumptions. Real concentrated exit planning requires individual tax advice, especially for ISO/AMT situations, spousal income interactions, and estate considerations. The tax rates cited (23.8% federal LTCG, 13.3% CA) reflect current law as of the post date; consult your advisor for current applicable rates.*

*Last updated: 2026-05-06 | What I'd update on: ISO/AMT interaction model; empirical exit timeline data | Open questions: see issues labeled `concentrated-exit`*
