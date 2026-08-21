# Durango → Steamboat, Aug 21–23 2026

A three-day drive guide, built to be read on a phone with no signal.

**Live guide:** `https://<username>.github.io/<repo>/`

## What's here

| File | What it is |
|---|---|
| `index.html` | The guide. Self-contained — one file, no build step, no dependencies except web fonts. |
| `PLANNING.md` | The decision log. Constraints, what got ruled out, and why. Read this before changing the route. |
| `CHANGELOG.md` | What changed between revisions of the plan. |

## Publishing

Settings → Pages → Source: **Deploy from a branch** → `main` / `root`. Live in about a minute.

The guide loads fonts from Google Fonts. Everything else is inline, so it renders offline once cached — open it on the phone over wifi before leaving, and it will work on Red Mountain and CO-13 where signal drops.

## Editing

`index.html` is hand-written HTML with a `<style>` block at the top. Structure:

- Each day is a `<section class="day" id="fri|sat|sun">`
- Each stop is a `<div class="stop">` with a time/elevation column and a body column
- `class="stop light"` marks a golden-hour or sunset stop (renders the heading in oxide red)
- `<span class="tag">` for a short label; add `moss` for the green variant
- `<div class="swap">` for an inline alternative or caveat

To retime a stop, edit the `<div class="t">` value. To add one, copy an adjacent `.stop` block. The elevation profile at the top is a hand-plotted SVG path — if the route changes materially, the path coordinates need updating too, or delete the block.

## Iterating with Claude

Paste this to pick up where the planning left off:

> I'm planning a road trip and tracking it in a repo. Here's the current state — read PLANNING.md for the constraints and decision log, and index.html for the itinerary. [paste both]
>
> Hard constraints: dog along, paved roads only, fixed lodging. Don't re-propose anything in the "Ruled out" section without saying why the reason no longer holds.

The last line matters. Without it the same rejected options resurface every session.

## Post-trip

The interesting version of this repo is the one edited *after* the drive: which timings were wrong, which stops were worth it, what the weather actually did. That's the part worth having next year.
