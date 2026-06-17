# Satya Kwok

Rust infrastructure engineer — Ethereum/EVM execution, consensus, and node systems.
I work upstream on the Rust Ethereum stack and run a production Rust L1.

[satyakwok.dev](https://satyakwok.dev) · [X @blackskyiee](https://x.com/blackskyiee) · [Telegram @Evtraf](https://t.me/Evtraf) · satyakwok88@gmail.com

### Focus

EVM execution and RPC correctness · consensus / BFT systems · node and validator
infrastructure · Ethereum tooling (alloy, Foundry, revm) · reliability primitives for
real services.

### Upstream contributions

Selected merged work across the Rust/Ethereum infrastructure stack:

- **alloy** — [core#1122](https://github.com/alloy-rs/core/pull/1122) validate event
  topic count before decoding the dyn-ABI log body ·
  [core#1124](https://github.com/alloy-rs/core/pull/1124) propagate `extra_derives` to
  generated `sol!` call enums ·
  [alloy#3976](https://github.com/alloy-rs/alloy/pull/3976) saturate out-of-`u64`
  `baseFeePerGas` on header deserialization.
- **CometBFT** — [#5890](https://github.com/cometbft/cometbft/pull/5890) proposer
  self-verifies its vote extension before broadcast ·
  [#5861](https://github.com/cometbft/cometbft/pull/5861) reject out-of-range float
  RPC IDs · [#5857](https://github.com/cometbft/cometbft/pull/5857) `LoadValidatorsFast`
  on the replay path.
- **Foundry** — [foundry-core#91](https://github.com/foundry-rs/foundry-core/pull/91)
  preserve base paths in generated block-explorer URLs.

Active in-review PRs across **Reth**, **Foundry**, **Alloy**, **Lighthouse**, **Agave**,
and **candle**. Full index: **[oss-contributions](https://github.com/satyakwok/oss-contributions)**.

### Sentrix Chain

[**Sentrix Chain**](https://github.com/sentrix-labs/sentrix) — a Rust EVM Layer-1 I
build and operate. Native Rust node, EVM execution via
[`revm`](https://github.com/bluealloy/revm), BFT consensus, and a full stack: RPC,
explorer, faucet, wallet, and validator tooling. Mainnet and a public testnet (chain
IDs `7119` / `7120`), registered in [viem](https://github.com/wevm/viem/pull/4603),
[ethereum-lists/chains](https://github.com/ethereum-lists/chains/pull/8266), and
[chainlist](https://github.com/DefiLlama/chainlist/pull/2707). I run the validators and
maintain the network day to day.

### Other projects

- [**reliakit**](https://github.com/satyakwok/reliakit) — zero-dependency Rust
  reliability toolkit (`no_std`-friendly, no `unsafe`): retry/backoff, timeout, rate
  limiting, circuit breaker, bounded collections, secret redaction, deterministic
  encoding, health checks. [crates.io](https://crates.io/crates/reliakit) ·
  [docs.rs](https://docs.rs/reliakit)
- [**evm-rust-lab**](https://github.com/satyakwok/evm-rust-lab) — practical Rust
  examples for Ethereum/EVM workflows with Alloy, REVM, and real RPC.
- [**solana-infra-doctor**](https://github.com/satyakwok/solana-infra-doctor) — Solana
  RPC readiness diagnostics and redaction-safe reporting in Rust.

### Stack

Rust · Ethereum / EVM · revm · alloy · Foundry · CometBFT · libp2p · Solidity ·
TypeScript · Docker · Linux.

### Open to

Remote Rust infrastructure roles — execution-layer and EVM systems, RPC correctness,
node/validator infrastructure, and consensus / BFT engineering.
