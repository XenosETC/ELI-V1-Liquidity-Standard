### **Example ELI-Compliant Tokenomics (50/25/25 Burn–LP–Ecosystem Model)**

---

# **Example Tokenomics for an ELI-Compliant Asset (ELI-V1 Standard)**

This is the recommended template tokenomics model for ELI assets.
It strongly aligns with ETC’s immutability, scarcity, and non-governance principles, while providing developers with a clean, simple structure that **cannot undermine immutable liquidity**.

---

# **1. Token Overview**

| Component                              | Value                                                  |
| -------------------------------------- | ------------------------------------------------------ |
| **Total Supply**                       | 100,000,000 (100M)                                     |
| **Burned Supply (Permanent)**          | 50,000,000 (50%)                                       |
| **Initial LP Allocation (Burned LP)**  | 25,000,000 (25%)                                       |
| **Ecosystem Incentives / Development** | 25,000,000 (25%)                                       |
| **Initial Circulating Supply**         | Determined by natural market distribution              |
| **Governance**                         | Zero governance; no DAO control                        |
| **Inflation**                          | Optional 0–3% annual emissions, capped and predictable |

This creates a **perfect scarcity + immutable base** split.

---

# **2. Supply Breakdown**

### **Total Supply: 100,000,000 tokens**

| Category                  | Amount | % of Total | Notes                                                       |
| ------------------------- | ------ | ---------- | ----------------------------------------------------------- |
| **Perma-Burned Supply**   | 50M    | 50%        | Burned at genesis to dead wallet (proof of commitment)      |
| **Burned LP Pool (PoBL)** | 25M    | 25%        | Paired with ETC and LP burned permanently                   |
| **Ecosystem Incentives**  | 25M    | 25%        | For staking, dev, grants, NOT allowed to affect LP baseline |

This creates the clean ELI structure:

### **50% Supply → Immutably burned**

### **25% Supply → Permanently burned LP (PoBL)**

### **25% Supply → Controlled incentives (ecosystem vesting)**

This is *mathematically safe* and cannot violate the LP.

---

# **3. Initial LP Design (PoBL)**

* **25M tokens** paired with ETC at launch
* LP tokens received from the AMM
* LP tokens burned to a **dead address**:

```
0x000000000000000000000000000000000000dEaD
```

This ensures:

* minimum liquidity depth
* immutable floor structure
* ETC-backed reserves
* zero governance over liquidity
* no team or multisig can interfere
* LP behaves like infrastructure

This is the heart of the ELI standard.

---

# **4. Burned Supply (50%)**

Burning **50% of total supply** at genesis shows:

* strong commitment
* extreme scarcity
* floor volatility reduction
* mathematical alignment with the LP ratio
* protection against supply shocks
* anti-fragile ecosystem behavior

This burn **does not** replace LP — it strengthens it by reducing token float.

---

# **5. Ecosystem Incentives (25%)**

The remaining **25%** is held for:

* staking rewards
* development
* liquidity extensions (secondary)
* community incentives
* partnerships
* grants
* listings

**Rules for ecosystem incentives:**

### ✔ MUST be multisig-controlled

### ✔ MUST follow a vesting schedule

### ✔ MUST NOT undermine PoBL

### ✔ MUST NOT exceed LP strength

### ✔ MUST NOT dump into LP floor

### ✔ MUST be transparent

A recommended vesting:

* 10% unlocked at launch
* 90% linear vest over 36–48 months

This ensures long-term alignment.

---

# **6. Emissions Model (Optional)**

Inflation must always be:

* programmatic
* predictable
* small (0–3% recommended)
* strictly non-governed
* transparent
* non-dilutive to LP depth

Suggested model:

| Receiver                | Percent |
| ----------------------- | ------- |
| **Stakers**             | 50%     |
| **Ecosystem Rewards**   | 30%     |
| **Development Funding** | 20%     |

Emissions should NEVER outpace:

* demand
* LP strength
* long-term floor growth

ELI protects holders from governance-manipulated inflation.

---

# **7. Price Behavior Under the ELI Ratio**

This 50/25/25 structure yields the highest stability:

* 50% burn → extreme scarcity
* 25% burned LP → strong immutable floor
* 25% incentives → growth without harming LP

Over time, volatility pushes ETC into the burned LP, strengthening reserves through:

* arbitrage
* natural AMM rebalancing
* reduced float
* slower sell wall formation

This model becomes **anti-fragile**.

---

# **8. Long-Term Reserve Behavior**

With this ratio:

### ✔ Price floors rise over cycles

### ✔ LP cannot collapse under human pressure

### ✔ Reserve strength deepens with ETC appreciation

### ✔ Ecosystem funds cannot overpower LP

### ✔ Tokenomics cannot corrupt the ELI standard

This design is **self-reinforcing** and survives even if the builders disappear.

---

# **9. Summary Table**

| Component               | Amount          | Purpose                             |
| ----------------------- | --------------- | ----------------------------------- |
| **Burned Supply (50M)** | 50%             | Scarcity + trust                    |
| **Burned LP (25M)**     | 25%             | Eternal liquidity + collateral      |
| **Ecosystem (25M)**     | 25%             | Growth incentives (non-destructive) |
| **Inflation**           | Optional (0–3%) | Sustainable only                    |
| **Governance**          | Zero            | No control over LP                  |
| **Vesting**             | Required        | Protect LP behavior                 |

---

# **10. Why This Is the Best Example**

This model:

* mimics the most stable monetary systems
* gives ETC the kind of DeFi it actually thrives on
* demonstrates how scarcity + immutable liquidity = sound finance
* is simple enough for devs to follow
* is robust enough to inspire future case studies
* is mathematically protective of the LP
* is perfectly aligned with ELI V1

This is the example that will be used as the **gold standard** for ELI builders.
