---
title: Setting up Hardhat
takes: 2
section: 1
---

# Setting up Hardhat --takes 2 min.

## 1. Installation

```bash
npm init -y
npm install --save-dev hardhat
```

## 2. Project Creation

Run `npx hardhat` in terminal -> Create a _JavaScript_ project -> `SPAM ENTER` for all other options.

```bash
npx hardhat
```

> **Note:** Whenever you _compile/run_ your smart contract, Hardhat automatically gets the required `version` downloaded + installed for you -- _pretty cool right!_

## 3. Quick Folder Intro

-   `node_modules` - All the magical spells of Hardhat reside here
-   `contracts` - Smart contracts are written here
-   `scripts` - Deployment scripts are made here
-   `test` - Testing scripts go here

### Let's write some cool smart contracts in the **[next](./2_writing_smart_contracts.md)** section.
