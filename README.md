# MILES — Arbitrum Dogs

The website for **$MILES**, a meme coin on Arbitrum One named after Miles, a
liver-and-white English Springer Spaniel who sits by the desk in an Arbitrum shirt.

Live at **https://miles-arbitrum-dogs.vercel.app**

A single self-contained static page. No build step, no dependencies, no framework.

```
index.html          the whole site — markup, styles and scripts in one file
assets/miles.jpg    Miles' portrait (also used as the favicon)
assets/miles2.jpg   the wide hero banner
vercel.json         cache and security headers
```

## Before you launch — two things to fill in

The page ships with placeholders. Search `index.html` for each and replace it:

| What | Placeholder | Where |
| --- | --- | --- |
| Contract address | `0x0000000000000000000000000000000000000000` | `<p class="ca__value" id="ca-value">` |
| Social links | `href="#"` | the hero `.btn-row` and the footer `.foot__links` |

There are five `href="#"` links to fill: **Chart**, **Telegram** and **X** in the
hero, then Telegram, X, Dexscreener, Arbiscan and Uniswap in the footer.

If the site moves to a custom domain, update the absolute origin in the `<head>` —
`canonical`, `og:url`, `og:image` and `twitter:image` all point at
`https://miles-arbitrum-dogs.vercel.app`. Link previews on X, Telegram and Discord
will not resolve a relative image URL, so these have to stay fully qualified.

The tokenomics in the *Token* section (1,000,000,000 supply, 0/0 tax, LP burned,
ownership renounced) are the conventional fair-launch defaults. Confirm each one
against the deployed contract and correct anything that differs.

## Design

Arbitrum's chain colours carry the page, warmed by Miles' own coat so it doesn't
read as a generic blue crypto site:

| Token | Hex | Role |
| --- | --- | --- |
| `--bg` | `#0B1420` | deep navy ground |
| `--line` | `#213147` | Arbitrum dark blue, borders |
| `--arb` | `#12AAFF` | Arbitrum light blue, the accent |
| `--liver` | `#B4713F` | Miles' liver coat, counter-accent |
| `--ink` | `#EFE7DF` | warm cream text |

Type is Archivo (variable width, set wide to echo the lettering in the banner),
Instrument Sans for body copy, and JetBrains Mono for the contract address and
stats.

The drifting speckle texture in the background is **ticking** — the flecked
marking on Miles' legs and chest that English Springers are known for. It is
generated on a canvas: one seamless tile of flecks built once, then panned as a
repeating pattern, so it costs a single `fillRect` per frame. It holds still for
anyone with `prefers-reduced-motion` set.

Both themes are defined at token level, covering all three viewer states — light,
dark, and the unstamped system default.

## Local preview

Any static server works:

```bash
python -m http.server 8000
# then open http://localhost:8000
```

## Deploy

Pushed to `main` deploys automatically. Or from the CLI:

```bash
vercel --prod
```

## Disclaimer

$MILES is a meme coin made for entertainment, with no intrinsic value and no
expectation of return. Nothing on the site is financial advice. It is not
affiliated with or endorsed by Offchain Labs, the Arbitrum Foundation, or the
Arbitrum DAO — the Arbitrum name and colours appear only to identify the network
the token runs on.
