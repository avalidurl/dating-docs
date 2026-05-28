# dating-docs — brand datasheet (DD-09)

Register: **markdown love letters × clinical deadpan — abstract, not cringe.** Influences,
named and obeyed: **Tufte** (data-ink, sparklines, small multiples, restraint), **Diátaxis**
(tutorial / how-to / reference / explanation), **US Graphics Company** clarity (austere,
monochrome, mono, timeless). Sibling to Plaintext Capital; its own motif.

## Motif — romance as a merge

Two branches → one document. Two heart-files merge into one couple-doc. The logo *is* a
merge mark: two author-heads, one madder bond-node, one trunk (the shared doc). Romance as
version control. No hearts, no roses, no gradients.

## Palette

| Token | Hex | Use |
|---|---|---|
| `--dd-ink` | `#14110E` | warm near-black; text, marks |
| `--dd-paper` | `#F3EEE3` | bone manuscript ground |
| `--dd-madder` | `#8A2B2B` | **the only brand accent** — the merge node; ≤10% of any surface |
| `--dd-margin` | `#8C857A` | annotation gray; metadata, rules, captions |
| `--dd-committed` | `#2E3A52` | **data only** — 'committed' state in charts; never chrome |

## Type

IBM Plex Mono (system voice, free) / Berkeley Mono (licensed ideal) / Menlo (stand-in).
IBM Plex Serif **only** for long-form datingdoc letter bodies. Wordmark + UI + part numbers
are always mono.

## Voice — the deadpan bureau

"Bureau of Mutual Documentation." Part numbers `DD-NN`. Dry, sincere, no winking.
> "A couple-doc is a merge commit between two souls. It is append-only — love does not rebase."

## Files

| File | What |
|---|---|
| `dd-mark.svg` | primary merge mark |
| `dd-mark-coin.svg` | token coin (for `$TICKER`) — mark in a struck ring |
| `dd-badge.svg` | avatar — mark on a bone disc with ink ring |
| `dd-lockup.svg` | wordmark lockup with datasheet frame + part number |
| `tokens.css` | palette + type as CSS custom properties |

SVG is the source of truth. Regenerate PNGs:

```sh
rsvg-convert -w 1024 dd-mark.svg      -o dd-mark-1024.png
rsvg-convert -w 1024 dd-mark-coin.svg -o dd-mark-coin-1024.png
rsvg-convert -w 512  dd-badge.svg     -o dd-badge-512.png
rsvg-convert -w 256  dd-badge.svg     -o dd-badge-256.png
rsvg-convert -w 1600 dd-lockup.svg    -o dd-lockup-1600.png
```

## House chart language (Tufte)

- **Couple lifeline** — a per-couple sparkline (tick = valid day, gap = silence, madder = milestone).
- **Small multiples** — a grid of lifelines = a season at a glance.
- **Market dot-plot** — each feasible pair a dot at its market-implied score; matched filled, infeasible hollow.
- No pie charts, no 3-D, no chartjunk. Direct labels over legends.

## Don'ts

Hearts, roses, blush gradients, cursive, "find your match!" energy, emoji, stock couples.
The romance lives in the *document* and the *data*, never the chrome.
