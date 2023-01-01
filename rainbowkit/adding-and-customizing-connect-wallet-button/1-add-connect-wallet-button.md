# Add Connect Wallet Button --takes 5 min.

## 1. Install RainbowKit + required dependencies.

```sh
npm install @rainbow-me/rainbowkit wagmi ethers
```

> To ensure our entire app has access to wallet connection, we need to configure + wrap it. So, we will modify \_app.js (Next)

## 2. Importing

```js index.js
import "@rainbow-me/rainbowkit/styles.css";
import { getDefaultWallets, RainbowKitProvider } from "@rainbow-me/rainbowkit";
import { configureChains, createClient, WagmiConfig } from "wagmi";
import { goerli, polygonMumbai } from "wagmi/chains";
import { alchemyProvider } from "wagmi/providers/alchemy";
import { publicProvider } from "wagmi/providers/public";
```

> For list of chains -- refer [this](https://wagmi.sh/react/chains#supported-chains)

## 3. Configuring

Go to [Alchemy](https://www.alchemy.com/) -- get your own API key on required network, add it to .env file.

```sh .env
GOERLI_API_KEY = YmDzvBst74rSPtrEDtYqYDdsoTSD7Sq7
POLYGON_MUMBAI_API_KEY = BnYvzDrb35eESrtDPtUzNYdoqUGS7Go1
```

```js index.js
const { chains, provider } = configureChains(
	[goerli, polygonMumbai],
	[
		alchemyProvider({ apiKey: process.env.POLYGON_MUMBAI_API_KEY }),
		publicProvider(),
	]
);

const { connectors } = getDefaultWallets({
	appName: "RainbowKit App",
	chains,
});

const wagmiClient = createClient({
	autoConnect: true,
	connectors,
	provider,
});
```

## 4. Wrapping

Wrapping means putting patty (RainbowKit) inside two buns (App Component), and calling it a hamburger (Shipped Product).

```js
export default function App({ Component, pageProps }) {
	return (
		<WagmiConfig client={wagmiClient}>
			<RainbowKitProvider chains={chains}>
				<Component {...pageProps} />
			</RainbowKitProvider>
		</WagmiConfig>
	);
}
```

## Connecting
