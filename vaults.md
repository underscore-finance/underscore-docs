---
description: Tokenized yield strategies managed by AI — open to everyone
---

# Vaults: AI-Managed Yield for Everyone

Underscore Vaults are AI-managed yield strategies wrapped into standard ERC-4626 tokens. Deposit assets, receive vault shares that represent your stake in an actively managed portfolio. The AI continuously finds the best yields and rebalances across DeFi protocols — you just hold the token.

The key difference from a normal [Underscore Wallet](user-wallet.md): your position isn't locked. Vault shares are composable tokens you can use anywhere in DeFi — trade them, use them as collateral, bridge them cross-chain. The underlying AI strategy keeps running no matter where your tokens go.

---

## Why Vaults Exist

### Scale

Imagine 100,000 users all running the same yield strategy. With individual wallets, that's 100,000 separate rebalancing transactions every time the AI optimizes. Expensive. Inefficient.

With a vault, 100,000 users share one strategy. The AI rebalances once. Everyone benefits. Gas costs get socialized. Efficiency gets maximized.

This isn't theoretical — it's exactly what we experienced building Hightop. Each user had their own [Underscore Wallet](user-wallet.md), and every yield optimization meant touching every wallet individually. A shared vault architecture changes the economics entirely.

That's how we scale to millions of users.

### Composability

Vault shares are standard ERC-20 tokens. This unlocks:

- **Collateral**: Use vault shares on Ripe Protocol to get a loan — your collateral keeps earning yield in the background
- **Liquidity**: Sell shares in liquidity pools for instant exit
- **Portability**: Bridge cross-chain, use in other protocols
- **Integration**: Any app can plug into vaults with a standard interface

Your position becomes a building block, not a locked asset.

### Simplicity

Users don't need to understand liquidity pools or yield aggregators. They deposit, get a token, and earn yield. All the complexity — multi-protocol strategies, AI rebalancing, risk management — happens behind the scenes.

---

## Earn Vaults

Simple yield optimization for your assets.

### How It Works

1. **Deposit**: Deposit USDC, ETH, or other supported assets into the vault
2. **Receive Shares**: Get vault tokens (e.g., _USDC) representing your share of the pool
3. **AI Optimizes**: The agent rebalances across approved protocols, vaults, and yield strategies
4. **Withdraw Anytime**: Redeem shares for underlying assets whenever you want

### What the AI Does

The AI agent continuously optimizes the vault's positions:

- **Rate Monitoring**: Watches yields across Morpho, Euler, Moonwell, Aave, Fluid, Compound, and other approved protocols
- **Risk Analysis**: Evaluates strategies beyond just APY — analyzing depositor count, total deposits, utilization ratios, and available liquidity to assess withdrawal risk
- **Automatic Rebalancing**: Moves funds to capture better risk-adjusted yields as conditions change
- **Reward Harvesting**: Claims and compounds protocol incentives automatically
- **Gas Optimization**: Batches operations to minimize transaction costs

### Example: USDC Earn Vault

**You deposit 10,000 USDC**:
- Vault has 1,000,000 USDC total at $1.00/share
- You receive 10,000 _USDC tokens

**After 3 months**:
- AI captured a 12% Morpho rate spike, moved to 8% Euler promotion, claimed $15k in rewards
- Vault now holds 1,025,000 USDC (2.5% growth)
- Your 10,000 _USDC now redeemable for 10,250 USDC
- No action required from you

---

## Capital Efficiency with Ripe Protocol

