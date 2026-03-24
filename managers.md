---
description: Give agents execution rights, not custody — within unbreakable boundaries you control
---

# Managers: Give Agents Execution Rights, Not Custody

Most agents can recommend. Underscore lets them execute — with real funds, without ever holding your private keys.

Managers are authorized operators that execute strategies and handle payments for your [Programmable Wallet](user-wallet.md) — without ever having full control. Set exact permissions: "Trade up to $50k USDC but never touch my ETH." Restrict to specific protocols: "Only rebalance between Aave, Morpho, Euler, and Compound." Define spending limits: "$10k daily, $100k monthly." Add time-based controls that auto-expire. Revoke access instantly with one click.

Let AI agents capture yield spikes at 3am. Let trading agents pay for their own data feeds and compute. Enable your CFO to pay vendor invoices without accessing reserves. Allow traders to work specific positions within exact boundaries. Every action validated onchain against your rules.

## Why Managers Exist

### The Agent Problem

AI agents need to execute transactions with real money — rebalancing yield positions, paying for data feeds, buying compute resources. But giving agents private keys or unrestricted access creates unacceptable risk. Traditional API keys and wallet delegation have no onchain enforcement. One bug, one exploit, and everything is gone.

Managers solve this by giving agents execution rights within smart-contract-enforced boundaries. The agent can do exactly what you authorize — nothing more, nothing less. Budgets, asset restrictions, protocol limits, and expiry windows are enforced by code, not policy.

### The Problem with Manual Wallet Management

Running a [Programmable Wallet](user-wallet.md) solo creates impossible tradeoffs:

- **24/7 Opportunities**: DeFi never sleeps, but you do
- **Routine Tasks**: Paying vendors, [claiming rewards](rewards.md), rebalancing — repetitive time drains
- **Specialized Knowledge**: Complex strategies require expertise you might not have
- **Emergency Access**: If something happens to you, your funds are locked

Traditional solutions all fail:

- **Shared keys**: One compromised key loses everything
- **Multi-sig**: Slow, requires coordination for every transaction
- **Custody services**: You lose control and pay high fees

### The Manager Solution

Managers enable programmable delegation with precise controls:

- **Limited Permissions**: Grant only specific actions (lend, swap tokens, pay [Payees](payees.md), etc.)
- **Spending Limits**: Hard caps on transaction and period amounts
- **Asset Restrictions**: Limit which tokens managers can touch
- **Instant Revocation**: Remove access with one transaction
- **Time Delays**: Optional cooling periods for sensitive actions

### Two-Phase Security Checks

Every manager action undergoes automatic validation:

**Before Any Action**:

- ✓ Is this manager still active?
- ✓ Can they perform this specific action?
- ✓ Can they touch this particular asset?
- ✓ Are they using an approved protocol?
- ✓ Has enough time passed since their last action?

**After The Action**:

- ✓ Did they stay under their per-transaction limit?
- ✓ Are they still within their daily/weekly/monthly budget?
- ✓ Have they exceeded their total lifetime allowance?

Both phases execute atomically within the transaction — if any check fails, the entire action reverts.

## Permissions: What Managers Can Do

Permissions are granular capabilities you grant to managers. You can mix and match these permissions to create the exact operator profile needed — from a CFO who only pays vendors to an AI that manages your entire DeFi strategy. Each permission is independent and can be combined with others.

### Transfer & Payment Operations

| Permission                       | Capability                                                                                  | Example Use Case        |
| -------------------------------- | ------------------------------------------------------------------------------------------- | ----------------------- |
| **General Transfers**            | Send assets to [Payees](payees.md), [Whitelist](whitelist.md), or via [Cheques](cheques.md) | Pay monthly expenses    |
| **Create [Cheques](cheques.md)** | Schedule one-time payments                                                                  | Delayed vendor payments |
| **Propose [Payees](payees.md)**  | Add recurring payment recipients                                                            | Onboard new contractors |

### DeFi Operations

| Permission           | Capability                            | Example Use Case                                   |
| -------------------- | ------------------------------------- | -------------------------------------------------- |
| **Buy & Sell**       | Swap tokens, rebalance portfolios     | Maintain 60/40 ETH/USDC ratio                      |
| **Manage Yield**     | Deposit/withdraw from yield protocols | Rebalance Morpho/Aave positions                    |
| **Manage Debt**      | Handle loans and collateral           | Keep 150% collateralization                        |
| **Manage Liquidity** | Provide/remove DEX liquidity          | Optimize Uniswap V3 ranges                         |
| **Claim Rewards**    | Harvest protocol incentives           | Collect and reinvest [farming rewards](rewards.md) |

### Administrative Operations

