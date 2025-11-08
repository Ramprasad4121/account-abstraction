# Account Abstraction

<br/>
<p align="center">
<img src="./img/ethereum/account-abstraction-again.png" width="500" alt="aa">
</p>
<br/>



## What is Account Abstraction?

EoAs are now smart contracts. That's all account abstraction is.

But what does that mean?

Right now, every single transaction in web3 stems from a single private key. 

> account abstraction means that not only the execution of a transaction can be arbitrarily complex computation logic as specified by the EVM, but also the authorization logic.

- [Vitalik Buterin](https://ethereum-magicians.org/t/implementing-account-abstraction-as-part-of-eth1-x/4020)
- [EntryPoint Contract v0.6](https://etherscan.io/address/0x5ff137d4b0fdcd49dca30c7cf57e578a026d2789)
- [EntryPoint Contract v0.7](https://etherscan.io/address/0x0000000071727De22E5E9d8BAf0edAc6f37da032)
- [zkSync AA Transaction Flow](https://docs.zksync.io/build/developer-reference/account-abstraction.html#the-transaction-flow)

## What's this repo show?

1. A minimal EVM "Smart Wallet" using alt-mempool AA
2. A minimal zkSync "Smart Wallet" using native AA
   1. [zkSync uses native AA, which is slightly different than ERC-4337](https://docs.zksync.io/build/developer-reference/account-abstraction.html#iaccount-interface)
 

# Getting Started 

## Requirements

- [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
  - You'll know you did it right if you can run `git --version` and you see a response like `git version x.x.x`
- [foundry](https://getfoundry.sh/)
  - You'll know you did it right if you can run `forge --version` and you see a response like `forge 0.2.0 (816e00b 2023-03-16T00:05:26.396218Z)`
- [foundry-zksync](https://github.com/matter-labs/foundry-zksync)
  - You'll know you did it right if you can run `forge-zksync --help` and you see `zksync` somewhere in the output

## Installation

```bash
git clone https://github.com/Ramprasad4121/account-abstraction.git
cd account-abstraction
make
```

# Quickstart 

## Vanilla Foundry

```bash
foundryup
make test
```

### Deploy - Arbitrum

```bash
make deployEth
```

### User operation - Arbitrum

```bash
make sendUserOp
```

## zkSync Foundry

```bash
foundryup-zksync
make zkbuild
make zktest
```

### Deploy - zkSync local network

#### Additional Requirements
- [npx & npm](https://docs.npmjs.com/cli/v10/commands/npm-install)
  - You'll know you did it right if you can run `npm --version` and you see a response like `7.24.0` and `npx --version` and you see a response like `8.1.0`.
- [yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable)
  - You'll know you did it right if you can run `yarn --version` and you see a response like `1.22.17`.
- [docker](https://docs.docker.com/engine/install/)
  - You'll know you did it right if you can run `docker --version` and you see a response like `Docker version 20.10.7, build f0df350`.
  - Then, you'll want the daemon running, you'll know it's running if you can run `docker --info` and in the output you'll see something like the following to know it's running:
```bash
Client:
 Context:    default
 Debug Mode: false
```

Install dependencies:
```bash
yarn
```

#### Setup - local node

```bash
# Select `in memory node` and nothing else
npx zksync-cli dev start
```

#### Deploy - local node

> [!IMPORTANT]  
> *Never* have a private key associated with real funds in plaintext. 

```bash
# Setup your .env file, see the .env.example for an example
make zkdeploy
```

> Note: Sending an account abstraction transaction doesn't work on the local network, because we don't have the system contracts setup on the local network. 

