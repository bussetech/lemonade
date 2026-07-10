# lemonade

**Status:** ![status](https://img.shields.io/badge/status-active-00843D) ·
[![ci](https://github.com/bussetech/lemonade/actions/workflows/ci.yml/badge.svg)](https://github.com/bussetech/lemonade/actions/workflows/ci.yml)
· **Site:** <https://lemonade.bussetech.com> · **Visibility:** `public`

Lemonade Stand — a modern, mobile web homage to the classic MECC educational business game (1973). Faithful mechanics, clean-room and respectfully attributed; the day's stand is worked by a rotating studio gnome.

A [Bussetech Software Studio](https://bussetech.com) project: a small,
self-contained web game — the studio's **c-archetype build 1** (a clean-room
homage to a public educational classic). Play it at
<https://lemonade.bussetech.com>.

## Layout

| path | what |
| --- | --- |
| `index.html` | the game — self-contained (inline CSS + vanilla JS), no external assets, plays offline |
| `history.html` | honest history of the 1973 MECC original and this homage port |
| `igotchi.snapshot.json` | display snapshot of studio gnomes; the day's stand is worked by one (render-side only) |
| `docs/founding/` | licensing determination, design survey, founding record |
| `_posts/` | site posts — each becomes a `/feed.json` item the studio portal aggregates |
| `.github/workflows/` | thin callers into the studio's shared CI + the Pages deploy |

The mechanics (weather, price, advertising, demand, spoilage) are a clean-room
reimplementation of public game ideas — no original code or assets were used.
See `docs/founding/licensing.md`.

## Build locally

```sh
bundle install
bundle exec jekyll serve      # http://127.0.0.1:4000
```

No studio access needed — the theme and CI machinery are public. See
`CLAUDE.md` for how this repo fits the studio (and how it detaches from it).

## Licenses

Code: MIT (`LICENSE`). Published datasets: CC BY 4.0 — license and
provenance statements live in `data/index.md`.