| Permission                 | Capability                    | Example Use Case                          |
| -------------------------- | ----------------------------- | ----------------------------------------- |
| **Whitelist Management**   | Add/remove approved addresses | Maintain vendor list                      |
| **Claim Protocol Rewards** | Harvest Underscore incentives | Auto-claim [platform rewards](rewards.md) |
| **Claim Loot**             | Collect revenue share         | Maximize [protocol earnings](rewards.md)  |

> **📝 Time Units in Underscore**  
> All time-based settings (delays, cooldowns, periods) are stored in blocks, not wall-clock time. On Base L2 with 2-second blocks:
>
> - 1 hour (1,800 blocks)
> - 1 day (43,200 blocks)
> - 1 week (302,400 blocks)
>
> Examples in this guide assume Base's 2-second block time.

## Controls: Security Boundaries

While permissions define what actions managers can take, controls set the boundaries within which they operate. These limits ensure that even trusted managers can't exceed your risk tolerance or drain your wallet through mistakes or malicious behavior. Every manager action must pass through these security checkpoints.

### Financial Limits

**Per-Transaction Limits**

- Maximum USD value for any single transaction
- Example: $5,000 cap prevents large one-time losses

**Period-Based Limits**

- Total USD value allowed within recurring time windows
- Period length set via `managerPeriod` in global settings (e.g., 1 day = 43,200 blocks)
- Periods reset automatically when the current period ends
- Example: $10,000 per day for trading operations

```
Week 1: Use $7k of $10k limit → Week 2: Fresh $10k limit
Unused amounts don't roll over — each period starts clean
```

**Lifetime Limits**

- Cumulative USD cap over Manager's entire tenure
- Example: $500,000 total for year-long AI service

### Operational Controls

**Transaction Cooldown**

- Mandatory waiting period between transactions
- Measured in blocks (e.g., 1 hour = 1,800 blocks on Base)
- Prevents rapid-fire mistakes or attacks

**Asset Restrictions**

- Limit Manager to specific tokens (e.g., only stablecoins)
- Granular control over what can be touched
- Maximum 40 different assets per manager

**Protocol Restrictions (Legos)**

