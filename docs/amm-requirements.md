# AMM Compatibility Requirements for the ELI Standard  
### How to Evaluate Automated Market Makers for Eternal Liquidity

**Version:** 1.0  
**Author:** Xenos  

---

## 1. Purpose

The ELI Standard (Eternal Liquidity Instrument) defines a way to create **immutable, governance-free liquidity** on Proof-of-Work chains like Ethereum Classic (ETC).

However, ELI does **not** mandate a specific DEX or AMM.

Instead, it defines **requirements** that any AMM must satisfy in order to safely host **ELI-compliant liquidity pools** (i.e., PoBL pools with burned LP).

This document explains:

- what makes an AMM ELI-compatible  
- how to evaluate an AMM contract  
- how HebeSwap V2 fits these requirements  
- when a developer should consider building a dedicated / custom AMM

---

## 2. High-Level Requirements

An AMM is considered **ELI-compatible** if:

1. **Contracts are immutable**  
   - No proxies, no upgrade hooks, no upgradable logic.

2. **There is no migrator / forced migration path**  
   - Liquidity cannot be forcibly moved to a new AMM version.

3. **LP tokens are standard and non-privileged**  
   - No owner, no pause, no admin mint/burn outside normal liquidity operations.

4. **Protocol fees (if any) do not threaten base LP immutability**  
   - No mechanism that can silently or unilaterally drain core liquidity.

5. **No governance over the liquidity behavior**  
   - No DAO, multisig or role can change pool invariants, forcibly withdraw LP, or impose upgrades on the pair.

6. **AMM can be used trustlessly via contract only**  
   - Frontend is optional; contracts behave correctly on-chain.

ELI is a **liquidity behavior standard**, not a DEX brand — but the DEX must meet these constraints.

---

## 3. Detailed Requirements

### 3.1 Immutability

- AMM contracts MUST NOT:
  - use proxy patterns
  - delegate logic to upgradable contracts
  - include owner-only upgrade functions

**Reason:**  
If the AMM logic can change, then “eternal” liquidity can be broken by future changes.

---

### 3.2 No Migrator or Forced Liquidity Moves

- There MUST NOT be any:
  - `migrator` variable
  - `setMigrator(address)` function
  - `migrate()` / `upgradeLiquidity()` style calls

**Reason:**  
“Proof of Burn Liquidity” (PoBL) assumes that burned LP **cannot be moved**.  
A migrator reintroduces the possibility of forced movement.

---

### 3.3 LP Token Properties

The LP token MUST:

- be a standard ERC-20  
- only be minted by the pair contract during `mint()`  
- only be burned during `burn()` via liquidity removal  
- have **no owner**, no `pause`, no `blacklist`

**Reason:**  
If someone can mint/burn LP arbitrarily, they can fake or distort PoBL and PoBLBS.

---

### 3.4 Protocol Fees (feeTo / feeToSetter)

Some AMMs (including Uniswap V2-style forks) implement protocol fees via:

- `feeTo` — address that receives protocol fees  
- `feeToSetter` — address that can set `feeTo`  
- `_mintFee()` — mints extra LP to `feeTo` when pool growth occurs

This does **not** directly move burned LP, but:

- it mints new LP (diluting the dead-wallet LP)  
- that LP can be burned by `feeTo` to withdraw underlying reserves  
- this can gradually **siphon a portion of pool value** out of the AMM

From an ELI perspective:

- **Acceptable (soft-ELI)** if:
  - `feeTo` is kept at `address(0)` (no protocol fee)
  - Or set to a **publicly-known, immutable burn address**
- **Stronger / ideal (hard-ELI)** if:
  - AMM implementation used for ELI pairs removes `feeTo`, `feeToSetter`, and `_mintFee` entirely

**Conclusion:**  
Protocol fees are **not inherently incompatible**, but they introduce **trust assumptions**.
For strict ELI usage, fees SHOULD be disabled or removed at the contract level.

---

### 3.5 No Governance Over LP Behavior

- The AMM MUST NOT:
  - let a DAO or multisig vote to change swap math
  - allow changing fee structure in ways that can confiscate LP
  - implement pausable or kill-switch behavior over pools

**Reason:**  
ELI’s core: **Zero Governance Finance (ZGF)** at the liquidity layer.

