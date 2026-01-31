# Vault Mechanics

This section covers the technical details of how Collective vaults work.

## Vault Structure

Each vendor operates a separate vault. A vault consists of:

1. **Smart contract** — Handles deposits, withdrawals, and vault token issuance (on HyperEVM)
2. **Liquidity pool** — Stablecoins held on-chain
3. **Off-chain inventory** — Physical cards held by the vendor
4. **Oracle/reporting layer** — Updates vault value based on inventory valuations

## Vault Tokens

When you deposit, you receive vault tokens representing your share. These follow the ERC-4626 standard (tokenized vault):

- **Deposit:** USDC in → vault tokens out
- **Withdraw:** Vault tokens in → USDC out
- **Value:** Vault tokens appreciate as the underlying vault grows

Vault tokens are transferable. You can send them to another wallet or (eventually) trade them on secondary markets.

### Token Math

```
Vault Token Price = Total Vault Value / Total Vault Tokens Outstanding

Your Tokens = Deposit Amount / Vault Token Price

Your Value = Your Tokens × Current Vault Token Price
```

**Example:**
- Vault value: $100,000
- Tokens outstanding: 100,000
- Token price: $1.00
- You deposit $10,000 → receive 10,000 tokens
- Vault grows to $120,000 → token price is now $1.20
- Your 10,000 tokens = $12,000

## Deposits

Deposits are accepted anytime and processed as follows:

1. User approves USDC spend
2. User calls `deposit()` on vault contract
3. USDC transferred to vault
4. Vault tokens minted at current price
5. Tokens sent to user's wallet

Deposits are immediately reflected on-chain, but capital may not be deployed until the next epoch.

## Withdrawals

Withdrawals follow the epoch system:

1. User calls `requestWithdraw()` with token amount
2. Request queued for end of epoch
3. At epoch close, vault calculates final value
4. User calls `completeWithdraw()` to claim USDC
5. Vault tokens burned

For liquidity buffer withdrawals (small amounts), steps 2-3 may be accelerated.

## Valuation

The vault's total value combines:

- **On-chain balance:** USDC in the vault contract (real-time)
- **Off-chain inventory:** Cards held by vendor (updated via oracle)

Inventory valuation uses:
- Recent comparable sales (eBay sold, auction results)
- Conservative estimates for less liquid items
- Discounts for ungraded or illiquid inventory

Valuations are updated at least weekly, always at epoch boundaries.

## Epoch System

| Phase | Duration | What Happens |
|-------|----------|--------------|
| Active | ~11 weeks | Normal trading, deposits accepted |
| Request | ~2 weeks | Withdrawal requests submitted |
| Settlement | ~1 week | Valuation finalized, withdrawals processed |

Exact timing varies by quarter and is announced in advance.

---

→ [Fee Structure](/protocol/fees)
→ [Smart Contracts](/protocol/contracts)
