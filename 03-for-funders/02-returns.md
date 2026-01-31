# How Returns Work

Collective vaults generate returns from vendor trading activity. Here's how it works.

## Source of Returns

Vendors make money by:

1. **Buy low, sell high** — Sourcing cards below market value and selling at fair price
2. **Arbitrage** — Exploiting price differences across platforms or regions
3. **Timing** — Buying before anticipated demand spikes (set rotations, anniversaries, etc.)
4. **Grading plays** — Buying raw cards, grading them, selling the graded versions at premium

Returns vary based on market conditions, vendor skill, and opportunities available.

## How Value Is Tracked

The vault's value is calculated as:

```
Vault Value = Cash on Hand + Inventory Value
```

**Cash on hand:** Stablecoins sitting in the vault (not yet deployed or from recent sales)

**Inventory value:** Fair market value of all cards held by the vendor, based on:
- Recent comparable sales
- Auction data
- Grading population reports
- Conservative estimates for illiquid items

Vault value is updated regularly (at least weekly) and always at epoch boundaries.

## Your Returns

Your returns are proportional to your vault token holdings:

```
Your Value = (Your Vault Tokens / Total Vault Tokens) × Vault Value
```

Returns compound automatically. As the vault grows, your tokens are worth more — no need to claim or reinvest.

## Fees

Vendors charge a **performance fee** on profits. This is only taken when the vault increases in value above its previous high (high-water mark).

**Current fee structure:**
- **Performance fee:** 20% of profits
- **Operating costs:** Covered from vault (travel, show fees, grading, shipping)

Operating costs are reported transparently and capped to prevent abuse.

**Example:**
- Vault starts at $100,000
- Vault grows to $120,000 → $20,000 profit
- 20% performance fee → $4,000 to vendor
- Net vault value → $116,000

If the vault later drops to $110,000 and recovers to $116,000, no fee is taken (high-water mark not exceeded).

## Historical Performance

Past performance is shown on each vendor's profile page. We display:

- Monthly and quarterly returns
- Cumulative performance since inception
- Comparison to relevant benchmarks (Pokémon market indices, etc.)

**Note:** Past performance does not guarantee future results.

---

→ [Withdrawing](/for-funders/withdrawals)
→ [Risks](/for-funders/risks)
