# STATUS — verification log (cardano-mock-oracle-fixtures)

**As-of:** 2026-10-02 PT (R1 deltas applied; skeleton 2026-09-28)  
**Label:** community learning / scaffolding draft — **local / Preview practice fixtures**  
**Not claimed:** battle-tested, production-ready, audited, mainnet, official,
live oracle E2E, CIP-30, live Orcfax freshness

## Matrix

| Check | Result | Notes |
|-------|--------|-------|
| Package skeleton (README / PLAIN / RECIPE / LICENSE / SECURITY / fixtures) | **PASS** (draft) | Assembled on box; not pushed |
| Orcfax Statement shape vs consume docs | **PASS** (docs) | feed_id / created_at / CER Rational — docs.orcfax.io/consume |
| Upstream mock publisher existence | **PASS** (docs) | orcfax-examples `./mock`; consume docs “mock Orcfax-publish” |
| Live Preview FS freshness today | **NOT PROVEN** (**Shaky**) | **2026-09-28 PT** Koios Preview scout: **278** FS-token UTxOs; newest sample block_time ~**2026-04-16** UTC. Same result recorded in sibling `orcfax-preview-consume-sketch` STATUS — not proof of fresh unpaid feeds today |
| OfflineFetcher / emulator seed E2E | **NOT RUN** | Fixtures only; no executable invent-hash tooling |
| Mesh unlock + oracle ref input | **NOT RUN** | Explicit non-goal for fixtures v0 |
| CIP-30 | **NOT RUN** | |
| Mainnet / TVL / users | **NOT CLAIMED** | Unknown |

## Sibling evidence (cite, do not re-claim)

| Sibling | What it proved | What it did **not** prove |
|---------|----------------|---------------------------|
| `cardano-preview-mesh-aiken-hello` | Mesh + Aiken hello lock/unlock on Preview | Oracle ref-input spend |
| `orcfax-preview-consume-sketch` | Docs + unpaid public-read FSP/FS existence; **Shaky** freshness | Live short-validity attach |
| `cardano-packaging-glue-starter` | Packaging map + comments-only stub | Live oracle E2E |

## Secrets

None. No wallet seeds, mnemonics, private keys, Orcfax credentials, or
Blockfrost project ids in this folder.

## Publishing stance

**Draft only** until peer review + publish approval. Preview-first.
Honesty labels Solid / Shaky / Unknown. Docs-only / no CI in this tree.

## Human skim

| Role | Result | Date (PT) |
|------|--------|-----------|
| Package owner skim (README / RECIPE / PLAIN-LANGUAGE) | **go** | 2026-10-02 |
| Peer review (Correctness + Presentation) | **PASS** (R2) | 2026-10-02 |

## Publish-day URL re-check (2026-10-02 PT)

| URL | Result |
|-----|--------|
| https://docs.orcfax.io/consume | **LIVE** — Statement `{feed_id, created_at, body}`; CER Rational; trailing `/`; Preview FSP `0690081b…4230` on Deployments table |
| https://docs.orcfax.io/deployments | **LIVE** — Preview Active FSP `0690081bc113f74e04640ea78a87d88abbd2f18831c44c4064524230`, FS `e6c8a314ae942401619460f00c69de3d1b996db588d4042243a4b259` (unchanged vs package docs ids) |
| https://github.com/orcfax/orcfax-examples | **LIVE** — repo exists; prefer `./mock` for real mock publisher |

Live Preview FS freshness remains **Shaky / NOT PROVEN** for short-validity attach (2026-09-28 Koios scout). Do **not** frame fixtures as live unpaid consume.
