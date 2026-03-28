---
description: Your Money Never Sleeps
---

# Underscore Protocol: Your Money Never Sleeps

One protocol. Two products.

1. **[Earn Vaults](vaults.md)** — two yield profiles built on the same share-based architecture: Core Vaults for passive AI-managed yield, and Amplified Vaults for Ripe-powered yield amplification.

2. **[Programmable Wallets](user-wallet.md)** — Agentic wallets where AI agents and operators pay, rebalance, and move funds within your rules. No custody. No private keys. No unrestricted access.

Your funds earn while you sleep. No manual management. No missed opportunities.

---

## Earn Vaults

Underscore Earn Vaults come in two forms:

- **Core Vaults** — AI-managed passive yield wrapped into standard ERC-4626 shares
- **Amplified Vaults** — built on top of Core Vault shares using Ripe to add a second yield layer with USD-based debt safety

Deposit assets, receive Earn Vault shares, and let the strategy run underneath.

- **Composable** — Earn Vault shares work anywhere in DeFi: trade them, bridge them, use as collateral
- **Productive collateral** — Borrow on Ripe while your collateral keeps earning yield
- **Scalable** — 100,000 users share one strategy. AI rebalances once. Everyone benefits.

**Perfect for:** Passive yield seekers, protocols needing productive collateral, and apps adding straightforward or amplified yield features

**→ Learn more: [Earn Vaults: Core Vaults and Amplified Vaults](vaults.md)**

---

## Programmable Wallets: Money For Agents

Most agents can recommend. Underscore lets them execute — with real funds, without ever holding your private keys.

Programmable Wallets give AI agents and operators onchain execution rights within strict boundaries. [Managers](managers.md) define permissions. [Payees](payees.md) handle recurring spend. [Digital Cheques](cheques.md) handle one-off payments with optional review delays. Everything is enforced onchain by smart contracts.

### [Managers: Give Agents Execution Rights, Not Custody](managers.md)

Authorize agents to manage yield, swap, borrow, repay, claim rewards, and pay. Restrict by asset, protocol, budget, cooldown, expiry.

- **Granular permissions** — Allow only what you specify
- **Hard spending limits** — Daily, monthly, and lifetime caps
- **Time-based controls** — Auto-expire after set periods
- **Instant revocation** — Your control is absolute

*Example: A yield agent can rebalance across Aave, Morpho, and Euler with a $25,000 daily limit.*

### [Payees: Let Agents Pay for the Services They Need](payees.md)

Pre-approve recurring recipients like market data feeds, model providers, compute vendors, contractors, payroll, subscriptions. Set per-payment caps, period limits, allowed assets, cooldowns.

- **Pre-approved recipients** with individual limits
- **Automated payments** while funds earn yield
- **Pull payment support** for subscriptions and service fees
- **Period-based caps** preventing overspending

*Example: Your trading agent keeps its data feed, inference API, and GPU provider online with fixed USDC allowances.*

### [Digital Cheques: One-Off Spend Without Blind Trust](cheques.md)

Turn transfers into controlled payment commitments. Small spends clear immediately. Larger payouts sit behind review delays and stay cancellable.

- **Security delays** for large amounts
- **Cancel anytime** before payment
- **Transparent onchain** for both parties
- **No funds locked** until actual payment

*Example: Your agent buys a $3 dataset instantly. Larger payouts wait behind a review window.*

### [Whitelist: Instant Access for Trusted Addresses](whitelist.md)

Unlimited access for your most trusted addresses.

- **No restrictions** for whitelisted addresses
- **Time-locked additions** for security
- **Instant removal** if ever needed

**Perfect for:** Multi-wallet strategies, hardware wallet, cold storage

> **Underscore lets agents execute with real money without ever giving them custody, private keys, or unrestricted access. Budgets, recipient rules, asset restrictions, review delays, and expiry windows are enforced onchain in open-source smart contracts.**

**→ Learn more: [Programmable Wallets](user-wallet.md)**

---

## How It All Works Together

Your Underscore infrastructure isn't just one thing — it's an ecosystem of intelligent features working in harmony.

### An Agent's Day

**3 AM**: Your [yield agent](managers.md) notices Morpho offering 1% better yield than Aave. It automatically rebalances $25k, staying within its $25,000 daily limit. You're asleep.

**6 AM**: Your trading agent's data feed subscription renews. $200 USDC pulls automatically from its [Payee](payees.md) allowance. The agent keeps running.

