---
title: "Exchange Funds vs DIY: When Do You Actually Need Eaton Vance?"
slug: "exchange-funds-vs-diy"
status: draft
voice: open-investigator
last_updated: 2026-05-06
what_id_update_on: "Current all-in fee disclosures from Eaton Vance, Goldman, and Morgan Stanley exchange fund programs; any IRS ruling updating the 7-year diversification holding requirement; empirical data on exchange fund performance vs. stated benchmark"
---

# Exchange Funds vs DIY: When Do You Actually Need Eaton Vance?

## The Claim

If you have a large concentrated stock position, you need an exchange fund. Products like Eaton Vance Tax-Managed Diversified Equity Income Fund or similar offerings from Goldman Sachs, Morgan Stanley, and Parametric allow you to contribute your concentrated shares, receive a diversified portfolio interest, and defer (not eliminate) the capital gains tax — all while getting the diversification you need. This is the institutional solution for a real problem.

I want to be fair to this framing: exchange funds are a real product with real legal basis (IRC §721, partnership contribution rules) and real institutional history. The Eaton Vance programs have been operating for decades. For the right client, they may be the right answer.

What I'm examining is the specific conditions under which they beat a disciplined DIY approach — and finding that the gap is narrower than the marketing implies.

## The Working

### How Exchange Funds Actually Work

An exchange fund (also called a "swap fund" historically) works under IRC §721: when multiple investors contribute appreciated securities to a partnership, no gain is recognized at contribution time. Each investor receives a proportional partnership interest rather than cash.

The key requirements:
- **Accredited investor or qualified purchaser**: Most programs require $5M+ investable assets (QP standard)
- **7-year holding requirement**: To get tax deferral, you must hold the partnership interest for at least 7 years without withdrawing. Premature withdrawal triggers the deferred gain.
- **20% illiquid asset requirement**: The fund must hold at least 20% in "illiquid" assets (typically real estate, private equity, or similar) to qualify under the 1987 partnership anti-abuse rules. This affects your portfolio composition.
- **Basis carryover**: Your cost basis in the partnership interest equals the basis in the contributed shares. The gain is deferred, not eliminated. You (or your heirs) will eventually realize it — unless the estate steps up the basis at death.

This last point is worth dwelling on. Exchange funds don't eliminate capital gains tax. They defer it. The gain is preserved in the partnership's carryover basis. If you exit the fund after 7 years by selling your interest, you realize the full original gain plus any appreciation in the fund. The only path to permanent tax elimination is holding until death (stepped-up basis) or donating to charity (DAF, charitable remainder trust).

### The Real Numbers: 1% × 7 Years × $2M

Let me run a side-by-side for a $2M concentrated position over 10 years.

**Assumptions**:
- Position: $2M NVDA, $100k cost basis → $1.9M unrealized LTCG
- Federal LTCG rate: 23.8% (20% + 3.8% NIIT)
- State: CA, 13.3%
- Combined LTCG rate: 37.1%
- Time horizon: 10 years
- Portfolio return assumption: 7% annually (both exchange fund and DIY diversified)
- Exchange fund all-in fee: 1.0% AUM (conservative estimate; some programs are 1.5% or higher for smaller balances)
- DIY approach: systematic TLH-based exit over 7 years, diversified into low-cost ETFs (0.05% expense ratio)

**Exchange Fund path**:
- Contribute $2M on Day 1, no immediate tax
- 7-year lock-up: fund grows at 7% minus 1% fee = ~6% net
- Value at Year 7: ~$2M × 1.06^7 = **$3.01M**
- Can withdraw after Year 7: no tax until exit
- But basis is still ~$100k; exit now triggers $1.9M + appreciation in fund as gain

Actually, let me recalculate more carefully. The fund holds your basis. If you exit at Year 7:
- Partnership interest value: ~$3.01M
- Basis: $100k (carryover)
- Gain on exit: ~$2.91M
- Tax on exit: $2.91M × 37.1% = **$1.08M**
- Net after exit: ~$1.93M

What if you don't exit and hold through year 10?
- Value at Year 10: ~$2M × 1.06^10 = **$3.58M** (after fees)
- Hold and defer tax: ongoing cost is the 1.0% fee, now on a larger base

The 1.0% annual fee compounds over 10 years: on a starting $2M position, that's approximately:
- Year 1: $20,000 in fees
- Year 5: ~$24,000 in fees (on $2.4M)
- Year 10: ~$35,000 in fees (on $3.5M)
- Total fees over 10 years: approximately **$275,000**

**DIY path** (systematic TLH exit, assumes 5-year exit):
- Year 1: Harvest $50k in losses from existing portfolio; sell $100k of NVDA (net of losses: $50k gain at 37.1% = $18,550 tax)
- Progress: $100k diversified per year while harvesting losses; tax cost ~$18k–$37k/year
- By Year 5–7: Position largely diversified; no ongoing management fee
- Portfolio managed in low-cost ETFs at 0.05% AUM → on $2M: **$1,000/year**, vs. $20,000+/year for exchange fund

