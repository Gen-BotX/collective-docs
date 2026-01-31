# Fee Structure

Collective's fee model is designed to align vendor incentives with funder success.

## Performance Fee

Vendors earn a percentage of profits. This is only charged when the vault increases in value.

| Component | Details |
|-----------|---------|
| Rate | 20% of profits |
| Timing | Charged at epoch end |
| High-water mark | Yes — fees only on new highs |

### High-Water Mark Explained

The high-water mark protects funders from paying fees on recovery:

1. Vault peaks at $120,000 — vendor takes 20% of $20,000 profit = $4,000
2. Vault drops to $100,000 — no fee (it's a loss)
3. Vault recovers to $115,000 — no fee (still below $120,000 high)
4. Vault grows to $130,000 — vendor takes 20% of $10,000 (new profit above $120k) = $2,000

This ensures vendors only profit when funders profit.

## Management Fee

**None.** We don't charge a percentage of assets under management. Vendors only earn when they perform.

## Operating Costs

Vendors incur real costs running the operation. These are passed through to the vault:

| Cost Type | Examples |
|-----------|----------|
| Shows | Travel, hotels, table fees |
| Grading | PSA/CGC submission fees |
| Shipping | Insured shipping for purchases/sales |
| Storage | Secure storage facilities |
| Insurance | Inventory insurance premiums |

### Guardrails

To prevent abuse:
- Operating costs are reported monthly with itemization
- Annual cap: [X]% of average vault value
- Large expenses (>$1,000) require advance disclosure
- All costs visible to funders in reports

## Withdrawal Fees

| Withdrawal Type | Fee |
|-----------------|-----|
| Standard (end of epoch) | 0% |
| Emergency (mid-epoch) | 3% |

The emergency fee compensates remaining funders for the disruption of forced liquidation.

## Platform Fee

Collective (the platform) takes a small fee to cover infrastructure and development:

| Fee | Amount |
|-----|--------|
| Platform fee | [X]% of vault value annually |

This is separate from vendor fees and covers:
- Smart contract maintenance
- Platform development
- Support and operations

## Fee Summary

| Fee | Who Receives | Amount |
|-----|--------------|--------|
| Performance | Vendor | 20% of profits |
| Management | — | None |
| Operating costs | Vendor (pass-through) | Variable, capped |
| Emergency withdrawal | Vault (remaining funders) | 3% |
| Platform | Collective | [X]% annually |

---

→ [Smart Contracts](/protocol/contracts)
→ [Transparency](/protocol/transparency)
