# Plain language — mock oracle fixtures (Preview practice)

**Scope:** community learning explanation for **local / Cardano Preview practice**.  
**Not claimed:** live Orcfax freshness, production oracle, **CIP-30** (Cardano Improvement Proposal 30 — the browser wallet connector that lets a website ask a wallet to sign), mainnet, or a working spend drill.

## What problem this package talks about

You can already lock and unlock a tiny Aiken script with Mesh on Preview
(sibling hello). You also have unpaid Orcfax **read** notes (sibling sketch).
What you still need for **unit tests** and emulator drills is a **fake sticky
note** that *looks like* an oracle Fact Statement — without pretending the
live Preview chain just published a fresh price.

## What these fixtures are

- JSON (and comments) that show the **shape** of an Orcfax-like statement:
  `feed_id`, `created_at`, and a **CER** (current exchange rate) body (`num` / `denom`).
- Teaching aids for seeding Mesh **OfflineFetcher** / local emulator UTxOs.
- Loudly labeled **mock / practice** — not a live feed.

## What these fixtures are not

- Not a live Orcfax publish.
- Not proof that Preview **FS** (Fact Statement) UTxOs are fresh today (last scout: **Shaky**,
  sample ~2026-04).
- Not a substitute for the upstream **`orcfax-examples` mock** when you need a
  real mock publisher locally.
- Not a Mesh spend that “succeeded” — we do **not** invent that.

## Two doors (keep them separate)

1. **Live unpaid consume** — read real on-chain FS UTxOs by following an **FSP** (Fact Statement Pointer — the on-chain pointer that helps you find statement UTxOs). See sibling `orcfax-preview-consume-sketch`. Freshness may be **Shaky**; re-probe before short-validity spends.
2. **Mock / fixture practice** — this package + upstream `orcfax-examples/mock`.
   Use for local attach drills. Label STATUS rows as mock.

## Honesty labels we use

| Label | Meaning here |
|-------|----------------|
| **Solid** | Statement shape matches public Orcfax consume docs; sibling hello path exists |
| **Shaky** | Fixture timestamps / any “looks like live Preview” claim |
| **Unknown** | Whether your OfflineFetcher wiring matches a future Mesh pin — re-check |

## What to do next

1. Read sibling packaging-glue + orcfax sketch.
2. Use `fixtures/` JSON as **shape samples** only.
3. Prefer upstream mock publisher for local publish drills.
4. Re-probe live Preview freshness before any “live attach” STATUS claim.
