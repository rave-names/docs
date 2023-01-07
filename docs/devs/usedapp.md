---
sidebar_position: 3
---

# Using useDapp with Rave

[useDapp](https://usedapp.io) is a [ReactJS](https://reactjs.org) framework for using Ethereum in dApps. It provides a lot of handy features, but the one we're looking at the `useLookupAddress` hook, which can be used to lookup addresses to Rave Names.

Make sure you have it installed with `npm i @usedapp/core`!

First, import the hook into your file:
```import { useLookupAddress } from '@usedapp/core'```

Then, to use it in a React functional component, use this:

```jsx
function App({ account }) {
  const { ens: name } = useLookupAddress(account, { rave: true });

  return <p>Address: {name ?? account}</p>;
}
```

If `App()` is fed '0x3e522051A9B1958Aa1e828AC24Afba4a551DF37d' as `account`, it will return:

`<p>Address: z.ftm</p>` or `<p>Address: 0x3e522051A9B1958Aa1e828AC24Afba4a551DF37d</p>` if the address didn't have a name.