**Summary comparison** ($2M position, 10-year horizon):

| | Exchange Fund | DIY Systematic Exit |
|---|---|---|
| Year 1 tax trigger | $0 | ~$37k (if no TLH offsets) |
| Annual fee | ~$20k–$35k/year | ~$1k/year |
| Total fees (10 yr) | ~$275,000 | ~$10,000 |
| Lock-up | 7 years | None |
| Minimum investment | Typically $1M+ | No minimum |
| Accreditation required | Yes (QP or AI) | No |
| Gain eliminated | No (deferred) | No (realized over time) |
| Estate benefit | Basis carryover preserved | Stepped-up on sale proceeds reinvested |

The $265,000 fee differential over 10 years is a real number. The exchange fund needs to either (a) generate significantly better pre-fee returns than a DIY portfolio, or (b) enable more tax deferral than the DIY path allows, to justify that gap.

### When the Exchange Fund Wins

I want to be clear about the cases where I think the exchange fund wins:

**Position size > $10M**: The fee as a percentage becomes more manageable and the absolute tax deferral on a $10M+ position is large enough that even $275k in fees is a small fraction of the deferred tax liability (~$3.7M on $10M at 37.1%).

**Estate interaction**: If you are older, have a large estate, and plan to pass the concentrated position to heirs who will benefit from the stepped-up basis, the exchange fund's deferred-not-eliminated gain doesn't matter — neither does the DIY path's gain if the position is held in taxable until death. But the exchange fund provides diversification *during your lifetime* without realizing the gain, which has real risk management value.

**You won't execute DIY**: This is the most honest reason. If you genuinely will not run a multi-year systematic exit program — won't harvest losses, won't set an annual gain budget, won't hold to the plan when the stock goes up — then the exchange fund provides a one-time structural commitment to diversification. The 7-year lockup is a feature, not a bug, for behavioral reasons.

**Position is truly illiquid during the 7-year window**: Some founders or executives have lockup agreements, 10b5-1 plan constraints, or SEC Rule 144 volume limits that prevent systematic selling anyway. If you can't sell for 7 years under any strategy, the exchange fund's lock-up is irrelevant.

### When DIY Wins

**You're below $10M with disciplined execution**: The fee differential is the dominant factor, and it's hard to overcome at $2M–$5M position sizes.

**You're in a low-enough bracket for LTCG exemption**: At MFJ income under ~$583k, you pay 15% federal LTCG (not 23.8%). The tax cost of systematic exit is meaningfully lower, improving the DIY case.

**You need the flexibility**: The 7-year lockup is real. Life changes — you may need liquidity, change your estate plan, relocate states (which affects the tax rate comparison significantly). DIY is fully flexible.

## What Optimal Is Building

The Optimal extension's TLH Calculator lets you run the exchange fund vs. DIY comparison using your actual position size, cost basis, state, tax bracket, and estate planning objectives. You enter your inputs; you see the 10-year side-by-side with fee totals and break-even analysis. The goal is to make the "do I actually need Eaton Vance?" question answerable in a few minutes rather than a few months of advisor conversations.

## What I Might Be Missing

1. **Current fee disclosures**: The 1.0% AUM figure I'm using is a rough estimate from public discussions and advisor conversations. Some exchange fund programs disclose fees only to qualified purchasers and the all-in number (management fee + fund expenses + real estate drag) can differ significantly. If you have access to actual fee disclosures from a specific exchange fund program, I'd appreciate knowing the real numbers.

2. **The 20% illiquid requirement**: I've glossed over the impact of the 20% real estate/private equity allocation that exchange funds hold to satisfy the partnership tax rules. That illiquid portion has different liquidity, return, and fee characteristics than the public equity portion. This could meaningfully affect the actual portfolio experience.

3. **State exit traps**: If you contribute to an exchange fund in California and later move to a no-income-tax state before year 7, I don't know whether the deferred gain is subject to CA tax at exit or if the tax follows you. This has significant implications for high-CA-tax positions.

**Open an issue at [GetOptimal/OptimalFinanceKB](https://github.com/GetOptimal/OptimalFinanceKB/issues)** labeled `exchange-fund-vs-diy` with current fee disclosures, state exit trap analysis, or any empirical data on exchange fund performance vs. stated benchmark. I'll update the comparison model with better data.

---

*Not legal, tax, or investment advice. Exchange fund tax treatment under IRC §721 involves complex partnership tax rules; consult a qualified tax attorney or CPA before contributing to any exchange fund. Fee estimates are approximations; actual fees should be verified from fund offering documents. The worked examples use illustrative numbers and assumed tax rates.*

*Last updated: 2026-05-06 | What I'd update on: Actual exchange fund fee disclosures; state exit trap analysis | Open questions: see issues labeled `exchange-fund-vs-diy`*
