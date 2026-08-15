# Awesome CosmWasm with stars

Collection of awesome things related to
[CosmWasm smart contracts](https://www.cosmwasm.com).

Please read the [contribution guidelines](CONTRIBUTING.md) if you want to
contribute.

## Contents

* [General Resources](#general-resources)
* [CosmWasm Framework](#cosmwasm-framework)
* [Smart Contract Libraries](#smart-contract-libraries)
* [Smart Contracts](#smart-contracts)
  * [`cw-plus` Specifications and Examples](#cw-plus-specifications-and-examples)
  * [Other Contracts](#other-contracts)
* [External Projects](#external-projects)
* [Tooling](#tooling)
* [dApps](#dapps)

## General Resources

* [CosmWasm framework](https://github.com/CosmWasm/cosmwasm) ⭐ 1,147 | 🐛 42 | 🌐 Rust | 📅 2026-07-19 - a "core" CosmWasm
  repo. This includes the core Rust framework for writing a smart contract, a
  virtual machine that runs smart contracts and is embedded in any chain running
  them, the IDL format for describing the interface of a smart contract, and
  more! A few of these are commonly dependencies of smart contracts.
* [CosmWasm template](https://github.com/CosmWasm/cw-template) ⭐ 297 | 🐛 7 | 🌐 Rust | 📅 2025-01-16 - a template for
  getting an empty smart contract up and running quickly. Instructions included!
* [The CosmWasm book](https://book.cosmwasm.com/) - a step-by-step guide to
  writing CosmWasm smart contracts.
* [AREA-52](https://area-52.io/) - an interactive tutorial to learn CosmWasm smart contracts.

## CosmWasm Framework

* [cosmwasm-std](https://crates.io/crates/cosmwasm-std)
  ([repo](https://github.com/CosmWasm/cosmwasm/tree/master/packages/std) ⭐ 1,147 | 🐛 42 | 🌐 Rust | 📅 2026-07-19): The
  standard library for building CosmWasm smart contracts. Code in this package
  is compiled into the smart contract.
* [cosmwasm-schema](https://crates.io/crates/cosmwasm-schema)
  ([repo](https://github.com/CosmWasm/cosmwasm/tree/master/packages/schema) ⭐ 1,147 | 🐛 42 | 🌐 Rust | 📅 2026-07-19): A
  dependency for CosmWasm contracts to generate the IDL (interface description)
  files. These are consumed e.g. by
  [`ts-codegen`](https://github.com/CosmWasm/ts-codegen) ⭐ 126 | 🐛 50 | 🌐 TypeScript | 📅 2026-05-09 to automagically get a
  *TypeScript* client for your contract.
* [cw-multi-test](https://crates.io/crates/cw-multi-test)
  ([repo](https://github.com/CosmWasm/cw-multi-test) ⭐ 56 | 🐛 10 | 🌐 Rust | 📅 2026-02-19):
* [cw-storage-plus](https://crates.io/crates/cw-storage-plus)
  ([repo](https://github.com/CosmWasm/cw-storage-plus) ⭐ 51 | 🐛 28 | 🌐 Rust | 📅 2026-02-23): Helper methods to
  reduce boilerplate for storing data types. Easier and more secure persistence
  layer.

## Smart Contract Libraries

* [cw-coins](https://crates.io/crates/cw-coins)
  ([repo](https://github.com/steak-enjoyers/cw-plus-plus) ⚠️ Archived): A helper for
  managing multiple coins in a smart contract.
* [cw-item-set](https://crates.io/crates/cw-item-set)
  ([repo](https://github.com/steak-enjoyers/cw-plus-plus) ⚠️ Archived): A `HashSet`
  equivalent (set of unique items) that can be stored in smart contract storage.
* [cw-utils](https://crates.io/crates/cw-utils)
  ([repo](https://github.com/CosmWasm/cw-utils) ⭐ 20 | 🐛 9 | 🌐 Rust | 📅 2026-01-13): A collection of (somewhat
  random) helpers we found useful when developing `cw-plus` contracts and specs.
  Available as a library at crates.io!

## Smart Contracts

Before you create a PR to add your contract here, read the
[publishing guidelines](https://github.com/confio/cosmwasm-template/blob/master/Publishing.md) ⭐ 297 | 🐛 7 | 🌐 Rust | 📅 2025-01-16
and make sure you complete them all, specifically adding an OSI-approved license
and checking in valid artifacts for the build (`contract.wasm`,
`schema/*.json`).

We do validate the artifacts and perform a basic code review of contracts
included in this list. However, nothing terribly comprehensive and inclusion
here should not be taken in lieu of a proper audit. We do provide some
guidelines on
[sharing code reviews in a decentralized manner](https://github.com/confio/cosmwasm-template/blob/master/Importing.md) ⭐ 297 | 🐛 7 | 🌐 Rust | 📅 2025-01-16
which can be used as the basis for a peer-reviewed audit.

### `cw-plus` Specifications and Examples

[The `cw-plus` repo](https://github.com/CosmWasm/cosmwasm-plus) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26 houses both
protocol specifications and their reference implementations. These
implementations are meant both as examples of production-ready contracts and
pieces you might like to use in your project as they are.

#### Specifications

* [cw1](https://github.com/CosmWasm/cosmwasm-plus/tree/master/packages/cw1) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26 -
  proxy contracts that are meant to forward a message (probably after checking
  the sender against some form of access control), this time with the contract
  as the sender.
* [cw2](https://github.com/CosmWasm/cw-plus/tree/main/packages/cw2) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26 - contract
  metadata (name and version) that can be inspected directly, without querying
  the contract.
* [cw3](https://github.com/CosmWasm/cosmwasm-plus/blob/master/packages/cw4/README.md) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26 -
  multisig and voting.
* [cw4](https://github.com/CosmWasm/cosmwasm-plus/blob/master/packages/cw4/README.md) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26 -
  group membership management with weights.
* [cw20](https://github.com/CosmWasm/cosmwasm-plus/tree/master/packages/cw20) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26 -
  fungible token.

#### Reference implementations

* [cw1-whitelist](https://github.com/CosmWasm/cosmwasm-plus/tree/master/contracts/cw1-whitelist) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26
  by [ethanfrey](https://github.com/ethanfrey): This may be the simplest
  implementation of
  [cw1](https://github.com/CosmWasm/cosmwasm-plus/tree/master/packages/cw1) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26, a
  whitelist of addresses. It contains a set of admins that are defined upon
  creation. Any of those admins may Execute any message via the contract, per
  the [CW1](https://github.com/CosmWasm/cosmwasm-plus/tree/master/packages/cw1) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26
  spec.
* [cw1-subkeys](https://github.com/CosmWasm/cosmwasm-plus/tree/master/contracts/cw1-subkeys) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26
  by [ethanfrey](https://github.com/ethanfrey): This builds on cw1-whitelist to
  provide the first non-trivial solution. It still works like cw1-whitelist with
  a set of admins (typically 1) which have full control of the account. However,
  you can then grant a number of accounts allowances to send native tokens from
  this account.
* [cw3-fixed-multisig](https://github.com/CosmWasm/cosmwasm-plus/tree/master/contracts/cw3-fixed-multisig) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26:
  This is a simple implementation of the
  [cw3 spec](https://github.com/CosmWasm/cosmwasm-plus/blob/master/packages/cw4/README.md) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26.
  It is a multisig with a fixed set of addresses created upon initialization.
  Each address may have the same weight (K of N) or some may have extra voting
  power.
* [cw3-flex-multisig](https://github.com/CosmWasm/cosmwasm-plus/tree/master/contracts/cw3-flex-multisig) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26:
  This builds on cw3-fixed-multisig with a more powerful implementation of the
  cw3 spec. It is a multisig contract that is backed by a
  [cw4](https://github.com/CosmWasm/cosmwasm-plus/tree/master/packages/cw4) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26
  (group) contract, which independently maintains the voter set.
* [cw4-group](https://github.com/CosmWasm/cosmwasm-plus/tree/master/contracts/cw4-group) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26:
  This is a basic implementation of the
  [cw4 spec](https://github.com/CosmWasm/cosmwasm-plus/blob/master/packages/cw4/README.md) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26.
  It fulfills all elements of the spec, including the raw query lookups, and it
  designed to be used as a backing storage for cw3 compliant contracts.
* [cw4-stake](https://github.com/CosmWasm/cosmwasm-plus/tree/master/contracts/cw4-stake) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26:
  This is a second implementation of the
  [cw4 spec](https://github.com/CosmWasm/cosmwasm-plus/blob/master/packages/cw4/README.md) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26.
  It fulfills all elements of the spec, including the raw query lookups, and it
  is designed to be used as a backing storage for cw3 compliant contracts.
* [cw20-base](https://github.com/CosmWasm/cosmwasm-plus/tree/master/contracts/cw20-base) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26
  by [ethanfrey](https://github.com/ethanfrey): Basic implementation of a
  [cw20](https://github.com/CosmWasm/cosmwasm-plus/tree/master/packages/cw20) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26
  contract. It implements the
  [cw20](https://github.com/CosmWasm/cosmwasm-plus/blob/master/packages/cw20/README.md) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26
  spec and is designed to be deloyed as is, or imported into other contracts to
  easily build cw20-compatible tokens with custom logic.

### Other Contracts

These contracts demonstrate best practices and learning references. Please do
not use them in production as is. You are welcome to fork them, and
independently review, refine and audit them, using them as a basis for your
protocol. Or just as inspiration

* [cw-nfts](https://github.com/CosmWasm/cw-nfts) ⭐ 201 | 🐛 28 | 🌐 Rust | 📅 2026-04-01 - non-fungible tokens. Official
  repository for all work on NFT standards and reference contracts. This is
  where the
  [`cw721 spec`](https://github.com/CosmWasm/cw-nfts/tree/main/packages/cw721) ⭐ 201 | 🐛 28 | 🌐 Rust | 📅 2026-04-01
  lives.
* [cw-tokens](https://github.com/CosmWasm/cw-tokens) ⚠️ Archived - a few other
  [cw20](https://github.com/CosmWasm/cosmwasm-plus/tree/master/packages/cw20) ⭐ 527 | 🐛 23 | 🌐 Rust | 📅 2026-06-26
  (fungible token) contracts.

## External Projects

These projects/contracts are developed and maintained by CosmWasm community.

* [DA0-DA0/dao-contracts](https://github.com/DA0-DA0/dao-contracts) ⭐ 218 | 🐛 78 | 🌐 Rust | 📅 2026-06-28 - DAO DAO is
  the leading software to build your own DAO on CosmWasm chains, quickly
  surpassing Aragon in functionality
* [astroport-fi/astroport-core](https://github.com/astroport-fi/astroport-core) ⭐ 170 | 🐛 3 | 🌐 Rust | 📅 2026-06-09 - Astroport is
  a multi pool type automated market-maker (AMM) protocol, it is one of the leading DEX on Terra.
* [AbstractSDK/abstract](https://github.com/AbstractSDK/abstract) ⭐ 82 | 🐛 9 | 🌐 Rust | 📅 2026-03-05 - Abstract is
  a development platform with a focus on code reusability and application sovereignty.
* [public-awesome/launchpad](https://github.com/public-awesome/launchpad) ⭐ 81 | 🐛 37 | 🌐 Rust | 📅 2026-07-24 -
  Stargaze provides contracts to easily create and manage new NFT collections.
* [srdtrk/cw-ica-controller](https://github.com/srdtrk/cw-ica-controller) ⭐ 43 | 🐛 5 | 🌐 Go | 📅 2024-10-27 -
  A controller contract for the Interchain Accounts
  ([ICS-27](https://github.com/cosmos/ibc/blob/main/spec/app/ics-027-interchain-accounts/README.md) ⭐ 1,017 | 🐛 31 | 🌐 Go | 📅 2026-08-15)
  spec. It allows users to create and manage interchain accounts on host chains that support the golang
  implementation of ICS-27.
* [mars-protocol/v1-core](https://github.com/mars-protocol/v1-core) - Delphi's
  "Mars Protocol" is the leading lending protocol on Terra, Osmosis, and soon launching on Neutron.
* [CronCats/cw-croncat](https://github.com/CronCats/cw-croncat) - Croncat provides a general purpose,
  fully autonomous network that enables scheduled function calls for blockchain contract execution.
  It allows any application to schedule logic to get executed in the future, once or many times,
  triggered by an approved “agent,” in an economically stable format.

## Tooling

* [cosmology-tech/create-cosmos-app](https://github.com/cosmology-tech/create-cosmos-app) ⭐ 167 | 🐛 40 | 🌐 TypeScript | 📅 2025-12-11 -
  set up a modern Cosmos app with one command, ready to be iterated on.
* [cosmwasm/rust-optimizer](https://github.com/CosmWasm/rust-optimizer) ⭐ 146 | 🐛 11 | 🌐 Rust | 📅 2025-06-26 - This is
  a Docker build with a locked set of dependencies to produce reproducible
  builds of cosmwasm smart contracts. It also does heavy optimization on the
  build size, using binary stripping and `wasm-opt`.
* [cosmwasm/ts-codegen](https://github.com/CosmWasm/ts-codegen) ⭐ 126 | 🐛 50 | 🌐 TypeScript | 📅 2026-05-09 - Convert your CosmWasm smart contracts into dev-friendly TypeScript classes so you can focus on shipping code.
* [beaker](https://github.com/osmosis-labs/beaker) ⭐ 106 | 🐛 34 | 🌐 Rust | 📅 2024-01-22 - A toolkit that simplifies interactions with CosmWasm smart contracts which offers scaffolding, deployment, upgrades, execution, querying, an interactive console, and task scripting capabilities.
* [cw-orchestrator](https://github.com/AbstractSDK/cw-orchestrator) ⭐ 80 | 🐛 19 | 🌐 Rust | 📅 2026-03-05 - A Rust-oriented CosmWasm scripting library that features a clean and unified syntax for interacting
  with contracts in any environment.
* [mandrean/cw-optimizoor](https://github.com/mandrean/cw-optimizoor) ⭐ 48 | 🐛 8 | 🌐 Rust | 📅 2026-03-22 - A very
  fast alternative to `rust-optimizer` for local development and testing.
  Written in Rust, no dependency on Docker.
* [Terran-One/cosmwasm-vm-js](https://github.com/terran-one/cosmwasm-vm-js) ⭐ 44 | 🐛 2 | 🌐 TypeScript | 📅 2023-01-09 - A JavaScript runtime for running CosmWasm contracts in Node.js or the browser.
* [cosmwasm devtools](https://cosmwasm.tools/)
  ([repo](https://github.com/aswever/cosmwasm-devtools) ⭐ 31 | 🐛 16 | 🌐 TypeScript | 📅 2024-05-07) -  A web-based console
  for interacting with CosmWasm smart contracts deployed locally or remotely.
  Can use Keplr account or generate new addresses as needed.
* [srdtrk/go-codegen](https://github.com/srdtrk/go-codegen) ⭐ 25 | 🐛 9 | 🌐 Go | 📅 2024-07-12 - A Go code generator for CosmWasm contracts. The quickest way to generate Go code for your CosmWasm smart contracts.
* [Cosmwasm Studio](https://github.com/oraichain/smart-studio) ⭐ 12 | 🐛 1 | 🌐 Rust | 📅 2023-12-07 - Monaco IDE that supports CosmWasm. It allows developers to code, build smart contracts and execute functions through a simulation. It supports its own rust-analyzer in Web Assembly so developers can code it the same as local VS Code.
* [cosmwasm-tools](https://github.com/oraichain/cosmwasm-tools) ⭐ 11 | 🐛 2 | 🌐 TypeScript | 📅 2024-11-12 - A super
  fast and cross-platform alternative to `rust-optimizer` that produces optimized wasm files.
  Written in Typescript, supporting watch mode, parallel builds, and ts-codegen sharing common dependencies.
* [CWSimulate](https://cwsimulate.terran.one) - An online playground / simulation environment for interacting with CosmWasm contract binaries without a blockchain. Can be used for execution visualization / interactive debugging with time-traveling navigation.
* [cosmy-wasmy](https://marketplace.visualstudio.com/items?itemName=spoorthi.cosmy-wasmy) - A vscode extension to interact with CosmWasm smart contracts on devnet or testnet chains. Allows to query, execute, upload contracts as well as provide code completion snippets.
* [cosmwander](https://cosmwander.xyz) - Explore on-chain cosmwasm contracts and discover their message scheme.
* [WELLDONE Code](https://docs.welldonestudio.io/code/getting-started) - Remix IDE plugin that supports CosmWasm. It is a web-based IDE that allows developers to deploy smart contracts and execute functions through a browser wallet. It supports its own compiler server, so developers do not need to set up a development environment.

## dApps

Looking for dApps to feature. See
[#19](https://github.com/CosmWasm/cw-awesome/issues/19) ⭐ 272 | 🐛 6 | 📅 2025-03-03.

***

> _Enhansomed by [enhansome](https://github.com/enhansome) on 2026-08-15._
