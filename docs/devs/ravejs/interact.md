---
sidebar_position: 3
---

# Use Rave.JS

You can do a lot with Rave.JS! Here are some examples. Full docs [here](https://www.npmjs.com/package/@rave-names/rave).
Resolve a name to an address:
```js
const ravejs = require('@rave-names/rave');

const rave = new ravejs.Rave();


// Using the RaveName type
async function resolveName(name) {
  return (await rave.resolveNameToAddress(name));
}

// Not using the RaveName type
async function resolveString(name) {
  return (await rave.resolveStringToAddress(name));
}

const rName = {
  name: 'z.ftm',
  isOwned: true
}

console.log(resolveName(rName));
// >> '0x3e522051a9b1958aa1e828ac24afba4a551df37d'
console.log(resolveString('z.ftm'));
// >> '0x3e522051a9b1958aa1e828ac24afba4a551df37d'
```

Reverse search an address to a Rave Name:
```js
const ravejs = require('@rave-names/rave');

const rave = new ravejs.Rave();

// get ALL data of a name
rave.reverse('0x3e522051a9b1958aa1e828ac24afba4a551df37d').then(res => {
  console.log(res);
});

/*>> {
    name: 'z.ftm',
    isOwned: true,
    owner: '0x3e522051a9b1958aa1e828ac24afba4a551df37d',
    avatar: 'https://cyber.fantoms.art/Opr.png',
    addresses: {
      btc: '',
      eth: '0x3e522051a9b1958aa1e828ac24afba4a551df37d',
      ...
    }
  }
  */

// get ONLY the name an address holds
rave.reverseToName('0x3e522051a9b1958aa1e828ac24afba4a551df37d').then(res => {{
  console.log(res);
});
// >> 'z.ftm' 
```

Rave can even be customized on the fly!
```js
const ravejs = require('@rave-names/rave');

const rave = new ravejs.Rave();

console.log(rave.address);
// >> 0x14ff...

rave.restart({
  provider: 'https://rpc-api.fantom.network',
  address: '0x0000000000000000000000000000000000000000'
});

console.log(rave.address);
// >> '0x0000000000000000000000000000000000000000'
```