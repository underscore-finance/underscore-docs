---
description: One wallet unifying top DeFi protocols with automated payments and secure delegation
---

# User Wallet: Your DeFi Command Center

The Underscore User Wallet is a smart contract wallet that unifies access to top DeFi protocols through a single address. Execute complex multi-protocol strategies in one transaction. Delegate operations to AI agents and trusted operators within strict boundaries. Automate payments while funds earn yield. Move millions between your wallets instantly.

Built on Base L2, your wallet combines institutional-grade security with the flexibility to capture opportunities 24/7 — whether you're actively managing or sound asleep.

At its core, Underscore provides four key components:

1. **Unified Protocol Access**: Direct integration with top DeFi protocols through standardized adapters
2. **Delegation System**: [Managers](managers.md) who can execute strategies within defined boundaries
3. **Payment Rails**: Automated payment systems for recurring transfers and one-time payments (see [Payees](payees.md) and [Cheques](cheques.md))
4. **Security Layers**: Time-locks, whitelists, and granular permissions protecting every operation

## One Wallet, Every Protocol

Underscore connects to DeFi protocols through standardized adapters called "Legos". Each Lego provides a consistent interface for protocol-specific operations, enabling atomic multi-protocol transactions with optimized gas usage. 

**Your wallet is future-proof**: When new DeFi protocols launch or existing ones add features, they're automatically available to your wallet through new Lego integrations. No need to migrate funds, deploy a new wallet, or update anything — your existing Underscore wallet instantly gains access to every new protocol the moment its Lego is deployed.

### Yield & Lending Protocols

**Integrated protocols**: Morpho, Moonwell, Aave, Euler, Fluid, Compound, plus specialized protocols like Avantis, ExtraFi, and more

**Capabilities**:

- Deposit assets to earn yield
- Withdraw funds with automatic unwinding
- Track yields and calculate profits
- Claim protocol rewards
- Rebalance between protocols

### Trading & DEX Integration

**Integrated DEXs**: Aerodrome, Uniswap, Curve

**Capabilities**:

- Swap tokens with smart routing (up to 5 hops)
- Add/remove liquidity with automatic ratio calculation
- Support for both standard (uni v2) and concentrated liquidity (uni v3+)
- Manage NFT positions and adjust ranges

### Debt Management

