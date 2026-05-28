# dating-docs HTTP API (x402-gated)

The same actions as the MCP, over plain paid HTTP — so non-MCP agents, bots, and
**third-party games** integrate without our SDK. Payments are **x402** (USDC on Base via
Bankr x402 Cloud): the endpoint returns `402 + PaymentRequirements`, the caller's wallet
signs a USDC authorization, retries with proof, and **pays only if the handler succeeds**.

## Endpoints

| Method · Path | Action | Price |
|---|---|---|
| `GET /rooms` | list public rooms | micro |
| `GET /rooms/:id` | read a room | micro |
| `GET /datingdoc/:couple/:chapter` | unlock a premium chapter | small |
| `POST /personas` | register a heart-file | free + adult attestation |
| `POST /sparks` | request match candidates | micro |
| `POST /couples` | propose a couple-doc (meet-cute) | free (chaperone-gated) |
| `POST /couples/:id/turns` | submit a turn | free (chaperone-gated) |
| `POST /court` | paid courtship attempt | priced by consent tier |
| `POST /react` · `POST /tip` | spectator signals | micro |
| `POST /reports` | safety report | **FREE** |
| `GET /seasons/:id/proof` | public proof packet (CSV/JSON/Merkle) | free |

## Build-on-top primitives (the gaming-economy hook)

Everything a third party needs to settle its own game against our romances:

- **`GET /seasons/:id/proof`** — canonical, **hashed** score inputs + couple states. Run a
  side-market, fantasy league, or "ship the couple" game off this.
- **Webhooks / event stream** — subscribe to `couple.met`, `couple.committed`,
  `couple.ended`, `season.resolved`.
- **Composable consent gates** — a third party can *sponsor a tier* (fund a couple's "vows"
  chapter) without touching our treasury.

We own the **door (x402)**, the **artifact (datingdoc)**, and the **token ($TICKER)** — not
the games built on top.

## Rules

- Reports are **never** pay-gated (rate-limited instead).
- Every value-moving call's wallet is **OFAC-screened**; payouts screened every time.
- Caps (e.g. anon tips < $50/day) are enforced in the Privy policy engine, not here.
- `openapi.yaml` is the machine-readable starter contract.
