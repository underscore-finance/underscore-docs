---
description: Understanding Underscore's role as infrastructure for next-generation financial applications
---

# Who Uses Underscore: Infrastructure for the Future of Finance

Underscore isn't a consumer app — it's the rails that power the next generation of financial applications. Users experience Underscore through the apps they love, without ever knowing it's there.

Think of Underscore like AWS for DeFi — but fully non-custodial. Just as millions use Netflix without knowing about Amazon's servers, millions will use financial apps powered by Underscore's infrastructure. The key difference: users always maintain control of their funds. The complexity stays under the hood while users enjoy seamless experiences.

Underscore provides two core products: **[Vaults](vaults.md)** for AI-managed yield that anyone can access, and **[User Wallets](user-wallet.md)** with [Managers](managers.md), [Payees](payees.md), [Cheques](cheques.md), and [Whitelists](whitelist.md) — components developers combine to create powerful financial applications.

## The Underscore Ecosystem

### Who Builds on Underscore

**Fintech Applications**

- Consumer-facing apps that need DeFi yields
- Neobanks offering crypto services
- Payment processors requiring automated flows
- Apps integrating [Vaults](vaults.md) for instant AI-managed yield features

**Crypto Wallets**

- Wallets adding advanced DeFi features
- Smart wallet providers needing [delegation](managers.md)
- Multi-signature solutions requiring automation

**AI & Automation Platforms**

- AI agents that manage user portfolios
- Automated trading systems
- Yield optimization bots
- DeFi strategy executors

**Enterprise Solutions**

- B2B payment platforms
- Corporate treasury management
- DAO financial operations
- Institutional DeFi access

### How End Users Experience Underscore

Users interact with friendly apps while Underscore handles the complexity:

- **Earning Yield**: "Deposit USDC, earn 8% APY" → [Vaults](vaults.md) route to optimal protocols automatically
- **Making Payments**: "Send $500 to contractor" → Underscore [cheque system](cheques.md) ensures safety
- **Portfolio Management**: "AI optimizes my yield" → Underscore [manager](managers.md) executes strategies
- **Asset Swaps**: "Trade ETH for USDC" → Underscore finds best rates across DEXs
- **Borrowing**: "Borrow against my ETH" → Underscore Ripe Protocol Lego manages collateral safely
- **Productive Collateral**: "Use my yield shares as collateral" → [Vault](vaults.md) shares work on Ripe while earning

The user sees a simple interface. Underscore does the heavy lifting.

## Case Study: Hightop

[Hightop](https://hightop.com) is a mobile app that demonstrates the power of building on Underscore infrastructure. Here's how they leverage different Underscore components to create a seamless user experience:

### What Hightop Offers Users

Through an intuitive mobile interface, Hightop users can:

- **Earn Yield** on their assets with one tap
- **Swap Assets** at competitive rates
- **Borrow** against their holdings
- **AI Private Banker** that manages your entire portfolio strategy
- **Instant Withdrawals** to their personal wallets

### How Underscore Powers Each Feature

**AI Private Banker (The Magic)**

- Hightop's AI is configured as an Underscore [Manager](managers.md)
- Currently optimizes yield by rebalancing between Aave, Morpho, Euler, Compound, Fluid
- Soon: Will execute complex DeFi strategies, manage debt positions, and capture arbitrage
- Operates within user-defined limits (e.g., "Only touch stablecoins", "Keep 20% in ETH")
- Adapts strategies based on market conditions and user goals
- Like having a Wall Street quant working 24/7 for your personal portfolio
- Users wake up to optimized positions and captured opportunities

**Yield Generation**

- Hightop uses Underscore's Lego integrations to access Morpho, Moonwell, Aave, and other yield protocols
- Users see "8.5% APY on USDC" — Underscore handles the protocol routing
- Their AI Manager automatically rebalances between protocols to optimize yields

**Asset Swaps**

- Leverages Underscore's DEX integrations (Uniswap, Curve, Aerodrome)
- Users swap with one tap — Underscore finds optimal routes
- No need to approve tokens for each protocol

**Borrowing**

- Utilizes Underscore's debt management Legos, specifically Ripe Protocol
- Users see simple "Borrow up to 50% of collateral"
- Underscore manages the complex protocol interactions

**User Withdrawals**

- Users' personal wallets are added to Underscore's [Whitelist](whitelist.md)
- Enables instant withdrawals with no limits
- Provides emergency exit if needed
- Maintains non-custodial security

### The Hightop User Experience

From the user's perspective:

1. Download [Hightop](https://hightop.com) app
2. Deposit USDC (soon fiat onramps)
3. Enable "AI Private Banker" for Yield Auto-Pilot
4. Watch balance grow
5. Withdraw anytime

What they never see:

- Token approvals for 20+ protocols
- Yield protocol comparisons
- Slippage calculations
- Smart contract interactions
- Permission management
- Any concept of gas, private keys, or seed phrases

They just earn. The complexity vanishes. That's the power of building on Underscore.

## Perfect for Vault Integration

The fastest way to add AI-managed yield to any application:

### Why Integrate Vaults

**For Fintech Apps**

Skip months of infrastructure development. Integrate [Vaults](vaults.md) directly:

- Standard ERC4626 interface — minimal integration work
- AI optimization handled entirely by Underscore
- Users deposit through your interface, you track shares
- No wallet infrastructure needed on your side

**For DeFi Protocols**

Make collateral productive:

- Accept vault shares as collateral
- Users earn yield while borrowing
- Standard ERC20 compatibility
- Vault value trackable on-chain

**For Portfolio Managers**

Offer managed strategies without building infrastructure:

- Earn Vaults for straightforward yield optimization
- Leveraged Vaults for amplified returns with managed risk
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
- **Every AI agent** managing portfolios
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

Remember: The best technology is invisible. Underscore handles the complexity so developers can build amazing experiences and users can enjoy financial freedom.
