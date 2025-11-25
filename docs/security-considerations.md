### **ELI Standard – Security Considerations & Risks**

*Version 1.0 – Xenos*

---

# **1. Overview**

The ELI Standard reduces many DeFi risks by eliminating governance from the liquidity layer.
But developers and integrators MUST understand the security assumptions and boundaries of ELI-V1.

---

# **2. Liquidity Layer Security**

## **2.1 LP Must Remain Burned**

LP tokens MUST be burned **permanently**.
If LP is not 100% burned:

* team can remove liquidity
* AMM pool can be migrated
* rugpulls are possible
* collateral integrity is compromised

**PoBL is non-negotiable.**

---

## **2.2 Dead Address Verification**

Always verify LP tokens were burned to a proper address:

```
0x000000000000000000000000000000000000dEaD
```

Protocol integrators should:

* check LP token total supply
* verify the burn tx
* ensure LP cannot reappear

---

## **2.3 No Upgradeable Liquidity**

ELI **forbids**:

* proxy LP contracts
* upgradeable AMM versions holding the base LP
* admin functions on LP token contracts

All of these reintroduce governance risk.

---

# **3. Tokenomics Security**

## **3.1 Tokenomics Must Not Undermine LP**

ELI assets must ensure:

* emissions do not exceed demand
* vesting is predictable
* no minting functions can dilute the LP
* ecosystem funds cannot destabilize the pool

The LP is sacred.

---

## **3.2 No Infinite Inflation**

Infinite inflation breaks:

* scarcity
* trust
* collateral properties

Inflation MUST be:

* low (0–3%)
* predictable
* non-governed

---

## **3.3 Vesting Must Be Transparent**

Ecosystem incentives MUST:

* use multisig
* have visible vesting schedules
* avoid dumping into LP floor
* avoid creating sudden supply shocks

---

# **4. Contract Security**

## **4.1 Non-Upgradeable Token Contracts**

Token contracts MUST NOT:

* have proxy patterns
* allow admins to change logic
* allow pausing or freezing balances

ELI assets require **immutable token logic**.

---

## **4.2 No Admin Keys Over Collateral Layers**

Any privilege that allows:

* withdrawing LP
* redirecting LP
* pausing AMM functionality
* altering reserve ratios

…breaks ELI compliance.

---

# **5. Ecosystem Risks**

## **5.1 AMM Protocol Risk**

The AMM must be:

* permissionless
* immutable
* non-upgradeable
* resistant to admin takeover

If the AMM can change versions via governance, base LP can be invalidated.

---

## **5.2 Chain-Level Risks**

ELI relies on ETC for:

* finality
* immutability
* replay protection
* PoW security

Not suitable for PoS chains that can:

* reorganize states
* reverse governance decisions
* override liquidity via upgrades

---

## **5.3 Market Manipulation**

While liquidity is immutable, markets may still experience:

* price manipulation
* flash volatility
* bot arbitrage
* whale dumping

This does NOT compromise LP, but affects price.

---

# **6. User Risks**

## **6.1 Impermanent Loss**

IL cannot be removed from AMMs.
ELI only eliminates *harmful governance-driven loss*, not market-driven IL.

---

## **6.2 Speculative Misunderstanding**

Users may:

* assume ELI = price stability
* misunderstand PoBL as price guarantee

ELI guarantees **liquidity permanence**, not price permanence.

---

# **7. Summary**

ELI-V1 improves DeFi security by:

* eliminating governance
* establishing immutable liquidity
* aligning tokenomics with sound-money principles
* enabling trustless collateral

But developers MUST respect:

* correct PoBL execution
* non-upgradeable contract design
* sustainable tokenomics
* AMM choice
* transparent vesting
* PoW alignment

ELI is secure by **design and discipline**, not intervention.
