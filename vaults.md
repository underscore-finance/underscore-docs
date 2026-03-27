---
description: Earn Vaults combine Core Vaults for passive AI-managed yield with Amplified Vaults for Ripe-powered yield amplification
---

# Earn Vaults: Core Vaults and Amplified Vaults

Underscore Earn Vaults share one architecture and two return profiles:

- **Core Vaults**: AI-managed passive yield wrapped into standard ERC-4626 shares
- **Amplified Vaults**: built on top of Core Vault shares, using Ripe Protocol to add a second yield layer while keeping the borrowed leg in USD-denominated strategies

Earn Vaults are non-custodial. Your assets stay yours. Withdraw anytime, no permissions required.

The key difference from a [Programmable Wallet](user-wallet.md): your position isn't locked. Vault shares are composable tokens you can use anywhere in DeFi — trade them, use them as collateral, bridge them cross-chain. The underlying strategy keeps running no matter where your tokens go.

---

## Why Earn Vaults Exist

### The Origin Story

Vaults weren't designed in a vacuum — they emerged from real problems we hit while building.

We started with [Hightop](https://hightop.com), where AI agents managed user portfolios through individual [Programmable Wallets](user-wallet.md). The AI would analyze yields across DeFi, then rebalance each user's wallet to capture better opportunities. It worked, but we quickly ran into a wall: every optimization meant touching every wallet. If we wanted to move 10,000 users into a higher-yield Morpho market, that was 10,000 separate transactions. Expensive. Slow. The AI was doing the same work over and over for users who wanted the same outcome.

Then came Ripe Protocol. Users would borrow against their yield-bearing positions — Aave deposits, Morpho positions, and the like. But once those positions became collateral, they were locked. Even if a better yield opportunity appeared, users couldn't rebalance that collateral without first repaying their loan. Their yield-earning assets were stuck.

Both problems came from the same place: real users, real usage, real feedback. We felt the inefficiency firsthand running AI optimization at scale on Hightop.

So we built Earn Vaults. The core insight: keep everything we built with Programmable Wallets — the AI capabilities, the clear boundaries, the onchain rules and policies — but give the AI just one "wallet" to manage. Users deposit into a shared vault and receive tokens representing their share. The AI optimizes once, everyone benefits. And because Core Vault shares are standard tokens, they can be used as collateral on Ripe while the AI keeps optimizing the underlying positions.

This architecture also opened the door to new vault types: Amplified Vaults, index vaults, and more — all built on the same foundation.

Today, Earn Vaults are live, and Core Vaults already power Hightop in production.

### Scale

One vault, one rebalance, everyone benefits.

That's how we scale to millions of users.

### Composability

Core Vault shares are standard ERC-20 tokens. This unlocks:

- **Collateral**: Use Core Vault shares on Ripe Protocol to get a loan — the AI keeps optimizing your collateral even while it's locked
- **Liquidity**: Sell shares in liquidity pools for instant exit
- **Portability**: Bridge cross-chain, use in other protocols
- **Integration**: Any app can plug into Earn Vaults with a standard interface

Your position becomes a building block, not a locked asset.

### Simplicity

Chasing yields is exhausting. Checking Morpho rates, comparing Aave markets, tracking Euler promotions, claiming rewards before they expire — it's a full-time job.

Core Vaults handle all of it. Users deposit, get a token, and earn yield. All the complexity — multi-protocol strategies, AI rebalancing, risk management, claiming and compounding rewards — happens behind the scenes.

---

## How Core Vaults Work

Simple yield optimization for your assets.

### How It Works

1. **Deposit**: Deposit USDC, ETH, or other supported assets into the vault
2. **Receive Shares**: Get vault tokens (e.g., _USDC) representing your share of the pool
3. **AI Optimizes**: The agent rebalances across approved protocols, vaults, and yield strategies
4. **Withdraw Anytime**: Redeem shares for underlying assets whenever you want

### What the AI Does

The AI agent continuously optimizes the vault's positions:

- **Continuous Monitoring**: Watches rates, liquidity, incentives, and withdrawal conditions across Morpho, Euler, Moonwell, Aave, Fluid, Compound, and other approved protocols
- **Risk-Adjusted Routing**: Evaluates strategies beyond raw APY — analyzing depositor count, total deposits, utilization ratios, and available liquidity before moving capital
- **Automatic Rebalancing**: Moves funds to capture better risk-adjusted yields as conditions change
- **Reward Harvesting**: Claims and compounds protocol incentives automatically

### Example: USDC Core Vault

**You deposit 10,000 USDC**:
- Vault has 1,000,000 USDC total at $1.00/share
- You receive 10,000 _USDC tokens

**After 3 months**:
- AI executed dozens of rebalances — capturing rate opportunities, evaluating risk before moving, rotating through promotions, claiming rewards as they unlock
- Vault now holds 1,025,000 USDC (2.5% growth)
- Your 10,000 _USDC now redeemable for 10,250 USDC
- No action required from you

---

## Capital Efficiency with Ripe Protocol

Core Vault shares become premium collateral on [Ripe Protocol](https://ripe.finance). This unlocks powerful capital efficiency:

1. **Deposit** into a Core Vault, receive _USDC
2. **Use _USDC as collateral** on Ripe to borrow stablecoins
3. **Your collateral keeps earning** — the AI optimizes yield in the background
4. **Borrow and deploy** those stablecoins elsewhere

Your collateral works 24/7. This isn't static collateral sitting idle — it's actively earning while you leverage it.

---

## Amplified Vaults

Higher yields through managed leverage built on Core Vault shares and Ripe Protocol — with built-in debt safety.

### How It Works

Amplified Vaults amplify your yield by borrowing against your collateral, but with a key safety feature: **borrowed funds always maintain USD-based exposure** to ensure the vault can always repay its debt. The borrowed amount is also deposited back into Ripe as additional collateral, giving you two layers of collateral backing your debt — your original asset plus the borrowed USD.

Here's the full flow:

1. **You deposit** a supported base asset into the Underscore Amplified Vault (currently cbBTC or USDC)
2. **Vault deposits** your asset into the corresponding Core Vault (AI optimizes yield)
3. **Vault uses** those yield-bearing shares as collateral on Ripe Protocol
4. **Vault borrows** GREEN (stablecoin) against that collateral
5. **Vault swaps** GREEN to USDC
6. **Vault deposits** USDC into the USDC Core Vault (more yield)
7. **Vault adds** those USDC Core Vault shares as additional collateral on Ripe

The result: your original asset earns yield, AND the borrowed amount earns yield — but the borrowed portion stays in USD-denominated assets.

#### Yield Math: Amplified cbBTC

Let's walk through the math with a $100,000 cbBTC deposit:

| Layer | Amount | Rate | Annual Yield |
|-------|--------|------|--------------|
| cbBTC in Core Vault | $100,000 | 0.5% | +$500 |
| Borrow from Ripe (70% LTV) | $70,000 | 3%* | -$2,100 |
| USDC in Core Vault | $70,000 | 8% | +$5,600 |
| **Net Yield** | | | **+$4,000** |

*\*Underscore Amplified Vaults receive discounted borrow rates (3% vs standard 6%)*

**Combined APY: 4.0%** on your original $100k cbBTC — an 8x improvement over the base 0.5% yield, while maintaining full BTC exposure.

### Why USD-Based Debt Matters

This design protects the vault from liquidation:

- **Borrowed funds stay in USDC or Savings GREEN** — The vault cannot swap borrowed capital into BTC or other volatile assets
- **Debt is always covered** — Even if your BTC collateral (cbBTC) drops 50%, the borrowed USD portion maintains its value
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

- **Collateral Management**: Deposits assets into Core Vaults, then into Ripe Protocol
- **Strategic Borrowing**: Borrows GREEN against collateral, then either swaps to USDC (if DEX liquidity is favorable) or stakes as Savings GREEN — either way, the borrowed amount earns yield
- **USD Exposure Only**: Borrowed funds stay in USD-denominated assets (USDC or GREEN) — never swapped to volatile assets
- **Debt Ratio Monitoring**: Maintains configurable maximum leverage
- **Automatic Deleveraging**: Reduces positions when debt ratios approach limits

### Risk Management

Amplified vaults include built-in safety mechanisms:

| Control | Purpose |
|---------|---------|
| **USD-Only Borrowing** | Borrowed funds maintain stablecoin exposure |
| **Max Debt Ratio** | Hard limit on leverage (e.g., 200% max) |
| **Auto-Deleverage** | Reduces positions as ratios approach limits |
| **Withdrawal Safety** | Automatically unwinds leverage for redemptions |
| **Continuous Monitoring** | AI watches health factor around the clock |

### Example: Amplified cbBTC Vault

**You deposit 1 cbBTC ($100,000)**:

```
Your 1 cbBTC
    ↓
cbBTC Core Vault (earning 0.5%)
    ↓
Deposit Core Vault shares to Ripe as collateral
    ↓
Borrow $70,000 GREEN (70% LTV) → swap to USDC
    ↓
USDC Core Vault (earning 8%)
    ↓
Deposit USDC Core Vault shares to Ripe as additional collateral
```

**Yield amplification**:
- Your cbBTC earns 0.5% in the cbBTC Core Vault → +$500/year
- Borrow cost at 3% (discounted rate) → -$2,100/year
- Your borrowed $70k earns 8% in the USDC Core Vault → +$5,600/year
- **Net yield: 4.0%** — an 8x improvement over base yield

**If cbBTC drops 40%**:
- Your cbBTC collateral: now worth $60,000
- Your USDC collateral: still worth $70,000
- Total collateral: $130,000 against $70,000 debt
- Position remains healthy — no liquidation risk

**Your risk exposure**: Only the price movement of your original deposit (cbBTC). The leverage doesn't amplify your losses — it only amplifies your yield. If cbBTC drops 40%, you lose 40% of your initial value, same as holding cbBTC directly. The borrowed USD portion maintains its value and doesn't add downside risk.

---

## Core Vaults vs Amplified Vaults

| Feature | **Core Vaults** | **Amplified Vaults** |
|---------|----------------------|----------------------|
| **Return profile** | Passive AI-managed yield | Core yield plus a second USD-based borrowed yield layer |
| **Borrowing inside the strategy** | No | Yes, via Ripe Protocol |
| **Debt exposure** | None | Managed debt with auto-deleverage |
| **Collateral usage** | Optional: use shares on Ripe yourself | Built into the vault strategy |
| **Best For** | Passive earners who want composable ERC-4626 shares | Users who want BTC or USDC exposure with additional yield amplification |

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

Each vault operates within strict boundaries — enforced by smart contracts, not company policies:

- **Whitelisted Destinations**: AI can only deposit to pre-approved yield protocols
- **Registry Controlled**: Underscore governance manages the approved protocol list
- **No Rogue Deposits**: The AI literally cannot move funds to unapproved destinations — it's not a matter of trust, it's code

These rules are onchain. No rogue trades. No experimental farms. No hallucinations.

### Deposit Controls

Earn Vaults can implement additional safeguards:

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

Earn Vaults charge fees only on profits — never on your principal:

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

## Core Vaults vs Programmable Wallets

| Feature | **Core Vaults** | **Programmable Wallets** |
|---------|------------|------------------|
| **Ownership** | Proportional shares (tokens) | Full control of assets |
| **Management** | AI-managed, hands-off | You + your managers decide |
| **Customization** | Fixed strategy per vault | Fully customizable |
| **Composability** | High (standard ERC-20) | Lower (assets in wallet) |
| **Access** | Anyone can deposit | Requires wallet deployment |
| **Use as Collateral** | Yes (shares are tokens) | More complex |
| **Best For** | Passive yield, composability | Active DeFi, custom strategies |

**Use Core Vaults When**: You want set-and-forget yield, need composable/productive collateral, or want to participate without wallet setup.

**Use Programmable Wallets When**: You want full control, custom strategies, agent execution, payment automation, or manager delegation with precise limits.

---

## Real-World Examples

### Passive Yield Seeker

**Sarah** has 50,000 USDC sitting idle. She wants yield but doesn't have time to monitor rates.

**Solution**: Deposits to the USDC Core Vault
- Receives _USDC tokens instantly
- AI captures yields across Morpho, Aave, Euler, and more.
- Uses _USDC as collateral on Ripe to borrow for other opportunities
- Her collateral earns yield while borrowed against

**Result**: Productive yield + productive collateral, zero management required.

### Fintech App Integration

**PayFlow** is a payment app wanting to offer yield on user balances.

**Problem**: Building yield infrastructure from scratch requires significant engineering effort and security audits.

**Solution**: Integrates Underscore Core Vaults directly
- Users deposit through PayFlow's interface
- Vault handles all yield optimization
- PayFlow tracks user shares internally
- Standard ERC4626 interface, minimal integration work

**Result**: AI-managed yield without building yield infrastructure.

### Amplified Yield Strategy

**Marcus** wants amplified yield on his BTC without managing liquidation risk.

**Solution**: Deposits 1 cbBTC to the Amplified cbBTC Vault
- cbBTC earns base yield in the cbBTC Core Vault
- Vault borrows USDC against his cbBTC-linked collateral (70% LTV) via Ripe Protocol
- Borrowed USDC earns yield in the USDC Core Vault
- Borrowed funds stay USD-denominated — no amplified downside if BTC drops
- AI manages rebalancing and debt ratios automatically

**Result**: ~8x yield improvement over base BTC yield, with risk exposure limited to BTC price movement only.

---

## Common Questions

**Can I withdraw anytime?**
Yes. Withdrawals are immediate — the vault automatically unwinds positions as needed to fulfill your request in a single transaction.

**What if the vault loses money?**
Your shares reflect actual vault value. If underlying assets lose value (market movement, not AI error), share price decreases. Performance fees only apply to profits.

**What assets can I deposit?**
Core Vaults specify their underlying asset (USDC, ETH, cbBTC, AERO, RIPE, etc.). Amplified Vaults currently support BTC- and USDC-based positions on Base.

**Are vault shares transferable?**
Yes. Vault shares are standard ERC-20 tokens. Transfer, trade, or use as collateral anywhere ERC-20 tokens are accepted.

**What's the minimum deposit?**
No protocol-enforced minimum, though gas costs make very small deposits impractical.

---

## Get Started

Ready to earn AI-optimized yield? [**Open the app →**](https://app.underscore.finance/)

- **Deposit directly**: Connect your wallet and deposit into a Core Vault or Amplified Vault
- **Choose your profile**: Use Core Vaults for passive yield or Amplified Vaults for a Ripe-powered second yield layer
- **Track your position**: Your vault shares appear in any ERC-20 compatible wallet
- **Use as collateral**: Deposit shares to Ripe Protocol to borrow against your yield
- **Withdraw anytime**: Redeem shares for underlying assets whenever you need them
- **Build on vaults**: Integrate into your app via [technical documentation](https://underscore-1.gitbook.io/developers)
- **Inspect live vault configs**: View current vault parameters and addresses in the [Params Explorer](https://params.underscore.finance/vaults)

For full control over your DeFi strategy, explore [Programmable Wallets](user-wallet.md) with custom managers, payment automation, and more.

---

_Deposit. Earn. Amplify. Compose._
