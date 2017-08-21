# Ethereum

> Beyond financial applications, any environments where trust, security, and permanence are important – for instance, asset-registries, voting, governance, and the internet of things – could be massively impacted by the Ethereum platform.

- Ethereum [yellow paper](http://yellowpaper.io)

## dApps (distributed Apps)

> [dApps Catalog](https://dapps.ethercasts.com/)


- [Vega fund](http://www.vega.fund/)
- [Nanome & Matryx](http://nanome.ai/) 3D assets
- [Ethlance](https://ethlance.com/) freelance network
- [swarm hash](http://swarm-gateways.net/bzz:/theswarm.eth/) & [Swarm hash wiki](https://github.com/ethereum/wiki/wiki/Swarm-Hash) ENS like DNS 
- [ENS domains](https://ens.domains/)
- [IPFS](https://ipfs.io/) peer to peer IP
- [git mango](https://github.com/axic/mango) decentralized git
- [Dharma Loans](https://dharma.io)

## Tools

- [Meta Mask](https://metamask.io/) Chrome Extension
- [My Ether Wallet](https://www.myetherwallet.com)
- [EPM](https://www.ethpm.com/registry) Ethereum Package Manager
- [ETH stats](https://ethstats.net/)
- [ETH Intelligence API](https://github.com/cubedro/eth-net-intelligence-api)

## Platforms

- [Legalease](https://legalese.com/) legal contracts ala blockchain

## Concepts

### Types of accounts

- There are two types of accounts which share the same address space.
- Every account has a persistent key-value store mapping 256-bit words to 256-bit words called **storage**.
- every account has a balance in Ether (in “Wei” to be exact) 

#### Externally Owned Accounts (EOAs)

- are controlled by private keys by humans
- The address of an external account is determined from the public key 


#### Contract Accounts

 - which are controlled by their contract code and can only be “activated” by an EOA
- the address of a contract is determined when it is created
- the address is derived from the creator address and the number of transactions sent from that address (the so-called “nonce”).



### Smart contracts

- “smart contracts” refers to code in a Contract Account – programs that execute when a transaction is sent to that account. Users can create new contracts by deploying code to the blockchain.

### Transactions

> Like in Bitcoin, users must pay small transaction fees to the network. This protects the Ethereum blockchain from frivolous or malicious computational tasks, like DDoS attacks or infinite loops. The sender of a transaction must pay for each step of the “program” they activated, including computation and memory storage. These fees are paid in amounts of Ethereum’s native value-token, **ether**.

- transactions are messages sent from account to account
- the messages can contain binary data (payload) and ether

### Gas

- Gas is the cost of processing each transaction in a contract
- the sending account has to pay the gas

### Mining

Bitcoin mining model encourages specialized equipment to solve the blockchain. Ethereum changed the model to a memory-hard computational problem so the general computer is the ideal machine to solve ethereums blocks. That way it guarantees the evenly distributed descentralization, instead of having a few mega miners.


## Security in dApps

- [Smart Contracts Best Practices](https://github.com/ConsenSys/smart-contract-best-practices)

## Dev tools

- [web3js](https://github.com/ethereum/web3.js/) to query the storage
- [Truffle Boxes](http://truffleframework.com/boxes/) boilerplate catalog 
- [Eth alarm clock](http://www.ethereum-alarm-clock.com/)
- [remix](https://remix.ethereum.org/#version=soljson-v0.4.15+commit.bbb8e64f.js)
- [dAppathon dockerized ide](https://github.com/rckprtrdv/dockerized-eth-ide)
- [ipfs node api](https://github.com/ipfs/js-ipfs-api)

## Learning resources

- [01-noob](http://consensys.github.io/developers/articles/101-noob-intro/)
- [Redit dev resources](https://www.reddit.com/r/ethdev/comments/5s9avy/the_big_ethereum_development_resources_list/)
- [create a cli with truffle](http://truffleframework.com/tutorials/creating-a-cli-with-truffle-3)