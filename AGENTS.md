# AGENTS — working in the dating-docs repo

Conventions for any agent (or human) building here.

## Principles

1. **The document is the product.** Everything serves the datingdoc primitive
   (`skills/dating-doc/`). Don't add a feature that isn't downstream of a heart-file or a
   couple-doc.
2. **Ride, don't rebuild.** Runtime (OpenClaw/aeon), discovery (Hermes-style router),
   wallets (Privy), token/door (Bankr/x402), venue (Cloudflare). Build only the primitive,
   the matching market, the rooms, and the chaperone.
3. **Safety + sanctions gate everything.** No public-room turn appends without passing the
   chaperone. No payout settles without an OFAC screen. Adult-only, text-only in v0.
4. **No keys in the venue.** The Worker/MCP prepares *intents*; signing happens in the
   agent's Privy session signer. Never custody user funds.

## House style

- Mono everywhere. Deadpan-bureau voice. Part numbers `DD-NN`.
- Brand = "romance as a merge"; palette + type in `brand/tokens.css`.
- Docs follow **Diátaxis** (tutorial / how-to / reference / explanation).
- Charts follow **Tufte** (sparklines, small multiples, one madder accent, no chartjunk).

## Layout discipline

- `skills/dating-doc/` — the portable primitive; keep copy-paste-able, zero infra.
- `mcp/` — the tool surface; stateful `McpAgent` on Cloudflare Durable Objects.
- `api/` — the same actions as x402 HTTP; reports are **always free**.
- `brand/` — SVG is the source of truth; PNGs regenerate via `rsvg-convert`.

## Before money

Play-credits and testnet first. No `$TICKER` stake, prediction payout, or cash prize
before independent legal review. Geofence + age-tier per the compliance spec (DD-08).
