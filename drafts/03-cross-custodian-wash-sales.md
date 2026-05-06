---
title: "Cross-Custodian Wash Sales: The §1091 Trap Your Broker Won't Catch"
slug: "cross-custodian-wash-sales"
status: draft
voice: open-investigator
last_updated: 2026-05-06
what_id_update_on: "IRS enforcement activity or audits specifically targeting cross-custodian wash sales; any ruling clarifying 'substantially identical' for ETF proxy pairs; updates to Rev. Rul. 2008-5 application"
---

# Cross-Custodian Wash Sales: The §1091 Trap Your Broker Won't Catch

## The Claim

Your 1099-B will catch your wash sales. Brokers are required to report wash sale adjustments, and the IRS gets the same data you do. As long as you follow your broker's wash sale warnings, you're covered.

This belief is almost universally held, and I understand why — it's technically true within a single account at a single broker. Fidelity will flag it if you sell TSLA at a loss in your Fidelity taxable account and buy it back within 30 days in the same account. That part of the system works.

The part that doesn't work is everything else.

## The Working

### §1091 Is Per-Taxpayer, Not Per-Broker

The wash sale rule under IRC §1091 applies to the **taxpayer**, not to any individual account or custodian. The statute doesn't know or care that your Fidelity account and your Schwab account are separate databases. The relevant unit is you (and, for these purposes, your spouse, and entities you control).

The 1099-B is per-broker. Your broker can only see what happens in accounts you hold at that broker. When you sell a position at a loss at Fidelity on Tuesday and rebuy the same security at Schwab on Friday (within the 30-day window), Fidelity has no idea the Schwab purchase happened. Fidelity's 1099-B correctly reports no wash sale. Schwab's 1099-B correctly reports a buy. Neither broker can see the violation — but the violation exists under the statute.

The IRS's matching system, which compares 1099-B data across filings, does not cross-reference transactions across brokers for wash sales. So the trap is real, underreported, and rarely caught — until it is.

### Three Scenarios Where This Bites You

**Scenario 1: Multi-Custodian Active TLH**

You're harvesting losses at Fidelity and you have a separate brokerage account at Schwab (perhaps opened for a specific deal or as a backup). You harvest VTI at a loss on Monday at Fidelity and immediately buy ITOT (a potential wash sale — more on that below) at Schwab. The 30-day window applies to the ITOT purchase, but it also applies to a VTI repurchase. If you buy VTI at Schwab within 30 days, the Fidelity harvest is disallowed. No one tells you.

**Scenario 2: Spousal IRA Rebuy**

Rev. Rul. 2008-5 established that wash sale rules apply to transactions between a taxpayer's taxable account and their **IRA** (traditional or Roth). This is the most commonly violated scenario I've seen in practice. The sequence:

1. Spouse A sells stock X at a loss in their taxable brokerage account
2. Spouse B (filing jointly) rebuys stock X in their Roth IRA within 30 days

The result under Rev. Rul. 2008-5 and §1091: the loss is **permanently disallowed** — not deferred, not carried into the IRA's basis, but gone. This is different from a regular wash sale where the loss adjusts the basis of the replacement shares. The IRA disallowance is a true permanent loss of the tax benefit.

The IRS rationale: you can't recover the disallowed loss later because IRA distributions don't track individual security basis the same way.

**Scenario 3: 401(k) Underlying Overlap**

This scenario is more theoretical but worth naming. If your 401(k) holds a mutual fund whose underlying holdings substantially overlap with securities you're harvesting in taxable, you could have a §1091 issue — though the "substantially identical" standard is harder to apply to mutual fund shares vs. individual securities, and there's no IRS guidance I've found specifically addressing this scenario. I flag it as an open question, not a settled rule.

### The "Substantially Identical" Boundary

Section 1091 disallows losses on sales of stock or securities if you acquire "substantially identical" stock or securities within 30 days before or after the sale. The 30/30 window: 30 days before the sale date through 30 days after.

What is "substantially identical"?

