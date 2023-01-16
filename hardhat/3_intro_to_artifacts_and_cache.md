---
title: Writing Scripts for Smart Contracts
takes: 2
---

# Intro to Artifacts & Cache --takes 4 min.

## Prerequisites

-   [Writing Smart Contracts](./2_writing_smart_contracts.md)

## 1. Importing Environment

Create a new file -- hello.js in scripts folder. We'll require hardhat's native environment in order to interact with our smart contract, therefore let's import it.

```js
const hre = require("hardhat");
```

## 2. Writing main()

Create the following main function after the import statement.

```js
const main = async () => {
    console.log("Hello World");
};

main().catch((error) => {
    console.error(error);
    process.exitCode = 1;
});
```

## 3. Executing main()

To run the script that we just made, run npx hardhat run scripts/hello.js

-   npx - telling NodeJS that you wanna do something
-   hardhat - specifying the package that you want to use
-   run - stating that you wanna run something
-   scripts/hello.js - setting the path of the file that you wanna run

```bash
npx hardhat run scripts/hello.js
```

## 4. Something Cool just Happened

You will notice two folders - artifacts & cache in your project directory now.

-   Coz' whenever you run a script in hardhat, all the contracts stored in contracts folder get compiled + generate all the deployment info.
-   P.S., in order to integrate smart contract into your frontend -- you'll require only .json file stored in artifacts/contracts/[CONTRACT_NAME].sol/[CONTRACT_NAME].json

## 5. Cleaning (Optional)

When you are dealing with many contracts + constantly executing some scripts -- they might run successfully on first execution
but after that, they keep emitting errors. If it happens, just use clean command -- it deletes artifacts folder and
removes all the files from cache folder.

```bash
npx hardhat clean
```

## 6. Done

You are now one of those Web3 developers who knows wtf goes behind the scenes.