**Integrated protocol**: [Ripe Protocol](https://ripeprotocol.com)

Ripe Protocol is Underscore's borrowing partner, letting you access liquidity without selling your assets. The key advantage: **Underscore Earn Vaults are accepted as collateral**. This means your assets can be earning AI-optimized yield while you borrow against them — you're not choosing between yield and liquidity, you get both.

**How It Works**:

1. **Deposit Collateral**: Lock assets in Ripe Protocol — including Underscore Earn Vault tokens
2. **Borrow Against It**: Take a loan in GREEN (stablecoin) or yield-bearing sGREEN
3. **Keep Earning**: If using Vault tokens as collateral, your underlying assets continue earning optimized yield
4. **Repay Anytime**: Pay back principal + interest on your schedule
5. **Reclaim Collateral**: Withdraw your assets once debt is cleared

**Why This Matters**:

Traditional borrowing forces a choice: either earn yield OR use assets as collateral. With Underscore + Ripe:
- Deposit into an Earn Vault (AI optimizes your yield)
- Use your vault tokens as collateral on Ripe
- Borrow GREEN/sGREEN for liquidity needs
- Your collateral keeps earning the whole time

**Capabilities**:

- Deposit any supported asset as collateral
- Use Underscore Earn Vault tokens as productive collateral
- Borrow GREEN (stablecoin) or sGREEN (yield-bearing stablecoin)
- Repay debt with any accepted token
- Earn and claim RIPE rewards on debt positions

**Manager Permissions**:
- **Manage Debt**: Add/remove collateral, borrow, repay
- Managers cannot withdraw borrowed funds to external addresses
- All operations respect standard manager limits

**Why Borrow?**
- Access liquidity without selling appreciating assets
- Keep earning yield on your collateral
- Tax efficiency — loans aren't taxable events
- Bridge short-term cash flow needs

### Asset Transformations

**Capabilities**:

- ETH ↔ WETH conversion with zero slippage
- Mint and redeem receipt tokens (like stETH)
- Handle delayed redemptions
- Automatic format conversion for protocol requirements

### Rewards & Incentives

**Capabilities**:

- Batch claim rewards across all protocols in one transaction
- Auto-compound rewards into productive positions
- Track lifetime earnings across protocols

## Batch Operations: Multiple Actions, One Transaction

Underscore's architecture allows complex multi-step operations to execute atomically in a single transaction. This provides significant gas savings and eliminates the risk of partial execution.

### Examples of Batch Operations

**Yield Rebalancing**:

```
1. Withdraw from Aave (lower yield)
2. Deposit to Morpho (higher yield)
3. Claim rewards from both protocols
4. Convert rewards to productive assets
→ All in one transaction
```

**Complex Position Entry**:

```
1. Deposit collateral to Ripe Protocol
2. Borrow against collateral
3. Provide borrowed funds as liquidity
4. Stake LP tokens for additional yield
→ Complete strategy in one click
```

**Portfolio Rebalancing**:

```
1. Remove liquidity from multiple pools
2. Swap assets to target allocations
3. Re-deploy into new positions
4. Claim and reinvest all [rewards](rewards.md)
→ Entire rebalance atomically
```

## Swaps: Trade Any Token

When you swap tokens through your Underscore wallet, the system finds the best route across integrated DEXes.

### How Swaps Work

Multi-hop routing example:
```
Want to swap USDC → PEPE?
Direct route may not exist or have poor liquidity.

Smart routing finds:
USDC → ETH → PEPE (2 hops)
or
USDC → WETH → PEPE (2 hops with better rate)

Up to 5 hops supported for optimal pricing.
```

### Slippage Protection

Every swap includes slippage protection — you specify the minimum amount you'll accept. If market conditions change and you'd receive less, the transaction reverts.

- Wallet default: Configurable per swap
- Manager limit: Managers have maximum slippage caps (e.g., 1% max)
- Fail-safe: Transactions revert rather than execute at bad prices

### Swap Fees

Underscore charges 0.25% on swaps. This is in addition to any DEX fees (which go to liquidity providers).

### Manager Swap Controls

When managers execute swaps, additional controls apply:
- Maximum slippage percentage
- Maximum swaps per period
- Minimum USD value per swap
- Asset restrictions (which tokens can be swapped)

---

## Liquidity Provision: Earn From Trading Fees

Your Underscore wallet lets you provide liquidity to decentralized exchanges and earn a share of trading fees. This is one of the most powerful DeFi strategies — your assets work for you by facilitating trades for others.

### How It Works

When you provide liquidity, you deposit a pair of tokens (like USDC and ETH) into a trading pool. Traders swap between these tokens and pay fees, which you earn proportionally to your share of the pool.

**Basic Example**:

```
You deposit: $5,000 USDC + $5,000 ETH worth
Pool share: 1% of total liquidity
Daily trading volume: $1,000,000
Fee rate: 0.3%
Your daily earnings: $30 (0.3% × $1M × 1%)
```

### Two Types of Liquidity

**Simple Liquidity (Uniswap V2 style)**

- Deposit equal value of two tokens
- Earn fees across all price ranges
- Receive LP tokens representing your share
- Supported on: Aerodrome Classic, Uniswap V2, Curve

**Concentrated Liquidity (Uniswap V3 style)**

- Choose specific price ranges for your liquidity
- Higher fees when price is in your range
- More capital efficient but requires monitoring
- Receive an NFT position (not fungible tokens)
- Supported on: Aerodrome Slipstream, Uniswap V3

### Manager Permissions for LP

Managers can handle liquidity operations with the **Manage Liquidity** permission:

- Add liquidity to approved pools
- Remove liquidity when rebalancing
- Subject to all standard manager limits

### Risks to Understand

**Impermanent Loss**: If token prices diverge significantly, you may have less value than if you held the tokens separately. This loss only becomes "permanent" when you withdraw.

**Smart Contract Risk**: LP positions exist within DEX smart contracts. Underscore integrates only with established, audited protocols.

---

## Other Wallet Features

### Eject Mode: Emergency Lockdown

If you suspect your wallet is compromised or need to restrict activity immediately, activate eject mode to lock down operations:

**When Active**:
- Only transfers and ETH/WETH conversions allowed
- No yield, swap, debt, or liquidity operations permitted
- Only wallet owner can perform any actions
- All managers are blocked from operating

**Use Case**:
```
Suspicious activity detected
    ↓
Activate eject mode (one transaction)
    ↓
Wallet locked to basic operations only
    ↓
Safely transfer funds to whitelisted addresses
    ↓
Deactivate eject mode when secure
```

Eject mode provides a panic button for emergencies — restrict first, investigate later.

### [Managers](managers.md): Delegated Operations

Managers are authorized operators — human or AI — who execute actions within your defined boundaries. They can trade, optimize yields, and manage payments, but cannot withdraw to external addresses or exceed your limits.

**Use cases**:

- 24/7 yield optimization by AI agents
- CFO handling vendor and contractor payments
- Professional traders managing portions of portfolio
- Automated debt position management
- Family members with emergency access

[→ Learn more about Managers](managers.md)

### [Payees](payees.md): Your Circle of Trust

Payees form your verified payment network — addresses that can only receive what you've pre-approved. Your funds earn yield until payment time, then transfer automatically. Only you can add addresses to this circle.

**Use cases**:

- Employee salaries paid from yield-earning funds
- Automated vendor and contractor payments
- Subscription services with pull payment capability
- Family allowances with monthly limits

[→ Learn more about Payees](payees.md)

### [Cheques](cheques.md): Digital Cheques with Control

Digital cheques bring the control of paper cheques to crypto — write payments that recipients cash on their schedule, cancel anytime before they do. Large amounts get automatic security delays. Your funds keep earning yield until payment.

**Use cases**:

- Contractor payments you can cancel if work isn't delivered
- Large transfers with built-in review time
- Social payments like splitting lunch ($30 to a friend)
- One-time vendor invoices with payment flexibility
- Any payment where you need an "undo" option

[→ Learn more about Cheques](cheques.md)

### [Whitelist](whitelist.md): Unlimited Trust

The whitelist breaks the emergency glass on your security — addresses that get unlimited transfers with no delays or limits. Time-locked additions protect against compromise, while instant removal maintains control.

**Use cases**:

- Hardware wallet for emergency fund access
- Corporate treasury requiring immediate consolidation
- Multi-wallet strategies for risk distribution
- Gnosis Safe for recovery if you lose access

[→ Learn more about Whitelist](whitelist.md)

## Architecture Comparison

| Traditional Multi-Wallet Setup      | Underscore Smart Wallet        |
| ----------------------------------- | ------------------------------ |
| Multiple interfaces and logins      | Single unified interface       |
| Manual token approvals per protocol | Pre-configured protocol access |
| External transfers between wallets  | Internal routing, no transfers |
| Manual yield tracking               | Automatic profit calculation   |
| Limited automation options          | Full delegation capabilities   |
| Separate security per wallet        | Unified security model         |


## Frequently Asked Questions

### 🔐 **Security & Control**

**Is this a self-custody wallet?**  
Yes, absolutely. You maintain complete control of your private keys and assets. Underscore provides the smart contract infrastructure, but only you can authorize transactions.

**What happens if Underscore disappears?**
Your funds remain safe and accessible. The smart contracts are immutable and don't depend on Underscore's servers. You could interact with your wallet directly through BaseScan or any other interface.

**Can I migrate to a new wallet?**
Yes. The protocol includes a migration system that lets you move funds and copy your configuration (managers, payees, whitelist) to a new Underscore wallet. Useful if you want access to new features or need to restructure your setup.

### 💰 **Costs & Fees**

**What are the fees?**

- **Swap fees**: 0.25% on token swaps
- **External reward claims**: 20% when claiming protocol rewards (MORPHO, WELL, etc.)
- **No fees on**: Transfers, idle funds, deposits, debt operations, liquidity provision, or ETH/WETH wrapping

See [Protocol Economics](protocol-economics.md) for details on how fees work and where they go.

### Technical Setup


**Can I use this with my existing wallet?**  
Yes. You deploy your Underscore smart wallet using your existing wallet (like MetaMask), which then acts as the owner key.

**What protocols can I access?**  
20+ protocols including Aave, Morpho, Compound (lending), Ripe Protocol (borrowing), Uniswap, Curve, Aerodrome (trading), and more. New protocols integrate automatically through the Lego system.

**What if Base L2 has issues?**  
Base inherits Ethereum's security model. In the unlikely event of L2 issues, established procedures exist for withdrawing assets to Ethereum mainnet. Your funds remain under your control.

---

## Your Move

Right now, while you're reading this, yields are compounding. Opportunities are emerging. Strategies are executing.

Just not yours.

Every day you delay is another day of:

- Manual approvals eating your time
- Missed yields while you sleep
- Anxiety about security
- Opportunities slipping through your fingers

Stop juggling wallets. Stop missing opportunities. Stop letting manual operations eat your time.

Your DeFi operations deserve professional tools. Deploy your Underscore wallet and take control of your financial future.

---

_One wallet. Every protocol. Total control._
