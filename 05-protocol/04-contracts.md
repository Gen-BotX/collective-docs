# Smart Contracts

Collective uses minimal, audited smart contracts for deposit and vault token management.

## Architecture

Our contracts are intentionally simple:

```
┌─────────────────┐     ┌─────────────────┐
│   User Wallet   │────▶│   Vault Contract │
└─────────────────┘     └─────────────────┘
                               │
                               ▼
                        ┌─────────────────┐
                        │  Vault Tokens   │
                        │   (ERC-4626)    │
                        └─────────────────┘
```

**What the contract does:**
- Accept USDC deposits
- Mint vault tokens proportionally
- Process withdrawal requests
- Burn vault tokens on withdrawal
- Track vault token price via oracle updates

**What the contract doesn't do:**
- Hold inventory (cards are physical)
- Make trading decisions
- Enforce vendor behavior

## Contract Addresses

| Contract | Address | Chain |
|----------|---------|-------|
| Collective Vault | [TBD] | HyperEVM |
| Vault Token | [TBD] | HyperEVM |

Contracts will be published and verified on block explorer.

## Security

### Design Principles

- **Minimal complexity** — Less code = fewer bugs
- **Battle-tested standards** — ERC-4626 for vault tokens
- **No admin keys** — Immutable where possible
- **Transparent upgrades** — Timelock for any changes

### Audits

Audit status: **Pending**

We plan to have contracts audited before mainnet launch. Audit reports will be published here.

### Bug Bounty

We will operate a bug bounty program for responsible disclosure:

| Severity | Reward |
|----------|--------|
| Critical | Up to $[X] |
| High | Up to $[X] |
| Medium | Up to $[X] |

Details: [TBD]

## Oracle System

The vault value includes off-chain inventory. We use an oracle to update this:

- **Update frequency:** At least weekly, always at epoch boundaries
- **Data source:** Vendor-reported inventory valuations
- **Verification:** Cross-checked against market data
- **Dispute window:** [X] hours before finalization

The oracle is a trusted role initially. As we grow, we'll explore more decentralized solutions.

## Risks

Smart contracts carry inherent risks:

- **Bugs:** Undiscovered vulnerabilities could lead to loss of funds
- **Oracle manipulation:** Incorrect valuations could affect withdrawals
- **Chain risk:** HyperEVM is newer and less battle-tested than Ethereum mainnet

See [Risks](/for-funders/risks) for full details.

---

→ [Transparency](/protocol/transparency)
→ [Risks](/for-funders/risks)
