# Durango → Steamboat → Pagosa → Durango, Aug 15–30 2026

A trip guide covering a Durango prologue, three days driving north, three and a half based in Steamboat, then the way back splits over two shorter days via a Buena Vista layover to a show in Pagosa Springs, then one more short hop back to Durango to close the loop — built to be read on a phone with no signal.

**Live guide:** `https://<username>.github.io/<repo>/`

## What's here

| File | What it is |
|---|---|
| `index.html` | The guide. Self-contained — one file, no build step, no dependencies except web fonts. |
| `PLANNING.md` | Everything else. Starts with a **"Right now" status table** — the only part worth reading on the road. Below that: constraints, what got ruled out and why, and a one-line-per-change log (this used to be a separate CHANGELOG.md; merged Aug 22 because two files was one too many to keep in sync from a phone). |

## Publishing

Settings → Pages → Source: **Deploy from a branch** → `main` / `root`. Live in about a minute.

The guide loads fonts from Google Fonts. Everything else is inline, so it renders offline once cached — open it on the phone over wifi before leaving, and it will work on Red Mountain and CO-13 where signal drops.

## Editing

`index.html` is hand-written HTML with a `<style>` block at the top. Structure:

- Each day is a `<section class="day" id="fri|sat|sun|week|thu|pagosa">`
- Each stop is a `<div class="stop">` with a time/elevation column and a body column
- `class="stop light"` marks a golden-hour or sunset stop (renders the heading in oxide red)
- `<span class="tag">` for a short label; add `moss` for the green variant
- `<div class="swap">` for an inline alternative or caveat

To retime a stop, edit the `<div class="t">` value. To add one, copy an adjacent `.stop` block. The elevation profile at the top of most day sections is a hand-plotted SVG path — if the route changes materially, the path coordinates need updating too, or just leave the block out (the return-to-Durango section has none, since there's no confirmed pass on that leg worth inventing coordinates for).

**Timeline (replaced the old collapse/archive UI on Aug 24).** All `<section class="day" ...>` elements live inside one `<div class="timeline">…</div>` and are always fully visible, photos and all — nothing on the page hides itself anymore. `data-until="YYYY-MM-DD"` is still on every day section and on each `<li>` in the watch list, but it now only drives two lightweight, always-reversible things, computed fresh against the viewer's own device clock on every page load (nothing hardcodes "today"):
- **Day sections** get a `.past` class (dims the timeline marker dot to moss) once their date has fully elapsed, a `.today` class on the current day (oxide marker), and a small "done" badge. The first non-past day also gets a `.today-marker` divider inserted just above it.
- **Watch-list items** get `.archived` once resolved, which just dims them via CSS opacity — they stay in the DOM and readable, never disappear.

Both passes share the same `today = new Date()` computed once per load, plus a shared `isPast()` helper, in the script block at the end of the file.

**Trip map (added Aug 31).** A hand-plotted schematic SVG (`.tripmap`, `.tm-node`, `.tm-route`) above `<nav>` — not to scale, but each stop's x/y is derived from real lat/lon so the shape is roughly honest, not just a straight line in visit order. Each `.tm-node` carries its own `data-until` and `data-target` (a section id) — colored past/today by the same `isPast()` pass as everything else, tap/click scrolls to the target section (respects `prefers-reduced-motion`, same pattern as the right-now bar). To add a stop: pick x/y by eye relative to the existing points (west/south is smaller x, north is smaller y), add a `.tm-node` `<g>`, and extend the `.tm-route` path's `d` attribute to route through it in visit order.

**Right-now bar (added Aug 26).** A sticky bar (`#nowBar`) pinned above `<nav>` always shows the current weekday/date and what's on, and jumps straight there on tap. For multi-day sections it matches the real weekday against that section's `.subday` divider text (e.g. lands on "Wednesday · water day" inside the Mon–Wed block, not just the block itself) — so if you add a new multi-day section, keep `.subday` text starting with the actual weekday name (`"Wednesday · ..."`), or the match silently falls back to the whole-section `.day-meta` text instead. Logic lives at the end of the script block, right after the today/past marking loop — it reuses the same `.day.today` element rather than recomputing "today" a second way.

## Iterating with Claude

Paste this to pick up where the planning left off:

> I'm planning a road trip and tracking it in a repo. Here's the current state — read PLANNING.md (start with "Right now" at the top) and index.html for the itinerary. [paste both]
>
> Hard constraints: dog along, paved roads only, fixed lodging. Don't re-propose anything in the "Ruled out" section without saying why the reason no longer holds.

The last line matters. Without it the same rejected options resurface every session.

**On the road, keep it light.** A correction ("I'm actually staying at X instead") only needs the "Right now" table and `index.html` updated immediately, plus one line in the Log. It doesn't need a full "Ruled out" writeup in the same breath — that can happen later, once, in a batch. Trying to fully reason through every change in real time from a phone is what made this hard to keep up to date in the first place.

## Post-trip

The interesting version of this repo is the one edited *after* the drive: which timings were wrong, which stops were worth it, what the weather actually did. That's the part worth having next year.
