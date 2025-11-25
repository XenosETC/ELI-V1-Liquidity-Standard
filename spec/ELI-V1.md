# **ELI-V1 Specification**

**Eternal Liquidity Instrument – Version 1**
**Status:** Draft
**Author:** Xenos
**License:** MIT
**Tagline:** *Sound money deserves sound liquidity.*

---

# **1. Introduction**

The **ELI Standard (Eternal Liquidity Instrument)** defines a liquidity and collateralization method optimized for immutable, Proof-of-Work blockchains, with a primary focus on **Ethereum Classic (ETC)**.

ELI-V1 establishes a **zero-governance, immutable liquidity foundation** by using **Proof-of-Burn Liquidity (PoBL)** and **Proof-of-Burn Liquidity Balance Sheets (PoBLBS)** to replace dynamic, governance-driven, or treasury-managed liquidity systems found on other chains.

ELI is not a protocol fork or client modification.
It is a **social-layer and smart contract-layer economic standard** that encourages builders to align liquidity behavior with ETC’s first principles:

* Immutability
* Scarcity
* Proof-of-Work finality
* Neutrality
* Anti-governance
* Stewardship over control

---

# **2. Definitions**

## **2.1 Eternal Liquidity Instrument (ELI)**

A category of tokens or protocols that meet all mandatory requirements of this standard, including:

* immutable liquidity via PoBL
* verifiable PoBLBS monetary integrity
* tokenomics that never undermine burned liquidity
* zero governance control over the liquidity base

An **ELI asset** is one whose base liquidity is burned *permanently*.

---

## **2.2 Proof of Burn Liquidity (PoBL)**

PoBL is the process of:

1. Creating an initial liquidity pair (LP tokens).
2. Permanently sending LP tokens to a verifiable, unspendable address (a dead wallet).

This ensures:

* LP cannot be withdrawn
* LP cannot be migrated
* LP cannot be governed
* LP cannot be upgraded or altered
* LP becomes a chain-native public good

PoBL creates **untouchable but usable liquidity** — immutable and eternal.

---

## **2.3 Proof of Burn Liquidity Balance Sheet (PoBLBS)**

PoBLBS is the **on-chain accounting model** for ELI assets.

It includes:

* proof of burned LP
* total ETC permanently locked
* total counter-asset permanently locked
* minimum liquidity depth
* baseline asset backing
* verifiable market floor behavior
* long-term collateral data

PoBLBS forms the *economic backbone* that builders and users can independently verify.

---

## **2.4 Zero Governance DeFi (ZG-DeFi)**

ZG-DeFi is a liquidity and collateral architecture defined by:

* **no treasuries**
* **no governance votes**
* **no admin keys controlling liquidity**
* **no migrations**
* **no upgrades altering liquidity**
* **minimum required trust**

ELI-V1 is the first formal ZG-DeFi standard.

---

# **3. Purpose**

ELI-V1 exists to:

1. Provide a **sound liquidity base** for ETC DeFi.
2. Replace fragile, mutable, governance-based liquidity systems.
3. Enable **slow, stable, anti-fragile economic growth**.
4. Align smart-contract economics with PoW immutability.
5. Create a new collateral class suitable for long-term viability.

---

# **4. Requirements**

## **4.1 Mandatory Requirements (MUST)**

To be compliant with ELI-V1, a token or dApp MUST:

### **4.1.1 Burn Liquidity Permanently (PoBL)**

* LP MUST be burned to a known dead address.
* LP MUST NOT be withdrawable by any party.
* LP MUST NOT be migratable to new AMM versions.

### **4.1.2 Publish a PoBLBS**

A project MUST publish verifiable on-chain data including:

* LP burn transaction(s)
* total ETC locked
* total token supply locked
* liquidity pair details
* immutable base depth
* tokenomics model
* any emissions or reward schedules

### **4.1.3 Zero Governance Over Liquidity**

* Liquidity MUST have no admin keys.
* No DAO or human process may modify the LP.
* The liquidity base MUST be immutable.

### **4.1.4 Tokenomics MUST NOT Undermine LP**

* No emissions schedule may debase the LP base.
* Token supply changes MUST NOT meaningfully distort permanent liquidity.
* Any inflation MUST be mathematically bounded and clearly disclosed.

---

## **4.2 Strong Recommendations (SHOULD)**

### **4.2.1 Use PoW-Aligned Tokenomics**

Inflation should be:

* minimal
* predictable
* non-dilutive toward LP backing
* long-term sustainable

### **4.2.2 Publish Open Documentation**

Projects should:

* document PoBL rationale
* publish audits (optional)
* describe economic assumptions
* provide transparent dashboards

### **4.2.3 Promote Stewardship**

Builders should:

* act as stewards, not rulers
* prioritize long-term sustainability
* encourage ELI adoption as a public good

---

## **4.3 Optional Enhancements (MAY)**

ELI projects may include:

* staking systems that DO NOT control LP
* rewards built on top of immutable pairs
* lending systems using PoBLBS as collateral metrics
* dashboards and analytics
* bridgeless side-systems built on top of the core LP

---

# **5. Economic Rationale**

## **5.1 Liquidity as a Public Good**

In mutable DeFi systems, liquidity is:

* withdrawable
* politically controlled
* migration-dependent
* treasury-funded
* fragile

ELI transforms liquidity into a **public good**:

* neutral
* permanent
* incorruptible
* time-reinforced
* PoW-aligned

This shifts DeFi from:

**governance dependence → mathematical permanence**

---

## **5.2 Hard Liquidity vs Soft Liquidity**

* PoS chains → **soft liquidity** (inflationary, governable)
* ETC under ELI → **hard liquidity** (immutable, sound)

Hard liquidity stabilizes:

* token prices
* collateral ratios
* user trust
* market behavior

---

## **5.3 Slow-Growth, High-Security DeFi**

ELI leads to:

* fewer but stronger dApps
* slower but more sustainable growth
* less speculation, more solidity
* systems that survive cycles

This mirrors Bitcoin’s slow but unstoppable growth pattern.

---

# **6. Compliance Tests**

A project is **ELI-V1 compliant** if:

1. LP is provably burned to a dead address.
2. PoBLBS is published and verifiable.
3. Tokenomics avoid undermining the LP.
4. No governance can modify liquidity.
5. Liquidity is AMM-usable and fully immutable.
6. The project explicitly declares ELI-V1 compliance.

---

# **7. Security Considerations**

* Developers MUST avoid upgradeable contracts controlling liquidity.
* Builders MUST avoid dependence on multisig vaults or DAOs.
* Emissions must be sustainable relative to LP depth.
* Projects MUST NOT introduce governance that overrides PoBL.

Immutable liquidity is the security model.

---

# **8. Future Versions**

ELI-V2 may include:

* collateral scoring metrics
* formalized PoBLBS dashboards
* automated compliance checks
* oracle-free collateral models
* additional asset classes

---

# **9. References**

* Ethereum Classic Philosophy
* Bitcoin Sound Money Theory
* AMM Liquidity Models
* Irreversible Burn Mechanisms
* Stewardship-Based System Design

---

# **10. Summary**

**ELI-V1 defines a zero-governance, immutable liquidity standard that aligns with ETC’s sound-money foundation.**

By adhering to PoBL, PoBLBS, and stewardship-based tokenomics, ELI assets create:

* untouchable but usable liquidity
* mathematically enforced collateral
* sustainable PoW-aligned economic systems
* slow but superior DeFi stability

**Sound money deserves sound liquidity.
ELI makes it possible.**
