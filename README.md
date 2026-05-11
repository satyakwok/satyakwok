# Satya Kwok

[![X](https://img.shields.io/badge/X-@blackskyiee-000000?style=flat-square&logo=x&logoColor=white)](https://x.com/blackskyiee)
[![Telegram](https://img.shields.io/badge/Telegram-@Evtraf-26A5E4?style=flat-square&logo=telegram&logoColor=white)](https://t.me/Evtraf)
[![Website](https://img.shields.io/badge/Website-sentrixchain.com-1f6feb?style=flat-square&logo=safari&logoColor=white)](https://sentrixchain.com)
[![Sponsor](https://img.shields.io/badge/Sponsor-crypto--only-2ea44f?style=flat-square&logo=ethereum&logoColor=white)](#sponsor)

Independent protocol engineer. Indonesia (UTC+7) · open to remote.

I solo-built **[Sentrix Chain](https://github.com/sentrix-labs/sentrix)** — a Rust EVM-compatible Layer-1 — and the surrounding product stack: explorer, indexer, SDKs, DEX UI, mobile wallet, canonical contracts. Mainnet on 4 validators, custom BFT consensus, libp2p networking, MDBX storage, `revm`-based execution.

Day-to-day I move between the consensus loop, the JSON-RPC / gRPC surface, the indexer, the explorer, and the contract suite. Patches I send upstream are small, regression-tested, and aimed at the Rust blockchain tooling I depend on day-to-day.

## Sentrix Chain

[`sentrix-labs/sentrix`](https://github.com/sentrix-labs/sentrix) · Rust · BUSL-1.1 · 16-crate workspace, ~58 k lines · chainId 7119 mainnet, 7120 testnet · 4-of-4 validators · [rpc.sentrixchain.com](https://rpc.sentrixchain.com) · [grpc.sentrixchain.com](https://grpc.sentrixchain.com) · [scan.sentrixchain.com](https://scan.sentrixchain.com)

| Crate | Scope |
|---|---|
| [`sentrix-bft`](https://github.com/sentrix-labs/sentrix/tree/main/crates/sentrix-bft) | Tendermint-style 3-phase BFT (Proposal / Prevote / Precommit, 2f+1 quorum, LastSignBytes equivocation guard). Proposer-prevote piggy-back variant saves 1 RTT per round; testnet steady state ~0.3-0.4 s/blk. |
| [`sentrix-evm`](https://github.com/sentrix-labs/sentrix/tree/main/crates/sentrix-evm) | `revm` 37 wrapper. Custom gas accounting, EIP-1559 fee market, 50/50 validator-burn split, native + EVM dual-layer. |
| [`sentrix-storage`](https://github.com/sentrix-labs/sentrix/tree/main/crates/sentrix-storage) + [`sentrix-trie`](https://github.com/sentrix-labs/sentrix/tree/main/crates/sentrix-trie) | MDBX-backed binary sparse Merkle (256-level). State root in block hash beyond activation height; cross-validator `STATE-FP` trace for divergence diagnosis. |
| [`sentrix-network`](https://github.com/sentrix-labs/sentrix/tree/main/crates/sentrix-network) | libp2p, gossipsub for BFT, kad + identify for discovery. Bounded-channel `try_send` + drop counters after a silent-thread-death class surfaced at h ~ 1.39 M. |
| [`sentrix-staking`](https://github.com/sentrix-labs/sentrix/tree/main/crates/sentrix-staking) | DPoS, epoch boundaries, LivenessTracker, jail/unjail, AddSelfStake self-recovery. BTC-parity halving curve, 315 M SRX cap post tokenomics-v2 fork. |

Production bug closures, each pinned by a regression test that fails on the prior commit: LivenessTracker non-determinism (v2.1.79), BFT channel saturation (v2.1.65 / v2.1.88), state-apply HashMap iteration order (v2.1.87), LastSignBytes same-bytes-replay (PR #548), proposer-prevote sign-order trap (PR #574).

## Ecosystem ([@Sentriscloud](https://github.com/Sentriscloud) + [@sentrix-labs](https://github.com/sentrix-labs))

| Repo | Stack | Purpose |
|---|---|---|
| [`frontend`](https://github.com/Sentriscloud/frontend) | Next.js + TypeScript | Single deployment hosting block explorer, faucet, DEX UI, CoinBlast launchpad, airdrop claim, marketing landing. Privy auth + Solux fallback. |
| [`sentrix-explorer-v2`](https://github.com/Sentriscloud/sentrix-explorer-v2) | Rust + Leptos + WASM | Standalone block explorer compiled to WASM, gRPC-Web client for direct chain reads. |
| [`indexer-rs`](https://github.com/Sentriscloud/indexer-rs) | Rust, Postgres, Redis, ClickHouse | Block / tx / log / token-transfer indexer. Etherscan-API-compatible REST surface. |
| [`solux`](https://github.com/Sentriscloud/solux) | Flutter / Dart | Self-custody mobile wallet. EVM signing, postMessage IPC for dApp approval. iOS + Android. |
| [`sdk-rs`](https://github.com/Sentriscloud/sdk-rs) + [`sdk-ts`](https://github.com/Sentriscloud/sdk-ts) | Rust (`alloy` + `tonic`) + TypeScript | Official SDKs. Typed EVM + native REST + gRPC + secp256k1 signing; TS mirrors with WebSocket helpers. |
| [`sentrix-grpc-wasm`](https://github.com/Sentriscloud/sentrix-grpc-wasm) | Rust + WASM | gRPC-Web client extracted as a reusable crate for any browser dApp. |
| [`canonical-contracts`](https://github.com/sentrix-labs/canonical-contracts) | Solidity + Foundry | WSRX wrapper, Multicall3, SentrixSafe multisig, TokenFactory, MerkleAirdrop, CoinBlast bonding-curve, StrategicReserveTimelock. Foundry-tested, Sourcify-verified. |
| [`sentrix-dex`](https://github.com/sentrix-labs/sentrix-dex) | Solidity | UniswapV2-fork AMM, live at [dex.sentrixchain.com](https://dex.sentrixchain.com). |

## Upstream contributions

Open PRs against external projects (links resolve to the patches):

| Project | PR | Subject |
|---|---|---|
| [`paradigmxyz/reth`](https://github.com/paradigmxyz/reth) | [#24136](https://github.com/paradigmxyz/reth/pull/24136) | `fix(engine)`: trigger backfill when canonical header is ahead of execution (#23234) |
| [`cometbft/cometbft`](https://github.com/cometbft/cometbft) | [#5857](https://github.com/cometbft/cometbft/pull/5857) | `consensus`: `LoadValidatorsFast` — 903× faster `ExecCommitBlock` proposer-priority advance (#1693) |
| [`cometbft/cometbft`](https://github.com/cometbft/cometbft) | [#5861](https://github.com/cometbft/cometbft/pull/5861) | `rpc/jsonrpc`: reject out-of-int-range float IDs in `idFromInterface` (#5846) |
| [`cometbft/cometbft`](https://github.com/cometbft/cometbft) | [#5864](https://github.com/cometbft/cometbft/pull/5864) | `consensus`: proposer self-verifies its own vote extension before broadcast (#5204) |
| [`cometbft/tendermint-rs`](https://github.com/cometbft/tendermint-rs) | [#1518](https://github.com/cometbft/tendermint-rs/pull/1518) | `impl PartialEq<{u8,u16,u32,u64}> for block::Height` (#1507) |
| [`alloy-rs/alloy`](https://github.com/alloy-rs/alloy) | [#3976](https://github.com/alloy-rs/alloy/pull/3976) | `fix(consensus-any)`: saturate `baseFeePerGas` above `u64::MAX` on deser (#3741) |
| [`ratatui/ratatui`](https://github.com/ratatui/ratatui) | [#2527](https://github.com/ratatui/ratatui/pull/2527) | `fix(terminal)`: skip wide-grapheme continuation cells in `insert_before` (#1332) |
| [`unhappychoice/splashboard`](https://github.com/unhappychoice/splashboard) | [#216](https://github.com/unhappychoice/splashboard/pull/216) | `feat`: `cache` management CLI — `list`, `clear`, `path` (#40) |
| [`crynta/terax-ai`](https://github.com/crynta/terax-ai) | [#162](https://github.com/crynta/terax-ai/pull/162) | `feat(pty)`: `pty_cwd` for tab-restore CWD lookup (#134) |
| `DefiLlama/chainlist`, `ethereum-lists/chains` | [#2714](https://github.com/DefiLlama/chainlist/pull/2714) · [#2715](https://github.com/DefiLlama/chainlist/pull/2715) · [#8266](https://github.com/ethereum-lists/chains/pull/8266) | Sentrix mainnet registration + EIP-3091 explorer URL |

Each patch fixes a class of bug I hit while building Sentrix, includes a regression test that fails on `main` and passes after, follows the host project's commit-message convention.

## Tech focus

- **Rust** — async (`tokio`), trait-driven design, no `unsafe` in the consensus path, MDBX FFI, libp2p, `revm`, `alloy`, `tonic`, `jsonrpsee`, `tower`. `cargo deny` + `cargo audit` + clippy `-D warnings` in CI.
- **Distributed systems** — Tendermint-style BFT, gossipsub mesh, leader election, equivocation slashing, deterministic state replication, snapshot / restore from peer rsync.
- **EVM** — `revm` integration, EIP-1559, RLP, custom precompiles, Sourcify pipeline, gas accounting, EIP-3091 explorer compliance.
- **Storage** — MDBX (cursor-based scans, range iterators), sparse Merkle, write batching, crash-consistent atomic save + load-replay.
- **Solidity / Foundry** — production contracts: AMM (UniswapV2 fork), token factory, multisig safe, timelock, Merkle airdrop, bonding-curve launchpad. Invariant + fuzz suites.
- **TypeScript / Next.js / Leptos** — multi-app monorepo deployment, WebSocket + gRPC-Web clients, RSC reconciliation, Privy + viem + wagmi.
- **Mobile** — Flutter / Dart for self-custody wallet, EVM signing, postMessage IPC.
- **Ops** — Docker compose, systemd, Caddy edge (`lb_try_duration` retry + CORS), Prometheus + Alertmanager, Telegram routing, GitHub Actions CI, branch-protection + `cargo audit` + `gitleaks` gates, hourly chain.db snapshots.

**Codebase composition** across my repos (vendored deps excluded): Rust 36% · TypeScript 29% · Solidity 23% · Dart 3% · HTML/TeX 6% · Shell/Dockerfile 1%.

---

## Sponsor

I build open-source blockchain infrastructure full-time, unpaid. Sponsorship buys me focused engineering hours: more upstream PRs, faster Sentrix Chain releases, better docs and tooling for everyone building on or alongside it.

**No fiat. No bank. No middleman. 100% on-chain.**

### What your sponsorship enables

- Upstream PRs to **CometBFT**, **tendermint-rs**, **Reth**, **alloy**, **libp2p**, **revm**, and other Rust + chain infra projects
- **Sentrix Chain** core development — BFT consensus hardening, libp2p reliability, validator tooling, RPC/gRPC parity, indexer + explorer
- **SentrisCloud** ecosystem — block explorer, faucet, wallets (web + mobile), SDKs (Rust + TS), dApp starters
- Security disclosures and audits (responsible-disclosure work pre-bounty)
- Time spent reviewing other people's PRs and helping new contributors

The full list of open patches is in [Upstream contributions](#upstream-contributions) above.

### Wallets

![Networks](https://img.shields.io/badge/Networks-EVM_%7C_Solana_%7C_Bitcoin_%7C_Sui-2ea44f?style=for-the-badge)

Four networks. Send from any wallet that supports the network you're on — every standard wallet works (MetaMask, Rabby, Coinbase Wallet, Phantom, Solflare, Backpack, Sparrow, Xverse, Sui Wallet, etc.).

<details>
<summary><b>🟦 EVM</b> — Ethereum · Base · Monad · BNB · Arbitrum · Optimism · Polygon · Sentrix Chain</summary>

<br>

<img align="right" width="180" src="./assets/sponsor/evm.png" alt="EVM wallet QR" />

```
0x25cF4d0e455b37387a1891712Bd3bF0a5bCd37c4
```

Accepts **ETH · USDC · USDT · BERA · SRX · any ERC-20** on any EVM-compatible chain. Send from any standard EVM wallet (MetaMask, Rabby, Coinbase Wallet, Frame, Phantom, etc.).

[Etherscan](https://etherscan.io/address/0x25cF4d0e455b37387a1891712Bd3bF0a5bCd37c4) · [Basescan](https://basescan.org/address/0x25cF4d0e455b37387a1891712Bd3bF0a5bCd37c4) · [Sentrix Scan](https://scan.sentrixchain.com/address/0x25cF4d0e455b37387a1891712Bd3bF0a5bCd37c4)

<br clear="all">

</details>

<details>
<summary><b>🟣 Solana</b> — SOL & any SPL token</summary>

<br>

<img align="right" width="180" src="./assets/sponsor/sol.png" alt="Solana wallet QR" />

```
Dkqj5ntv66cZFTFpMWZ9KaiF45srY9ZxZNLwmAtrG1nT
```

Accepts **SOL · USDC-SPL · USDT-SPL · any SPL token**. Send from any standard Solana wallet (Phantom, Solflare, Backpack, etc.).

[Solscan](https://solscan.io/account/Dkqj5ntv66cZFTFpMWZ9KaiF45srY9ZxZNLwmAtrG1nT)

<br clear="all">

</details>

<details>
<summary><b>🟦 Sui</b> — SUI & any Sui asset</summary>

<br>

<img align="right" width="180" src="./assets/sponsor/sui.png" alt="Sui wallet QR" />

```
0x281695f02524b848cf3d18bf1b2e769c7647685e223315489b81c210da7f30f3
```

Accepts **SUI · USDC · any Sui-native token**. Send from any standard Sui wallet (Sui Wallet, Suiet, Phantom, etc.).

[SuiScan](https://suiscan.xyz/mainnet/account/0x281695f02524b848cf3d18bf1b2e769c7647685e223315489b81c210da7f30f3) · [SuiVision](https://suivision.xyz/account/0x281695f02524b848cf3d18bf1b2e769c7647685e223315489b81c210da7f30f3)

<br clear="all">

</details>

<details>
<summary><b>🟧 Bitcoin (Taproot)</b> — BTC</summary>

<br>

<img align="right" width="180" src="./assets/sponsor/btc.png" alt="Bitcoin Taproot wallet QR" />

```
bc1pfgkpanxcyv6kl4k3jmtgegh53x8c8lukz7fr4gdsd625gacg6ygs2q534d
```

P2TR (Taproot) address. Send from any Taproot-capable wallet (Sparrow, Xverse, Muun, Keystone, Phantom, etc.).

[Mempool.space](https://mempool.space/address/bc1pfgkpanxcyv6kl4k3jmtgegh53x8c8lukz7fr4gdsd625gacg6ygs2q534d)

<br clear="all">

</details>

### Why crypto-only

GitHub Sponsors requires a bank account and Stripe verification. I'd rather receive value the same way the network I build operates — on-chain, transparent, no intermediary, no chargebacks. If you sponsor, you can see exactly where it goes.

---
