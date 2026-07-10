# Lemonade Stand — founding record (c-build 1)

> **Status:** founding record (EPIC4-08, 2026-07-10). The game is **built and
> verified** (`site/`); founding the `lemonade` repo + DNS + Pages is a
> **sysop/FACTORY_TOKEN act** (ADR-0008/0013) — proposed here, executed by the
> sysop. c-archetype build 1 (the clean-room simple-port).

## What shipped (built this session, staged in `site/`)

A complete, self-contained modern web *Lemonade Stand*:

- `site/index.html` — the game. Inline CSS + vanilla JS, **zero external assets,
  zero network** (CSP-safe, plays offline / from `file://`). Faithful mechanics
  (weather multiplier, price elasticity, advertising with diminishing returns,
  spoilage of unsold cups), integer-cents money, 7-day run, honest end summary.
  Verified: `node --check` OK; full-run trace sane (washout event → 0 sales;
  cash stays integer and finite).
- `site/history.html` — honest history honoring the original (MECC / Bob Jamison,
  1973/1979) and what the port changed.
- `site/igotchi.snapshot.json` — a trimmed 8-gnome display snapshot for the
  attendant render.
- `site/README.md` — seed description + firewall note.

Studio design language, mobile-sane, accessible, `bussetech | software studio`
footer + history link.

## The gnome shift (display-only charm — ADR-0036 firewall)

Each game-day the stand shows **today's attendant**: a studio gnome drawn from
igotchi display data (`glyph` + `display_name` + `stage`, rotating by day index —
`gnomes[(day-1) % len]`). It is **strictly render-side**: the game *reads*
`igotchi.snapshot.json` (the live game would fetch the project's `igotchi.json`);
**nothing ever flows back** into any gnome/igotchi file. The HTML carries the
required firewall comment. This is a live demo of the workforce brand inside a
playable artifact (the showcase, 12, will use it); the firewall sentinel
(`scripts/igotchi-firewall.sh`) stays green — the game is in no harness context
path and writes nothing inbound.

## Registry entry (proposed — activates on the founding merge)

```yaml
  - name: lemonade
    subdomain: lemonade         # lemonade.bussetech.com
    status: active
    description: "Lemonade Stand — a modern, mobile web homage to the classic MECC educational business game (1973). Faithful mechanics — weather, price, advertising, demand, spoilage — clean-room and respectfully attributed; the day's stand is worked by a rotating studio gnome."
    visibility: public
    listed: true
    archetype: brownfield       # entered via the brownfield practice (homage reimplementation of a legacy design)
    client: false
```

Not committed live this session (registering *is* the act of creation; the repo
does not exist yet) — it lands with the sysop's founding act. **Note:** the
factory today founds `archetype: info` via the form; **brownfield is a console
adoption** (`docs/new-project.md`) — so `lemonade` is founded via the console
`scripts/new-project.sh lemonade --description "…" --visibility public`, then the
game seeded from `site/`, or via the founding issue filed this session.

## Receipts, feed, portal card (on founding)

- **Receipts:** the build is reproducible from `site/` (static, offline). Once
  founded and served, the go-live checklist issue tracks HTTPS/Pages.
- **Feed:** a `_posts/` founding entry surfaces it on the portal (JSON Feed 1.1,
  `docs/feeds.md`).
- **Portal card:** the `listed: true` registry entry renders on the portal with
  zero `www` changes (ADR-0012).

## What is sysop-gated

- Founding the `lemonade` repo + DNS + Pages (admin/FACTORY_TOKEN).
- Merging this PR (GD-0019).
- Seeding the founded repo from `site/` (a follow-on push once the repo exists).
