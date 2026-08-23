# Durango → Steamboat → Pagosa, Aug 21–28 2026

An eight-day trip guide — three days driving in, three and a half based in Steamboat, then the way back splits over two shorter days via a Buena Vista layover to a show in Pagosa Springs — built to be read on a phone with no signal.

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

To retime a stop, edit the `<div class="t">` value. To add one, copy an adjacent `.stop` block. The elevation profile at the top is a hand-plotted SVG path — if the route changes materially, the path coordinates need updating too, or delete the block.

**Archiving (added Aug 22, extended same day).** Anything tagged `data-until="YYYY-MM-DD"` gets checked against the viewer's own device clock on every page load and archived once that date has fully passed — nothing on the page hardcodes "today." Two things carry this attribute:
- **Day sections** (`<section class="day" ...>`) collapse to just `.day-head` + `.day-note` with a "Show details" toggle. Everything else inside the section needs to live in a `<div class="day-body">…</div>` for this to work — copy that wrapper along with the stops if you add a new day section. Granularity is per-section, not per-sub-day: the Mon–Wed Steamboat section archives as one block once Wednesday passes.
- **Watch-list items** (`<li data-until="...">` inside `.watch`) hide entirely once resolved, rather than collapsing — a reminder about Friday's altitude or Saturday's Red Mountain check is just noise once that day's gone, not something worth a "show details" toggle. If a reminder spans multiple days (e.g. "fuel in Durango Friday, fuel in Rifle Sunday"), give it the *last* relevant date so it stays up until it's actually done.

Both use the same `isPast()`/`wireStatus()` machinery in the script block — a "N of M done, Show archived" line appears in the header for days and above the watch list for reminders, once at least one of each exists.

## Iterating with Claude

Paste this to pick up where the planning left off:

> I'm planning a road trip and tracking it in a repo. Here's the current state — read PLANNING.md (start with "Right now" at the top) and index.html for the itinerary. [paste both]
>
> Hard constraints: dog along, paved roads only, fixed lodging. Don't re-propose anything in the "Ruled out" section without saying why the reason no longer holds.

The last line matters. Without it the same rejected options resurface every session.

**On the road, keep it light.** A correction ("I'm actually staying at X instead") only needs the "Right now" table and `index.html` updated immediately, plus one line in the Log. It doesn't need a full "Ruled out" writeup in the same breath — that can happen later, once, in a batch. Trying to fully reason through every change in real time from a phone is what made this hard to keep up to date in the first place.

## Post-trip

The interesting version of this repo is the one edited *after* the drive: which timings were wrong, which stops were worth it, what the weather actually did. That's the part worth having next year.
