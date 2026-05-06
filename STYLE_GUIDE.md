# OptimalFinanceKB Style Guide

This document defines the voice, structure, and formatting standards for all content published in the OptimalFinanceKB repository. Its purpose: ensure that posts written by different contributors at different times sound like they came from the same place.

---

## Voice Blend

> **Open Investigator 70% / Practitioner-Engineer 20% / Documentarian 10%**

- **Open Investigator** (70%): First-person singular, showing working, naming uncertainty, inviting correction. The dominant register. Sounds like a rigorous analyst thinking out loud.
- **Practitioner-Engineer** (20%): Specific, technical, actionable. Numbers, formulas, tables. Shows that the author has actually done the thing.
- **Documentarian** (10%): Clear, well-organized, persistent. Good headings, consistent formatting, durable reference quality.

---

## The Three Beats

Every substantive post runs through three beats in this order:

### Beat 1: The Claim

> What the marketing / industry / conventional wisdom says, stated fairly enough that a proponent would nod.

The Claim section is **not adversarial**. It presents the conventional view with genuine charity. If the conventional view has real merit, say so. If a proponent would find the summary fair, you've done it right.

**In-voice example:**
> "Margin interest is tax-deductible. That's one of the reasons borrowing against your portfolio is efficient — the IRS lets you write off the interest cost against your investment income. Box spreads don't come with a clean interest statement, so they're not obviously better on a tax basis."

**Out-of-voice example (wrong):**
> "The financial industry tells you margin is deductible so you'll borrow from them and pay their rates. This is misleading."
>
> *Why wrong: adversarial, assumes bad faith, doesn't steelman the argument.*

---

### Beat 2: The Working

> What I find when I trace the math, mechanism, or incentives. First-person singular. Specific. Show working, don't just assert.

The Working section is the substance of the post. It should:
- Use "I" for personal analysis and conclusions
- Show actual math (tables, calculations, derivations)
- State assumptions explicitly and bracket them
- Cite sources for non-obvious claims
- Concede edge cases before the reader brings them up

**In-voice example:**
> "Let me run specific numbers. Assumptions: Filing status MFJ, W-2 income $350,000, federal marginal rate 32%, CA 9.3%... For a $200,000 loan at 6.5% APR → annual interest $13,000... The effective after-tax rate: ~3.82%."

**Out-of-voice example (wrong):**
> "The math works out in favor of box spreads when you account for the tax treatment."
>
> *Why wrong: asserts conclusion without showing work; "math works out" is not a number.*

---

### Beat 3: The Open Hand

> What I might be missing, and a specific invitation for evidence that would update my view.

The Open Hand section ends every post. It should:
- Name specific things the author is uncertain about (not vague hedge language)
- Describe evidence that would change the conclusion (be specific: what data, from whom, in what format)
- End with a concrete ask pointing to the issues tracker

**In-voice example:**
> "I've built this from first principles and validated it against a handful of real trades at Interactive Brokers. I don't have data on whether thinkorswim or Tastytrade achieves comparable fills. If you've executed a box spread at a non-IBKR broker and have fill data, I'd genuinely like to see it. Open an issue at GetOptimal/OptimalFinanceKB labeled `box-spread-execution`."

**Out-of-voice example (wrong):**
> "Please note this may not apply to all situations. Consult your financial advisor."
>
> *Why wrong: generic hedge, no specific ask, doesn't invite the reader into the dialogue.*

---

## Pronoun Discipline

| Pronoun | When to Use |
|---|---|
| **I** | Opinions, analysis, working, uncertainty ("I find," "I estimate," "I might be missing") |
| **we** | What OptimalFinance (the project/extension) is building or doing ("we build," "we're working on," "we give you") |
| **they / the literature / the disclosures** | Claims being examined ("they say," "the literature shows," "the disclosures note") |

**Never**: "you might want to consider" as a hedge without an actual recommendation. Either make the recommendation or name the specific condition under which you would.

---

## Eight House Style Devices

### 1. Steelman Before Critiquing

Pre-empt the strongest version of the opposing view. Credit what's right about it. Then proceed to the analysis.

> ✅ "The people saying this aren't wrong that box spreads require more setup than clicking 'borrow' on a margin account. The complexity is real. What I dispute is the framing of *what kind* of complexity it is."

### 2. Distinguish Known from Assumed

State assumptions explicitly and bracket them. Use a consistent format:

> "Assumptions: bracket MFJ, income $350k, federal 32%, CA 9.3%, NIIT excluded for simplicity."

Or in a table if multiple assumptions apply. Every worked example should have a visible assumptions block.

### 3. Name Uncertainty in Dollars, Not Vague Language

Don't say "may vary significantly." Say "the spread is roughly $200–$800 depending on [specific conditions]."

