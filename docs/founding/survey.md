# Lemonade Stand — intake-style design survey

> **Provenance.** A **console-executed** application of the `gn_intake_surveyor`
> stance (EPIC4-06) to the *reference design* of the classic MECC *Lemonade
> Stand* — not a receipt-backed live gnome run, and not a survey of a studio
> repo (there is no adopted codebase; the "codebase" is one circulating BASIC
> file used as **design documentation only**, never transcribed). Brownfield
> discipline practiced even when the source is a single file. Doubles as the
> source material behind the history page (`site/history.html`).

## What it is

*Lemonade Stand* is a **single-player, turn-based business simulation** teaching
elementary economics. A run is a sequence of days; each day the player makes
supply/pricing/marketing decisions against a weather forecast and a demand
response, and learns from the profit/loss.

## Mechanics, decomposed (the behavior to reimplement)

- **The day loop.** Forecast → decisions → simulate sales → report → next day.
- **Weather.** A forecast (sunny / hazy / hot-and-dry / cloudy / storms) sets a
  base **demand multiplier**; hot-and-dry is peak, storms suppress or wash out.
- **Player decisions.** Price per cup; how many cups to make (each costs
  ingredients paid up front); how much advertising to buy.
- **Demand response.** Sales fall as price rises (price elasticity) and rise with
  advertising (diminishing returns), scaled by weather and a little randomness.
- **Settlement.** Cups sold = min(made, demanded); revenue = sold × price;
  **unsold cups spoil** (the core lesson — overproduction is a real loss); profit
  = revenue − ingredient cost − advertising cost; carry the cash balance forward.
- **Events.** Occasional one-off shocks (heat wave, storm washout, street closed,
  a competitor) that perturb a day.

## Adoption lanes (the intake frame, applied)

- **Adopt-now / build:** the mechanics above — public, trivially reimplementable,
  clean-room (`site/index.html`). Studio design language, mobile-sane, `archetype:
  brownfield`, `public`, maturity rung 1.
- **Modernize (what the port adds):** a web/mobile UI; integer-cents money (no
  float bugs); a rotating **studio-gnome attendant** rendered from live igotchi
  data (display-only; ADR-0036 firewall — the game *reads* gnome display data,
  nothing flows back); accessibility (labels, contrast, keyboard).
- **Leave alone (resist — guardrail):** anything the original didn't teach.
  Lemonade stays an afternoon-scale classic, not a platform. No accounts, no
  multiplayer, no economy beyond the one lesson.

## Licensing

Resolved in `licensing.md`: an **homage reimplementation** of public educational
mechanics, clean-room, respectfully attributed — **no legal-review flag**. The
circulating BASIC listing is design/history reference only.

## Risk notes

- **None of substance.** No untrusted input (single-player, offline, no
  network), no secrets, no PII, no data pipeline. The one discipline that matters
  is the **igotchi firewall**: the attendant render must stay strictly read-side
  (the sentinel `scripts/igotchi-firewall.sh` stays green). Verified in the seed
  (a bundled snapshot the game only reads).
