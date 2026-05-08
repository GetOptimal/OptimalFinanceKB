# OptimalFinanceKB

Welcome to Optimal Finance. This is a documentation-first repository for optimizing taxes, debt, and asset allocation. We treat personal finance as a System Engineering problem—shifting focus from "Saving" to "Efficiency Maximization." Below is a list of topics we would plan to build documentation on.


🗂️ The Optimization Index

**Cash Strategies**
1. Highest-yield placement: Evaluating 2026 spreads between HYSAs, VUSXX, and T-Bills.
2. Reverse Box Spread vs HYSA: More complicated but better aftertax return 
3. Emergency fund sizing vs. drag: Math on the opportunity cost of liquidity.
4. Bank-hopping for FDIC coverage: Using sweep networks to manage risk above $250k.

**Credit & Rewards Strategies**
1. Spend audits and optimization: Category matching for maximum point-per-dollar yields.
2. Card-stacking (e.g., Chase trio): Multiplier logic for premium rewards.
3. Cashback vs. points with time-value: Comparing immediate value vs. flexible but delayed redemption.
4. The Point Valuation Fallacy: Correcting for inflated redemption prices vs. true worth.

**Investing & Asset Allocation Strategies**
1. Three-ETF core portfolios: The broad-diversification base.
2. Active vs. passive management: Analysis of "Fee Decay" on terminal value.
3. DIY vs. robo-advisor vs. full advisor: Cost-of-time vs. Alpha trade-offs.
4. Rent-buy arbitrage: Modeling the $0 cost-to-buy delta in HCOL markets.
5. Zero-cost ETFs like BKLC: Removing structural drag.
6. Low/no-dividend ETFs: Minimizing tax drag in taxable accounts.
7. Dividends vs. controlled selling: Manual share liquidation vs. company-timed yields.
8. Concentration vs. diversification: Circle of Competence vs. broad indexes.

**Behavioral & Personality Strategies**
1. Panic triggers and selling fixes: Building buffers for market downturns.
2. Automation for savers: Removing willpower from the wealth-building pipeline.
3. Life-fit tweaks: Choosing the plan that actually works for you.
4. Marginal-benefit check: Evaluating if additional optimizations justify the effort.

**Rental Strategies**
1. Short-term vs. long-term rentals: Yield comp against operational overhead.
2. Segregated tax buckets: Isolating P&L for maximum deduction capture.
3. Depreciation horizons: Using non-cash expenses to lower taxable income.
4. Bonus write-offs: Sec. 179/Bonus depreciation for upfront cost deductions.

**Company Benefit Optimization**
1. HSA maximization: The triple-tax shield.
2. 401(k) front-load + match: Maximizing time-in-market early in Q1.
3. Backdoor Roth: High-earner access to Roth benefits.
4. Mega backdoor Roth: The after-tax pipeline for tax-free growth.
5. ESPP discounts: Arbitraging the discount and lookback period.
6. Deferred compensation: Tax deferral vs. employer credit risk.
7. Retirement equity vesting (55/15 or 60/10): Post-employment vesting rules.
8. Pregnancy disability/FMLA bridge: Stacking leave for extended paid time off.
9. Big-balance RMD cliff: Age-73 planning to avoid bracket jumps.
10. Dependent care FSA front-loading: The "Interest-Free Loan" childcare mechanic.
11. Mortgage-rate leverage: Using liquidity for sub-market rates.

**Tax Plays**
1. Converting 35k of 529 to Roth after 15 years: Re-pathing "trapped" education funds.
2. Tax-loss harvesting: Turning market "bugs" into income offsets.
3. Augusta rule 14-day rental: Tax-free rental income logic.
4. Mortgage interest deduction: Optimizing the $750k debt limit.
5. 529 plans: Tax-advantaged education savings.
6. Whole-life loans: Tax-free borrowing against cash value.
7. Tax-aware hedge wraps: Converting ordinary income to LTCG.
8. Exchange funds: Diversifying concentrated positions without tax triggers.
9. Buy-borrow-die: Leverage + stepped-up basis.
10. 83(b) elections: Locking in low cost basis for startup equity.
11. Qualified Small Business Stock (QSBS): The 100% tax exclusion for startup stock.
12. Medicaid for billionaires: Asset-shielding for long-term care.
13. Inheritance tax: Navigating gifting limits and portability.
14. Estate trust hacks: Minimizing estate taxes for heirs.
15. Prop-13 death shields: Preventing property tax reassessment.

**Debt Management Strategies**
1. Good debt vs. bad: Appreciating assets vs. consumption.
2. Payoff order: Avalanche vs. snowball logic.
3. Box spread loans: Synthetic low-interest borrowing via options.
4. Asset-backed loans: Preserving upside while accessing liquidity.

**Long-term Wealth Vehicles**
1. Roth IRA: Tax-free growth and withdrawals.
2. Backdoor Roth: (Repeated for emphasis).
3. 529 plans: (Repeated for emphasis).
4. Life-insurance cash bucket: Building cash value for volatility buffers.
5. Using life insurance like a Roth (If no Mega Backdoor): Creating a tax-free bucket when employer plans are limited.

🤝 Community Dialogue
This is a peer-review project for your wealth.
Debug the Math: See a bug in my logic? Open an Issue.
Suggest a Patch: Have a specific company's benefit guide? Submit a PR.
Dialogue: Join the daily optimization threads on X (@optimal_finance) or walkthroughs on YouTube.

