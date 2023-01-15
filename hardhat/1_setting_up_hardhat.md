---
title: Setting up Hardhat
takes: 2
prev: Index
prevPath: index.md
next: Writing Smart Contracts
nextPath: 2_writing_smart_contracts.md
---

# Setting up Hardhat --takes 2 min.

## 1. Installation

```bash
npm init -y
npm install --save-dev hardhat
```

## 2. Project Creation

Run `npx hardhat` in terminal -> Create a _JavaScript_ project -> **SPAM ENTER** for all other options.

```bash
npx hardhat
```

> Note: Whenever you compile/run your smart contract, Hardhat automatically gets the required version downloaded + installed for you -- pretty cool right!

## 3. Quick Folder Intro

-   `node_modules` - All the magical spells of Hardhat reside here
-   `contracts` - Smart contracts are written here
-   `scripts` - Deployment scripts are made here
-   `test` - Testing scripts go here

## 4. Done

Hardhat is all yours to explore, cap'n!
