# Example: Using an ELI Asset as Collateral  
### Based on the 50/25/25 ELI Tokenomics Model

This example shows how an **ELI-compliant token** (using the 50/25/25 structure) can be used as collateral in a lending or vault protocol on **Ethereum Classic (ETC)**.

---

## 1. ELI Asset Recap (Token Structure)

For this example, assume the asset follows:

- **Total Supply:** 100,000,000  
- **50% (50M) Permanently Burned**  
- **25% (25M) Used for LP & Burned (PoBL)**  
- **25% (25M) Reserved for Ecosystem Incentives (Vested)**  

LP is paired with ETC and **all LP tokens are burned** to a dead address.  
This creates:

- immutable liquidity  
- a non-removable ETC backing  
- a verifiable PoBLBS (balance sheet)  

This is our base collateral object.

---

## 2. Collateral Properties of an ELI Asset

Because of the ELI structure, this asset has:

- **Immutable Liquidity:** LP cannot be pulled, migrated, or governed.  
- **Predictable Floor Behavior:** As long as the AMM exists, there is always depth.  
- **PoW-Enforced Finality:** The reserves backing the token are secured by ETC mining.  
- **Transparent Backing:** PoBLBS shows the actual ETC + token locked forever.  
- **Anti-Fragility:** Volatility and arbitrage naturally deepen the reserves over time.

These properties make it suitable as **hard collateral**, not just a speculative token.

---

## 3. Example Lending Model (ELI-Backed Borrowing)

A lending protocol on ETC wants to support ELI assets as collateral.

### 3.1 Basic Rules

1. Only **ELI-V1 compliant tokens** are allowed.  
2. PoBL and PoBLBS must be verifiable on-chain.  
3. Tokenomics must **never** undermine the LP (e.g., no insane inflation).  
4. Ecosystem incentives (25%) must be vested and transparent.

### 3.2 Collateral Onboarding

The protocol:

- Reads PoBLBS data (ETC locked, token locked, LP depth).  
- Confirms the LP burn transaction.  
- Confirms total supply, burned supply, and ecosystem allocation.  

Once verified, the asset is allowed as collateral with conservative parameters.

---

## 4. Example Collateral Parameters

For our 50/25/25 ELI asset, a lending protocol might set:

- **Initial LTV (Loan-to-Value):** 30–40%  
- **Liquidation Threshold:** 45–55%  
- **No governance overrides:** Risk parameters change only via transparent, code-bound rules (not arbitrary DAO votes).

As PoBLBS shows continued reserve strengthening over time (e.g., more ETC in the pool, deeper liquidity):

- LTV can be gradually increased (e.g., from 35% → 45%).  
- Liquidation thresholds can be adjusted safely.  

But the **LP base remains immutable** regardless.

---

## 5. Why ELI Collateral Is Safer Than Typical Tokens

### Ordinary Token (Non-ELI)

- LP can be pulled or rugged.  
- DAO or multisig can change liquidity.  
- Treasuries can drain or reallocate reserves.  
- Liquidity can move to new versions or chains.  
- Collateral can evaporate during crises.

### ELI Asset (50/25/25 Model)

- LP is permanently burned (cannot be removed).  
- Reserves are **non-political** (no DAO control).  
- Time and volatility reinforce backing.  
- 50% supply is burned, 25% is immutable LP, 25% is vested and transparent.  
- Collateral is anchored to an unchangeable economic base.

This makes ELI-backed collateral **more predictable and structurally safer** for long-term lending.

---

## 6. Example User Flow

1. User deposits ELI tokens into the lending protocol as collateral.  
2. Protocol reads PoBLBS and real-time price from the AMM.  
3. Protocol allows the user to borrow ETC or a stable asset up to, say, **40% LTV**.  
4. If the ELI price drops and LTV breaches the liquidation threshold, the position is liquidated **into an AMM with immutable depth**, reducing systemic risk.

Because the LP cannot vanish, liquidations always have a base pool to route through.

---

## 7. Summary Table

| Property              | ELI Asset (50/25/25)                  |
|-----------------------|----------------------------------------|
| Liquidity Control     | None (LP burned permanently)          |
| Backing               | ETC + Token locked in AMM             |
| Governance Dependence | None at the liquidity layer           |
| Collateral Stability  | Increases over time (PoBLBS growth)   |
| Main Risks            | Market price risk, not LP rug risk    |
| Ideal Use Cases       | Lending, vaults, hedging, perps base  |

---

## 8. Key Takeaways

- ELI assets provide **hard collateral**, not soft, governance-dependent collateral.  
- The **50/25/25 split** ensures:
  - strong scarcity (50% burn)  
  - strong immutable base (25% PoBL)  
  - controlled growth (25% ecosystem)  
- Lending and DeFi protocols on ETC can safely integrate ELI tokens as long as they respect:
  - PoBL  
  - PoBLBS  
  - Zero Governance over liquidity  
  - Long-term tokenomics integrity.

This is how **sound money meets sound liquidity** at the collateral layer.
