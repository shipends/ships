---
title: Deploying Smart Contracts
takes: 5
---

# Deploying Smart Contracts --takes 5 min.

## Prerequisites

-   [Writing Contracts](./2_writing_contracts.md)
-   [Under the Hood](./3_under_the_hood.md)

## 1. Creating Deploy Script

Create **deploy.js** file in `scripts` folder -- if it _already_ exists, `delete` all the content in it,
coz' we _gonna_ start from scratch like **_pros_**.

## 2. Writing Boilerplate

`Copy + Paste` the following code in `deploy.js`

```js
const hre = require("hardhat");

const main = async () => {
	// We'll write deployment logic here
};

main().catch((error) => {
	console.error(error);
	process.exitCode = 1;
});
```

## 3. Understanding Deployment Process (Optional)

-   To _deploy_ a smart contract, it's `bytecode` is required -- you can find bytecode's value in `artifacts/contracts/[CONTRACT_NAME].sol/[CONTRACT_NAME].json` stored in the **bytecode** variable.

> Note: Bytecode consists of anything + everything your smart contract does. It will be then converted to machine level binary code.

-   Bytecode is taken by a function of _ethers_ called `getContractFactory`.
-   Then, we will call the **_deploy_** method returned by getContractFactory object.
-   Now, just _wait_ for the `deployed promise` to get fulfilled.

## 4. Writing Deployment Logic

-   Setting `Contract Factory`

```js
const contractFactory = await hre.ethers.getContractFactory("CONTRACT_NAME");
```

-   Calling **Deploy** Method

```js
const contract = await contractFactory.deploy();
```

-   **Waiting** for Deployment to Complete

```js
await contract.deployed();
```

Finally, your `main` function will look like **below**.

```js
const main = async () => {
	const contractFactory = await hre.ethers.getContractFactory("Hello");
	const contract = await contractFactory.deploy();
	await contract.deployed();

	console.log(`Deployment address is ${contract.address}`);
};
```

> **_p.s._**, you can also `console.log` _contractFactory_ + _contract_ objects to sell all that _nerdy_ stuff which happens behind the scenes.

## 5. Executing Deploy Script

Run `npx hardat run scripts/deploy.js` in terminal -- it will _spin_ a local blockchain => `execute` your deploy script =>
_terminate_ the local instance -- all in just **one** command, that's Hardhat _bruh_.

```bash
npx hardhat run scripts/deploy.js
```

### Yay! You just deployed a smart contract, now let's **[learn](./5_calling_contract_functions.md)** how to call those smart functions.