- Restrict to specific DeFi protocols by ID
- Each protocol (["Lego"](user-wallet.md#the-lego-system) = standardized integration, e.g., Aave, Curve) registered in LegoBook
- Example: Only allow Aave and Compound interactions
- Maximum 25 different protocols per manager

**Approved Yield Protocols Only**

- Restrict managers to pre-approved vault tokens for yield deposits
- Prevents deposits into risky, unvetted, or unknown protocols
- Managed through the protocol's VaultRegistry whitelist
- Enable via `onlyApprovedYieldOpps` setting

**Payee Restrictions**

- Limit transfers to pre-approved addresses only
- Perfect for business operations with known vendors
- Maximum 40 approved [payees](payees.md) per manager

**Fail on Zero Price**

- Safety feature blocking transactions when asset price is $0
- Prevents trading during oracle failures
- Protects against manipulation when prices unavailable

### Swap Controls

Control trading activity with dedicated swap permissions that protect against excessive losses and manipulation:

| Setting | Purpose | Example |
|---------|---------|---------|
| **Max Slippage** | Maximum acceptable price movement on swaps | Default: 5% max |
| **Max Swaps Per Period** | Limit trading frequency | Default: 2 swaps per day |
| **Require USD Value** | Both tokens must have price data | Prevents trading unpriced tokens |

**How Slippage Protection Works**:

Before each swap, the system calculates the minimum acceptable output based on your slippage setting. If the actual output would fall below this threshold, the transaction reverts automatically.

```
Example: Swapping $1,000 USDC → ETH with 5% max slippage
Minimum acceptable: $950 worth of ETH
If DEX would return only $940 worth → Transaction reverts
```

This protects against:
- MEV sandwich attacks
- Price manipulation during execution
- Extreme market volatility
- Accidental bad trades

The system uses the tighter (lower) limit between global and manager-specific settings.

### Time-Based Security

**Activation Delay**

- New Managers wait before permissions activate
- Configurable delay period set by you (e.g., 1 hour, 1 day, 1 week)
- Time to verify additions and cancel if suspicious
- Protects against rushed or malicious manager additions

**Activation Length**

- Set Manager expiration periods
- Auto-revoke after: 30 days (trial), 90 days (quarterly), 365 days (annual)
- No action needed — permissions end automatically

### Global vs Specific Settings

Underscore employs a dual-layer configuration system where the most restrictive settings always apply:

**Global Manager Settings**

- Master template for all managers in your wallet
- Sets maximum boundaries no manager can exceed
- Includes `canOwnerManage` flag determining if you're subject to limits

**Specific Manager Settings**

- Individual configuration per manager
- Can be more restrictive than global, never less
- Both global AND specific permissions must allow an action

```
Example: Permission Hierarchy
Global: Can trade = Yes, Max per tx = $100k
Manager A: Can trade = Yes, Max per tx = $50k → Limited to $50k
Manager B: Can trade = No, Max per tx = $200k → Cannot trade at all
```

## Real-World Examples

### Yield Optimization

**Setup**: $100k in stablecoins with YieldMaxAI Agent

**Permissions**:

- Assets: Stablecoins only (USDC, USDT, DAI)
- Protocols: Aave, Morpho, Euler only
- Limits: $20k per transaction, 6-hour cooldown

**Results**:

- Captured 5.2% Morpho rate at 3am
- Moved to 6.1% Euler promotional rate
- Auto-claimed $312 in missed [rewards/incentives](rewards.md)
- Additional yield: $3,000 annually

### Agent Service Payments

**Setup**: Trading agent that needs live data feeds, inference APIs, and compute

**Permissions**:

- General Transfers: To approved [Payees](payees.md) only
- Create [Cheques](cheques.md): For one-off data purchases
- Assets: USDC only
- Limits: $500 per transaction, $5,000 monthly
- Cooldown: 1 hour between payments

**Results**:

- Agent keeps its data feed, inference API, and GPU provider online
- Small dataset purchases ($3-$50) clear instantly via Digital Cheques
- All spend tracked, capped, and revocable
- Agent never has custody, private keys, or unrestricted access

### Business Operations

**Setup**: Global crypto company with 30+ contractors and vendors, CFO as manager

**Permissions**:

- Recipients: Pre-approved contractor and vendor addresses only
- Limits: $2,500 per payment, $25,000 weekly
- Cooldown: 1 hour between payments
- Assets: USDC only

**Results**:

- CFO handles vendor payments independently
- Eliminated $1,750/month in wire fees
- Owner freed from payment operations
- Investment funds remain untouchable

### Family Office Trading

**Setup**: 5 professional traders as individual managers

**Permissions per trader**:

- Assets: ETH, BTC, stablecoins
- Protocols: Major DEXes only
- Limits: $100k per trade, $500k daily cap per trader
- Duration: Quarterly contracts, 3-day activation delay

**Results**:

- Risk distributed across multiple traders
- No single trader can exceed loss limits
- Each trader's P&L tracked separately
- Underperformers removed at quarter end

### Debt Management AI

**Setup**: Ripe Protocol Debt Manager AI Agent

**Permissions**:

- Manage Debt: Repay loans, add collateral
- Manage Yield: Withdraw from Aave/Morpho for repayments
- Limits: $50k per transaction, $200k daily

**Results**:

- Maintains 150% collateralization ratio 24/7
- Auto-withdraws yield to repay when needed
- Added $15k collateral during market volatility
- Prevented liquidation during 20% market drop

### Teen Trading Education

**Setup**: 16-year-old son learning DeFi with monthly allowance

**Permissions**:

- Buy & Sell: Can swap between major tokens
- Manage Yield: Can deposit to Aave/Morpho/Euler only
- Assets: Limited to ETH, USDC, and top 10 tokens
- Limits: $100 per transaction, $500 monthly cap
- Cooldown: 30 minutes between trades
- Duration: 6-month trial period

**Results**:

- Son learns DeFi with real money, real stakes
- Losses capped at affordable education cost
- Can't access family's main holdings
- Built experience before accessing own wallet at 18

## Lifecycle Management

### Manager States

```
Added → Waiting → Active → Expired
  │        │         │        │
  └────────┴─────────┴────────┴─→ Removable anytime
           │         │
           │         └─→ Extendable (resets expiry)
           │
           └─→ Cancellable before activation
```

### Administrative Hierarchy

**You (The Owner)**

- Add, update, remove any Manager
- Modify all settings and limits
- Extend activation periods
- Ultimate control always

**The Manager**

- Can only remove themselves
- Cannot modify permissions
- Cannot add other Managers
- Prevents permission escalation

## Common Questions

**Can managers add other managers?**
No. Only the wallet owner can add new managers. This prevents permission escalation attacks.

**What happens when a manager expires?**
They automatically lose all permissions. No action needed from you.

**Can I change limits without removing the manager?**
Yes. You can modify permissions, limits, and allowed assets/protocols anytime.

**Do unused period limits roll over?**
No. Each period starts fresh with the full limit. Use it or lose it.

## Working with Other Features

### Managers and Payees

- Managers can transfer to approved [payees](payees.md) within their limits
- Add payee restrictions to limit manager transfers to known addresses
- Perfect for accounts payable roles with vendor payment access

### Managers and Cheques

- Managers can create [cheques](cheques.md) within their spending limits
- Cheque amounts count against manager's daily/period/lifetime caps
- Time delays on cheques add extra security layer

### Managers and Whitelist

- Managers can interact with the [whitelist](whitelist.md) only if you explicitly grant whitelist-management permissions
- Once an address is whitelisted, transfers to it bypass normal payee and cheque controls
- Use whitelist for emergency access and internal capital routing; use managers, payees, and cheques for day-to-day operations