- **Same security**: clearly yes. VTI → VTI is a wash sale.
- **Same underlying ETF, different share class**: almost certainly yes. VTI (Vanguard) → VITSX (same underlying fund, institutional class) — very likely treated as substantially identical.
- **Competing ETFs tracking the same index**: uncertain, and this is where the practitioner community has the most debate. VTI (total market) → ITOT (total market, BlackRock) — same index, same coverage. The IRS has not issued a ruling specifically on whether two ETFs tracking the same index are substantially identical. The conservative view is that they are; the aggressive view is that different issuers, different fund structures, and different tracking methodologies are distinct securities. I lean conservative.
- **Competing ETFs tracking different but correlated indexes**: probably safe. VTI (CRSP US Total Market) → SCHB (Dow Jones Broad Market) — different index committees, different constituent selection, different rebalancing rules. The academic literature on index overlap doesn't directly inform the tax analysis, but the more different the index methodology, the stronger the "not substantially identical" argument.
- **Factor ETFs vs. broad index**: generally safe, with clear economic differences. VTI → VBR (small-cap value) is a meaningful style shift that should hold up.

I keep a proxy pair table (see also Post #4 on direct indexing) for reference:

| Harvest | Proxy | Risk Level | Notes |
|---|---|---|---|
| VTI | ITOT | Moderate | Same index; IRS has not ruled |
| VTI | SCHB | Lower | Different index methodology |
| QQQ | ONEQ | Higher | Very similar coverage |
| QQQ | VGT | Moderate | Tech-focused, different weights |
| XLK | VGT | Moderate | Sector ETF overlap |
| SPY | IVV | Higher | Same index; likely substantially identical |
| SPY | SCHX | Lower | Broader index, different methodology |

### The Detection Gap Is Structural

This isn't a theoretical problem. I've spoken with tax preparers who say cross-custodian wash sales are among the most common errors on self-prepared returns. The tax law is per-taxpayer; the information reporting is per-broker; the taxpayer is in the middle, responsible for reconciling what neither broker can see.

If you're running TLH across multiple custodians, you need a manual or automated system that:
1. Tracks all wash-sale-relevant positions across all accounts (taxable + IRAs + 401(k) where possible)
2. Flags a harvest in Account A when any account held at any custodian has bought a substantially identical security within the prior 30 days, or might do so in the next 30
3. Enforces the 30-day hold on replacement shares across all accounts

## What Optimal Is Building

The **Optimal extension** connects to multiple custodians simultaneously and enforces §1091 at the household level. When you harvest a position at Fidelity, the extension holds a 30-day rebuy flag on that security (and any securities it deems substantially identical based on our pairing table) across all connected accounts — Schwab, Vanguard, IRAs, wherever. Staging a harvest in one account automatically blocks rebuy in any other connected account for the window. This is the primary operational reason TLH benefits from a tool: a human tracking 4+ accounts across 30-day windows manually will make errors; the extension doesn't.

## What I Might Be Missing

1. **Rev. Rul. 2008-5 and Roth IRA rebuys**: I've cited this ruling for traditional IRAs but I believe it applies equally to Roth IRAs. If there's a distinction in the ruling or subsequent guidance I'm not aware of, please flag it.

2. **401(k) overlap**: I've noted this as an open question. If you know of IRS guidance, a PLR, or a Tax Court case specifically addressing whether 401(k) plan purchases can trigger §1091 wash sales, I'd like to see it. The structural argument that you can't control 401(k) investment timing seems relevant but I haven't found it adjudicated.

3. **State conformity**: Most states conform to federal wash sale treatment. But not all. If your state has a non-conforming wash sale rule (or no capital gains tax), the cross-custodian risk profile changes. I've written this in the federal-conforming state model; add your state situation in the comments.

4. **The "substantially identical" standard for bond ETFs and commodity ETFs**: I've focused on equity ETFs. If you're harvesting fixed income ETFs or commodity ETFs, the substantially identical analysis is different and I haven't fully worked through it.

**Open an issue at [GetOptimal/OptimalFinanceKB](https://github.com/GetOptimal/OptimalFinanceKB/issues)** labeled `wash-sale-cross-custodian` with any of the above. Specifically: if you've had a wash sale dispute with the IRS involving cross-custodian transactions, I'd like to understand what triggered the examination and how it resolved.

---

*Not legal, tax, or investment advice. Rev. Rul. 2008-5 is cited from publicly available IRS guidance; confirm its applicability to your situation with a qualified tax advisor. The "substantially identical" analysis for specific ETF pairs is my working interpretation, not a settled legal determination. The IRS has not issued comprehensive guidance on ETF-to-ETF substantially identical questions; a conservative approach and qualified tax advice are warranted.*

*Last updated: 2026-05-06 | What I'd update on: IRS guidance on ETF substantially identical; any enforcement actions involving cross-custodian TLH | Open questions: see issues labeled `wash-sale-cross-custodian`*
