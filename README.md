# Wild Explorer
A bitcoin block explorer built on top of my node_faker project

# What is this?
It's a block explorer, but instead of relying on a single node as a backend, it uses my [node_faker](https://github.com/supertestnet/node_faker) project. This means electrum relays are picked at random and data about the blockchain is sourced from them.

# How can I try it?
Just click here and follow the instructions: https://supertestnet.github.io/wild_explorer

# Video explainer
[![](https://supertestnet.github.io/wild_explorer/node_faker_and_wild_explorer.png)](https://www.youtube.com/watch?v=QAc4L7tSZMs)

# Why did you make this?
First I made [node_faker](https://github.com/supertestnet/node_faker), which pretends to be a bitcoin node by emulating bitcoind's api, but getting the data from electrum servers. Then I tried various apps against it, among which were [LND](https://github.com/lightningnetwork/lnd) -- which worked, albeit slowly -- and [btc-rpc-explorer](https://github.com/janoside/btc-rpc-explorer) -- which did not work.

I'm not exactly sure why btc-rpc-explorer did not work, but instead of debugging it, I just decided to implement my own block explorer. Luckily, I already had one for [my testnet_generator project](https://github.com/supertestnet/testnet_generator), so I repurposed that to work with the "real" blockchain, after accounting for the limitations of node_faker's API. And voila! Wild Explorer was born.

# Why is it so slow?
Because its backend is a bitcoind emulator written in javascript, and such a tool is bonkers, and definitely NOT optimized for a job like running a block explorer. But it technically works! So I'm excited.