Vault shares become premium collateral on [Ripe Protocol](https://ripe.finance). This unlocks powerful capital efficiency:

1. **Deposit** into an Earn Vault, receive _USDC
2. **Use _USDC as collateral** on Ripe to borrow stablecoins
3. **Your collateral keeps earning** — the AI optimizes yield in the background
4. **Borrow and deploy** those stablecoins elsewhere

Your collateral works 24/7. This isn't static collateral sitting idle — it's actively earning while you leverage it.

---

## Leveraged Vaults

Higher yields through managed leverage on Ripe Protocol — with built-in debt safety.

### How It Works

Leveraged Vaults amplify your yield by borrowing against your collateral, but with a key safety feature: **borrowed funds always maintain USD-based exposure** to ensure the vault can always repay its debt. The borrowed amount is also deposited back into Ripe as additional collateral, further strengthening the health of the debt position.

Here's the full flow:

1. **You deposit** a volatile asset (e.g., cbBTC, ETH)
2. **Vault deposits** your asset into the corresponding Earn Vault (AI optimizes yield)
3. **Vault uses** those yield-bearing shares as collateral on Ripe Protocol
4. **Vault borrows** GREEN (stablecoin) against that collateral
5. **Vault swaps** GREEN to USDC
6. **Vault deposits** USDC into the USDC Earn Vault (more yield)
7. **Vault adds** those USDC vault shares as additional collateral on Ripe

The result: your original asset earns yield, AND the borrowed amount earns yield — but the borrowed portion stays in USD-denominated assets.

#### Yield Math: Leveraged cbBTC

Let's walk through the math with a $100,000 cbBTC deposit:

| Layer | Amount | Rate | Annual Yield |
|-------|--------|------|--------------|
| cbBTC in Earn Vault | $100,000 | 0.5% | +$500 |
| Borrow from Ripe (70% LTV) | $70,000 | 3%* | -$2,100 |
| USDC in Earn Vault | $70,000 | 8% | +$5,600 |
| **Net Yield** | | | **+$4,000** |

*\*Underscore Vaults receive discounted borrow rates (3% vs standard 6%)*

**Combined APY: 4.0%** on your original $100k cbBTC — an 8x improvement over the base 0.5% yield, while maintaining full BTC exposure.

### Why USD-Based Debt Matters

This design protects the vault from liquidation:

- **Borrowed funds stay in USDC** — The vault cannot swap borrowed stablecoins into volatile assets like BTC or ETH
- **Debt is always covered** — Even if your collateral (cbBTC, ETH) drops 50%, the borrowed USD portion maintains its value
- **No death spiral** — The borrowed amount doesn't amplify losses from price drops

**Example**: Using the same $100k cbBTC deposit from above:
- Vault borrows $70,000 in GREEN (70% LTV), swaps to USDC
- cbBTC drops 40% → Your original collateral is now worth $60,000
- But the $70,000 borrowed is still earning yield as USDC
- That USDC is also deposited as collateral on Ripe — so you have $60k + $70k = $130k total collateral against $70k debt
- Position remains healthy because borrowed funds didn't lose value AND they add to your collateral

Compare this to traditional leveraged positions where borrowed funds buy more of the volatile asset — those can cascade into liquidation.

### What the AI Does

The AI manages both yield and risk:

- **Collateral Management**: Deposits assets into Earn Vaults, then into Ripe Protocol
- **Strategic Borrowing**: Borrows GREEN against collateral, converts to USDC
- **USD Exposure Only**: Borrowed funds always go into USDC Earn Vault — never swapped to volatile assets
- **Debt Ratio Monitoring**: Maintains configurable maximum leverage
- **Automatic Deleveraging**: Reduces positions when debt ratios approach limits

### Risk Management

Leveraged vaults include built-in safety mechanisms:

| Control | Purpose |
|---------|---------|
| **USD-Only Borrowing** | Borrowed funds maintain stablecoin exposure |
| **Max Debt Ratio** | Hard limit on leverage (e.g., 200% max) |
| **Auto-Deleverage** | Reduces positions as ratios approach limits |
| **Withdrawal Safety** | Automatically unwinds leverage for redemptions |
| **Continuous Monitoring** | AI watches health factor around the clock |

### Example: Leveraged cbBTC Vault

**You deposit 1 cbBTC ($100,000)**:

```
Your 1 cbBTC
    ↓
cbBTC Earn Vault (earning 0.5%)
    ↓
Deposit vault shares to Ripe as collateral
    ↓
Borrow $70,000 GREEN (70% LTV) → swap to USDC
    ↓
USDC Earn Vault (earning 8%)
    ↓
Deposit USDC vault shares to Ripe as additional collateral
```

**Yield amplification**:
- Your cbBTC earns 0.5% in the cbBTC Earn Vault → +$500/year
- Borrow cost at 3% (discounted rate) → -$2,100/year
- Your borrowed $70k earns 8% in the USDC Earn Vault → +$5,600/year
- **Net yield: 4.0%** — an 8x improvement over base yield

**If cbBTC drops 40%**:
- Your cbBTC collateral: now worth $60,000
- Your USDC collateral: still worth $70,000
- Total collateral: $130,000 against $70,000 debt
- Position remains healthy — no liquidation risk

**Your risk exposure**: Only the price movement of your original deposit (cbBTC). The leverage doesn't amplify your losses — it only amplifies your yield. If cbBTC drops 40%, you lose 40% of your initial value, same as holding cbBTC directly. The borrowed USD portion maintains its value and doesn't add downside risk.

---

## Deposits & Shares

### Making a Deposit

1. Approve the vault contract to spend your tokens
2. Call `deposit()` with your desired amount
3. Receive vault shares to your wallet

**Share Price Calculation**:
```
Share Price = Total Vault Assets / Total Shares Outstanding
```

For the first deposit, 1 share = 1 asset. As the vault earns yield, share price increases.

### Understanding Your Shares

Vault shares represent proportional ownership of everything in the vault:

- **100 shares at $1.00** = $100 claim on vault assets
- **Vault earns 10% yield** = Share price rises to $1.10
- **Your 100 shares now worth $110** = You captured the yield

You don't need to claim rewards or rebalance. Your shares automatically reflect the vault's performance.

### Withdrawing

Redeem shares for underlying assets anytime:

1. Call `redeem()` or `withdraw()` with your share amount
2. AI automatically unwinds positions as needed
3. Receive underlying assets to your wallet

A small buffer (2%) ensures you receive your expected amount even during position unwinding.

---

## Vault Safety & Controls

### Approved Protocols Only

Each vault operates within strict boundaries:

- **Whitelisted Destinations**: AI can only deposit to pre-approved yield protocols
- **Registry Controlled**: Underscore governance manages the approved protocol list
- **No Rogue Deposits**: AI cannot move funds to unapproved or risky protocols

### Deposit Controls

Vaults can implement additional safeguards:

| Control | Purpose |
|---------|---------|
| **Deposit Caps** | Maximum total assets to prevent concentration |
| **Allowlist Mode** | Restrict deposits to approved addresses only |
| **Pause Deposits** | Temporarily stop new deposits if needed |

### Emergency Controls

For extreme market conditions:

- **Freeze Operations**: Governance can halt all vault activity
- **Pause Withdrawals**: Temporary hold during market stress (governance only)
- **Protected Funds**: Even frozen, your share claim remains valid

---

## Performance Fees

Vaults charge fees only on profits — never on your principal:

- **Rate**: 20% of yield generated
- **Applied To**: Profits only, not deposits
- **Transparent Tracking**: Fees tracked separately from share mechanics
- **No Surprise Deductions**: Your withdrawal reflects actual asset value

**Example**:
- Vault earns $1,000 in yield
- 20% fee = $200 to protocol
- $800 distributed to depositors via increased share price

See [Protocol Economics](protocol-economics.md) for how fees are used.

---

## Vaults vs User Wallets

| Feature | **Vaults** | **User Wallets** |
|---------|------------|------------------|
| **Ownership** | Proportional shares (tokens) | Full control of assets |
| **Management** | AI-managed, hands-off | You + your managers decide |
| **Customization** | Fixed strategy per vault | Fully customizable |
| **Composability** | High (standard ERC-20) | Lower (assets in wallet) |
| **Access** | Anyone can deposit | Requires wallet deployment |
| **Use as Collateral** | Yes (shares are tokens) | More complex |
| **Best For** | Passive yield, composability | Active DeFi, custom strategies |

**Use Vaults When**: You want set-and-forget yield, need composable/productive collateral, or want to participate without wallet setup.

**Use Wallets When**: You want full control, custom strategies, payment automation, or manager delegation with precise limits.

---

## Real-World Examples

### Passive Yield Seeker

**Sarah** has 50,000 USDC sitting idle. She wants yield but doesn't have time to monitor rates.

**Solution**: Deposits to USDC Earn Vault
- Receives _USDC tokens instantly
- AI captures yields across Morpho, Aave, Euler, and more.
- Uses _USDC as collateral on Ripe to borrow for other opportunities
- Her collateral earns yield while borrowed against

**Result**: Productive yield + productive collateral, zero management required.

### Fintech App Integration

**PayFlow** is a payment app wanting to offer yield on user balances.

**Problem**: Building yield infrastructure from scratch requires significant engineering effort and security audits.

**Solution**: Integrates Underscore Vaults directly
- Users deposit through PayFlow's interface
- Vault handles all yield optimization
- PayFlow tracks user shares internally
- Standard ERC4626 interface, minimal integration work

**Result**: AI-managed yield without building yield infrastructure.

### Leveraged Yield Strategy

**Marcus** wants amplified yield on his ETH without managing liquidation risk.

**Solution**: Deposits 20 ETH to Leveraged ETH Vault
- ETH earns base yield in the ETH Earn Vault
- Vault borrows USDC against his ETH (70% LTV) via Ripe Protocol
- Borrowed USDC earns yield in the USDC Earn Vault
- Borrowed funds stay USD-denominated — no amplified downside if ETH drops
- AI manages rebalancing and debt ratios automatically

**Result**: ~8x yield improvement over base ETH yield, with risk exposure limited to ETH price movement only.

---

## Common Questions

**Can I withdraw anytime?**
Yes. Withdrawals are immediate — the vault automatically unwinds positions as needed to fulfill your request in a single transaction.

**What if the vault loses money?**
Your shares reflect actual vault value. If underlying assets lose value (market movement, not AI error), share price decreases. Performance fees only apply to profits.

**What assets can I deposit?**
Each vault specifies its underlying asset (USDC, ETH, etc.). You deposit that asset and receive vault-specific shares.

**Are vault shares transferable?**
Yes. Vault shares are standard ERC-20 tokens. Transfer, trade, or use as collateral anywhere ERC-20 tokens are accepted.

**What's the minimum deposit?**
No protocol-enforced minimum, though gas costs make very small deposits impractical.

---

## Get Started

Ready to earn AI-optimized yield?

- **Deposit directly**: Send supported assets to any Underscore vault contract
- **Track your position**: Your vault shares appear in any ERC-20 compatible wallet
- **Use as collateral**: Deposit shares to Ripe Protocol to borrow against your yield
- **Withdraw anytime**: Redeem shares for underlying assets whenever you need them
- **Build on vaults**: Integrate into your app via [technical documentation](https://underscore-1.gitbook.io/developers)

For full control over your DeFi strategy, explore [User Wallets](user-wallet.md) with custom managers, payment automation, and more.

---

_Deposit. Earn. Compose._
