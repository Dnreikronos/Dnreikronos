# Hey 👋

I'm João, a backend engineer with about 6 years in Go. Most of that time has been spent keeping things from falling over at scale, and lately I've been spending nights and weekends on Rust and ZK cryptography.

A few things I've shipped recently:

- Fixed a concurrency bug in an invoicing pipeline that handles 140M+ transactions a month. The race was breaking fiscal compliance, and a mutex around the right section made it go away.
- Cut some PostgreSQL queries by up to 85% (over a minute off the worst aggregations) by rewriting execution plans and adding targeted indexes.
- Saved roughly $10k in licensing and compute by moving an invoicing stack off Java/Oracle and onto Go/PostgreSQL.
- 30 merged PRs into [Zed](https://github.com/zed-industries/zed), the Rust code editor (70k+ stars on GitHub). Most of them are bugs I hit while using it.
- Ship ZK systems for fun: halo2 and arkworks circuits, Groth16 verifiers on both EVM and Solana.

---

## What I'm building right now

**[DarkPool-Exchange](https://github.com/Dnreikronos/DarkPool-Exchange)**, a ZK dark pool DEX. Orders stay private until settlement. The engine matches them in batch auctions every 5 seconds with one clearing price per round, which kills most front-running and MEV. I'm working on the Rust and Web3 side: halo2 and arkworks circuits, client-side proof generation (WASM and native), the proof aggregator, and the Solidity verifier integration.

**[zksettle](https://github.com/yuribodo/zksettle)**, a Solana compliance layer for stablecoin fintechs. Proves travel-rule and sanctions conformance without putting any PII on-chain. A Token-2022 Transfer Hook verifies Groth16 proofs in under 200k compute units, and proof generation runs in the user's browser via Noir + WASM so nothing sensitive ever leaves the device.

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

**Languages:** Go, Rust, Solidity, TypeScript, Java, Python, SQL, Bash

**Backend:** Spring Boot, NestJS, REST, gRPC, GraphQL, microservices

**Data:** PostgreSQL, MongoDB, Redis, Elasticsearch, MySQL, SQL Server

**Infra:** Docker, Kubernetes, ArgoCD, Datadog, Grafana, ELK, AWS, OCI

**Messaging:** Apache Kafka, RabbitMQ, SQS

**Web3:** Anchor, Foundry, Hardhat, halo2, arkworks, Groth16, Circom, Noir, MetaMask, Phantom

---

## Stats

![Streak](https://github-readme-streak-stats.herokuapp.com/?user=Dnreikronos&theme=vue-dark&hide_border=true)

---

## Contact

- Brazil (UTC-3), remote, comfortable with US and EU overlap
- Email: [blsoaresdev@gmail.com](mailto:blsoaresdev@gmail.com)
- LinkedIn: [linkedin.com/in/blsoaresdev](https://www.linkedin.com/in/blsoaresdev/)
