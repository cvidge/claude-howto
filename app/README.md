# Claude Code Quest — interactive learning app

A self-contained, gamified companion app for this repository. One file, no build step,
no dependencies: open `index.html` in any browser. On an iPad, open it in Safari and
use **Share → Add to Home Screen** to install it as a full-screen app.

## What it is

Twelve quest stations covering the full curriculum (modules `01`–`10` in the
repository's recommended learning order, plus a First Contact intro and an
Automation & CI capstone). Every station has the same predictable shape:

1. **Learn** — tap-to-reveal concept cards
2. **Quiz** — multiple choice, command builders, and match-pairs with instant feedback
3. **Boss** — 6 reshuffled questions, no retries, badge on victory
4. **Ship it** — a concrete "do this at work today" action worth bonus XP

Gamification: XP, 12 level titles, badges, daily streaks, combo multipliers, and a
"memory vault" that recycles missed questions until they stick (lightweight spaced
repetition). Progress is stored in `localStorage` on the device.

Accessibility was a first-class design goal (ADHD- and autism-friendly): one item on
screen at a time, the same structure everywhere, literal microcopy, no timers, no
sound, optional break check-ins, and settings for motion, celebrations, theme, and
text size. `prefers-reduced-motion` is respected automatically.

## Sources

Curriculum content is distilled from this repository's modules and cross-checked
against the [official Claude Code documentation](https://code.claude.com/docs).
Start with the repository's [learning roadmap](../LEARNING-ROADMAP.md) if you prefer
reading the source material directly.

## Evolving the app

All content lives in the `MODULES` array inside `index.html` — plain data, no
framework. To add a card, a question, or an entire new station, append to that
array; the map, XP economy, bosses, and badges pick it up automatically. Question
types: `mcq` (works for true/false and scenarios), `build` (compose a command or
path from chips), and `match` (pair matching).