If your liquidity depends on a governance decision, it is not ELI-grade.

---

### 3.6 Frontend Independence

The AMM contracts:

- MUST be callable directly on-chain  
- MUST not rely on off-chain components for core behavior

**Reason:**  
PoBL and PoBLBS are long-term concepts; liquidity must remain usable even if all frontends vanish.

---

## 4. HebeSwap V2 Evaluation (On ETC)

Based on the provided source code, **HebeSwap V2** is:

- a direct Uniswap V2-style AMM  
- with:
  - **no migrator**
  - immutable pair contracts
  - standard LP token behavior
  - `feeTo` / `feeToSetter` protocol fee logic
  - no owner/governance for liquidity logic

### 4.1 Positives for ELI

- ✅ No migrator  
- ✅ Uniswap V2 mechanics (xy = k)  
- ✅ Immutable pair contracts  
- ✅ LP burn is permanent and verifiable  
- ✅ No governance controlling swaps or LP

This makes HebeSwap an excellent match for ELI **from a structural AMM design perspective.**

### 4.2 Protocol Fee Caveat

- The factory contract includes:
  - `address public feeTo;`
  - `address public feeToSetter;`
  - `setFeeTo(address _feeTo)` and `setFeeToSetter(address _feeToSetter)`

- Pairs include `_mintFee()`, which:
  - mints new LP to `feeTo` if `feeTo != address(0)`

**Impact:**

- If `feeTo` is set to a non-zero address:
  - protocol fees accumulate as extra LP  
  - when `feeTo` burns its LP, some pool reserves can be withdrawn  
  - this can effectively skim part of the pool over time

**ELI Recommendation for HebeSwap:**

- For ELI-grade pools on HebeSwap:
  - `feeTo` SHOULD remain `address(0)`  
  - ELI implementers SHOULD prefer pools where protocol fees are known to be disabled  
- For maximal purity:
  - a dedicated factory **for ELI pairs only** can be deployed, with:
    - `feeTo` hardcoded to zero or removed  
    - `setFeeTo` / `setFeeToSetter` removed

---

## 5. Recommendation Summary

### 5.1 Using Existing AMMs (like HebeSwap)

**Pros:**

- Already deployed on ETC  
- Battle-tested mechanics  
- Familiar UX for users  
- Easy to integrate

**ELI Stance:**

- HebeSwap V2 is **recommended** for ELI pairs **provided**:
  - protocol fees remain disabled (`feeTo == address(0)`)  
  - ELI implementers understand the residual trust in feeToSetter  

This is a **practical, Pro-ETC path** for current builders.

---

### 5.2 Building a Dedicated ELI AMM

For devs who want absolute purity, ZGF-maximalism, and zero trust assumptions:

**Recommended approach:**

- Start from a Uniswap V2 reference implementation  
- Remove:
  - `feeTo`, `feeToSetter`
  - `_mintFee()` logic
  - any governance hooks
- Ensure:
  - no migrator  
  - no owner/admin  
  - no upgradability  
- Deploy as:
  - `ELI-AMM` or similar, used exclusively for ELI-grade pools

This yields an AMM that fully matches:

> **Immutable Liquidity for Immutable Chains.**

---

## 6. Quick Checklist for ELI AMM Compatibility

When evaluating any AMM for ELI:

- [ ] No migrator / migration functions  
- [ ] No upgradeable contracts or proxies  
- [ ] LP tokens are non-privileged, ERC-20 only  
- [ ] No functions to force-remove or confiscate LP  
- [ ] Protocol fees are disabled or cannot harm base liquidity  
- [ ] No governance over liquidity behavior  
- [ ] AMM is callable directly on-chain without off-chain dependence  

If all items are satisfied, the AMM is a suitable host for ELI-compliant pools.

---

## 7. Final Note

ELI does not pick winners among AMMs.

It simply asserts:

> *“If you want eternal liquidity, the AMM must be as immutable and non-governed as your tokenomics.”*

HebeSwap V2 on ETC, as a Uniswap V2-style AMM without migrator, is a strong match under these principles.  
Developers who want **absolute purity** are encouraged to deploy **ELI-specialized AMMs** with fees and governance logic removed entirely.

