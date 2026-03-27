---
description: Infrastructure for agents, apps, and protocols building with programmable payments and Earn Vaults
---

# Who Uses Underscore: Infrastructure for Agents, Apps, and Protocols

Underscore is infrastructure for agents, apps, and protocols. Some users experience it through products like Hightop, which uses Underscore to deliver digital banking for AI agents, made simple for humans. Others through AI systems operating inside Programmable Wallets. Most end users never know it's there.

Think of Underscore like AWS for DeFi — but fully non-custodial. Just as millions use Netflix without knowing about Amazon's servers, millions will use financial apps powered by Underscore's infrastructure. The key difference: users always maintain control of their funds. The complexity stays under the hood while users enjoy seamless experiences.

Underscore provides two core products: **[Earn Vaults](vaults.md)** for onchain yield that anyone can access, including Core Vaults and Amplified Vaults, and **[Programmable Wallets](user-wallet.md)** with [Managers](managers.md), [Payees](payees.md), [Cheques](cheques.md), and [Whitelists](whitelist.md) — agentic wallets where AI agents and operators execute with real funds within onchain rules.

## The Underscore Ecosystem

### Who Builds on Underscore

**Fintech Applications**

- Consumer-facing apps that need DeFi yields
- Neobanks offering crypto services
- Payment processors requiring automated flows
- Apps integrating [Earn Vaults](vaults.md) for instant yield features, whether that means Core Vaults for passive yield or Amplified Vaults for a second yield layer

**Crypto Wallets**

- Wallets adding advanced DeFi features
- Wallet providers needing [programmable delegation](managers.md)
- Multi-signature solutions requiring automation

**AI Agents & Autonomous Systems**

- **Yield Optimization Agents**: Operate as [Managers](managers.md) within Programmable Wallets, rebalancing across Aave, Morpho, Euler, and Compound 24/7 within strict budget and protocol restrictions
- **Trading Agents**: Pay for market data feeds, inference APIs, and compute resources through [Payees](payees.md) with fixed budgets — keeping their own infrastructure running autonomously
- **Autonomous Economic Actors**: Use [Digital Cheques](cheques.md) for one-off purchases — datasets, temporary compute, analysis reports — with review delays on large purchases
- **Agent Orchestrators**: Platforms that deploy multiple agents, each with their own Manager permissions, budgets, and asset restrictions on a single Programmable Wallet

Underscore lets agents execute with real money without ever giving them custody, private keys, or unrestricted access. Budgets, recipient rules, asset restrictions, review delays, and expiry windows are enforced onchain.

**Enterprise Solutions**

- B2B payment platforms
- Corporate treasury management
- DAO financial operations
- Institutional DeFi access

### How End Users Experience Underscore

Users interact with friendly apps while Underscore handles the complexity:

- **Earning Yield**: "Deposit USDC, earn 8% APY" → [Core Vaults](vaults.md) route to optimal protocols automatically
- **Making Payments**: "Send $500 to contractor" → Underscore [cheque system](cheques.md) ensures safety
- **Portfolio Management**: "AI optimizes my yield" → Underscore [manager](managers.md) executes strategies
- **Asset Swaps**: "Trade ETH for USDC" → Underscore finds best rates across DEXs
- **Borrowing**: "Borrow against my ETH" → Underscore Ripe Protocol Lego manages collateral safely
- **Productive Collateral**: "Use my yield shares as collateral" → [Core Vault shares](vaults.md) work on Ripe while earning

The user sees a simple interface. Underscore does the heavy lifting.

## Case Study: Hightop

