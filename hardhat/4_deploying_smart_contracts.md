# Deploying Smart Contracts --takes 5 min.

## Prerequisites

-   [1. Writing Smart Contracts](./2_writing_smart_contracts.md)
-   [2. Intro to Artifacts & Cache](./3_intro_to_artifacts_and_cache.md)

## 1. Creating Deploy Script

Create deploy.js file in scripts folder -- if it already exists, delete all the content in it,
coz' we gonna start from scratch like pros.

## 2. Writing Boilerplate

Copy + Paste the following code in deploy.js

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

-   To deploy a smart contract, it's bytecode is required -- you can find bytecode's value in artifacts/contracts/[CONTRACT_NAME].sol/[CONTRACT_NAME].json stored in the "bytecode" variable.

> Note: Bytecode consists of anything + everything your smart contract does. It will be then converted to machine level binary code.

-   Bytecode is taken by a function of ethers called getContractFactory.
-   Then, we will just call the deploy function retured by getContractFactory object.
-   Now, just wait for the deployed promise to get fulfilled.

## 4. Writing Deployment Logic

-   Setting Contract Factory

```js
const contractFactory = await hre.ethers.getContractFactory("CONTRACT_NAME");
```

-   Calling Deploy Method

```js
const contract = await contractFactory.deploy();
```

-   Waiting for Deployment to Complete

```js
await contract.deployed();
```

Finally, your main function will look like this.

```js
const main = async () => {
    const contractFactory = await hre.ethers.getContractFactory("Hello");
    const contract = await contractFactory.deploy();
    await contract.deployed();

    console.log(`Deployment address is ${contract.address}`);
};
```

> P.S., you can also console log contractFactory + contract objects to sell all those nerdy stuffs that happen under the hood.

## 5. Executing Deploy Script

Run npx hardat run scripts/deploy.js in terminal -- it will spin a local blockchain => execute your deploy script =>
terminate the local blockchain -- damn those people who say blockchain is slow.

```bash
npx hardhat run scripts/deploy.js
```

## 6. Done

Fun Fact, now you can start interacting with your smart contracts.
