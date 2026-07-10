# Lemonade Stand — licensing determination

> **Status:** determination of record (EPIC4-08, 2026-07-10). **No legal-review
> flag raised** — see the conclusion. This is c-archetype build 1: a clean-room
> homage reimplementation of a public-mechanics educational classic.

## The question

Can the studio build and publicly ship a modern web *Lemonade Stand* — the
weather/price/advertising/demand business-sim — without a licensing problem?

## The facts

- **The original.** *Lemonade Stand* was written in **1973 by Bob Jamison of the
  Minnesota Educational Computing Consortium (MECC)** and became a widely
  distributed **Apple II** educational staple (notably a 1979 release). It taught
  a generation the basics of supply, demand, weather risk, advertising, and
  profit.
- **What circulates.** Applesoft BASIC listings of the Apple II version circulate
  as nostalgia. They are a **reference to how the original worked**, not a
  dependency the studio needs or uses.
- **What is protectable vs not.** Game *mechanics and rules* — sell lemonade,
  weather sets demand, price and advertising move sales, unsold cups spoil — are
  **ideas/systems**, not protected expression. What *is* protectable is a specific
  original's **code, text, art, and assets**. The studio uses **none** of those.

## The determination

This build is an **homage reimplementation** of a **public, educational game's
mechanics**, built **clean-room**: the studio's own code, its own copy, its own
design language, its own art — **no original source lines, text, or assets are
copied**. The mechanics (weather multiplier, price elasticity, advertising with
diminishing returns, spoilage of unsold stock) are trivially and independently
reimplementable and are reimplemented from scratch (`site/index.html`).

The history page (`site/history.html`) **attributes the original respectfully** —
MECC, Bob Jamison, 1973/1979, and what the port changed — as homage and
education, not as a claim over the original.

**Conclusion: no legal-review flag.** An homage reimplementation of
public-domain-adjacent *educational game mechanics*, with clean-room code and
respectful attribution and zero copied assets, is well inside safe practice. Were
the studio to copy the original's code, screen text, or art — or trade on MECC's
name as an endorsement — that would change; it does none of these. If a future
session finds a reason (e.g. a trademark on the exact title in the studio's
market), raise the flag then; nothing observed here warrants it.

## Provenance discipline (kept)

- The circulating BASIC listing is **design/history reference only** — read as
  documentation of "how the original worked," never transcribed into the build.
- The studio's build cites **its own** design survey (`survey.md`), not original
  source lines — the same clean-provenance rule the GenMURK rebuild follows.
- Attribution on the history page is honest homage, not affiliation.
