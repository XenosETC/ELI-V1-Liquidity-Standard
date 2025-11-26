## **Overview**

The ELI V1 Liquidity Standard introduces a dual-layer liquidity model designed for Ethereum Classic (ETC).
This system separates **immutable, permanent liquidity** (“Hard Liquidity”) from **user-owned, flexible liquidity** (“Soft Liquidity”).
The result is a liquidity architecture that is:

* Immutable
* Anti-fragile
* Governance-free
* Timechain-reinforced
* Compatible with DeFi
* Resistant to rugpulls and liquidity loss

This document explains how both layers function and why this design is uniquely suited to ETC.

---

# 🟩 **Hard Liquidity (Immutable Liquidity)**

## **Definition**

**Hard Liquidity** is the liquidity permanently locked—via LP token burn—into an AMM pool.
It is:

* **Unowned**
* **Irreversible**
* **Permanent**
* **Unseizable**
* **Non-collateralizable**
* **Unruggable**
* **Unaffected by governance or human decisions**

Once added and burned, it becomes *protocol-level collateral* that cannot ever be withdrawn.

## **Properties**

* **LP tokens burned to a dead address**
* **Acts as immutable collateral**
* **Forms the liquidity “base” of the pool**
* **Deepens over time through swap-fee auto-burn (if AMM enables it)**
* **Anti-fragile: volatility strengthens it**

## **Purpose**

Hard Liquidity acts as the **granite foundation** of the asset’s economic system — ensuring permanent depth, stability, and trust.

It provides:

* Guaranteed liquidity
* A minimum floor for trading
* Protection from liquidity crises
* Stronger AMM curves under volatility

---

# 🟦 **Soft Liquidity (User-Owned Liquidity)**

## **Definition**

**Soft Liquidity** is the liquidity added by users who receive **LP tokens they control** (not burned).
It sits **on top of** the immutable base.

Soft Liquidity is:

* **User-owned**
* **Withdrawable**
* **Collateralizable**
* **Tradable**
* **Usable in yield systems**
* **Optional**

It behaves exactly like traditional DeFi LP tokens **without compromising Hard Liquidity**.

## **Properties**

* Can enter or exit freely
* Can be staked or yield-farmed
* Can be used as collateral in lending markets
* Can be leveraged
* Subject to impermanent loss
* Exists alongside Hard Liquidity in the same AMM pool

## **Purpose**

Soft Liquidity empowers DeFi flexibility while Hard Liquidity guarantees safety.

Together, they create a **dual-layer collateral model**:

```
Hard Liquidity  → Immutable, unowned, permanent
Soft Liquidity  → User-owned, collateralizable, flexible
```

---

# 🔀 **How Both Layers Coexist in One AMM Pool**

An ELI-compliant AMM pool may contain:

* **Hard LP (burned)** → permanent base
* **Soft LP (user-owned)** → optional liquidity

Both types of LP coexist **in the same pool**, operating under the same AMM curve.

### Hard LP ensures:

* permanent depth
* stability
* protection against rugpull
* a foundation for price discovery

### Soft LP enables:

* DeFi participation
* lending & borrowing
* staking & yield farming
* user incentives

Soft LP can be used as collateral.
Hard LP cannot — and should not.

This preserves the **integrity** of the immutable base.

---

# 🧱 **Why This Makes ELI Uniquely Anti-Fragile**

Hard liquidity is *untouchable* and grows over time through AMM usage.
Soft liquidity is *optional* and can expand, contract, and participate in DeFi without ever threatening the base.

This creates a system where:

* volatility strengthens the base
* yield farming cannot harm stability
* collateral systems remain safe
* AMM pools cannot collapse
* trading always has depth
* governance cannot alter fundamentals

This is the first anti-fragile liquidity architecture built natively for ETC.

---

# 🟩 **Summary**

| Feature          | Hard Liquidity         | Soft Liquidity                |
| ---------------- | ---------------------- | ----------------------------- |
| Ownership        | None (burned)          | User-owned                    |
| Withdrawable     | No                     | Yes                           |
| Permanent        | Yes                    | No                            |
| Collateralizable | No                     | Yes                           |
| Governance Risk  | Zero                   | Low (soft layer only)         |
| Rugpull Risk     | Zero                   | Zero (if exists with Hard LP) |
| DeFi Use Cases   | Stability, price floor | Collateral, yield, staking    |
| Alignment        | Pure ETC immutability  | Flexible, optional DeFi layer |

---

# **Conclusion**

Hard Liquidity forms the immutable economic foundation of ELI-compliant assets.
Soft Liquidity enables user-driven DeFi without compromising the permanence of the base.

Together, they create the **dual-layer liquidity model** that makes the ELI Standard uniquely suitable for Ethereum Classic — a chain defined by simplicity, immutability, and certainty.


Just say the word.
