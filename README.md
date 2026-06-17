# Satya Kwok

Rust infrastructure engineer focused on blockchain systems — EVM/RPC tooling,
validator/node infrastructure, and reliability-focused developer tools.
Indonesia (UTC+7) · open to remote.

[![Portfolio](https://img.shields.io/badge/Portfolio-satyakwok.dev-1f6feb?style=flat-square&logo=safari&logoColor=white)](https://satyakwok.dev)
[![GitHub](https://img.shields.io/badge/GitHub-satyakwok-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/satyakwok)
[![X](https://img.shields.io/badge/X-@blackskyiee-000000?style=flat-square&logo=x&logoColor=white)](https://x.com/blackskyiee)

## Focus areas

- Rust backend / infrastructure engineering
- Ethereum / EVM tooling and RPC correctness
- Validator / node infrastructure and operations
- Distributed-systems reliability
- Open-source blockchain infrastructure

## Selected work

- **[Sentrix Chain](https://github.com/sentrix-labs/sentrix)** — solo-built open-source EVM-compatible Layer-1 in Rust. 21-crate workspace; custom Tendermint-style 3-phase BFT, libp2p networking, MDBX storage, `revm` execution. Runs on a small self-operated validator set (4 validators — engineering proof, not a claim of broad adoption).
- **[reliakit](https://github.com/satyakwok/reliakit)** — zero-dependency, `no_std`-friendly Rust reliability toolkit (retry/backoff, circuit breaker, rate limiter, bounded collections, redacted secrets, canonical codecs). 17 crates on crates.io, `#![forbid(unsafe_code)]`.
- **[solana-infra-doctor](https://github.com/satyakwok/solana-infra-doctor)** — Rust CLI for Solana RPC production-readiness diagnostics: endpoint comparison, WebSocket + Yellowstone gRPC readiness, redaction-safe reports. On crates.io + GitHub Marketplace.
- **[evm-rust-lab](https://github.com/satyakwok/evm-rust-lab)** — practical Rust EVM examples (Alloy + revm) and an `evm-lab` RPC CLI.
- **[oss-contributions](https://github.com/satyakwok/oss-contributions)** — case-study index of upstream contributions across the Rust/blockchain infrastructure stack.

## Open-source contributions

Selected merged upstream work (full case studies in
[oss-contributions](https://github.com/satyakwok/oss-contributions)):

- **Alloy** — Ethereum header deserialization fix for out-of-`u64` `baseFeePerGas`; dyn-ABI event-topic validation; `sol!` codegen `extra_derives` propagation.
- **Foundry** — preserve base paths in generated block-explorer URLs.
- **CometBFT** — proposer self-verifies its vote extension before broadcast; `LoadValidatorsFast`; JSON-RPC float-id range validation.

While building Sentrix I send fixes upstream to the Rust + blockchain stack it
depends on. Each patch is regression-tested and follows host-project conventions.

<a href="https://github.com/lowlighter/metrics">
  <img src="./github-metrics.svg" alt="GitHub metrics — generated daily by lowlighter/metrics" />
</a>

### Stack

![Rust](https://img.shields.io/badge/Rust-000000?style=flat&logo=rust&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Solidity](https://img.shields.io/badge/Solidity-363636?style=flat&logo=solidity&logoColor=white)
![Foundry](https://img.shields.io/badge/Foundry-FFD700?style=flat&logo=ethereum&logoColor=black)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