## How publishing works

- Posts in this repo are published at `https://getoptimal.app/blog/<slug>`, where `<slug>` is the `slug:` value in each post's YAML frontmatter.
- Only posts with `status: published` are published. Posts marked `status: draft` stay private (while still visible in this repo and editable in the CMS).
- A push to `main` that touches `drafts/**`, `tax-plays/**`, or `STYLE_GUIDE.md` triggers the **Trigger Netlify rebuild** workflow, which calls a Netlify build hook for the <a href="https://github.com/GetOptimal/LandingPage">`GetOptimal/LandingPage`</a> site.
- For the workflow to trigger a Netlify build, this repo must have a `NETLIFY_BUILD_HOOK` secret configured:
  1. In the Netlify site for LandingPage → **Site configuration → Build & deploy → Build hooks** → **Add build hook**. Name it `kb-content-updated`, branch `master`, then copy the generated URL.
  2. In this repo → **Settings → Secrets and variables → Actions → New repository secret**. Name: `NETLIFY_BUILD_HOOK`; Value: the URL copied from Netlify.
- Non-content edits (for example CI/config/docs-only changes) do not trigger a rebuild. To force a rebuild, run the workflow manually from the **Actions** tab using **Run workflow** (`workflow_dispatch`).

---

## 📝 Blog Draft Index

Twelve lead-tier drafts written in the [Open Investigator voice](STYLE_GUIDE.md). Each post traces the math on a specific strategy, shows working, and ends with a specific invitation for evidence that would update the analysis.

**Suggested publishing order** (rationale in [STYLE_GUIDE.md](STYLE_GUIDE.md)):

| # | File | Title | Why This Order |
|---|---|---|---|
| 1 | [drafts/08-tax-aware-long-short-funds.md](drafts/08-tax-aware-long-short-funds.md) | Tax-Aware Long-Short Funds: The Strategy You Can Never Leave | Highest-leverage post; addresses institutional product most readers have heard of; strongest Beat 3 ask |
| 2 | [drafts/01-box-spread-pipeline.md](drafts/01-box-spread-pipeline.md) | Box Spread Loans: A Five-Stage Pricing Pipeline, Not a Hack | Establishes technical credibility; foundational for posts #2 and #5 |
| 3 | [drafts/02-1256-vs-163d.md](drafts/02-1256-vs-163d.md) | The §1256 Tax Treatment That Makes Box Spreads Structurally Cheaper Than Margin | Quantifies the tax advantage; best read after #1 |
| 4 | [drafts/03-cross-custodian-wash-sales.md](drafts/03-cross-custodian-wash-sales.md) | Cross-Custodian Wash Sales: The §1091 Trap Your Broker Won't Catch | Common operational failure; motivates why automation matters |
| 5 | [drafts/09-lot-level-vs-account-level-tlh.md](drafts/09-lot-level-vs-account-level-tlh.md) | Lot-Level vs Account-Level TLH: The Math Gap Is Bigger Than You Think | Pairs with #4; both are "what your broker won't do for you" posts |
| 6 | [drafts/04-subsector-direct-indexing.md](drafts/04-subsector-direct-indexing.md) | Subsector Direct Indexing Without Paying Wealthfront 0.25% | Shows the DIY framework after reader understands the wash-sale and lot-level context |
| 7 | [drafts/05-self-liquidating-leverage.md](drafts/05-self-liquidating-leverage.md) | Self-Liquidating Leverage: Borrow to Harvest, Harvest to Exit, Exit to Repay | Synthesizes box spreads + TLH into a de-risking cycle |
| 8 | [drafts/06-multi-year-concentrated-exit.md](drafts/06-multi-year-concentrated-exit.md) | Engineering a Multi-Year Exit from Concentrated Stock | Detailed playbook; best read after #7 establishes the leverage-as-bridge concept |
| 9 | [drafts/07-exchange-funds-vs-diy.md](drafts/07-exchange-funds-vs-diy.md) | Exchange Funds vs DIY: When Do You Actually Need Eaton Vance? | Alternative for concentrated positions; closes the loop on post #8 |
| 10 | [drafts/10-whole-life-policy-loans.md](drafts/10-whole-life-policy-loans.md) | Whole Life Policy Loans: The Honest Math | Standalone; honest broker on a topic where honest takes are rare |
| 11 | [drafts/11-deferred-comp-nqdc.md](drafts/11-deferred-comp-nqdc.md) | Deferred Comp: The Senior-Employee Perk Most Eligible People Don't Use | Largest single tax lever for top-bracket W-2 earners; scarce honest treatment |
| 12 | [drafts/12-rmd-cliff-smart-withdrawals.md](drafts/12-rmd-cliff-smart-withdrawals.md) | RMD Cliff at 73? Why the Right Move Might Be to Start Smart Withdrawals at 60 | Integrated RMD + IRMAA + NIIT + SS stacking problem; gap-year conversion ladder |

### Voice & Style

All posts follow the **Open Investigator voice** defined in [STYLE_GUIDE.md](STYLE_GUIDE.md):
1. **The Claim** — conventional wisdom, stated charitably
2. **The Working** — traced math, first-person, specific numbers
3. **The Open Hand** — what I might be missing + a real ask for evidence

Each post ends with a specific invitation to open an issue with data that would update the analysis. This is peer review for finance, not a content blog.
