# 2026 FIFA World Cup Tracker

A single-file, self-updating tracker for the 2026 FIFA World Cup (USA · Canada · Mexico). Open it in any browser — no install, no build step, no account.

**Live site:** `https://owlball.github.io/world-cup-tracker/`


---

## What it does

Six tabs cover the whole tournament:

- **Standings** — all 12 groups, sorted by points → goal difference → goals, with FIFA world-ranking badges.
- **3rd-place race** — the cross-group table that decides which four third-placed teams miss out.
- **Results & fixtures** — every group and knockout match, with scores, venues, and cascading filters (by day, group, and team). Each played match expands to show goalscorers and team stats.
- **Stats** — leaderboards for goals, assists, yellow cards, and red cards.
- **Confederations** — participants per confederation, a group/knockout/overall performance table, and a head-to-head record matrix between confederations.
- **Knockout bracket** — a live bracket from the Round of 32 to the final that advances winners automatically (including penalty shootouts), with venues and dates.

Other niceties: light/dark theme toggle, automatic conversion of kickoff times to your local time zone, and country flags.

## How it works

Everything runs in the browser. On load — and every 10 minutes after — the page pulls live scores and goalscorers from ESPN's public World Cup feed and folds them into the display. If that feed can't be reached, it falls back to saved results so the standings, bracket, and stats still render correctly offline.

The whole app is one `index.html` file: HTML, CSS, and JavaScript together, with no dependencies beyond a flag-image library loaded from a CDN. That's what makes it trivial to host as a static page.

## Hosting it yourself (GitHub Pages)

1. Create a **public** repository.
2. Upload `index.html` (the filename matters — Pages serves `index.html` as the homepage).
3. Go to **Settings → Pages**, set the source to **Deploy from a branch**, pick **main / (root)**, and save.
4. After a minute your site is live at `https://YOUR-USERNAME.github.io/REPO-NAME/`.

To update later, replace `index.html` in the repo and commit — the live site refreshes within a minute, and everyone with the link sees the new version.

## Data sources & caveats

- **Live scores & goalscorers:** ESPN's public/undocumented feed. It's not an official API, so it can change or be unavailable; the app degrades gracefully when that happens.
- **FIFA rankings:** a hardcoded snapshot (official list, 11 June 2026), with a best-effort live override.
- **Cards:** goals and assists come from the live feed; per-player card totals are a manually verified list, since no complete per-player card feed is published.
- **Some scorelines are baked in** so the bracket and standings stay correct offline. A few final-group results were reconstructed to match the confirmed qualifiers where an exact score wasn't published; the live feed overwrites any of these if it reports something different.

## Notes

This is an unofficial fan project and is not affiliated with FIFA, ESPN, or any confederation. All trademarks belong to their respective owners.
