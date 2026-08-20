# MILES

The website for MILES, a meme coin on Arbitrum One named after Miles, an English
Springer Spaniel who sits by the desk in an Arbitrum shirt.

Live at https://miles-arbitrum-dogs.vercel.app

One self contained static page. No build step, no dependencies, no framework.

```
index.html          the whole site, markup and styles and script in one file
assets/miles.jpg    Miles' portrait, also used as the favicon
assets/miles2.jpg   the wide banner strip
vercel.json         cache and security headers
```

## Token

| | |
| --- | --- |
| Contract | `0x6beadFCC25F6BC71C158a4Bff85bf2F1746D2ca7` |
| Network | Arbitrum One |
| Total supply | 1,000,000,000 at 18 decimals |
| Pair | Uniswap, against WETH |
| Pair address | `0x06f2d9e061dfc85561595e79022531ce099d1501` |

Every figure above was read off the contract and the Uniswap pair, not assumed.
If you add anything to the token section, verify it the same way first.

## Design

Arbitrum's chain colours carry the page, warmed by the brown of Miles' coat so it
does not read as a generic blue crypto site. One committed dark look, no light
theme.

| Token | Hex | Role |
| --- | --- | --- |
| `--navy` | `#0E1626` | ground |
| `--card` | `#16233A` | panels |
| `--line` | `#27395A` | borders |
| `--blue` | `#12AAFF` | Arbitrum blue, the accent |
| `--liver` | `#C4834E` | Miles' coat, counter accent |
| `--cream` | `#F5F0E8` | text |

Type is Anton for the big poster headlines, Figtree for body copy, and JetBrains
Mono for the contract address and labels.

The page is plain ASCII throughout on purpose. No em dashes, no slash separators,
no box drawing characters in the comments. Keep it that way when you edit it.

## Local preview

```bash
python -m http.server 8000
```

Then open http://localhost:8000

## Deploy

Pushing to `main` deploys automatically. From the CLI:

```bash
vercel --prod
```

If the site moves to a custom domain, update the absolute origin in the `head`.
The `canonical`, `og:url`, `og:image` and `twitter:image` tags all point at
`https://miles-arbitrum-dogs.vercel.app` and link previews on Telegram, Twitter
and Discord will not resolve a relative image path.
