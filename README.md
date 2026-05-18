# Wassup 👋

I'm João. I'm transitioning into Web3, mostly focused on zero-knowledge cryptography. Day job pays the bills as a senior backend engineer (6+ years in Go), but the part I care about is shipping ZK circuits and on-chain code on Ethereum and Solana.

What I've been working on:

- Built the Rust and Web3 side of a ZK dark pool DEX: halo2 and arkworks circuits, client-side proof generation in WASM, a proof aggregator that batches individual proofs into a single on-chain check, and integration with the Solidity Groth16 verifier.
- Shipped a Solana compliance layer that proves sanctions and travel-rule conformance without putting PII on-chain. Groth16 verification runs in a Token-2022 Transfer Hook under 200k compute units, with proof generation in the browser via Noir + WASM.
- Built Anchor programs (Solana) and Solidity contracts (Ethereum) across several real-money projects: Token-2022 hooks, PDA-based subscription authorities, escrow contracts, and ERC-20 / SPL token flows.
- 30 merged PRs into [Zed](https://github.com/zed-industries/zed), the Rust code editor (70k+ stars). Mostly fixing bugs in GPUI, the editor core, and platform-specific rendering paths.

---

## What I'm building right now

**[DarkPool-Exchange](https://github.com/Dnreikronos/DarkPool-Exchange)**, a ZK dark pool DEX. Orders stay private until settlement. The engine matches them in batch auctions every 5 seconds with one clearing price per round, which kills most front-running and MEV. I work on the Rust and Web3 side: halo2 and arkworks circuits, WASM and native proof generation, the proof aggregator, and the Solidity verifier integration.

**[zksettle](https://github.com/yuribodo/zksettle)**, a Solana compliance layer for stablecoin fintechs. Proves travel-rule and sanctions conformance without putting any PII on-chain. A Token-2022 Transfer Hook verifies Groth16 proofs in under 200k compute units. Off-chain side is a Rust workspace: issuer service, OFAC sanctions updater with a Sparse Merkle Tree, Helius-webhook indexer that pins attestations to Arweave, and an axum API gateway.

---

## Other Web3 projects

- **[Crypto-Tip](https://github.com/Dnreikronos/crypto-tip)** (35 stars): decentralized tipping platform. Solidity contracts on Ethereum plus a Solana program in Rust, integrated with MetaMask and Phantom.
- **[Pattpay](https://github.com/Dnreikronos/pattpay)** (26 stars, Cypherpunk Hackathon): Solana payment gateway for one-time and recurring subscriptions. Anchor programs use a delegate-authority PDA to charge subscribers automatically. Supports SPL Token and Token-2022.
- **[givemoney.fun](https://github.com/Dnreikronos/givememoney.fun-crypto)**: crypto donation platform for Twitch and Kick streamers. Solidity `StreamerDonations` contract on Ethereum (Foundry + OpenZeppelin) and an Anchor program on Solana for SOL and SPL Token-2022 donations.
- **[Proof Of Learn](https://github.com/Dnreikronos/proof-of-learn)** (NearX and ZKVerify Hackathon): AI-generated learning roadmaps validated by Circom ZK circuits, with on-chain NFT credentials issued via Solidity smart contracts (Foundry).

---

## Web3 community

Web3 Technical Mentor and Ambassador at **Borderless Coding** (USA). Mentored 60+ engineers on Solidity smart contracts and blockchain architecture, ran 20+ live workshops with Foundry, Hardhat, and Remix, and helped grow the technical community by 200%.

---

## Open source

Active contributor to **[Zed](https://github.com/zed-industries/zed)** (Rust). 56 PRs submitted, 30 merged across 15+ subsystems, around 6,800 lines of code. A few I'm proud of:

- [#51035](https://github.com/zed-industries/zed/pull/51035): found and fixed a macOS deadlock in the GPUI rendering framework. Re-entrant key status changes were freezing the UI.
- [#50705](https://github.com/zed-industries/zed/pull/50705): reworked picker selection logic across 11 files so non-selectable entries can no longer confirm unintended actions in the command palette.
- [#51623](https://github.com/zed-industries/zed/pull/51623): SVG renderer was failing to render text when system fonts were unavailable.
- [#53712](https://github.com/zed-industries/zed/pull/53712): semantic tokens weren't appearing when opening a buffer from a multibuffer.

Plus 5 merged PRs on the OCaml extension (Dune support, MLX files, LSP argument forwarding, project root detection).

[All my Zed PRs here](https://github.com/zed-industries/zed/pulls?q=author%3ADnreikronos).

---

## Tech stack

**Web3:** Solidity, Rust (Solana / Anchor), Foundry, Hardhat, Remix, Token-2022, PDAs, ERC-20

**ZK:** halo2, arkworks, Groth16 (BN254), Circom, Noir, WASM proof generation, Sparse Merkle Trees

**Languages:** Rust, Go, TypeScript, Solidity, Java, Python, SQL, Bash

**Backend (day-job stack):** Go, Spring Boot, NestJS, REST, gRPC, GraphQL, microservices, Kafka, PostgreSQL, MongoDB, Redis

**Infra:** Docker, Kubernetes, ArgoCD, Datadog, AWS, OCI

---

## Backend, briefly

Six years of senior backend work, mostly in Go. A few things from that side:

- Fixed a concurrency bug in an invoicing pipeline that processes 140M+ transactions a month.
- Cut PostgreSQL query times by up to 85% on the heaviest aggregations.
- Saved roughly $10k by migrating an invoicing stack from Java/Oracle to Go/PostgreSQL.

The full backend history lives on my LinkedIn.

---

## Stats

![Streak](https://github-readme-streak-stats.herokuapp.com/?user=Dnreikronos&theme=vue-dark&hide_border=true)

---

## Contact

- Brazil (UTC-3), remote, comfortable with US and EU overlap
- Email: [blsoaresdev@gmail.com](mailto:blsoaresdev@gmail.com)
- LinkedIn: [linkedin.com/in/blsoaresdev](https://www.linkedin.com/in/blsoaresdev/)
