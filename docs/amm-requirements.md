# AMM Compatibility Requirements for the ELI Standard  
### How to Evaluate Automated Market Makers for Eternal Liquidity

**Version:** 1.1  
**Author:** Xenos  

---

## 1. Purpose

The ELI Standard (Eternal Liquidity Instrument) defines a way to create **immutable, governance-free liquidity** on Proof-of-Work chains like Ethereum Classic (ETC).

ELI does **not** mandate a specific AMM.  
Instead, it provides **requirements** that ensure burned LP (PoBL) liquidity remains:

- immutable  
- non-withdrawable  
- ungoverned  
- anchored for the lifetime of the chain  

This document explains:

- what makes an AMM ELI-compatible  
- how protocol fees affect (or do not affect) PoBL  
- how HebeSwap V2 fits these requirements  
- when a developer should deploy a dedicated ELI-only AMM

---

## 2. High-Level Requirements

An AMM is considered **ELI-compatible** if:

1. **Contracts are immutable**  
   - No proxies, no upgrade hooks.

2. **No migrator / forced migration path**  
   - Liquidity cannot be forcibly moved to new versions.

3. **LP tokens are standard and non-privileged**  
   - No owner, no pause, no blacklist, no arbitrary mint.

4. **Protocol fees (if present) cannot break the PoBL base**  
   - Fees must not allow draining or touching the immutable PoBL LP.

5. **No governance over liquidity behavior**  
   - No DAO or multisig can alter how LP or swaps behave.

6. **AMM is permanently usable via contract alone**  
   - No off-chain dependencies required for swaps.

ELI is a behavior standard for liquidity — not a swap or DEX brand.

---

## 3. Detailed Requirements

### 3.1 Immutability

AMM contracts MUST NOT:

- use proxies  
- be upgradeable  
- include owner-only override functions  

**Why:**  
If AMM logic can change, PoBL’s permanence is no longer guaranteed.

---

### 3.2 No Migrator or Forced Liquidity Moves

MUST NOT contain:

- `migrator` variables  
- `setMigrator()`  
- `migrate()`  
- `upgradeLiquidity()`  

**Why:**  
A migrator can forcibly move liquidity out of the original AMM, breaking immutability.

---

### 3.3 LP Token Properties

LP tokens MUST:

- be ERC-20  
- be minted only during `mint()`  
- be burned only during `burn()`  
- have **no owner**, **no pause**, **no blacklist**  

**Why:**  
PoBL relies on LP tokens being trustless, non-privileged assets.

---

### 3.4 Protocol Fees (feeTo / feeToSetter)  
**Clarified based on code analysis**

Some AMMs (including Uniswap V2 forks like HebeSwap) implement protocol fees:

- `feeTo` — address that receives protocol fees  
- `feeToSetter` — role that can set `feeTo`  
- `_mintFee()` — mints **new LP tokens** to `feeTo` based on pool growth

This mechanism:

- 🔒 **cannot remove or touch the original PoBL LP**  
- 🔒 **cannot withdraw PoBL’s underlying reserves**  
- 🔒 **cannot “rug” liquidity**  

What it *can* do:

- Mint **additional LP** to `feeTo` over time  
- Allow `feeTo` to burn *its own minted LP* and withdraw **its proportionate share** of reserves  
- Slightly dilute the dead-wallet LP’s percentage ownership of the pool  
- But **never degrade or confiscate the PoBL base**

#### From an ELI perspective

- **Acceptable (soft-ELI)**
  - If `feeTo == address(0)` (protocol fees disabled)
  - Or if protocol fees are publicly known and transparent

- **Ideal (hard-ELI)**
  - Remove `feeTo`, `feeToSetter`, and `_mintFee()` entirely in a dedicated ELI AMM  
  - This maintains *zero trust surface* and absolute immutability

#### Conclusion
Protocol fees introduce **proportional dilution**, but **cannot break or exploit the immutable PoBL base**.

---

### 3.5 No Governance Over LP Behavior

AMM MUST NOT allow:

- DAO votes on pair logic  
- admin control over fees that change swap math  
- pausable or kill-switch behavior  
- any function that could block usage or force migration

**Why:**  
ELI requires Zero-Governance Finance (ZGF) on the liquidity layer.

---

### 3.6 Frontend Independence

AMM MUST remain usable:

- directly via contract calls  
- with zero reliance on a web interface  

**Why:**  
PoBL and PoBLBS must survive decades of chain time.

---

## 4. HebeSwap V2 Evaluation (ETC)

HebeSwap V2 is:

- a direct Uniswap V2 fork  
- **no migrator**  
- immutable pair contracts  
- pure XYK invariant  
- standard LP behavior  
- protocol fee mechanism intact (optional)

### 4.1 Strengths for ELI

- ✔ No migrator  
- ✔ LP burn = permanent  
- ✔ No admin withdrawal  
- ✔ No proxy contracts  
- ✔ LP can never be touched by owner  
- ✔ No governance that modifies liquidity

### 4.2 Protocol Fee Assessment

- Protocol fees **cannot touch the Genesis PoBL LP**  
- Protocol fees **can only mint new LP** for `feeTo`  
- That LP represents only **a share of pool growth**, not the base  
- If `feeTo` stays unset → pool remains fully immutable and non-dilutive

### ELI Recommended Usage

- Enable pools on HebeSwap when:
  - `feeTo == 0x0000000000000000000000000000000000000000`
  - No active protocol fee harvesting

- For strictest ELI compliance:
  - Deploy a custom factory with protocol fees removed entirely

---

## 5. Recommendation Summary

### ✔ Using HebeSwap (Practical ELI)

**Recommended**  
If `feeTo` is zero or protocol fees are publicly disclosed.

- Safe  
- On-chain  
- Immutable base  
- No rug mechanics  
- PoBL anchor guaranteed  

### ⭐ Building a Dedicated ELI-Only AMM (Maximal ELI)

For builders who want:

- zero governance  
- zero trust  
- zero dilution  
- perfect immutability  

Deploy a Uniswap V2–derived AMM with:

- no `feeTo`  
- no `feeToSetter`  
- no `_mintFee()`  
- no governance roles  
- no fee logic at all

This becomes the **canonical ELI AMM**.

---

## 6. Quick Checklist for ELI AMM Compatibility

- [ ] No migrator  
- [ ] No upgradable logic  
- [ ] LP tokens have no owner/privilege  
- [ ] Protocol fees cannot touch PoBL  
- [ ] No governance over AMM logic  
- [ ] AMM is 100% usable via contract alone  

---

## 7. Final Note

ELI remains neutral about AMMs.

> **“Immutable liquidity requires an immutable AMM.  
> If the AMM fits the principle, the pool is eternal.”**

HebeSwap V2 is a strong, practical choice for ELI.  
A custom fee-less factory represents the ideal future for complete ELI purity.
