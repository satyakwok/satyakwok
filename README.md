# Satya Kwok

[![X](https://img.shields.io/badge/X-@blackskyiee-000000?style=flat-square&logo=x&logoColor=white)](https://x.com/blackskyiee)
[![Telegram](https://img.shields.io/badge/Telegram-@Evtraf-26A5E4?style=flat-square&logo=telegram&logoColor=white)](https://t.me/Evtraf)
[![GitHub Sponsors](https://img.shields.io/badge/Sponsor-%E2%9D%A4-ea4aaa?style=flat-square&logo=githubsponsors&logoColor=white)](https://github.com/sponsors/satyakwok)

Rust developer working on open-source infrastructure: Ethereum/EVM tooling, consensus systems, and developer tools. I build in public.

I contribute upstream to Rust/Ethereum infrastructure — with merged PRs in **[alloy](https://github.com/alloy-rs)**, **[Foundry](https://github.com/foundry-rs)**, and **[CometBFT](https://github.com/cometbft/cometbft)** — and build **[Sentrix Chain](https://github.com/sentrix-labs/sentrix)**, a Rust-based EVM Layer-1 with a live testnet, plus **[reliakit](https://github.com/satyakwok/reliakit)**, a zero-dependency reliability toolkit published on [crates.io](https://crates.io/crates/reliakit).

### Focus

Rust infrastructure · Ethereum / EVM tooling · RPC correctness · consensus / BFT systems · developer tooling · node and validator operations · reliability primitives for real services.

### Merged upstream contributions

**Rust / Ethereum infrastructure**

- [alloy-rs/core#1122](https://github.com/alloy-rs/core/pull/1122) — validate event topic count before decoding the log body in dyn-ABI.
- [alloy-rs/core#1124](https://github.com/alloy-rs/core/pull/1124) — propagate `extra_derives` to generated function-call enums in the `sol!` macro.
- [alloy-rs/alloy#3976](https://github.com/alloy-rs/alloy/pull/3976) — saturate out-of-`u64` `baseFeePerGas` on Ethereum header deserialization.
- [foundry-rs/foundry-core#91](https://github.com/foundry-rs/foundry-core/pull/91) — preserve base paths in generated block-explorer URLs.

**Consensus / BFT**

- [cometbft/cometbft#5890](https://github.com/cometbft/cometbft/pull/5890) — have the proposer self-verify its own vote extension before proposing.
- [cometbft/cometbft#5861](https://github.com/cometbft/cometbft/pull/5861) — reject out-of-int-range float JSON-RPC request IDs.
- [cometbft/cometbft#5857](https://github.com/cometbft/cometbft/pull/5857) — add `LoadValidatorsFast` to skip redundant proposer recomputation.

**Developer tooling**

- [unhappychoice/splashboard#216](https://github.com/unhappychoice/splashboard/pull/216) — add a cache-management CLI (list, inspect, clear).

**Ecosystem integrations** (Sentrix Chain): [wevm/viem#4603](https://github.com/wevm/viem/pull/4603) · [ethereum-lists/chains#8266](https://github.com/ethereum-lists/chains/pull/8266) · [DefiLlama/chainlist#2707](https://github.com/DefiLlama/chainlist/pull/2707) · [DefiLlama/icons#2374](https://github.com/DefiLlama/icons/pull/2374)

### Open contributions under review

Active PRs across major Rust projects:

- [paradigmxyz/reth#25224](https://github.com/paradigmxyz/reth/pull/25224) — use the furthest-reached stage as the pipeline-consistency reference at node launch.
- [huggingface/candle#3624](https://github.com/huggingface/candle/pull/3624), [#3626](https://github.com/huggingface/candle/pull/3626) — Qwen3 batched causal mask; reject oversized pickle `Long1` (DoS guard).
- [sigp/lighthouse#9435](https://github.com/sigp/lighthouse/pull/9435) — Unix domain socket support for the beacon HTTP API.
- [anza-xyz/agave#13076](https://github.com/anza-xyz/agave/pull/13076) — surface rollback accounts in fees-only simulation results.
- [foundry-rs/foundry#15128](https://github.com/foundry-rs/foundry/pull/15128) — complete `eth_feeHistory` when the cache lags the chain head.
- [bevyengine/bevy#24593](https://github.com/bevyengine/bevy/pull/24593) — don't resurrect removed required components on `insert_if_new`.

### Projects

**[Sentrix Chain](https://github.com/sentrix-labs/sentrix)** — Rust-based EVM Layer-1 with a live testnet. Native Rust chain implementation, EVM execution via [`revm`](https://github.com/bluealloy/revm), and full RPC / explorer / faucet / wallet / validator / infra tooling, plus testnet operations and node maintenance.

**[reliakit](https://github.com/satyakwok/reliakit)** — small, zero-dependency reliability toolkit for Rust (`no_std`-friendly, no `unsafe`): validated primitives, secret redaction, bounded collections, deterministic encoding, retry/backoff, timeout, rate limiting, circuit breaker, and health checks. [crates.io](https://crates.io/crates/reliakit) · [docs.rs](https://docs.rs/reliakit)

**[evm-rust-lab](https://github.com/satyakwok/evm-rust-lab)** — practical Rust examples for Ethereum/EVM workflows using Alloy, REVM, and real RPC calls.

**[solana-infra-doctor](https://github.com/satyakwok/solana-infra-doctor)** — Solana RPC readiness diagnostics, comparison, WebSocket checks, and redaction-safe reporting in Rust.

### Stack

![Rust](https://img.shields.io/badge/Rust-000000?style=flat&logo=rust&logoColor=white)
![Ethereum](https://img.shields.io/badge/Ethereum-3C3C3D?style=flat&logo=ethereum&logoColor=white)
![Solidity](https://img.shields.io/badge/Solidity-363636?style=flat&logo=solidity&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)

Also: Alloy · REVM · Foundry · CometBFT · libp2p · RPC.

### Open to

Remote Rust infrastructure work — Ethereum/EVM and execution-layer systems, RPC correctness, node and validator infrastructure, consensus / BFT systems, developer tooling, and reliability-focused Rust libraries.

### Contact

[satyakwok.dev](https://satyakwok.dev) · [X @blackskyiee](https://x.com/blackskyiee) · [Telegram @Evtraf](https://t.me/Evtraf) · satyakwok88@gmail.com

### Support my work

If something I build is useful to you, you can support it: [GitHub Sponsors](https://github.com/sponsors/satyakwok) · [Saweria](https://saweria.co/satyakwok) (Indonesia).

<!-- sponsors --><!-- sponsors -->
