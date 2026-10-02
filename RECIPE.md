# RECIPE — mock-oracle fixtures (outline)

**Type:** community scaffolding recipe (learning docs).  
**Network:** local emulator / OfflineFetcher practice; **Preview** framing only.  
**Not claimed:** live Orcfax E2E, CIP-30, mainnet, invented spend success.

## Goal

After reading this outline, you can:

1. Point at a **JSON fixture** that matches the Orcfax `Statement` shape
   (`feed_id`, `created_at`, CER `body`).
2. Seed a **local** Mesh OfflineFetcher / emulator path with that shape.
3. Keep STATUS honest: **mock fixture**, not live Preview freshness.
4. Know when to switch to upstream `orcfax-examples/mock` instead.

## 0. Preconditions

- Sibling hello understood: `cardano-preview-mesh-aiken-hello`
- Packaging map + comments stub: `cardano-packaging-glue-starter`
- Orcfax unpaid consume docs: `orcfax-preview-consume-sketch` (freshness **Shaky**)
- Practice pins (from sibling VERSIONS): Aiken **v1.1.23**, `@meshsdk/core` **1.9.1**, Node **20.x** — re-check publish day

## 1. Fixture shape (Solid — docs)

Public consume docs (`docs.orcfax.io/consume`) describe:

```
Statement { feed_id, created_at, body }
CER body = Rational { num, denom }
feed_id prefix match including trailing `/` after feed name
```

Documented Preview Active ids (copy from orcfax sketch VERSIONS — **docs**, not
a freshness claim):

| Item | Value |
|------|-------|
| Preview FSP (Active) | `0690081bc113f74e04640ea78a87d88abbd2f18831c44c4064524230` |
| Preview FS (Active) | `e6c8a314ae942401619460f00c69de3d1b996db588d4042243a4b259` |
| FSP token name | `000de140` |
| FS token name | empty bytearray |

## 2. Suggested local drill order (DIY — NOT RUN in this draft)

1. Load `fixtures/sample-cer-statement.json` and confirm fields parse.
2. (Later DIY) Seed OfflineFetcher / ScalusEmulator with oracle-shaped UTxO
   comments — **do not** invent Preview tx hashes in STATUS.
3. (Later DIY) Attach as reference-input shape in comments stub
   (`packaging-glue` → `stub/oracle-read.sketch.ts`).
4. If you need a **real mock publisher**: use `orcfax/orcfax-examples` `./mock`
   (Deno / WIP) and label STATUS as mock-publish, not unpaid live consume.

## 3. Stop rules

- Do **not** record “spend succeeded” without a real dated tx hash from **your** run.
- Do **not** copy sibling hello lock/unlock hashes and claim they prove oracle attach.
- Do **not** claim fixture `created_at` equals live Preview publish time.
- Preview-only until unpaid public freshness is Solid via re-probe runbook.

## 4. Explicit non-goals

- No executable that invents hashes
- No Subbit / on-demand path
- No Midnight Compact mixed into this L1 fixture kit
