---
description: Let agents pay for the services they need — recurring payments within exact limits
---

# Payees: Let Agents Pay for the Services They Need

Payees are pre-approved addresses that receive payments from your [Programmable Wallet](user-wallet.md) — within exact limits you control. Pre-approve recurring recipients like market data feeds, model providers, compute vendors, contractors, payroll, and subscriptions. Set per-payment caps, period limits, allowed assets, cooldowns. Your funds keep earning in DeFi until the millisecond they're needed.

Your trading agent keeps its data feed, inference API, and GPU provider online with fixed USDC allowances. Your CFO pays vendors without accessing reserves. Employees pull their exact salary. Every payment validated against your rules, every penny earning yield until sent.

## Why Payees Exist

### The Agent Payment Problem

AI agents need to pay for services to operate: data feeds for market intelligence, inference APIs for decision-making, compute providers for execution. But giving agents unrestricted spending access is dangerous — one bug or exploit could drain your wallet.

Payees solve this by pre-approving specific recipients with hard spending caps. Your trading agent can keep its data feed and GPU provider online with fixed USDC allowances — but cannot overspend, cannot add new recipients, and cannot access funds beyond its budget. The agent (as a [Manager](managers.md)) can execute payments. Only you can decide who gets paid.

### The Problem with Recurring Crypto Payments

For both agents and humans, making regular crypto payments today means choosing between bad options:

- **Manual transfers**: Re-enter addresses, risk typos, waste time every pay period
- **Give full access**: Share private keys or grant unlimited spending permissions
- **Traditional banking**: Pay wire fees, lose DeFi yield, wait for processing

None of these work for agents, businesses, or individuals who need reliable, controlled automation.

### The Payee Solution

Payees create a verified recipient list with granular controls:

```
Traditional: Give vendor your credit card → They charge whatever, whenever
Underscore: Add vendor as Payee → $5,000/month limit → Only USDC → Auto-expires quarterly
```

Your funds stay in DeFi earning yield (via protocols like Aave, Morpho, Euler) until the moment of payment. The system automatically withdraws only what's needed, when it's needed. Plus, you earn [rewards](rewards.md) on all your DeFi activity.


## Pre-Approved Recipients, Enforced Onchain

### Owner-Controlled Recipient List

**Direct owner control**: Only you, as the [wallet owner](user-wallet.md), can directly add, confirm, or widen payees. Managers can propose new payees, but those proposals stay pending until you approve them after the configured delay. Payees can remove themselves, but nobody besides you can activate or expand them. This is enforced by smart contracts, not policy.

### Tamper-Resistant Recipient Records

**Onchain recipient records**: Once a payee is configured, the recipient address and limits live onchain. A manager cannot silently swap "GPU Provider" to a different address or widen the allowance without your approval.

### Managers Can Pay, Not Expand the List

**Separation of powers**: Managers can execute payments to active payees within the configured caps. They cannot unilaterally activate new recipients, raise payee limits, or route funds to unapproved destinations. You control the recipient list. Agents and operators handle the approved flow.

This is the core payee model: recurring recipients are approved first, then payments execute only within those limits.

## Payee Controls & Configuration

You can set comprehensive controls for each payee, ensuring payments happen exactly as intended. These controls protect against overspending, timing errors, and unauthorized changes.

### Financial Limits

#### Dual Protection System

Every payee supports both token amount AND USD value limits:

- **Transaction Limits**: Maximum per single payment (e.g., 1,000 USDC or $1,000)
- **Period Limits**: Maximum per time period (e.g., 5,000 USDC or $5,000/month)
- **Lifetime Limits**: Total cumulative maximum (e.g., 50,000 USDC or $50,000)

The most restrictive limit always applies, protecting against price volatility.

#### Period Configuration

