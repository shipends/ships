---
title: Writing Smart Contracts
takes: 3
section: 2
---

# Writing Smart Contracts --takes 3 min.

## Prerequisites

-   [Setting up Hardhat](./1_setting_up_hardhat.md)

## 1. Installing Extension

Install `Solidity` extension in VS Code by _Juan Blanco_ from **[here](https://marketplace.visualstudio.com/items?itemName=JuanBlanco.solidity)** -- it will help in debugging + developing _faster_.

## 2. Exploring

All the smart contracts are written in the `contracts` folder -- if you don't know how to write one, check **[this](https://solidity-by-example.org/)** out.

## 3. Hello World Contract

Create a file -- **Hello.sol** in `contracts` folder. Then, _copy + paste_ the following code.

```js
// SPDX-License-Identifier: MIT

pragma solidity ^0.8.17;

import "hardhat/console.sol";

contract Hello {
    string public message = "Hello World";

    function getMessage() public view returns (string memory) {
        return message;
    }
}
```

## 4. Knowing console.sol

`console.sol` = `console.log in JavaScript` -- it helps in _printing statements_ to terminal during development.

> **Note:** Remove `console.sol` import statment in _production_.

### Wanna see some magical stuff? -- let's **[gooo](./3_under_the_hood.md)** then.
