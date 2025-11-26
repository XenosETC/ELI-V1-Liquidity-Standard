<p align="center">
  <img src="assets/eli_standard_banner_clean.png" alt="ELI Standard Banner" width="100%">
</p>

# ELI V1 Liquidity Standard

**Repository:** `ELI-V1-Liquidity-Standard`  
**Standard:** ELI V1 – Eternal Liquidity Instrument  
**Tagline:** *Sound money deserves sound liquidity.*

---

## Overview

The **ELI Standard (Eternal Liquidity Instrument)** defines a liquidity and collateral framework for **immutable, Proof-of-Work chains**, with a primary focus on **Ethereum Classic (ETC)**.

ELI is a **social-layer and smart contract standard**, not a protocol fork. It describes how to structure liquidity, tokenomics, and DeFi architecture so that they *align with ETC’s core principles*:

- Immutability  
- Scarcity  
- Proof-of-Work security  
- Zero governance interference  
- Stewardship > control  

At its core, ELI is about:

> **Liquidity that is untouchable but usable.**  
> LP that cannot be moved or rugged, but can still power DEXes, collateral, and DeFi.

---

## Core Ideas

ELI V1 formalizes three main components:

### 1. PoBL – Proof of Burn Liquidity

**Proof of Burn Liquidity (PoBL)** is the act of **permanently burning LP tokens** to a dead wallet address so that:

- Liquidity cannot be withdrawn  
- Liquidity cannot be migrated  
- Liquidity cannot be governed or seized  
- Liquidity becomes *effectively immutable*

This turns liquidity into a **public good** secured by the chain itself, not by a team, DAO, or multisig.

### 2. PoBLBS – Proof of Burn Liquidity Balance Sheets

**PoBLBS** is the on-chain accounting layer that treats burned LP as:

- Verifiable reserves  
- A permanent collateral base  
- A transparent, immutable “balance sheet” for a token or protocol

It lets anyone calculate:

- How much ETC (and paired asset) is permanently locked  
- The effective minimum depth and baseline backing  
- The long-term collateral quality of an asset

### 3. ZG-DeFi / ZGF – Zero Governance DeFi / Zero Governance Finance

ELI is designed for **Zero Governance DeFi (ZG-DeFi)**:

- No DAO votes required to secure liquidity  
- No treasury management required to back the asset  
- No admin keys needed to “control” reserves  
- No L1 governance changes required

The **only “governance” is self-sovereignty**:  
Your “vote” is your token, backed by immutable LP burned to the dead wallet. Anyone can build on top of that base.

---

## Design Goals

ELI V1 is built around these goals:

- **Immutable Liquidity** – LP that cannot be rugged, migrated, or politically altered  
- **PoW Alignment** – Liquidity behavior that matches the economic reality of a finite, PoW chain (like ETC)  
- **Zero Governance** – No DAOs or treasuries required for the liquidity base itself  
- **Stewardship First Principles** – Builders act as stewards, not rulers; they commit liquidity, not control it  
- **Tokenomics Integrity** – Issuance and supply behavior must **never** undermine the burned LP base  
- **Slow, Strong Growth** – ELI systems favor slower but more secure, long-lived DeFi over fast, fragile models

---

## Who Is This For?

This repo is intended for:

- **ETC / PoW DeFi Developers** – designing tokens, DEXes, or protocols using immutable liquidity  
- **Token Issuers** – who want to commit to honest, non-rug, PoBL-based tokenomics  
- **Researchers & Economists** – exploring hard liquidity, PoW-aligned DeFi, and social-layer design  
- **ETC Community Members** – who want a formal reference for the ELI concept and architecture

---

## Repository Structure (Planned)
```
ELI-V1-Liquidity-Standard/
├─ README.md                      
│   # Main entrypoint. Overview, philosophy, and navigation links.
│   # Explains the purpose of ELI, PoBL, PoBLBS, ZGF, and the rationale.
│
├─ LICENSE                        
│   # MIT License (open-source, permissive; allows adoption + derivatives)
│
├─ spec/
│  └─ ELI-V1.md                   
│       # Formal written specification of the Eternal Liquidity Instrument (ELI)
│       # Defines PoBL, PoBLBS, ZGF, compliance rules, and required-liquidity behavior.
│
├─ docs/
│  ├─ overview.md                 
│  │    # High-level explanation of ELI architecture, purpose, scope, and mental model.
│  │
│  ├─ design-principles.md        
│  │    # Stewardship foundations. Why immutable liquidity matters.
│  │    # PoW alignment, scarcity ethics, zero-governance requirements (ZGF).
│  │
│  ├─ faq.md                      
│  │    # Common questions, misconceptions, clarifications for devs/users.
│  │
│  ├─ amm-requirements.md         
│  │    # AMM compatibility checklist for ELI-compliant liquidity pools.
│  │    # Defines immutability requirements, LP token rules, fee constraints,
│  │    # and evaluation framework for AMMs like HebeSwap or custom AMMs.
│  │
│  ├─ security-considerations.md  
│  │    # Threat model for ELI liquidity.
│  │    # Covers dilution, protocol fee risks, pool-invariant integrity,
│  │    # admin key analysis, AMM-level risks, and safe deployment practices.
│  │
│  └─ terminology.md              
│       # Canonical definitions used across the entire standard:
│       # PoBL, PoBLBS, ZGF, Immutable Liquidity, ELI-Asset, ELI-Pair,
│       # Eternal Liquidity, Base Liquidity, Hard Collateral, etc.
│
├─ examples/
│  ├─ example-tokenomics.md       
│  │    # Standardized 50/25/25 ELI-compliant token design
│  │    # Demonstrates healthy supply distribution that respects LP invariants.
│  │
│  ├─ example-pobl-flow.md        
│  │    # Step-by-step lifecycle of PoBL: minting, LP burn, anchoring behavior,
│  │    # temporal strengthening, and long-term liquidity mechanics.
│  │
│  └─ example-collateral-usage.md 
│       # Illustrates how ELI assets function as hard collateral
│       # Using PoBLBS as on-chain balance-sheet proof for lending/DeFi.
│
├─ case-studies/
│  ├─ case-1.md      
│  │    # Case Study #1 — Token A: First PoBL implementation.
│  │    # Details design choices, burn events, tokenomics, and lessons learned.
│  │
│  └─ case-2.md       
│       # Placeholder template for future ELI projects.
│       # Encourages open-source builders to log real-world applications.
│
│
└─ CONTRIBUTING.md                
    # Rules and guidance for contributing.
    # Ensures philosophical consistency, technical accuracy, and correct structure.
    # Defines how to submit issues, improvements, and case studies.