[Hightop](https://hightop.com) is digital banking for AI agents, made simple for humans. Let agents pay and get paid. You stay in control.

Hightop handles [Programmable Wallets](user-wallet.md) infrastructure, gas, and money movement behind the scenes.

Under the hood, Underscore provides the money-control and execution layer for agent permissions, payments, withdrawals, Earn Autopilot, and portfolio execution. Hightop's Earn Autopilot uses both Core Vaults and Amplified Vaults, while borrowing and the leverage rails behind Amplified Vaults are powered by Ripe.

### What Hightop Offers Users

Through one product, Hightop users can:

- **Fund an account** and move money in and out through familiar rails
- **Set limits, permissions, and payment rules for each agent**
- **Let agents pay, get paid, earn, borrow, invest, and move money** without handing them private keys or unrestricted wallet access
- **Keep everything in a simple app** while [Programmable Wallets](user-wallet.md) infrastructure, gas, and money movement stay behind the scenes and the control layer stays onchain and verifiable

### How Underscore Powers Each Feature

**Agent Control Layer**

- Hightop's agent control profiles map to Underscore [Managers](managers.md)
- Wallet-wide and per-agent rules define what each agent can do, which assets and venues it can touch, who it can pay, how much it can spend, and when it expires
- Key boundaries are enforced onchain by immutable, open-source smart contracts, not just remembered by the app backend
- That trust model is transparent, onchain smart-contract infrastructure rather than opaque balance-sheet custody hidden behind an app

**Payments and Money Movement**

- Approved recurring counterparties map cleanly to Underscore [Payees](payees.md)
- Ad hoc payouts and larger purchases use [Digital Cheques](cheques.md) with optional review delays and cancellation windows
- Trusted withdrawal and self-custody paths use the [Whitelist](whitelist.md) for instant transfers to approved destinations
- Agents can also get paid through one-off, usage-based, and x402-compatible flows over HTTP. A research agent can get paid per request, or a support agent can get paid per workflow
- This is how Hightop lets agents pay vendors, get paid, and move money without giving them open-ended account access

**Earn Autopilot**

- Hightop's Earn Autopilot uses Underscore's yield Legos plus both [Core Vaults](vaults.md) and [Amplified Vaults](vaults.md) to keep idle cash productive across multiple yield profiles
- Hightop's AI autopilot can maximize yield and help manage the portfolio without exposing users to protocol complexity

**Portfolio Execution**

- Swaps and portfolio moves run through Underscore's DEX integrations
- Agents can buy supported assets, rebalance portfolio targets, and execute approved strategies across venues like Aerodrome, Uniswap, and Curve
- Execution stays policy-aware, so agents can rebalance toward targets and rotate exposure without going off-script

**Cards (Coming Soon)**

- Hightop also highlights virtual cards as a coming-soon surface on top of the same control model
- Each agent can get its own virtual card, with spend rules enforced onchain and balances that can be auto-funded from Earn at the moment of purchase

**Borrowing**

- Hightop presents borrowing as a simple in-app feature
- The lending layer is powered by Ripe, which also supplies the leverage rails behind Amplified Vaults, while Underscore handles the surrounding agent controls, [Programmable Wallets](user-wallet.md) permission model, and agent execution model

### The Hightop User Experience

From the user's perspective:

1. Download [Hightop](https://hightop.com) app
2. Fund the account through familiar bank or crypto rails
3. Create an agent and give it clear rules
4. Let that agent pay, get paid, earn, invest, or protect the portfolio inside its lane
5. Borrow when needed and withdraw to trusted destinations anytime

What they never see:

- Token approvals for 20+ protocols
- Yield protocol comparisons and cash routing logic
- Slippage calculations
- Smart contract interactions
- Agent permissions, payment-path rules, and spending guardrails
- Any concept of gas, private keys, or seed phrases

They just use a clean product while the money layer stays programmable. That's the power of building on Underscore.

## Case Study: AI Trading Agent

A trading agent needs to operate autonomously: rebalance positions, pay for data feeds, and buy occasional datasets — all without custody or private keys.

### How Underscore Powers the Agent

**Execution ([Manager](managers.md))**

- Agent is configured as a Manager on the wallet owner's Programmable Wallet
- Permissions: Buy & Sell, Manage Yield, General Transfers to approved Payees
- Limits: $25,000 daily, stablecoins only, approved protocols only
- Time controls: 6-hour cooldown, 90-day expiry with renewal

**Recurring Costs ([Payees](payees.md))**

- Data feed provider: $200/month pull payment
- Inference API: $1,000/month, 50 transactions max
- Compute vendor: $500/week

**One-Off Purchases ([Cheques](cheques.md))**

- Dataset purchases under $100: instant
- Larger purchases: 3-day review window, cancellable by owner

**What the agent never gets:**

- Private keys
- Ability to add new payment recipients
- Access to exceed its budget
- Permission to touch restricted assets

The agent executes with real money. The owner maintains full control. All boundaries enforced onchain.

## Perfect for Vault Integration

The fastest way to add AI-managed yield to any application:

### Why Integrate Vaults

Underscore Earn Vaults share one architecture but two return profiles: Core Vaults for straightforward AI-managed yield, and Amplified Vaults for a Ripe-powered second yield layer.

**For Fintech Apps**

Skip months of infrastructure development. Integrate [Core Vaults](vaults.md) directly, or build around [Amplified Vaults](vaults.md) when you want a second yield layer:

- Standard ERC4626 interface — minimal integration work
- AI optimization handled entirely by Underscore
- Users deposit through your interface, you track shares
- No wallet infrastructure needed on your side

**For DeFi Protocols**

Make collateral productive:

- Accept Core Vault shares as collateral
- Users earn yield while borrowing
- Standard ERC20 compatibility
- Vault value trackable on-chain

**For Portfolio Managers**

Offer managed strategies without building infrastructure:

- Core Vaults for straightforward yield optimization
- Amplified Vaults for amplified returns with managed risk
- White-label as your own product
- Focus on user acquisition, not infrastructure

### Example: Quick Vault Integration

A payment app wants yield on user float:

```
Traditional approach:
- Build yield infrastructure (3-6 months)
- Integrate multiple protocols (ongoing maintenance)
- Build rebalancing logic (security risk)
- Audit everything ($$$$)

Vault approach:
- Call deposit() with user funds
- Track user shares internally
- Call redeem() for withdrawals
- Done in 2 weeks
```

The vault handles protocol selection, rebalancing, reward claiming, and risk management. The app handles UX.

---

## Perfect for Payment Applications

Underscore's payment infrastructure makes it ideal for the next generation of payment apps:

### Cross-Border Remittance Apps

Transform international money transfers with:

- **[Cheques](cheques.md)** for secure, cancellable transfers with built-in fraud protection
- **[Payees](payees.md)** for recurring family remittances with spending limits
- **Instant settlement** through stablecoins while funds earn yield waiting for pickup
- **Pull payments** letting recipients withdraw when exchange rates are favorable

### B2B Global Payment Platforms

Revolutionize business payments with:

- **Automated invoicing** through [Payees](payees.md) with net-30/60/90 terms
- **Escrow-like functionality** using [Cheques](cheques.md) with approval workflows
- **Multi-currency treasuries** earning yield between payment cycles
- **Delegated payment approval** via [Managers](managers.md) for finance teams

### Payroll & Expense Platforms

Modernize employee payments with:

- **Pull-based salaries** where employees withdraw their exact pay
- **Expense reimbursements** with automatic limits and approvals
- **Contractor payments** using cancellable [Cheques](cheques.md)
- **Multi-level approval chains** through [Manager](managers.md) permissions

### Why Underscore for Payments?

- **Programmable money**: Set exact rules for every payment relationship
- **Yield on float**: Funds earn DeFi yields until the second they're needed
- **Fraud prevention**: Time-locks, cancellations, and limits protect users
- **Global instant settlement**: No banking hours, no correspondent banks
- **Regulatory friendly**: Clear audit trails and permission systems

## Why Developers Choose Underscore

**Speed to Market**

- Ship DeFi features in weeks, not months
- One integration gives access to all the top DeFi protocols
- Pre-built delegation and payment systems
- Production-ready smart contracts from day one

**Risk Reduction**

- Battle-tested security patterns
- User funds protected by time-locks and permissions
- Clear audit trails for every transaction
- No infinite token approvals or honeypot risks

**Future-Proof**

- New protocols automatically available through Legos
- No re-integration when protocols update
- Built for multi-chain expansion
- Community-driven protocol additions

## The Future: Invisible Infrastructure

As Underscore grows, it becomes more invisible. Users won't ask "Does this use Underscore?" any more than they ask "Does this use HTTPS?" It will simply be the standard for:

- **Every fintech** offering DeFi yields
- **Every wallet** with advanced features
- **Every AI agent** managing portfolios and paying for its own services
- **Every platform** needing payment automation

The best infrastructure disappears into the background, enabling experiences that feel like magic.

---

## Join the Revolution

Ready to build on Underscore or learn more about the future of financial infrastructure?

### Connect With Us

- **Discord Community**: Join our developer discussions at [discord.gg/Y6PWmndNaC](https://discord.gg/Y6PWmndNaC)
- **Follow Updates**: Stay informed on Twitter/X [@underscore_hq](https://x.com/underscore_hq)
- **GitHub**: Explore the code at [github.com/underscore-finance](https://github.com/underscore-finance/underscore-protocol)

Whether you're building the next billion-dollar fintech, optimizing payment flows, or creating AI-powered financial tools, our community is here to help.

---

Remember: the best infrastructure disappears into the background. Underscore handles the complexity so developers can build products where agents, apps, and operators move real money safely.
