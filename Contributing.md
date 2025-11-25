# ✅ **`CONTRIBUTING.md`**

### *Guidelines for Contributing to the ELI Standard Repository*

---

# **Contributing to the ELI-V1 Liquidity Standard**

Thank you for your interest in contributing to the **Eternal Liquidity Instrument (ELI) Standard**.
This repository defines the liquidity architecture for immutable, Proof-of-Work DeFi on **Ethereum Classic (ETC)**.

Because this standard represents a **philosophical model**, a **technical specification**, and a **community reference**, contributions must follow clear guidelines to preserve ETC’s first principles.

---

# **1. Contribution Types Accepted**

You may contribute in the following areas:

### ✔ Improvements to documentation

* clearer language
* reorganized structure
* expanded explanations
* improved diagrams
* better examples

### ✔ Clarification of technical details

* PoBL processes
* PoBLBS accounting
* Zero-governance constraints
* collateral modeling

### ✔ Case studies & real-world ELI implementations

* tokens
* dApps
* lending/collateral models
* dashboards
* tooling

### ✔ Security considerations

* attack vector analysis
* risk models
* best practices

### ✔ Ecosystem integration examples

* how ELI interacts with ETC mining
* AMM integration
* wallet/portfolio tooling
* immutable LP analytics

### ✔ Academic or economic research

* timechain economics
* anti-fragility modeling
* PoW financial structures

If you want to propose changes to the **core specification**, please read Section **3** before submitting.

---

# **2. Contribution Types NOT Accepted**

To protect ELI’s purpose and ETC’s philosophy, the following contributions will not be accepted:

### ❌ Governance-based liquidity models

This includes DAOs, treasury-managed LP, or any system that can modify liquidity.

### ❌ Proposals requiring ETC protocol or consensus changes

ELI is a **social-layer standard**, not an L1 modification.

### ❌ Tokenomics that undermine PoBL or PoBLBS

If tokenomics can collapse or dilute the LP base, it violates the standard.

### ❌ Marketing promises, speculative content, or shilling

This repository is for engineering, economics, and research — not hype.

### ❌ Incomplete or unverifiable PoBL claims

All PoBL assertions must include links to on-chain transactions.

---

# **3. Rules for Proposing Changes to the Core Spec (ELI-V1.md)**

The ELI Specification defines an entire **asset class** and must remain stable, objective, and philosophically aligned.

Before proposing changes:

### ✔ Ensure your change respects ETC principles

* immutability
* PoW
* sound-money economics
* zero governance
* neutrality

### ✔ Provide mathematical or economic justification

Show how your change improves stability, trust, or clarity.

### ✔ Include references

Academic, crypto-economic, or code references are ideal.

### ✔ Be aware that core spec changes are rare

Like Bitcoin’s consensus, stability is more important than constant revision.

---

# **4. How to Submit a Contribution**

### **Step 1 — Open an Issue**

Before making a pull request:

* describe your idea
* link related files, examples, or code
* include relevant research or reasoning

This ensures community review before implementation.

### **Step 2 — Wait for Maintainer Review**

Feedback will determine:

* whether your idea belongs in core spec
* belongs in documentation
* belongs in examples
* or belongs as a separate repo linked here

### **Step 3 — Submit a Pull Request**

Once approved:

* fork the repo
* make your changes
* submit a PR
* follow formatting and markdown guidelines

### **Step 4 — Discussion & Verification**

All contributions are reviewed for:

* correctness
* clarity
* philosophical integrity
* technical accuracy
* ETC alignment

---

# **5. Formatting Standards**

### ✔ Use standard Markdown

### ✔ Avoid excessive formatting

### ✔ Keep examples minimal and clear

### ✔ Use code blocks for addresses, ABI snippets, etc.

### ✔ Use neutral, consistent terminology

Acceptable section structure:

```
## Title
### Subtitle (if needed)
Explanation text here...
```

---

# **6. Adding ELI Case Studies**

You may add real-world examples of PoBL, PoBLBS, or ELI-compliant tokenomics.

A valid case study must include:

* token address
* LP creation tx
* LP burn tx
* PoBLBS snapshot
* circulating supply
* proof that tokenomics do not undermine LP
* optional: dashboard link

Case studies are placed in:

```
/examples/case-studies/
```

A new folder will be created when the first case study is submitted.

---

# **7. Security Requirements**

For any technical contribution:

### ✔ Must avoid upgradable proxies

### ✔ Must avoid admin-controlled LP

### ✔ Must avoid governance dependencies

### ✔ Must not introduce attack vectors for LP corrosion

### ✔ Must respect the immutability assumptions of PoBL

Security contributions are especially valuable.

---

# **8. Code of Conduct**

Contributors must:

* be respectful
* remain objective
* avoid speculation
* avoid insults or chain tribalism
* focus on the technical + economic mission

We want an environment where ETC can grow through **soundness**, not hype.

---

# **9. Licensing**

All contributions are automatically licensed under the **MIT License**, which governs this repository.

This ensures:

* maximum openness
* maximum interoperability
* no legal barriers
* attribution is preserved

---

# **10. Final Note**

**ELI is a public good.**
It belongs to ETC, not to any individual.

This repository is the stewardship center for:

* immutable liquidity
* sound tokenomics
* zero-governance finance
* PoW-aligned DeFi
* a new class of digital assets

Thank you for helping define the economic future of Ethereum Classic.
