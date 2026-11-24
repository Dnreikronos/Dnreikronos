# Wassup

I'm Joao, a senior software engineer at [Mother.tech](https://mother.tech). Before that I spent 6+ years doing senior backend work, mostly in Go. Outside work I write zero-knowledge circuits and smart contracts for Ethereum and Solana.

Highlights:
- At Mother.tech I built the company's first LLM evaluation harness and a 726-trial security benchmark.
- A ZK dark pool DEX (halo2 + arkworks) and a Solana compliance layer that runs Groth16 verification inside a Token-2022 transfer hook under 200k compute units.
- 71 merged PRs across Rust open source: 36 in the [Rust compiler](https://github.com/rust-lang/rust), 33 in [Zed](https://github.com/zed-industries/zed), 2 in [Sway](https://github.com/FuelLabs/sway).
- Web3 mentor at Borderless Coding: 60+ engineers, 20+ live workshops.

## Day job: Mother.tech

Senior Software Engineer since July 2026, remote. I work on Skeleton, which keeps a user's memory and documents in a structured store they own. Any AI tool they use reads and writes through it.

- Built the company's first LLM evaluation harness. Over 1,800 runs on 5 models, our retrieval scored 98-100% on 4 of them, vs 68-82% for raw dumps and 70-79% for RAG. A model 146x cheaper lost about 1 point of accuracy.
- Then built a 726-trial security benchmark. At 120 contacts we finished 100% of tasks and sent the model 99.5% fewer facts than a raw dump, at 15x lower cost. 0 of 100 injected attacks reached the model, vs 100 of 100 for dumps and 33 of 100 for RAG.
- Moved cloud agents to zero data retention in production on every Claude model except Fable, enforced on our server. Providers don't keep what they get, and we send them less user data.
- Gave 7 agent task types a self-learning loop that learns only from verified outcomes.
- Found and fixed the cause of 94% of runner stalls (2-3 minutes per reply) and 71% of repeat cold starts (~100s per reply).
- Search on our heaviest accounts went from 5.4s to 1.4s in production, 74% faster. Repeat searches got 68% faster (114ms to 36ms) and permission reads fell 80%.
- Cost per correct answer fell 28% and tool payloads shrank 46%, while benchmark accuracy went from 83% to 100%.
- Preloaded the most-used tools. In a 30-day production replay, sessions that had to search for one first fell from 39% to 24%, and those tools were reached 30% faster (4.7s to 3.3s).
- Doubled recall on agent task routing from 48% to 96%, with 98.7% precision and a 1.25s median.
- Moved ~11,700 lines of code out of the agent's reach in the sandbox.
- Created the mutation testing program and brought 6 codebases to a 100% kill rate on ~7,200 mutants. Electron went from 50% to 100%.

## What I'm building outside work

**[DarkPool-Exchange](https://github.com/Dnreikronos/DarkPool-Exchange)**, a ZK dark pool DEX. Orders stay private until settlement. The engine matches them in batch auctions every 5 seconds with one clearing price per round, which kills most front-running and MEV. I work on the Rust and Web3 side: halo2 and arkworks circuits, WASM and native proof generation, the proof aggregator, and the Solidity verifier integration.

**[zksettle](https://github.com/yuribodo/zksettle)**, a Solana compliance layer for stablecoin fintechs. Proves travel-rule and sanctions conformance without putting any PII on-chain. A Token-2022 Transfer Hook verifies Groth16 proofs in under 200k compute units. Off-chain side is a Rust workspace: issuer service, OFAC sanctions updater with a Sparse Merkle Tree, Helius-webhook indexer that pins attestations to Arweave, and an axum API gateway.

## Other Web3 projects

- **[Crypto-Tip](https://github.com/Dnreikronos/crypto-tip)** (35 stars): decentralized tipping platform. Solidity contracts on Ethereum plus a Solana program in Rust, integrated with MetaMask and Phantom.
- **[Pattpay](https://github.com/Dnreikronos/pattpay)** (26 stars, Cypherpunk Hackathon): Solana payment gateway for one-time and recurring subscriptions. Anchor programs use a delegate-authority PDA to charge subscribers automatically. Supports SPL Token and Token-2022.
- **givemoney.fun** ([backend](https://github.com/Dnreikronos/givememoney.fun-backend) · [contracts](https://github.com/Dnreikronos/givememoney.fun-crypto)): crypto donation platform for Twitch and Kick streamers. Solidity `StreamerDonations` contract on Ethereum (Foundry + OpenZeppelin) and an Anchor program on Solana for SOL and SPL Token-2022 donations.
- **[Proof Of Learn](https://github.com/Dnreikronos/proof-of-learn)** (NearX and ZKVerify Hackathon): AI-generated learning roadmaps validated by Circom ZK circuits, with on-chain NFT credentials issued via Solidity smart contracts (Foundry).

## Web3 community

Web3 Technical Mentor and Ambassador at **Borderless Coding** (USA). Mentored 60+ engineers on Solidity smart contracts and blockchain architecture, ran 20+ live workshops with Foundry, Hardhat, and Remix, and helped grow the technical community by 200%.

## Open source

**[Zed](https://github.com/zed-industries/zed)** (Rust, 70k+ stars): 62 PRs submitted, 33 merged across 15+ subsystems, around 3,000 lines. A few I'm proud of:

- [#51035](https://github.com/zed-industries/zed/pull/51035): found and fixed a macOS deadlock in the GPUI rendering framework. Re-entrant key status changes were freezing the UI.
- [#50705](https://github.com/zed-industries/zed/pull/50705): reworked picker selection logic across 11 files so non-selectable entries can no longer confirm unintended actions in the command palette.
- [#51623](https://github.com/zed-industries/zed/pull/51623): SVG renderer was failing to render text when system fonts were unavailable.
- [#53712](https://github.com/zed-industries/zed/pull/53712): semantic tokens weren't appearing when opening a buffer from a multibuffer.

Plus 5 merged PRs on the OCaml extension (Dune support, MLX files, LSP argument forwarding, project root detection). [All my Zed PRs](https://github.com/zed-industries/zed/pulls?q=author%3ADnreikronos).

**[Rust compiler](https://github.com/rust-lang/rust)** (Rust, 114k+ stars): 49 PRs submitted, 36 merged, 9 still open. Around 3,500 lines added across 255 files, concentrated in the next-generation trait solver, diagnostics, HIR and AST lowering, and borrowck. A few merged ones I'm proud of:

- [#158588](https://github.com/rust-lang/rust/pull/158588): fixed `-Zassumptions-on-binders` diagnostics in trait selection. 24 files, the largest change I've landed in the compiler.
- [#161012](https://github.com/rust-lang/rust/pull/161012): normalized non-rigid aliases when NLL relates types in borrowck.
- [#157680](https://github.com/rust-lang/rust/pull/157680) and [#157542](https://github.com/rust-lang/rust/pull/157542): tightened the new `#[pin_v2]` attribute. Require it for explicit pin-projection patterns, reject it on `#[repr(packed)]` types.
- [#156968](https://github.com/rust-lang/rust/pull/156968): taught const-operation diagnostics to suggest `generic_const_args`. 73 files of test output moved with it.
- [#156885](https://github.com/rust-lang/rust/pull/156885): fixed a misattributed type-inference error span on index expressions.
- [#158874](https://github.com/rust-lang/rust/pull/158874): fixed anonymous const type recovery in HIR type lowering.
- [#160390](https://github.com/rust-lang/rust/pull/160390): handled slice-tailed DSTs in autodiff type trees.
- [#157270](https://github.com/rust-lang/rust/pull/157270): capture upvars by reference for `.use` in non-move closures (ergonomic clones).

Most of the recent work is on the next-gen trait solver: tracking canonical response universe assumptions ([#159987](https://github.com/rust-lang/rust/pull/159987)), resolving region vars in the max universe ([#157921](https://github.com/rust-lang/rust/pull/157921)), normalizing next-gen region constraints ([#158404](https://github.com/rust-lang/rust/pull/158404)), and turning the solver on globally for assumptions-on-binders ([#160513](https://github.com/rust-lang/rust/pull/160513)).

Nine PRs open right now: async closure output propagation in `hir_typeck`, closure trait errors pointed at the captured values that caused them, naming the item that discards an unused type parameter in `wfcheck`, keeping type-op region constraints in borrowck, resolving inference variables after deep normalization, representing live alias arguments as bitsets, and normalizing autodiff typetree struct fields.

[All my rustc PRs](https://github.com/rust-lang/rust/pulls?q=author%3ADnreikronos).

**[Sway](https://github.com/FuelLabs/sway)** (Rust, 61k+ stars): the smart-contract language for the Fuel blockchain. 8 PRs submitted, 2 merged.

- [#7629](https://github.com/FuelLabs/sway/pull/7629): optimized away zero-length MCP/MCPI instructions in the compiler backend.
- [#7628](https://github.com/FuelLabs/sway/pull/7628): fixed `forc-fmt` collapsing an empty if-body and its `else` onto one line.

[All my Sway PRs](https://github.com/FuelLabs/sway/pulls?q=author%3ADnreikronos).

## Tech stack

**AI:** AI agents, MCP, Claude Agent SDK, RAG, knowledge graphs, LLM evaluation

**Web3:** Solidity, Rust (Solana / Anchor), Foundry, Hardhat, Remix, Token-2022, PDAs, ERC-20

**ZK:** halo2, arkworks, Groth16 (BN254), Circom, Noir, WASM proof generation, Sparse Merkle Trees

**Languages:** Rust, Go, TypeScript, Solidity, Java, Python, SQL, Bash

**Backend:** Go, Spring Boot, NestJS, REST, gRPC, GraphQL, microservices, Kafka, PostgreSQL, MongoDB, Redis, Supabase

**Infra:** Docker, Kubernetes, ArgoCD, Datadog, AWS, OCI

## Backend, briefly

Six years of senior backend work, mostly in Go. A few things from that side:

- Fixed a concurrency bug in an invoicing pipeline that processes 140M+ transactions a month.
- Cut PostgreSQL query times by up to 85% on the heaviest aggregations.
- Saved roughly $10k by migrating an invoicing stack from Java/Oracle to Go/PostgreSQL.

The full backend history lives on my LinkedIn.

## Stats

![Streak](https://github-readme-streak-stats.herokuapp.com/?user=Dnreikronos&theme=vue-dark&hide_border=true)

## Contact

- Brazil (UTC-3), remote, comfortable with US and EU overlap
- Email: [blsoaresdev@gmail.com](mailto:blsoaresdev@gmail.com)
- LinkedIn: [linkedin.com/in/blsoaresdev](https://www.linkedin.com/in/blsoaresdev/)
