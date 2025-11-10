# Account Abstraction

<<<<<<< HEAD
=======
<!-- <div align="center">
  <a href="https://github.com/Ramprasad4121/account-abstraction">
    <img src="docs/images/aa-banner.png" alt="Account Abstraction Banner" width="600" height="300"> <!-- Add your banner image here -->
  </a>
</div> -->

<div align="center">
  Smart Wallets with Alt-Mempool & Native AA
  <br />
  <a href="#about"><strong>Explore the demo »</strong></a>
  <br />
  <br />
  <a href="https://github.com/Ramprasad4121/account-abstraction/issues/new?assignees=&labels=bug&template=01_BUG_REPORT.md&title=bug%3A+">Report a Bug</a>
  ·
  <a href="https://github.com/Ramprasad4121/account-abstraction/issues/new?assignees=&labels=enhancement&template=02_FEATURE_REQUEST.md&title=feat%3A+">Request a Feature</a>
  ·
  <a href="https://github.com/Ramprasad4121/account-abstraction/issues/new?assignees=&labels=question&template=04_SUPPORT_QUESTION.md&title=support%3A+">Ask a Question</a>
</div>

<div align="center">
<br />
>>>>>>> a08736c (updated readme.md)

[![Solidity](https://img.shields.io/badge/Solidity-^0.8.20-blue)](https://soliditylang.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-green)](LICENSE)

</div>

<details open="open">
<summary>Table of Contents</summary>

- [Account Abstraction](#account-abstraction)
  - [About](#about)
    - [Built With](#built-with)
  - [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
  - [Usage](#usage)
    - [EVM (Arbitrum)](#evm-arbitrum)
    - [zkSync Local](#zksync-local)
    - [Other](#other)
  - [Roadmap](#roadmap)
  - [Support](#support)
  - [Project Assistance](#project-assistance)
  - [Contributing](#contributing)
  - [Authors \& Contributors](#authors--contributors)
  - [Security](#security)
  - [License](#license)
  - [Acknowledgements](#acknowledgements)

</details>

---

## About

Demonstrates account abstraction by turning EOAs into smart wallets. Features minimal EVM implementation with alt-mempool AA and zkSync native AA via IAccount (differs from ERC-4337). Supports deployment to Arbitrum and zkSync local for testing user operations and simulations.

Why this? To illustrate AA differences across chains, enabling gasless txs, social recovery, and batching.

<!-- <details>
<summary>Screenshots</summary>
<br>

|                               EVM Deployment Console                               |                               zkSync Test Output                               |
| :-------------------------------------------------------------------: | :--------------------------------------------------------------------: |
| <img src="docs/images/deploy-eth.png" title="Arbitrum Deploy" width="100%"> | <img src="docs/images/zk-test.png" title="zkSync Tests" width="100%"> |

> Add screenshots of `make deployEth` and `make zktest`.

</details> -->

### Built With

- [Foundry](https://book.getfoundry.sh/) – EVM testing/deployment
- [foundry-zksync](https://github.com/zksync-toolchain/foundry-zksync) – zkSync tooling
- Solidity ^0.8.20
- [Make](https://www.gnu.org/software/make/) – Automation
- zkSync CLI, Docker – Local node

## Getting Started

### Prerequisites

- Git (`git --version`)
- Foundry (`curl -L https://foundry.paradigm.xyz | bash && foundryup`; `forge --version`)
- foundry-zksync (`curl -L https://github.com/zksync-toolchain/foundry-zksync/releases/latest/download/foundryup-init.sh | bash`; `foundryup-zksync`)
- npm/yarn (`npm --version`; `yarn --version`)
- Docker (`docker --version`; ensure daemon running)

### Installation

1. Clone:
   ```bash
   git clone https://github.com/Ramprasad4121/account-abstraction.git
   cd account-abstraction
   ```

2. Setup:
   ```bash
   forge build
   make
   ```

3. `.env` from `.env.example`: Add `PRIVATE_KEY` (test only; no real funds).

## Usage

### EVM (Arbitrum)

- Test: `make test`
- Deploy: `make deployEth`
- Send UserOp: `make sendUserOp`

### zkSync Local

1. Start node:
   ```bash
   yarn
   npx zksync-cli dev start  # Select in-memory node
   ```

2. Build/Test: `make zkbuild`; `make zktest`
3. Deploy: `make zkdeploy`  # Note: UserOps limited on local

### Other

- Format: `forge fmt`
- Clean: `make clean`

## Roadmap

[Open issues](https://github.com/Ramprasad4121/account-abstraction/issues).

- Enhancements: ERC-4337 full stack, paymasters
- Bugs: Vote with 👍

Future: Multi-chain AA, frontend integration.

## Support

- [Issues](https://github.com/Ramprasad4121/account-abstraction/issues/new?assignees=&labels=question&template=04_SUPPORT_QUESTION.md&title=support%3A+)
- [X](https://x.com/0xramprasad)

## Project Assistance

- ⭐ [Star](https://github.com/Ramprasad4121/account-abstraction)
- Tweet: "#AccountAbstraction #zkSync"
- Blog: [Dev.to](https://dev.to/)

## Contributing

Fork, branch (`git checkout -b feature/xyz`), commit, PR. See [CONTRIBUTING.md](docs/CONTRIBUTING.md).

## Authors & Contributors

- [Ramprasad4121](https://github.com/Ramprasad4121)

[Contributors](https://github.com/Ramprasad4121/account-abstraction/contributors)

## Security

Review before prod; test keys only. Report: [SECURITY.md](docs/SECURITY.md). "As is."

## License

MIT License. See [LICENSE](LICENSE).

## Acknowledgements

- [zkSync](https://zksync.io/) – Native AA
- [Foundry](https://getfoundry.sh/) – Tooling
- Ethereum/AA community docs.