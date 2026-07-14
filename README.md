# The House

Crew scheduling for back and front of house — the two sides that meet at the pass, run from one board.

**Live:** https://gigi-lang.github.io/the-house/

A personal learning project. Single-file, no build step, deployed straight off GitHub Pages — same discipline as [garden-tracker](https://github.com/gigi-lang/garden-tracker).

---

## What it does (v0.1)

- **Schedule board** — a Mon→Sun week × Open / Mid / Close grid. Click any shift to assign crew station by station.
- **Coverage rail** — each shift carries a minimum staffing rule. Unfilled required stations show up as **86'd** slots so gaps read at a glance, the way a chef reads the rail.
- **FOH / BOH at a glance** — front of house in brass, back of house in teal, everywhere on the board.
- **Labor projection** — running cost per shift, per day, and per week, driven by each person's hourly rate.
- **Crew** — add cooks and servers with station and pay rate; a sample crew loads in one click.
- **Orders** — a stub tab holding the seat for a Toast-style layer (tickets, checks, payments) that will ride on the same crew-and-shift data.

Everything is stored locally in your browser (localStorage). Single-user for now.

---

## Stack & conventions

- One self-contained `index.html`. No framework, no build step, vanilla JS.
- State persists to `localStorage` under the key `the-house:v1`, wrapped in try/catch.
- One web font (Bricolage Grotesque) loaded from Google Fonts; falls back to a system font cleanly when offline.
- Deployed via GitHub Pages from the `main` branch root.
- **Deploy:** commit to `main`, then load with a cache-buster before the hash — e.g. `/the-house/?v=1`.
- Short, present-tense commit messages. Bump the version only after the prior one is confirmed live.

## Design tokens

| token | value | use |
|-------|-------|-----|
| `--ink` | `#242a27` | seasoned charcoal-green, primary text |
| `--paper` | `#f2ece0` | manila / ticket-paper background |
| `--card` | `#fbf7ee` | lighter ticket surface |
| `--foh` | `#b8763a` | front of house — warm brass |
| `--boh` | `#3f6b6e` | back of house — fired teal |
| `--flag` | `#c1442e` | 86'd — a station short |
| `--ok` | `#4a7a52` | fully covered |

---

## Roadmap

- **Per-day / per-shift coverage rules** — a Friday close needs more than a Tuesday open.
- **Multi-user** — staff read their own schedule; Firebase (Spark) sync, same path chosen for garden-tracker.
- **Editable stations & shift blocks** — customize roles, hours, and times to a real spot.
- **Availability & time-off requests.**
- **The Orders layer** — the Toast-style build, mounted on the crew-and-shift spine.

---

*v0.1 — where back of house meets front of house.*
