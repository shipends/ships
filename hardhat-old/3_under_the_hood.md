---
title: Under the Hood
takes: 2
section: 3
---

# Under the Hood --takes 3 min.

## Prerequisites

-   [Writing Smart Contracts](./2_writing_smart_contracts.md)

## 1. Importing Environment

Create a new file -- **hello.js** in `scripts` folder. We'll require Hardhat's native environment in order to _interact_ with our smart contract, therefore let's `import` it.

```js
const hre = require("hardhat");
```

## 2. Writing main()

Create the following _main_ function after the import statement.

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

To **_run_** the script that we just made, run `npx hardhat run scripts/hello.js`

-   `npx` - telling NodeJS that you wanna do something
-   `hardhat` - specifying the package that you want to use
-   `run` - stating that you wanna run something
-   `scripts/hello.js` - setting the path of the file that you wanna run

```bash
npx hardhat run scripts/hello.js
```

## 4. Something Cool just Happened

You will notice **_two_** folders - _artifacts_ & _cache_ in your project directory now.

-   **_Coz'_** whenever you run a script in hardhat, _all_ the contracts stored in `contracts` folder get _compiled_ + _generate_ all the deployment info.
-   **_p.s._**, in order to _integrate_ smart contract into your frontend -- you'll require only `.json` file stored in _artifacts/contracts/[CONTRACT_NAME].sol/[CONTRACT_NAME].json_

## 5. Cleaning (Optional)

When you are dealing with _many_ contracts + constantly _executing_ some scripts -- they might run successfully on first execution;
but after that, they would just keep _emitting_ errors. If it happens, just use `clean` command -- it _deletes_ artifacts folder and
_removes_ all the files from cache folder.

```bash
npx hardhat clean
```

### Done already? -- Let's **[see](./4_local_deployment.md)** it in action then.
