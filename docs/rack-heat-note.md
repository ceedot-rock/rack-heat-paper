# rack-heat-note — lab note (merged 2026-09-21)

Lab notes folded in from the archived private repo `ceedot-rock/rack-heat-note`.
Standalone folds and the paper itself stayed in the original repos where noted.

# LAB20 #6 — Video CDN originals

Rule: one master + derived seats. Not twenty stored ladders in v0.

CuNi emit catalog is programs, not video. This row stays **framed** until a media pin exists.
Do not pretend PCCX is a video codec.

## Fold

SKIP framed. No media pin. Not a product.

---

# LAB20 #7 — S3 / egress duplication

Rule: a second copy is only a copy if `source_hash` matches. Else it is a new object.

Receipt fields already on check/translate/squeeze. First slice: store the hash next to the blob; refuse “replicate” without it.

## Fold

PASS → folded into lab-agent POST /v1/deposit. Hash mismatch = new object.

---

# LAB20 #8 — Agent tool chatter

Rule: three verbs. Retry only on 5xx, not on refuse.

Live: POST /v1/check /v1/translate /v1/squeeze. MCP names cuni_check, bank_paste, pccx_encode.

## Fold

PASS → lab-agent receipts retry:false on refuse. Three verbs live.

---

# LAB20 #9 — JSON-as-database RPC

Rule: seal or compact before the hop. Chamber cloak/open is the product.

https://github.com/ceedot-rock/json-chamber-sdk

## Fold

PASS → Chamber json-chamber 1.4.1 (PyPI). One ciphertext, keys open.

---

# LAB20 #10 — Eval-farm busywork

Rule: exactness pack over 1k junk prompts.

Live stand-in: cuni check, examples/bank/add.py, eval/bank-add.json on lab-agent.

## Fold

PASS → lab-agent eval/bank-add.json + cuni check.

---

# LAB20 #11 — PUE theater

Rule: software kW is not a facility PUE sticker.
Paper: paper.html. Do not quote 18.75 kW as a measured rack.

## Fold

STANDALONE → paper.html in this repo. Not a SKU.

---

# LAB20 #12 — Edge always-on

Rule: boxes sleep when idle. Pattern: Fly auto_stop / min machines (lab-agent fly.toml).
Not a shop-floor agent this turn.

## Fold

PASS → spl-lab-agent fly.toml auto_stop=stop min_machines=0.

---

# LAB20 #13 — Model-weight shipping

Rule: delta + prove, not a raw FP16 dump.
Framed. No weight-delta pin. Do not call PCCX a model format.

## Fold

SKIP framed. No weight-delta pin.

---

# LAB20 #14 — Unverified artifacts

Rule: CI must prove the hook. cuni master runs `cuni bank --help` and paste py→py (7eedba2).
Close issues only with a URL + PASS.

## Fold

PASS → cuni CI bank paste + lab-agent tests/test_lab20.py.

---

# LAB20 #15 — Polyglot drift

Rule: paste N get X or refuse.
Live: cuni-bank-0.1.0 · POST /v1/translate
119 = check after ingest, not 119 parsers.

## Fold

PASS → CuNi Bank cuni-bank-0.1.0 /v1/translate.

---

# LAB20 #16 — Pay-per-call

Rule: an agent buys a verb. No signature → **402** + pay URL. Signature ok → same receipt as today.

## Current (measured)

`https://spl-lab-agent.fly.dev/v1/*` runs **without** a payment header.
Catalog `pay` field points at `https://www.slidphilabs.com/api/agent`.
That is a lab commerce URL, not a meter on the three POSTs.

## 402 body (when the meter is on)

```json
{
  "verb": "check",
  "ok": false,
  "source_hash": "",
  "pin": "v0.1.10",
  "refuse": "payment required",
  "pay": "https://www.slidphilabs.com/api/agent"
}
```

HTTP status **402**. Header to send later: `Payment-Signature` (x402 / lab grant). Free health and `/.well-known/ai-products.json` stay free.

## First slice

1. Do not break anonymous `GET /healthz`.
2. Gate only `POST /v1/check|translate|squeeze` behind env `LAB_REQUIRE_PAY=1`.
3. Default off until a test payment returns 200 + receipt.

## Not this row

Stripe dashboard. New token. Charging before a failed exactness (you can still charge a refuse if you want; say so in the grant).

## Status

Meter **ON** Fly (`LAB_REQUIRE_PAY=1`). GET /healthz and `/.well-known/ai-products.json` stay free. POST /v1/check|translate|squeeze without `Payment-Signature` or `X-PAYMENT` → **402**.

## Fold

PASS code. Meter default OFF (LAB_REQUIRE_PAY=0). 402 path unit-tested. Folded into lab-agent.

---

# LAB20 #17 — Cooling-water politics

Rule: cut kW in software; do not lobby a city from this repo.
Donate: https://www.slidphilabs.com/

## Fold

STANDALONE → paper.html. Not a SKU.

---

# LAB20 #18 — Corpus bitrot

Rule: deposit by source_hash. Recompute from dirt if the hash is missing.
Bank/check receipts already name the hash.

## Fold

PASS → GET /v1/deposit/{source_hash}. Folded into lab-agent.

---

# LAB20 #19 — On-device battery

Rule: small payloads squeeze or stay.
Partial: /v1/squeeze. ZRW exists as a separate integer path. Not a phone app this turn.

## Fold

PASS → POST /v1/squeeze.

---

# LAB20 #20 — Compliance clones

Rule: one ciphertext, keys open. Chamber cloak/open.
https://github.com/ceedot-rock/json-chamber-sdk

## Fold

PASS → Chamber 1.4.1. Folded into json-chamber-sdk.

---

