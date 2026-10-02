# cardano-mock-oracle-fixtures

**Community learning / scaffolding draft** — **JSON + comments-only fixtures** for
local / **Preview practice** attach of **oracle-shaped** Fact Statement data.

**Who this is for:** builders who already have Mesh + Aiken hello on Preview and
want unit / emulator drills without claiming live Orcfax freshness.

> **Not official Orcfax, Mesh, or Aiken docs.**  
> **Not** a live oracle. **Not** live Orcfax freshness. **Not** CIP-30 (Cardano Improvement Proposal 30 — browser wallet dApp connector). **Not** mainnet.  
> **Not** production-audited. Fixtures are for **local / Preview practice attach** only.  
> No seeds / keys / Blockfrost project ids. No invented spend success.

> ### Honesty banner (read this first)
> These fixtures **do not** publish on-chain Orcfax statements and **do not**
> prove Preview **FS** (Fact Statement) freshness. Sampled live Preview FS UTxOs were **months-stale**
> at last scout (**Shaky** — ~2026-04; see sibling `orcfax-preview-consume-sketch`).
> Prefer the upstream **`orcfax/orcfax-examples` `./mock`** path for a real mock
> publisher; this package only ships **shape samples** (JSON / comments) so you
> can wire OfflineFetcher / emulator seeds without inventing hashes.

## Verified scope (draft assemble 2026-09-28 PT)

| | |
|---|---|
| **Solid (docs)** | Orcfax consume shape (**FSP** = Fact Statement Pointer → FS token → `Statement { feed_id, created_at, body }`); official examples include a **mock** publisher under `orcfax-examples/mock` (docs.orcfax.io/consume) |
| **Solid (sibling)** | Mesh + Aiken hello on Preview — `cardano-preview-mesh-aiken-hello` |
| **Shaky** | Any claim that fixture `created_at` matches live Preview publish cadence |
| **Not verified / NOT RUN** | Live Mesh unlock with Orcfax ref input; emulator E2E in this tree; CIP-30 |
| **Not claimed** | production-ready, audited, official, “matches mainnet Orcfax” |

## Package contents (outline)

| Path | Role |
|------|------|
| `README.md` | This front door |
| `PLAIN-LANGUAGE.md` | Everyday explanation |
| `RECIPE.md` | How to use fixtures locally (outline) |
| `STATUS.md` | Evidence / NOT RUN matrix |
| `SECURITY.md` | How to report problems |
| `LICENSE` | MIT (Brady Sheldon, 2026) |
| `fixtures/` | JSON samples + comments (no executable invent-hash tooling) |

## Sibling packages (cite, don’t fork)

| Package | Role |
|---------|------|
| `cardano-preview-mesh-aiken-hello` | Verified Mesh + Aiken hello lock/unlock on Preview |
| `cardano-packaging-glue-starter` | Packaging map + comments-only Mesh attach stub |
| `orcfax-preview-consume-sketch` | Unpaid Preview consume docs; **Shaky** freshness; points at upstream mock |

## Upstream mock (prefer for real local publish)

- Repo: https://github.com/orcfax/orcfax-examples — subtree `./mock` (mock publisher)
- Docs: https://docs.orcfax.io/consume — “helpers for creating your own mock Orcfax-publish”
- Caveat: WIP / demo; off-chain examples skew **Deno**, not Mesh — label STATUS honestly

## What we do NOT claim

- No live feed spend / unlock submitted from this tree
- No inventing Preview tx hashes, TVL, or “spend succeeded” rows
- No claiming fixtures match live Preview publish cadence

## Publishing stance

Preview-first community draft. Honesty labels: **Solid / Shaky / Unknown**. MIT.
Reviewed before any public release. Docs-only / no CI in this tree.
