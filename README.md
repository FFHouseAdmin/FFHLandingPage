# Firm Foundation House — firmfoundationhouse.org

Landing page for Firm Foundation House, a faith-based residential ministry in Phelan, CA.
**Rebuilt on the Rock.**

## What's here

- `index.html` — the entire site. One self-contained file: all CSS, JS, and images (logo embedded as data URIs) are inline. No build step, no dependencies beyond Google Fonts at runtime.
- `.nojekyll` — tells GitHub Pages to serve files as-is.

## Platform decisions (Sept 2026)

- **Giving: Zeffy** (zeffy.com) — $0 platform/processing fees; cards, Google Pay, ACH for large one-time gifts; monthly recurring by card.
- **Email capture: Zeffy** as well — its free email tools share one contact database with donors.

## Wiring status (complete)

1. **Giving — WIRED.** Every Give button opens the Zeffy donation form in an **on-page popup** (`GIVING_EMBED_URL`, loaded only when opened). The hosted form (`GIVING_URL`) remains the fallback: it's the button `href` for no-JS/modified clicks, and the popup's "Prefer Apple Pay? Open in Zeffy" link. Google Pay works inside the popup (the iframe carries `allow="payment"`); Apple Pay is Safari-only and needs the hosted page.
2. **Email signup — WIRED.** The Zeffy newsletter embed is in place (with a fallback iframe if the embed script fails to load).

One item remains for later: the **video** — search for `VIDEO EMBED` and replace the placeholder frame with the YouTube/Vimeo embed when Mark's testimony film is ready.

The contact form needs no backend — it opens the visitor's email app addressed to admin@firmfoundationhouse.org.

## Hosting

GitHub Pages: Settings → Pages → deploy from `main`, folder `/ (root)`. Custom domain (firmfoundationhouse.org, registered via Bizee) is pointed at Pages via DNS records; if a `CNAME` file appears in this repo after that step, leave it in place.

## Updating the site

Replace `index.html` with the new version and commit with a short note saying what changed. Pages redeploys automatically within a minute or two. The commit history is the change log.
