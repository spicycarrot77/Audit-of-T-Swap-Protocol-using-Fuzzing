#  T-Swap Protocol — Security Audit

This repository contains a **formal security audit of the T-Swap protocol**, which is a **simplified / toned-down version of Uniswap V2**.  

The purpose of this project was to **practice real-world smart contract auditing**, focusing on identifying vulnerabilities that **break core protocol invariants**.

The audit was performed using a combination of **manual code review** and **stateful fuzzing**.

---

##  About T-Swap

- T-Swap is inspired by **Uniswap V2**
- It follows the **constant product AMM model**
- Core logic includes:
  - Liquidity pools
  - Swaps
  - Reserve updates
  - Fee mechanics

Because it’s a simplified version, it’s ideal for learning:
- AMM mechanics
- Protocol invariants
- Common DeFi failure modes

---

##  Audit Approach

The audit was carried out using two main techniques:

### 1. Manual Review
- Read through the entire codebase line by line
- Identified trust assumptions and external call risks
- Checked whether protocol invariants are always preserved
- Looked for edge cases around swaps, liquidity changes, and fees

### 2. Stateful Fuzzing
- Wrote invariant-based fuzzing tests
- Tested how the protocol behaves across **many state transitions**
- Focused on breaking assumptions that should always hold true

---

##  Audit Report

- The full audit report is available in **`report.md`**
- It includes:
  - Identified issues
  - Invariant violations
  - Severity classification
  - Explanations and reasoning

---

##  Tests & Fuzzing

### Invariant Tests
- Located in the **`invariant`** test file
- Designed to:
  - Continuously test protocol invariants
  - Catch unexpected state transitions
  - Detect value creation or loss

### Basic Tests
- Functional tests covering:
  - Pool creation
  - Liquidity addition and removal
  - Swap functionality
- Ensures the protocol behaves as expected in normal conditions

---

##  Invariants Checked

Some of the key invariants tested include:
- Constant product formula must hold
- Reserves must stay in sync with balances
- No free value creation
- Fees are applied correctly
- Swaps cannot drain the pool unfairly

---

##  Tools & Tech Stack

- **Solidity** – Smart contract language
- **Foundry** – Testing and fuzzing
- **Invariant / Stateful fuzz testing**
- **Manual code review**

---

##  Learning Goals

This project helped me:
- Understand how AMMs work internally
- Learn how real audits are structured
- Practice writing invariant-based tests
- Identify subtle bugs that aren’t obvious in unit tests

---

##  License

MIT License
