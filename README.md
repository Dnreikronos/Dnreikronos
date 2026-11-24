# Wassup

I'm Joao, a senior software engineer writing Rust at [Mother.tech](https://mother.tech), after 6+ years of backend work in Go. Outside work I write zero-knowledge circuits and smart contracts for Ethereum and Solana.

**Highlights:**
- A ZK dark pool DEX (halo2 + arkworks) and a Solana compliance layer that runs Groth16 verification inside a Token-2022 transfer hook under 200k compute units.
- 86 merged PRs across Rust open source: 51 in the [Rust compiler](https://github.com/rust-lang/rust), 33 in [Zed](https://github.com/zed-industries/zed), 2 in [Sway](https://github.com/FuelLabs/sway).
- Web3 mentor at Borderless Coding: 60+ engineers, 20+ live workshops.

---

## What I'm building right now

**[DarkPool-Exchange](https://github.com/Dnreikronos/DarkPool-Exchange)**, a ZK dark pool DEX. Orders stay private until settlement. The engine matches them in batch auctions every 5 seconds with one clearing price per round, which kills most front-running and MEV. I work on the Rust and Web3 side: halo2 and arkworks circuits, WASM and native proof generation, the proof aggregator, and the Solidity verifier integration.

**[zksettle](https://github.com/yuribodo/zksettle)**, a Solana compliance layer for stablecoin fintechs. Proves travel-rule and sanctions conformance without putting any PII on-chain. A Token-2022 Transfer Hook verifies Groth16 proofs in under 200k compute units. Off-chain side is a Rust workspace: issuer service, OFAC sanctions updater with a Sparse Merkle Tree, Helius-webhook indexer that pins attestations to Arweave, and an axum API gateway.

---

## Other Web3 projects

- **[Crypto-Tip](https://github.com/Dnreikronos/crypto-tip)** (35 stars): decentralized tipping platform. Solidity contracts on Ethereum plus a Solana program in Rust, integrated with MetaMask and Phantom.
- **[Pattpay](https://github.com/Dnreikronos/pattpay)** (26 stars, Cypherpunk Hackathon): Solana payment gateway for one-time and recurring subscriptions. Anchor programs use a delegate-authority PDA to charge subscribers automatically. Supports SPL Token and Token-2022.
- **givemoney.fun** ([backend](https://github.com/Dnreikronos/givememoney.fun-backend) · [contracts](https://github.com/Dnreikronos/givememoney.fun-crypto)): crypto donation platform for Twitch and Kick streamers. Solidity `StreamerDonations` contract on Ethereum (Foundry + OpenZeppelin) and an Anchor program on Solana for SOL and SPL Token-2022 donations.
- **[Proof Of Learn](https://github.com/Dnreikronos/proof-of-learn)** (NearX and ZKVerify Hackathon): AI-generated learning roadmaps validated by Circom ZK circuits, with on-chain NFT credentials issued via Solidity smart contracts (Foundry).

---

## Web3 community

Web3 Technical Mentor and Ambassador at **Borderless Coding** (USA). Mentored 60+ engineers on Solidity smart contracts and blockchain architecture, ran 20+ live workshops with Foundry, Hardhat, and Remix, and helped grow the technical community by 200%.

---

## Open source

**[Zed](https://github.com/zed-industries/zed)** (Rust, 70k+ stars): 62 PRs submitted, 33 merged across 15+ subsystems, around 3,000 lines. A few I'm proud of:

- [#51035](https://github.com/zed-industries/zed/pull/51035): found and fixed a macOS deadlock in the GPUI rendering framework. Re-entrant key status changes were freezing the UI.
- [#50705](https://github.com/zed-industries/zed/pull/50705): reworked picker selection logic across 11 files so non-selectable entries can no longer confirm unintended actions in the command palette.
- [#51623](https://github.com/zed-industries/zed/pull/51623): SVG renderer was failing to render text when system fonts were unavailable.
- [#53712](https://github.com/zed-industries/zed/pull/53712): semantic tokens weren't appearing when opening a buffer from a multibuffer.

Plus 5 merged PRs on the OCaml extension (Dune support, MLX files, LSP argument forwarding, project root detection). [All my Zed PRs](https://github.com/zed-industries/zed/pulls?q=author%3ADnreikronos).

**[Rust compiler](https://github.com/rust-lang/rust)** (Rust, 122k+ stars): 66 PRs submitted, 51 merged, 8 still open. Around 5,500 lines added across 371 files, mostly in the next-generation trait solver, borrowck, diagnostics, and HIR lowering. A few merged ones I'm proud of:

- [#158588](https://github.com/rust-lang/rust/pull/158588): fixed `-Zassumptions-on-binders` diagnostics in trait selection. 24 files, the largest change I've landed in the compiler.
- [#161012](https://github.com/rust-lang/rust/pull/161012): normalized non-rigid aliases when NLL relates types in borrowck.
- [#157680](https://github.com/rust-lang/rust/pull/157680) and [#157542](https://github.com/rust-lang/rust/pull/157542): tightened the new `#[pin_v2]` attribute. Require it for explicit pin-projection patterns, reject it on `#[repr(packed)]` types.
- [#156968](https://github.com/rust-lang/rust/pull/156968): taught const-operation diagnostics to suggest `generic_const_args`. 73 files of test output moved with it.
- [#156885](https://github.com/rust-lang/rust/pull/156885): fixed a misattributed type-inference error span on index expressions.
- [#158874](https://github.com/rust-lang/rust/pull/158874): fixed anonymous const type recovery in HIR type lowering.
- [#160390](https://github.com/rust-lang/rust/pull/160390): handled slice-tailed DSTs in autodiff type trees.
- [#157270](https://github.com/rust-lang/rust/pull/157270): capture upvars by reference for `.use` in non-move closures (ergonomic clones).
- [#161624](https://github.com/rust-lang/rust/pull/161624): pointed closure trait errors at the captured values that caused them.
- [#161708](https://github.com/rust-lang/rust/pull/161708): propagated an async closure's output type into its body in `hir_typeck`.
- [#161467](https://github.com/rust-lang/rust/pull/161467): `wfcheck` now names the item that discards an unused type parameter.
- [#163713](https://github.com/rust-lang/rust/pull/163713): propagated reported errors from ABI checks in codegen.

Most of the recent work is on the next-gen trait solver: tracking canonical response universe assumptions ([#159987](https://github.com/rust-lang/rust/pull/159987)), resolving region vars in the max universe ([#157921](https://github.com/rust-lang/rust/pull/157921)), normalizing next-gen region constraints ([#158404](https://github.com/rust-lang/rust/pull/158404)), turning the solver on globally for assumptions-on-binders ([#160513](https://github.com/rust-lang/rust/pull/160513)), adding implied outlives assumptions ([#162238](https://github.com/rust-lang/rust/pull/162238)), handling reflexive region constraints ([#161988](https://github.com/rust-lang/rust/pull/161988)), preserving eager normalization failures ([#162618](https://github.com/rust-lang/rust/pull/162618)), and resolving region vars before eager placeholder handling ([#164103](https://github.com/rust-lang/rust/pull/164103)).

Eight PRs open right now. Two are on `Reborrow` in borrowck: fixing an ICE on types with several lifetimes and skipping ignorable places when gathering loans. The rest explain implicit object lifetimes in static calls, reject escaping bound vars in anon const arg types, restore type-op solver constraints, fix `Field::OFFSET` normalization in the next solver, add minimal coroutine binder assumptions, and normalize autodiff typetree struct fields.

[All my rustc PRs](https://github.com/rust-lang/rust/pulls?q=author%3ADnreikronos).

**[Sway](https://github.com/FuelLabs/sway)** (Rust, 61k+ stars): the smart-contract language for the Fuel blockchain. 8 PRs submitted, 2 merged.

- [#7629](https://github.com/FuelLabs/sway/pull/7629): optimized away zero-length MCP/MCPI instructions in the compiler backend.
- [#7628](https://github.com/FuelLabs/sway/pull/7628): fixed `forc-fmt` collapsing an empty if-body and its `else` onto one line.

[All my Sway PRs](https://github.com/FuelLabs/sway/pulls?q=author%3ADnreikronos).

---

## Tech stack

**AI:** AI agents, MCP, Claude Agent SDK, RAG, knowledge graphs, LLM evaluation

**Web3:** Solidity, Rust (Solana / Anchor), Foundry, Hardhat, Remix, Token-2022, PDAs, ERC-20

**ZK:** halo2, arkworks, Groth16 (BN254), Circom, Noir, WASM proof generation, Sparse Merkle Trees

**Languages:** Rust, Go, TypeScript, Solidity, Java, Python, SQL, Bash

**Backend:** Go, Spring Boot, NestJS, REST, gRPC, GraphQL, microservices, Kafka, PostgreSQL, MongoDB, Redis

**Infra:** Docker, Kubernetes, ArgoCD, Datadog, AWS, OCI

---

## Day job: Rust at Mother.tech

Since July 2026 I've been a senior software engineer at Mother.tech, writing Rust on Skeleton. It keeps a user's memory and documents in a structured store they own, and any AI tool they use reads and writes through it. The work I'm proudest of so far:

- Built the company's first LLM evaluation harness. Across 1,800+ runs on 5 models, our retrieval scored 98-100% on 4 of them, vs 68-82% for raw dumps and 70-79% for RAG.
- Built a 726-trial security benchmark: 0 of 100 injected attacks reached the model, vs 100 of 100 for raw dumps and 33 of 100 for RAG.
- Cut search on our heaviest accounts from 5.4s to 1.4s in production.
- Found and fixed the cause of 94% of agent runner stalls, which cost 2-3 minutes per reply.

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