**10 AM**: The trading agent needs a one-time dataset for backtesting. It creates a $3 [Digital Cheque](cheques.md) — clears instantly, under the review threshold.

**2 PM**: A larger $5,000 compute job needs payment. The agent creates a cheque with a 3-day review window. You can cancel if something looks wrong.

**11 PM**: Your portfolio rebalanced 3 times today across 5 protocols. Your agent paid for its own services. You didn't lift a finger. No keys were shared.

### A Human's Day

**10 AM**: Monthly rent is due. Your landlord (configured as [Payee](payees.md)) pulls exactly $2,500 USDC. Not a penny more. Your remaining funds keep earning yield.

**2 PM**: You need to pay a contractor. Create a $5,000 [cheque](cheques.md) with 3-day delay. If they don't deliver, cancel it.

**4 PM**: Time to fund your trading wallet. Move $20k to your other Programmable Wallet ([whitelisted](whitelist.md)) instantly.

---

## Who Uses Underscore

Underscore isn't a consumer app — it's infrastructure for agents, apps, and protocols. Think of it like AWS for DeFi — but fully non-custodial.

### Applications Building on Underscore

- **AI Agents & Autonomous Systems**: Yield optimization agents, trading bots, and autonomous economic actors operating as [Managers](managers.md) within user-defined limits — paying for their own data feeds, compute, and inference APIs through [Payees](payees.md) and [Cheques](cheques.md)
- **Fintech Apps**: Like [Hightop](https://hightop.com), which uses Underscore to deliver digital banking for AI agents, made simple for humans — letting agents pay, get paid, keep cash productive, and move money while users stay in control
- **Vault Integrators**: Apps adding AI-managed yield without building infrastructure — integrate [Core Vaults](vaults.md) for passive yield or [Amplified Vaults](vaults.md) for a second yield layer
- **Payment Platforms**: Cross-border remittance, B2B payments, and payroll systems leveraging our [Cheques](cheques.md) and [Payees](payees.md)
- **Wallet Providers**: Adding advanced DeFi features and [programmable delegation](managers.md) to existing wallets

### The Hightop Example

Hightop demonstrates the power of building on Underscore:
- **Digital banking for AI agents, made simple for humans**: Hightop gives users a clean product for agent money while Underscore provides the programmable control layer underneath
- **Let agents pay and get paid. You stay in control**: Hightop maps agent execution to [Managers](managers.md), recurring counterparties to [Payees](payees.md), one-off payouts to [Cheques](cheques.md), and trusted exits to the [Whitelist](whitelist.md)
- **Wallets, gas, and money movement stay behind the scenes**: Hightop abstracts [Programmable Wallets](user-wallet.md) infrastructure, gas, and money movement while Underscore enforces limits, permissions, and payment rules onchain
- **Earn Autopilot and portfolio execution run on Underscore**: [Core Vaults](vaults.md), [Amplified Vaults](vaults.md), and Underscore Legos handle yield, swaps, and policy-aware asset execution across 25+ supported assets, while Ripe powers the lending layer and the leverage rails behind Amplified Vaults
- **x402-ready flows are live, and cards are coming soon**: Hightop already supports API-native inbound payments for agents and is extending the same control model to virtual cards

Most users will never interact with Underscore directly. They'll use apps like Hightop that leverage our infrastructure to deliver seamless experiences.

**→ Learn more: [Who Uses Underscore](who-uses-underscore.md)**

---

## Common Questions

**Is my wallet upgradeable?**
No. Your wallet code is immutable for security. New features come through Lego integrations. If new features come, you can migrate to a new Programmable Wallet.

**What are Legos?**
Standardized integrations with DeFi protocols. When new protocols launch, your wallet can use them immediately.

**Can I use multiple wallets?**
Yes. Whitelist them for instant transfers between your wallets.

**What about L2s?**
Currently Base L2 only. More chains coming.

**How do fees work?**
Small fees on swaps (0.25%) and external reward claims (20%). Earn Vaults charge 20% performance fees on yield profits only. No fees on transfers, deposits, or idle funds. 100% of protocol revenue buys back [$RIPE](https://app.ripe.finance/ripe) in the open market. See [Protocol Economics](protocol-economics.md) for details.

**What happens if I lose my owner wallet?**
If you've set up managers and whitelisted addresses beforehand, managers can still transfer funds to your whitelisted addresses (like hardware wallets), providing a recovery path.

**Can managers steal my funds?**
No. Managers operate within blockchain-enforced limits. They can only perform authorized actions within your spending caps and cannot withdraw to external addresses or modify their own permissions.

**How do I handle emergency transfers?**
Pre-whitelist your hardware wallet or secure addresses. Unlike payees (with limits) or cheques (with delays), whitelisted addresses can receive unlimited transfers instantly for emergencies.

---

## Payment Methods Comparison

Understanding which payment tool to use for different situations:

| Feature | **[Whitelist](whitelist.md)** | **[Payees](payees.md)** | **[Cheques](cheques.md)** |
|---------|--------------------------------|--------------------------|---------------------------|
| **Use Case** | Instant unlimited transfers to trusted addresses | Automated recurring payments | One-time payments with control |
| **Payment Limits** | None — completely unlimited | Customizable per-recipient | Set per cheque |
| **Setup Time** | Time-locked addition (configurable) | Immediate with limits | No setup needed |
| **Key Benefit** | Emergency access & multi-wallet strategies | Set once, runs automatically | Cancel anytime before cashed |
| **Best For** | Hardware wallets, cold storage, other wallets | Agent services, salaries, subscriptions | Agent purchases, contractors, large transfers |
| **Risk Level** | Highest — can drain wallet | Medium — capped by limits | Low — cancellable |

---

## Getting Started

### Quick Start

**Want passive yield? (2 minutes)**
1. Connect your wallet to Underscore
2. Choose a vault profile: Core Vaults for passive yield, or Amplified Vaults for yield amplification
3. Deposit — AI handles everything from here

**Building an AI agent? (10 minutes)**
1. Deploy a [Programmable Wallet](user-wallet.md)
2. Add your agent as a [Manager](managers.md) with permissions and budget
3. Configure [Payees](payees.md) for recurring service costs (data feeds, compute, APIs)
4. Use [Digital Cheques](cheques.md) for one-off payments

**Want full control? (5 minutes)**
1. Deploy your [Programmable Wallet](user-wallet.md)
2. Add managers, payees, or whitelist addresses as needed
3. Start using 20+ DeFi protocols from one place

### Explore Features

**For Passive Yield**: Start with [Core Vaults](vaults.md) — deposit and let AI optimize. No wallet setup required.

**For Amplified Yield**: Explore [Amplified Vaults](vaults.md) to keep BTC or USDC exposure while adding a second yield layer through Ripe.

**For AI Agents**: Deploy a [Programmable Wallet](user-wallet.md) and configure [Managers](managers.md) for execution, [Payees](payees.md) for recurring costs, and [Cheques](cheques.md) for one-off spend.

**For Full Control**: Deploy a [Programmable Wallet](user-wallet.md) and explore features that match your needs:

- **For Automation**: Set up [Managers](managers.md) to delegate operations
- **For Recurring Payments**: Configure [Payees](payees.md) for automated transfers
- **For One-Time Payments**: Use [Cheques](cheques.md) with cancellation ability
- **For Multi-Wallet Strategies**: Add addresses to your [Whitelist](whitelist.md)
- **For Earning Rewards**: Learn about [revenue sharing and bonuses](rewards.md)

---

## Technical Documentation

For developers and integrators: [Complete Technical Documentation](https://underscore-1.gitbook.io/developers/)

Build on Underscore's infrastructure with detailed guides on smart contract architecture, Lego Partner integrations, and security models. Over 30 production contracts documented with integration examples.

For live protocol parameters and contract deployments, use the [Params Explorer](https://params.underscore.finance).

---

## Community & Support

- **Discord**: [discord.gg/underscore](https://discord.gg/Y6PWmndNaC)
- **Twitter/X**: [@underscore_hq](https://x.com/underscore_hq)
- **GitHub**: [github.com/underscore-finance](https://github.com/underscore-finance/underscore-protocol)

---

## The Future of Financial Operations

AI agents need more than APIs — they need money. The ability to pay for services, capture yield, and move funds autonomously within safe boundaries.

Underscore delivers what crypto promised: programmable money that works as hard as you do. Your agents executing strategies within unbreakable boundaries. Your funds earning across protocols while maintaining liquidity for payments. Your security protecting without restricting.

Earn Vaults + Programmable Wallets. Your money never sleeps.