| Instead of | Write |
|---|---|
| "may vary significantly" | "typically $200–$800 depending on VIX level" |
| "could be substantial" | "the tax bill on a forced lapse could be $69,000–$120,000 in this example" |
| "might be an issue" | "at $500k AUM, this costs approximately $1,250/year in fees with ~$1,450/year in offsetting TLH benefit — net $200" |

### 4. Cite Practitioner Literature

When making non-obvious claims, cite:
- **Kitces.com** for financial planning analysis
- **Bogleheads wiki** for index/passive investing mechanics
- **IRS publications** for tax rules (Pub. 550, Pub. 946, etc.)
- **Revenue Rulings** (Rev. Rul. 2008-5, etc.) for specific IRS positions
- **AQR/Vanguard/DFA white papers** for factor/portfolio research
- **Academic literature** where relevant (Berkin & Ye, Israel & Moskowitz, etc.)

Do not use broker marketing materials as primary sources. Use disclosures (10-K, prospectus) as secondary sources.

### 5. Concede Edge Cases Proactively

Name the cases where your conclusion is wrong *before* the reader identifies them. This builds credibility and prevents the post from overstating its conclusions.

> ✅ "I should concede this clearly: for small loans (< $50k), margin is almost certainly better. The friction model breaks down at small size..."

### 6. The Optimal Hook (where applicable)

Each post should include 1–2 lines noting what the Optimal extension is building to make the strategy less manual, tedious, or error-prone. **Only where applicable.** Framing:

> "Most reasons NOT to do [strategy] DIY are operational — manual, tedious, error-prone. The Optimal extension automates [specific function]."

**Posts where the hook is brand-positioning only (no extension feature)**: Post #8 (TALSF) and Post #10 (whole life). Be explicit that these are brand-position posts, not feature posts.

### 7. Distinguish Deferred from Eliminated

Tax deferral and tax elimination are not the same. Exchange funds defer gains; they do not eliminate them. Policy loans are not income (not deferred, not a gain), but policy lapse converts the deferred gain to taxable income. Be precise.

| Instead of | Write |
|---|---|
| "tax-free policy loans" | "policy loans are not taxable income — but lapse converts the gain to ordinary income" |
| "eliminates capital gains" | "defers capital gains — the basis carries over and the gain survives" |
| "tax-free growth" | "tax-deferred growth — tax is due at distribution, not during accumulation" |

### 8. The Specific Ask

Every "What I Might Be Missing" section ends with a specific ask directed to the issues tracker. The ask should name:
1. The issue label
2. The specific data or information wanted
3. A format hint (screenshot, table, redacted statement, etc.)

> ✅ "Open an issue at GetOptimal/OptimalFinanceKB labeled `talsf-decay-curve` with your program's annual TLH yield over the years you've held it. Redact the program name and absolute dollar amounts — just the yield-as-percentage-of-AUM by year."

---

## Formatting Requirements

### Frontmatter

Every post file must begin with:

```yaml
---
title: "..."
slug: "..."
status: draft
voice: open-investigator
last_updated: YYYY-MM-DD
what_id_update_on: "..."
---
```

### Section Structure

- **H1**: Post title (once, at top)
- **H2**: Major sections (The Claim / The Working / What I Might Be Missing, plus any sub-topics within The Working)
- **H3**: Sub-sections within H2 sections

### Tables

Use Markdown tables for comparisons, assumptions, and worked examples with multiple variables. Minimum: a header row and one data row. Keep column headers short; use the caption row above the table for context.

### Code Blocks

Use fenced code blocks (` ``` `) for formulas, calculations, or pseudocode. Use inline code (`` ` ``) for single variables, rates, and specific values referenced in prose.

### Target Length

**1,500–2,500 words per draft.** Drafts are allowed to be long; published posts may be trimmed. Don't pad; don't truncate substance.

---

## Standing Footer Template

Every KB page ends with this footer:

```
---

*[Standard disclaimer: Not legal, tax, or investment advice. [Brief policy-specific note on what the analysis covers and where it simplifies]. Consult qualified advisors. [State any material assumptions if not already in the body].]*

*Last updated: YYYY-MM-DD | What I'd update on: [specific conditions that would change the analysis] | Open questions: see issues labeled `[label]`*
```

The disclaimer is kept short — a trust signal, not a legal document. Use language from existing posts as a template; don't introduce new qualifications not grounded in the post's content.

---

## Publishing Order Rationale

The suggested publishing order (see drafts index) leads with Post #8 (TALSF) because it:
1. Addresses an institutional product most readers have heard of but few have stress-tested
2. Has a strong Beat 3 ask (we want empirical data)
3. Positions Optimal against a clear alternative

Subsequent order: technical posts (#1, #2) establish credibility → operational posts (#3, #9) show problems automation solves → strategy posts (#4, #5, #6) show the full playbook → alternative analysis (#7, #10) complete the picture.

---

*This style guide should be updated when new voice conventions are established or when existing conventions prove unworkable. Open an issue labeled `style-guide` to propose changes.*
