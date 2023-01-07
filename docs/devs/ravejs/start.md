---
sidebar_position: 2
---

# Initialize Rave.JS
*All code will be in CommonJS*

Rave.JS needs to be initialized to be used.

If you want to use Rave on Fantom mainnet, use this:

```js
const ravejs = require('@rave-names/rave');

const rave = new ravejs.Rave();
```

If you want to use a rave-like contract on a different chain, or different address, you can!

```js
const ravejs = require('@rave-names/rave');
const ethers = require('ethers');

const rave = new ravejs.Rave();

const YOUR_PROVIDER = new ethers.providers.JsonRpcProvider('RPC_URL'); // JSON-RPC provider
const YOUR_RAVE_ADDRESS = "0x0000000000000000000000000000000000000000"; // Rave Names contract address
const YOUR_EXTERNAL_RECORDS = "0x0000000000000000000000000000000000000001"; // ExternalRegistryV2 address

const rave = new Rave(YOUR_RAVE_ADDRESS,YOUR_PROVIDER);
```