- **Custom Periods**: Set any duration in blocks (e.g., 43,200 blocks ≈ 1 day on Base)
- **Auto-Reset**: Limits refresh each period (unused amounts don't roll over)
- **Common Settings**: Daily, weekly, bi-weekly, monthly, quarterly

### Payment Controls

#### Transaction Restrictions

- **Max Transactions**: Limit payment count per period (e.g., 1 for monthly salary)
- **Cooldown Period**: Minimum time between payments (prevents accidental double-pays)
- **Expiry Date**: Auto-deactivate payees after set time (e.g., contractor end date)

#### Asset Restrictions

Control exactly which tokens each payee can receive:

- **Single Asset**: Lock to one token only (e.g., USDC for salaries)
- **Preferred Asset**: Set default with flexibility for others
- **Any Asset**: Accept all tokens (useful for trading desks)

### Security Features

#### Global Settings (Wallet-Wide)

- **Pull Payment Master Switch**: Enable/disable all pull payments
- **Self-Payment Toggle**: Allow/block payments to yourself
- **Default Limits**: Base settings inherited by new payees

#### Individual Overrides

- **Custom Limits**: Override globals for specific relationships
- **Pull Permission**: Enable per-payee even if globally disabled
- **Asset Whitelist**: Restrict tokens beyond global settings

### System Limits

- **Maximum 40 Payees**: Per wallet capacity
- **Maximum 40 Assets**: Per payee restriction list
- **Fail-Safe Protection**: Blocks payments if price oracles unavailable
- **Keep it enabled**: A broken price feed could otherwise drain your wallet
- **Only disable for**: Pure stablecoin operations where you trust the 1:1 peg

Price oracles are essential services that provide real-world asset prices to the blockchain. By blocking payments when this price data is unavailable, the system prevents potential exploits that could otherwise drain funds during an oracle malfunction.

### Pull Payment Safety

**Hard requirement**: You _cannot_ enable pull payments without setting limits. The system enforces at least one cap (transaction or period) to prevent unlimited access.

## Permission System

### Who Can Add Payees

**Owner**: Full control to add, confirm, modify, or remove any payee
**Managers**: Can propose new payees (requires owner approval after delay)
**Others**: No access to change payees or their limits

### Who Can Execute Payments

**Owner**: Can pay any active payee within limits
**Managers**: Can pay active payees only, subject to both manager and payee limits
**Payees**: Can pull payments if explicitly enabled

### Who Can Remove

**Owner**: Can remove any payee immediately
**Payees**: Can remove themselves (clean exit option)
**Managers**: Cannot remove payees directly

## Lifecycle Management

### Activation Flow

```
Added → Pending → Active → Expired/Removed
         (delay)   (working)
```

### Typical Activation & Expiry Combinations

| Use Case                 | Activation Delay | Auto-Expiry | Why This Combo                                        |
| ------------------------ | ---------------- | ----------- | ----------------------------------------------------- |
| **New Vendor**           | 7 days           | 90 days     | High security for new relationships; quarterly review |
| **Regular Employee**     | 3 days           | 365 days    | Moderate security; annual contract cycle              |
| **Trusted Family**       | 1 day            | Never       | Quick access for emergencies; permanent relationship  |
| **Subscription Service** | 2 hours          | 30 days     | Fast setup; monthly renewal matches billing           |

### Administrative Hierarchy

**Owner (You)**

- Direct add/update/remove
- Confirm manager proposals
- Full control always

**[Managers](managers.md)** — Authorized Operators

- Can make payments to active payees within limits
- Can suggest new Payees (requires your approval)
- Cannot directly activate, remove, or widen payees
- Perfect for delegating routine payments while maintaining control

**Payees**

- Can remove themselves
- Enables clean exits

> **📋 Manager Proposals Need Your Approval**  
> If a manager proposes a new payee, you'll see a pending request. After the security delay (configurable by you), you must manually confirm to activate the payee. This two-step process prevents unauthorized additions.

## Pull Payments: Optional Recipient-Initiated Billing

Enable Payees to pull payment directly from your wallet, always within your preset limits.

### How It Works

1. Payee initiates withdrawal from your wallet
2. Smart contract validates against all configured limits
3. Funds automatically sourced from yield positions if needed
4. Payment executes immediately if within limits

### Double Activation Required

```
Global: canPull = true  AND  Payee: canPull = true
                ↓
        Pull payments enabled
```

### Real Numbers

Traditional subscriptions:

- $500/month sitting idle = $0 earned

With pull payments:

- $500/month earning 5% = $25/year extra
- $6,000 annual subscriptions = $300/year bonus

**Safety**: Pull Payees MUST have limits. No unlimited access allowed.

## Real-World Configurations

### Agent Data Feed

```
Payee: Market Data Provider
Period: 30 days
Limits: $200/month, 1 transaction
Pull Enabled: Yes
Cooldown: 25 days
Asset: USDC only
Result: Agent's data feed stays online automatically
```

### Agent Compute Provider

```
Payee: GPU Compute Vendor
Period: 7 days
Limits: $500/week, $50 per transaction
Pull Enabled: No (agent pushes payment)
Asset: USDC only
Result: Compute costs capped with weekly budget resets
```

### Agent Inference API

```
Payee: Inference API Provider
Period: 30 days
Limits: $1,000/month, 50 transactions
Pull Enabled: Yes
Cooldown: 6 hours
Asset: USDC only
Result: Agent calls inference endpoint, provider pulls payment per-use
```

### Employee Payroll Configuration

```
Payee: John Smith - Developer
Limits: $5,000 bi-weekly, USDC only
Schedule: 1st and 15th of each month
Result: Automatic payment from yield-earning funds
```

### Vendor Management

```
Vendor: SupplyCo
Period: 7 days
Limits: $2k/tx, $8k/week, $100k lifetime
Cooldown: 1 hour
Asset: Any stablecoin
Result: Flexible payments within boundaries
```

### Family Support

```
Payee: College Daughter
Period: 30 days
Limits: $2k/month split across 2 payments
Asset: USDC only
Activation: 1 day delay
Result: Automated allowance, adjustable anytime
```

### SaaS Subscriptions

```
Service: Analytics Platform
Pull Enabled: Yes
Period: 30 days
Limits: $149/month, 1 transaction
Cooldown: 25 days
Asset: USDC only
Result: Never miss payment, earn yield on float
```

## Common Questions

**What happens at expiry?**
Payees automatically deactivate. Payments blocked until you renew.

**What if I overpay by mistake?**
Impossible. Hard limits enforced by smart contracts on the blockchain prevent sending more than configured.

**Do I need separate Payees for each employee?**
Yes. Each payee has individual limits and tracking.

**Can I modify limits after setup?**
Yes. Changes take effect immediately.



## The Perfect Partnership: Managers + Payees

**Payees** define which recurring recipients can receive funds.
**Managers** ([Managers](managers.md)) handle the approved payment flow within their own permissions and budgets.

Together, they create unbreakable security:

- You verify payment addresses once (adding them as Payees)
- Your manager handles daily operations (paying only those Payees)
- You maintain ultimate control (only you can directly activate or widen payees)

This separation of powers means you can delegate work without delegating trust. Your CFO can pay approved vendors without adding a fake recipient. Your AI can keep approved services online without routing funds to an unknown address.

For AI agents, this separation is critical. The agent (Manager) can execute payments to pre-approved service providers (Payees), but cannot add new recipients or modify spending limits. The wallet owner defines which services the agent can pay for and how much it can spend — enforced onchain, not by policy.

**Learn more**: See how [Managers](managers.md) can automate your payment workflows.

## Related Features

- **[Cheques](cheques.md)**: One-time payments with time delays and cancellation ability
- **[Managers](managers.md)**: Learn how to delegate payment tasks to AI or team members
- **[Whitelist](whitelist.md)**: Configure instant, unlimited transfers for your most trusted addresses
- **[Programmable Wallets](user-wallet.md)**: Explore your agentic wallet and all its features
