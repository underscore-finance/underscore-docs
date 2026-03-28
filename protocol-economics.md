---
description: How Underscore generates revenue and what happens with it
---

# Protocol Economics

Underscore generates revenue through fees on value-generating activities. Most of that revenue comes from a 20% performance fee on vault profits, so the protocol earns when vault users earn. 100% of protocol revenue is used to buy back [$RIPE](https://app.ripe.finance/ripe) in the open market.

---

## Revenue Sources

### Vault Performance Fees (Primary)

The largest source of protocol revenue comes from [Underscore Earn Vaults](vaults.md). That includes both Core Vaults and Amplified Vaults.

- **Fee**: 20% of yield profits
- **Applied to**: Profits only, never principal
- **When charged**: When yield is realized

**Example**: A vault generates $100,000 in yield across all depositors
- $20,000 → Protocol revenue
- $80,000 → Distributed to depositors via increased share price

Vault performance fees scale with protocol TVL and yield performance, making this the primary revenue driver as Underscore grows.

### Swap Fees

Charged on token swaps executed through Underscore wallets.

- **Fee**: 0.25% of trade amount
- **Applied to**: All swaps (including stablecoin pairs)

**Example**: $10,000 swap → $25 fee

### External Reward Claim Fees

Charged when claiming rewards from integrated protocols (MORPHO, WELL, AERO, etc.).

- **Fee**: 20% of claimed rewards
- **Applied to**: External protocol incentives only

**Example**: Claim $200 in MORPHO rewards → $40 fee

---

## What's Free

No fees on:
- Transfers between wallets
- Deposits and withdrawals
- Idle funds
- Debt operations (borrowing/repaying)
- Liquidity provision
- ETH/WETH wrapping

---

## Revenue Allocation: $RIPE Buybacks

100% of protocol revenue is used to buy back [$RIPE](https://app.ripe.finance/ripe) in the open market.

As Underscore usage grows, buyback demand scales with it and flows back into the broader ecosystem.

**Verify onchain**: View current fee parameters in the [Params Explorer](https://params.underscore.finance/protocol).

---

## Summary

| Revenue Source | Fee | Relative Size |
| -------------- | --- | ------------- |
| Vault Performance | 20% of yield | Largest (scales with TVL) |
| Swap Fees | 0.25% of amount | Medium |
| External Rewards | 20% of claims | Smaller |

**100% of revenue → [$RIPE](https://app.ripe.finance/ripe) bought back in the open market**
