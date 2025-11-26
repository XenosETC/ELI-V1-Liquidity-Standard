# **Example PoBL Flow (Proof of Burn Liquidity)**

### *ELI-V1 Standard — Immutable Liquidity Lifecycle*

---

# **1. Introduction**

This document outlines the full lifecycle of **Proof of Burn Liquidity (PoBL)** for an ELI-compliant token using the recommended **50/25/25 tokenomics structure**:

* **50% supply permanently burned**
* **25% supply used for initial LP and burned**
* **25% supply reserved for ecosystem incentives (vested)**

This is the canonical process for creating **immutable, PoW-aligned liquidity** on Ethereum Classic.

---

# **2. Full PoBL Lifecycle (Step-by-Step)**

---

## **Step 1 — Deploy Token Contract (ETC Network)**

Requirements:

* **Non-upgradeable contract** (no proxy)
* **No admin minting of arbitrary tokens**
* **No ability to freeze or seize balances**
* **Transparent, documented tokenomics**

This ensures trustlessness before liquidity is created.

---

## **Step 2 — Execute Initial Token Burns (50% Supply)**

Burn **50% of total supply** immediately to a dead address:

```
0x000000000000000000000000000000000000dEaD
```

Purpose:

* reduce long-term float
* align scarcity with ETC principles
* strengthen LP behavior
* anchor supply to PoBL
* enforce trust and fairness

This burn is separate from the LP burn; both are required.

---

## **Step 3 — Create the Initial Liquidity Pool**

Pair the **LP allocation (25% of supply)** with ETC on an ETC AMM (HebeSwap, etc.).

Example:

* **25,000,000 tokens**
* paired with **X ETC**

The initial ratio determines early market pricing but DOES NOT affect the long-term floor (that emerges from volatility + LP immutability).

---

## **Step 4 — Receive LP Tokens From the AMM**

The AMM returns LP tokens representing:

* control of liquidity
* right to withdraw liquidity
* right to migrate pools
* right to alter the pair through upgrades

Under ELI:

> **This control must be permanently eliminated.**

---

## **Step 5 — Perform PoBL (Burn the LP Tokens Permanently)**

Send **ALL LP tokens** to the designated dead address:

```
0x000000000000000000000000000000000000dEaD
```

Once burned:

* LP becomes **irreversible**
* liquidity becomes **public infrastructure**
* no individual or multisig can ever access it
* no DAO can vote to alter it
* no team can migrate it
* no upgrade path can move it
* no treasury can reclaim it

This is the core requirement of ELI.

---

## **Step 6 — Verify PoBL On-Chain**

Before continuing, verify:

* LP burn transaction hash
* LP token total supply
* LP burned amount = 100%
* confirmations on ETC chain
* AMM pair still functional
* no admin controls present

This verification establishes the **PoBLBS Generation Block (Genesis Sheet)**.

---

## **Step 7 — Publish the First PoBLBS Snapshot**

The project publishes the first **Proof of Burn Liquidity Balance Sheet**, including:

* **ETC locked in LP (permanent)**
* **Token locked in LP (permanent)**
* **LP token total supply burned**
* **minimum liquidity depth**
* **LP floor ratio**
* **initial reserve metrics**

This becomes the long-term collateral foundation.

---

## **Step 8 — Begin Ecosystem Incentive Vesting (25%)**

The remaining 25% is:

* stored in a multisig
* vested linearly over 36–48 months
* released predictably
* never allowed to disrupt LP behavior

Rules:

### ✔ MUST NOT dump into LP

### ✔ MUST NOT override PoBL economics

### ✔ MUST NOT exceed LP stability

### ✔ MUST remain transparent

This ensures the tokenomics layer NEVER compromises the liquidity layer.

---

## **Step 9 — Allow the Market to Function Under Immutable Liquidity**

Now the AMM handles:

* swaps
* arbitrage
* volatility
* depth adjustments
* ETC accumulation
* token accumulation

Because LP cannot move or shrink:

### ✔ price floors strengthen over time

### ✔ volatility deepens LP reserves

### ✔ ETC value accrues into the pool

### ✔ market behavior self-corrects

This is **timechain reinforcement** in action.

---

## **Step 10 — Maintain Ongoing PoBLBS Updates**

As time moves on:

* ETC increases in LP
* token supply adjusts across markets
* liquidity becomes anti-fragile
* price floors climb
* volatility enriches reserves

Every cycle, update PoBLBS with:

* ETC locked
* Token locked
* Reserve changes
* Floor levels
* Liquidity growth metrics

These become historical financial records for the asset.

---

# **3. The 50/25/25 PoBL Flow Summary**

### **✔ 50% Supply Permanently Burned**

Creates scarcity and market integrity.

### **✔ 25% Supply Burned as LP (PoBL)**

Creates immutable liquidity that cannot be removed.

### **✔ 25% Ecosystem Incentives (Vested)**

Feeds the project gradually without harming the LP.

This model:

* protects users
* protects liquidity
* protects ETC principles
* aligns with PoW
* creates an ELI asset class
* drives multi-year sustainability

---

# **4. Visual Summary Table**

| Stage                | Description                               |
| -------------------- | ----------------------------------------- |
| Deploy               | Token contract deployed (non-upgradeable) |
| Burn (50%)           | Genesis burn ensures extreme scarcity     |
| LP Creation (25%)    | Liquidity added using 25% supply          |
| PoBL                 | LP tokens burned permanently              |
| Verification         | On-chain verification of burn             |
| PoBLBS Genesis       | Initial balance sheet recorded            |
| Vesting Begins       | 25% ecosystem allocation unlocks slowly   |
| Market Reinforcement | Volatility deepens reserves               |
| PoBLBS Updates       | Ongoing collateral tracking               |

---

# **5. Why This PoBL Flow Is the Gold Standard**

This approach:

* maximizes immutability
* eliminates all LP governance
* protects users from team risk
* ensures long-term reserve strength
* creates mathematically honest tokenomics
* matches ETC’s “code is law” reality
* empowers ZG-DeFi (Zero Governance Finance)
* forms the economic foundation for ELI assets

It’s **simple, powerful, and completely future-proof**.
