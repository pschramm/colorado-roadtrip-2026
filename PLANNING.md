# Planning notes

The itinerary is in `index.html`. This file is why it looks the way it does.

## Right now

*Last updated Aug 26 (mid-trip, based in Steamboat). This is the one block worth reading on the road — everything below is the reasoning archive, not the status.*

| Night | Where | Status |
|---|---|---|
| Sat 15 | Motel 6, Clovis, NM (1616 Mabry Dr) | done |
| Sun 16 – Fri 21 | La Quinta, Durango (125 Mercury Village Dr) | done, 6 nights |
| Fri 21 | Altus Lodge, Silverton | done |
| Sat 22 | Ore House Inn, New Castle | done |
| Sun 23 – Wed 26 | La Quinta, Steamboat Springs (3155 Ingles Ln) | checkout Thu morning |
| Thu 27 | Super 8, Buena Vista (530 N US-24) | confirmed |
| Fri 28 | Motel SOCO, Pagosa Springs (651 W US Hwy 160) | confirmed |
| Sat 29 | Baymont by Wyndham, Durango (3255 Main Ave) | confirmed, checkout date unclear — see open items |
| Sun/Mon 30/31 – Wed 2 | Durango, extended stay | **not booked** |
| Thu 3 – Fri 4 | El Rey Court, Santa Fe (1862 Cerrillos Rd) | **not booked** |

**Fixed points:** Thu 27, ~6pm — Carlos, The Slammer, Buena Vista. Fri 28, 7pm — Mike Dillon Band, Motel SOCO. Fri Sep 4, 6–10pm — Cactus Lee / Swarming Branch, El Rey Court Event Lawn, Santa Fe (free).

**Open items:**
- Super 8 Buena Vista's calendar booking still covers Thu *and* Fri nights, but Fri night is now Motel SOCO — check whether that second Super 8 night needs cancelling.
- **Baymont Durango checkout date is ambiguous.** The confirmation email (Wyndham, #91458EE045225, received Aug 25) explicitly states "1 Room(s) / 1 Night(s)" with check-in Sat Aug 29 and checkout Sun Aug 30. But the Google Calendar event auto-created from that same email spans Aug 29 → Aug 31 (2 nights, same pattern as the Super 8 event, which does correctly show 2 nights for a checkout-Sat-29 booking). Real discrepancy between the email text and Google's own parse of it — not resolved by rereading either source again. Call the front desk ((970) 247-5200) or check the Wyndham app before Aug 29 to know whether the trip actually ends Sunday or Monday.
- Room booked: 1 King Bed, Deluxe Suite, non-smoking, $157.20 total for (at least) one night. Dog fee found separately (BringFido/Expedia/ReservationDesk, not the confirmation email): $20/pet/night, up to 2 pets — not yet confirmed directly with the property.
- **Durango lodging gap, Aug 30/31 – Sep 2.** Added Aug 26: user decided to stay in Durango through Wednesday night rather than head straight to Santa Fe, to catch Cactus Lee there Friday. Up to four nights with nowhere booked — whether that's extending the Baymont stay, a different Durango hotel, or something else hasn't been decided.
- **El Rey Court, Santa Fe — not booked.** Two nights (Thu–Sat checkout) needed before the Thursday-morning departure from Durango. Address and dog policy (1 dog any size, or 2 up to 70lbs, $50/stay) confirmed via BringFido; nothing reserved.
- **What happens after the Sep 4 Santa Fe show is undecided.** Asked the user directly (round trip back to Durango, vs. continuing toward the Sept 5 Austin→Raleigh flight already on the calendar) and got an answer only on the Durango-nights question, not this one. Don't assume either direction — the guide currently stops at Santa Fe with this explicitly open.
- The Durango week (Aug 16–21) is now fully filled from Google Photos, not memory — all six days: Sun (Animas River Trail evening walk), Mon (Balcony Bar & Grill), Tue (Avalanche Bowl Company, 11th Street Station), Wed (Anarchy Brewing), Thu (Dallabetta Park), Fri (checkout, already covered by "Leave Durango" in the Friday section). Each confirmed by matching the photo's embedded GPS against the actual venue on Google Maps — see "Photo-sourced Durango content" below for the method. Google Photos' web UI is fragile to drive programmatically (scroll position resets, photo viewer sometimes needs 2-3 open attempts, Escape can kick all the way back to the library root) — budget for retries if repeating this. (Two calendar entries in the same window — "taos?" and a show at "Vacancy" — were initially pulled in as trip content and then removed: both were logged in Central time, not Mountain, meaning they're unrelated personal calendar entries that happened to fall in the same date range, not part of this trip. Don't re-pull calendar events into the guide without checking timezone/location match the trip first.)
- **In progress, not yet pushed:** embedding actual photos (not just text) into the Durango stops. Two captured so far via the browser's screenshot save (actual file download doesn't work — the automated Chrome runs in a sandbox separate from the filesystem Bash can reach): Sunday's river photo and Thursday's Dallabetta Park photo, sitting in `img/` uncommitted and not yet wired into `index.html`. Paused mid-capture (Wed/Mon/Tue still needed) to push the text content first since the user was mobile and wanted it live. Pick this back up if photos are still wanted.
- Expense tracking: user asked about linking a Capital One login to track meal/gas spend. Declined — no banking connector available, and entering financial credentials isn't something this assistant does regardless. Offered two alternatives, neither set up yet: (1) a manual running log the user texts amounts to, (2) parsing a bank-exported CSV the user provides directly (no credentials involved). Pick one if this is still wanted.

**Updating this on the road:** tell me what changed (a new booking, a cancelled plan, a corrected time). I'll update this table and `index.html` right away. Full reasoning in the sections below gets added when there's time — it doesn't have to happen in the same message.

## Fixed constraints

These drove every decision. Changing one invalidates a lot of what follows.

- **Dog along the whole way.** Rules out the Silverton–Durango train, the Ouray Hot Springs pool, Glenwood Hot Springs and Iron Mountain, Hanging Lake, Chimney Rock, and trails inside Mesa Verde and Colorado National Monument. Roads and overlooks only at NPS sites. Extends into the Steamboat week and Pagosa leg (see below).
- **Paved roads only.** Regular car. No gravel or dirt, including short spurs.
- **Steamboat check-in is Sunday.** Friday and Saturday nights both had to be solved on the road.
- **Friday departure ~noon.** Roughly five usable hours of daylight driving, not nine.
- **Lodging booked:** Altus Lodge, Silverton (Fri Aug 21). Ore House Inn, New Castle (Sat Aug 22). La Quinta Inn & Suites by Wyndham, 3155 Ingles Ln, Steamboat Springs (Sun Aug 23 check-in, **checkout Thu Aug 27 morning** — 4 nights, Sun–Wed, confirmed directly from the calendar booking, address confirmed correct against an earlier wrong "S Lincoln Ave" guess). Super 8 by Wyndham, 530 N US-24, Buena Vista (**Thu Aug 27 night**, confirmed — Thursday's stop). Motel SOCO, 651 W US Hwy 160, Pagosa Springs (**Fri Aug 28 night**, confirmed directly by the user). Baymont by Wyndham, 3255 Main Ave, Durango (**Sat Aug 29**, confirmation #91458EE045225 pulled directly from the Wyndham confirmation email once Gmail access was reconnected to the correct personal account on Aug 26 — checkout date unclear, see open items above). **Open item:** the Super 8 Buena Vista calendar booking spans Thu+Fri nights (checkout Sat 29), but Friday night is now Motel SOCO — the second Super 8 night is likely unused/redundant. Not resolved; flagged in the guide's watch list rather than assumed away.
- **Camera:** Fuji X-E5, 23mm and 33mm. Wide for passes and lakes, normal for towns, falls, and the dog.
- **Fixed tentpole: Fri Aug 28, 7pm set.** The Mike Dillon Band (feat. Kris Myers, Brian Haas) at Motel SOCO / El Camino Lounge, Pagosa Springs — again the same address as that night's lodging, as it was in every version of this plan before the brief Aug 21 detour into day-trip logic. Venue and date confirmed via the Bandsintown event page directly (not just search snippets, which also surfaced a conflicting "First Baptist Church" venue for the same date — that appears to be bad data). **Set time is 7pm per direct confirmation — Bandsintown's own event page listed 8pm, so if this resurfaces from a fresh search, trust the 7pm figure over it**, not the other way around.
- **New fixed point, Thu Aug 27 evening: meet Carlos at The Slammer, Buena Vista.** Added Aug 21. This is why Thursday's stop is Buena Vista specifically and not some other halfway town.

## Route as chosen

| Day | Route | Miles | Driving |
|---|---|---|---|
| Fri | Durango → US-550 → Silverton | ~85 | 2h10 |
| Sat | Silverton → Red Mtn → Ouray → Montrose → Grand Jct → I-70 → Rifle Falls → New Castle | ~250 | ~5h |
| Sun | New Castle → Glenwood Springs (brunch/hike/brewery) → Rifle → CO-13 → Craig → US-40 → Steamboat | ~175 | ~3h20 |
| Mon–Wed | (based in Steamboat, no driving days) | — | — |
| Thu 27 | Steamboat → US-40 → CO-9 → CO-91 (Fremont Pass) → US-24 → Buena Vista | ~157 | ~2h54 |
| Fri 28 | Buena Vista → US-285 → US-160 (Wolf Creek Pass) → Pagosa Springs | ~159 | ~2h50 |

Saturday is deliberately the long day of the first leg. The original plan pushed Steamboat straight to Pagosa in one 317-mile day; as of Aug 21 that's split into Thursday's 157-mile leg to Buena Vista and Friday's 159-mile leg to Pagosa — almost exactly the same total distance (316 vs 317), just spread across two easier days instead of one long one, with a fixed evening stop on each end (Carlos Thursday, the show Friday). A same-day version of this split (drive down, see the show, drive back to Buena Vista that night) was drafted and discarded within hours on Aug 21 — see "Ruled out" below.

## Ruled out — and why

Don't re-propose these without a reason the constraint changed.

**Aspen, Sunday morning (Aug 23).**
Considered as a detour before heading north to Steamboat. New Castle → Aspen is 1h9/53.7mi each way via CO-82 — real, paved, dog-fine road, but a genuine backtrack (Aspen is south of Glenwood, Steamboat is north). Round trip alone is ~2h20 of driving before spending any time there, and Maroon Bells specifically requires its own shuttle reservation system (7am–3pm operating window; dogs allowed on the shuttle and most trails but not the Scenic Loop). Stacked on top of the Glenwood brunch/hike/brewery morning already planned, it didn't fit without cutting one of those. Skipped — not because Aspen isn't worth it, but because the day already had a good morning and Aspen would have doubled it. Revisit if a future version of this trip has a slower Sunday with nothing else planned.

**Telluride / CO-145 (Lizard Head Pass, Dallas Divide).**
Genuinely the better photography route and it avoids the Red Mountain construction. Lost by choosing Silverton for Friday night — Silverton is on 550, Telluride is on 145, and there's no way to have both without adding ~2h to Saturday. This is the single biggest thing given up. If a future version of this trip starts earlier on Friday or sleeps in Ouray instead, 145 comes back.

**Palisade (all lodging).**
Palisade Peach Festival fell on Aug 21–22, the exact two nights. The town and the Grand Junction side were booked out for months. Not a search problem.

**Flat Tops Trail Scenic Byway (Meeker → Yampa).**
Spectacular, and roughly 40 of its 82 miles are gravel at 10,000 ft with no gas and no cell service. Fails the paved-only constraint. CO-13 through Craig is the paved equivalent and costs nothing in time.

**Rifle Falls camping.**
Only 20 sites, reservations required through cpwshop.com, fills most summer weekends. Then 35–45% rain forecast Saturday and Sunday killed it outright. Rifle Falls survives as a late-afternoon day stop, which is the better use of it anyway.

**Wingate New Castle.**
3.7/708 with a consistent pattern — musty rooms, deferred maintenance, a reported ownership change with no reinvestment, one guest locked out by an unactivated key card with no staff on site. Also at the I-70 interchange rather than downtown, which defeats the reason for choosing New Castle at all.

**Glenwood Springs (Sat night).**
Right idea, no rooms. New Castle is 13 minutes west and put dinner within walking distance instead of a drive.

**Grand Junction (Fri night, earlier draft).**
Dropped when Friday shortened. Already familiar territory, and Colorado National Monument went with it.

**Colorado National Monument.**
Casualty of the Silverton decision. Was the best golden-hour location on the route. Dogs are restricted to roads and overlooks there regardless.

**Yampa River Botanic Park (Steamboat week).**
Free, dawn–dusk, right by the river trail. Dogs aren't allowed on the garden paths themselves — only on the adjacent Yampa River Trail outside the park boundary. Same shape as Ouray Hot Springs: the constraint, not the destination, kills it.

**Old Town Hot Springs (Steamboat week).**
No published dog policy found, but pools are near-certainly no-dog, same as every other hot springs on this trip. Not worth a special trip to confirm by phone unless the plan changes.

**Howelsen Hill / gondola (Steamboat week).**
Dogs aren't allowed inside the ski area boundary per the town's official uphill-access policy. Rules out the gondola as a stop.

**Lobo Peak Overlook, Wolf Creek Pass (Friday transit).**
Exists and would be a nice add near the summit, but the final approach to it is gravel. Fails paved-only. The USFS picnic area right at the summit, directly off US-160, is the substitute — same idea, no detour, no dirt.

**Strings Music Festival and the free Music on the Mountain concert series (Steamboat week).**
Both are Steamboat's marquee live-music draws, and both are over before the visit — Strings runs June 28–Aug 13, the free series' last show is Aug 14 (Lyrics Born). Don't re-check these for the Aug 24–27 window; check next year's dates instead if this trip repeats.

**Art in the Park (Steamboat week).**
Steamboat's craft/art fair. July 11–12, 2026 — over a month before the visit. Not a live option for this window.

**Farmers Market as a Mon–Thu stop.**
Main Street Steamboat's farmers market runs Saturdays only (Yampa St, June–Sept). The Saturday before the visit (Aug 22) is still in transit; the Saturday after (Aug 29) is after departure. Doesn't fit a Sun-checkin/Fri-checkout week no matter how it's arranged.

**Friday as a Buena Vista day trip (drafted and discarded, both on Aug 21).**
Briefly the plan for a few hours: drive Buena Vista → Pagosa for the show, then back to Buena Vista the same night, treating Motel SOCO as the venue only. Drafted after a Super 8 Buena Vista booking appeared on the calendar covering Thu+Fri nights, which read as evidence the user no longer intended to sleep in Pagosa. Directly contradicted minutes later — the user confirmed they are staying at Motel SOCO Friday night after all. Reverted. **Net result:** Motel SOCO is Friday's lodging, same as every version of this plan before that afternoon. The Super 8 Friday-night booking is the one now in question — see the fixed-constraints note above and the guide's watch list. Don't re-derive the day-trip idea from the Super 8 booking again; ask first, the calendar isn't always the last word.

**First Baptist Church as the Aug 28 show venue.**
One search result attributed the Mike Dillon Band show to "First Baptist Church" in Pagosa Springs rather than Motel SOCO. Checked directly against Bandsintown's own event page (not a search snippet) and against the venue's own booking — Motel SOCO / El Camino Lounge is correct. Treat the church attribution as bad data if it resurfaces.

## Photo-sourced Durango content (method)

The Durango week had no written record anywhere — no calendar events, no emails, nothing searchable. The only real source turned out to be Google Photos' location data. Method, so a future session can repeat or extend it:

1. photos.google.com → Places → search "Durango" in the location autocomplete (not the main search bar as free text — that triggers an all-time text search across the whole library, not a location-filtered one). Click the actual place-tile suggestion.
2. This returns photos grouped by day (Yesterday, Thursday, Wednesday, ...) for that location specifically.
3. Open a representative photo for the day, press `i` for the info panel, scroll to the map at the bottom, click the pin — opens Google Maps at the exact EXIF GPS coordinate (confirmed real: Google Photos refused to let it be edited, "Can't edit locations added by your camera").
4. Cross-reference that coordinate against Maps search (e.g. search "bar" or "park" near the coordinate, or search a guessed venue name directly) to identify the actual place. A match this close (~30-100m) plus the venue already being in the user's own Google Maps favorites is strong independent confirmation, not a guess.
5. **Skip anything that isn't a venue** — a napkin with a stranger's name and phone number turned up in one day's photos; that's private, not trip content, and got excluded on sight. Same instinct that killed the miscategorized calendar events earlier.

Ruled out as a bulk alternative: `gphotos-cli` (github.com/trinhdrew1418/gphotos-cli) — a Go CLI for bulk photo download. Doesn't parse GPS itself (that's still an open TODO in the project), would need a full OAuth grant to a small unverified third-party app, and the user judged it out of date. The manual browser method above got real results without any new account access.

**Known limitation:** the Google Photos web UI is fragile to drive this way — programmatic scroll resets to the top unpredictably, the photo viewer sometimes needs the `i` key pressed twice, and `Escape` can kick all the way back to the library root instead of just closing the current photo. Budget for a lot of retries; this is not a fast process (roughly 5-8 browser steps per single photo's GPS lookup).

## Judgment calls worth revisiting

- **Santa Fe over Lubbock, Trinidad, or Pagosa Springs for Cactus Lee.** User's original idea (Aug 26) was driving to Lubbock's Blue Light for a Wednesday Sep 2 show. Checking the artist's own tour dates on Bandsintown turned up three other stops that week: Trinidad, CO (258mi/4h47, Thu Sep 3), Santa Fe, NM (212mi/3h57, Fri Sep 4), and — notably — Pagosa Springs, CO (61mi/1h13, Sat Sep 5, the town already on this itinerary for Aug 28). Lubbock itself is 534mi/8h43 and crosses into Central time. Presented all four with real mileage; user picked Santa Fe. Reasoning not stated beyond "makes more sense" — plausibly the middle ground between Pagosa (zero extra driving, but a week later, meaning more open Durango nights to fill) and Lubbock (the original pull, but a brutal single push with a dog). Don't re-litigate this in favor of Pagosa or Trinidad without a reason the calculus changed — this was a real comparison, not a default.
- **Dinner at 5:45 Friday** so the Andrews Lake → Molas Pass run has room before an ~7:50 sunset. Golden Block closes at 9; Alpine Tavern till 10 is the only later option.
- **Horsefly in Montrose over Ouray Brewery** for Saturday lunch. Ouray's rooftop is the better view; Horsefly's timing and covered dog patio fit the day better.
- **Casey Brewing (Glenwood) left optional.** Best beer on the route by a distance, but it's 20 minutes east of the room and a drive back on I-70.
- **Skipping Ridgway.** Colorado Boy doesn't open until 2pm Saturday; you pass through around 11:45.
- **Fish Creek Falls stays leashed.** One source claims off-leash is fine past the first quarter-mile; the more consistent and official-sounding line is leash required throughout. Went with the conservative read rather than the convenient one.
- **Emerald Mountain / Blackmer is leashed, not off-leash.** Steamboat's city council closed it to off-leash dogs in 2019 on a CPW recommendation. Older trip reports calling it off-leash are out of date — don't trust them if this resurfaces in a future search.
- **Wednesday evening moved to Snow Bowl's free Wednesday Sessions** (Float Like a Buffalo plays Aug 26) instead of Butcherknife Brewing. Butcherknife's open status is now confirmed (checked directly on Google) — the move stands on its own merit as live music plus a dog-run, not as a way of dodging a closure risk. Butcherknife remains the swap option for anyone who'd rather have the brewery.
- **Monday evening moved to Timber & Torch** (live music ~5:30–8pm, dog-friendly patio, Steamboat Square) instead of Storm Peak Brewing. Storm Peak kept as the weather-fallback swap since it's the only spot this week with an indoor dog option — Timber & Torch's seating is outdoor-by-a-fire, not indoor.
- **Steamboat Art Museum added as an optional Thursday stop**, not a group one. No dog policy confirmed anywhere searched, and museums are a poor bet for off-leash-adjacent activities generally — framed in the guide as a solo duck-in while the other person holds the dog outside, not a planned joint stop.
- **Backcountry Provisions' patio confirmed dog-friendly** via BringFido's dedicated listing (outdoor tables for dogs, matches the address/hours already in the guide) — the earlier "ask when you order" hedge is resolved, no longer an open item.
- **Twin Lakes moved from Friday to Thursday.** Originally a Friday-drive detour; now that Buena Vista is the Thursday destination rather than a Friday waypoint, Twin Lakes sits naturally on Thursday's route instead (~6-7 mile paved CDOT-resurfaced spur off US-24, just past Leadville). Same stop, different day.
- **Baymont Durango kept and flagged, not hidden, despite a 2.7★/483-review Google rating.** Specific complaints found: a broken bathroom outlet, a room reported as looking broken into. Already booked and paid for by the time this was checked (Aug 26), so the choice was disclose-honestly-in-the-guide vs. suppress — went with disclosure, matching how the Wingate New Castle rejection was handled (see "Ruled out"). Not proposing a swap; there's no time to rebook before Aug 29 and the user hasn't asked for one.
- **Eddyline / Cool River Cafe (Buena Vista) dropped from the written itinerary, not ruled out.** Both were the old Friday halfway-lunch candidates; now that Buena Vista is the Thursday base rather than a drive-through, either is still a fine dinner option in town — just not written in as a fixed stop, since The Slammer (Carlos) already owns Thursday evening.

## Live checks before departure

- **COtrip, Saturday morning** — Red Mountain Pass. 24/7 construction signals, delays up to 20 min, no stopping in work zones. The Gold Mountain burn scar sits above the highway northeast of Ouray and is prone to debris flows after heavy rain. If it closes, the detour is back through Durango, Cortez and Dolores: roughly +3h.
- **Fuel** — Durango before leaving Friday; Rifle before turning north Sunday. CO-13 is 88 miles with essentially no services.
- **Cash** — Ore House pet fee is cash at check-in, and check-in is contactless.
- **COtrip, Thursday Aug 27 morning** — Rabbit Ears and Fremont passes, before leaving Steamboat.
- **COtrip, Friday Aug 28 morning** — Wolf Creek Pass, before leaving Buena Vista. Conditions at 10,857 feet can turn fast even in late August.
- **Weather for Aug 24–29** — more than a month out at time of planning; the table below only covers the original Aug 21–23 leg. Re-check closer to departure, especially for the two pass-crossing days.

## Precheck, Fri Aug 21 (departure morning)

Checked CDOT/COtrip for all four passes on the itinerary. Real-time conditions still need a same-morning check per the live-checks list above — this is what's known in advance.

- **Red Mountain Pass (Sat)** — reopened July 31 after a flood-driven closure in late July; the 24/7 retaining-wall/tunnel construction between Ouray and Ironton already in this plan is still active, expected complete September 2026. No change to the existing plan or the ~20-min-delay expectation.
- **Wolf Creek Pass (Fri Aug 28)** — new finding: the eastside tunnel (mile point 174) is closed 24/7 for maintenance May 18–early October 2026. Traffic is on a signed, paved bypass the whole time; CDOT's own language is "brief intermittent delays," 25mph work zone, doubled fines. Added to the guide's Wolf Creek stop and watch list. Not a threat to the 7pm deadline on its own, but worth knowing about before the pass, not at it.
- **Fremont Pass (CO-91) and Rabbit Ears Pass (US-40)** — no 2026 construction or advisories found for either. Nothing to add.

Re-run this same check the morning of Aug 28 specifically — a precheck a week out doesn't substitute for the day-of COtrip look already called for above.

**Note, later the same day (Aug 21 evening):** the plan changed twice after this precheck — briefly to a Wolf Creek round trip, then back to a one-way crossing with an overnight in Pagosa. The tunnel-maintenance finding above applies either way.

## Weather at time of planning

| | Fri | Sat | Sun |
|---|---|---|---|
| San Juans | 40% | 75% | 70% |
| Colorado valley | 20% | 65% | 45% |
| Steamboat | — | 40% | 30% |

Saturday's storm was the reason the plan moved west rather than lingering in the mountains.

## Log

One line per change, newest first. This replaced a separate CHANGELOG.md on Aug 22 — same content, one less file to update. For anything that needs real reasoning, put it in "Ruled out" or "Judgment calls" above and just link back to it here.

- **Aug 28** — Added two photo stops to the Pagosa→Durango leg: Chimney Rock overlook (~17mi in via CO-151, photographable from the parking area without paying for the trails — dogs not allowed past the visitor center) and Yellowjacket Pass (7,785′, mile point 115.6). Correct order confirmed by mile-marker search after a first Maps query (queried in the wrong sequence) silently added a detour instead of erroring — don't trust a multi-stop Maps total alone to confirm point order, check it independently. Also corrected this leg's stop text, which previously and wrongly said "no passes" — Yellowjacket is real, just smaller than Wolf Creek or Red Mountain. Added a breakfast stop, "Two Chicks and a Hippie" (135 Country Center Dr) — user said "2 Hippies and a Truck," which doesn't match anything findable; flagged as a likely match (van mural fits) rather than assumed correct.

- **Aug 26** — Added the Santa Fe leg: extended the Durango return section through Wednesday Sep 2 (previously just Aug 29–30) and added a new Thu–Sat section for Durango → Santa Fe (212mi/3h57) and Cactus Lee at El Rey Court, Fri Sep 4, 6–10pm, free. See "Judgment calls" for why Santa Fe over Lubbock/Trinidad/Pagosa. Two real lodging gaps now flagged in the guide and watch list rather than glossed over: up to four unbooked Durango nights, and El Rey Court itself unbooked. Mileage 842 → 1,054. What happens after the Santa Fe show is explicitly left open — asked the user, only got the Durango-nights half of the answer.
- **Aug 26** — Repo renamed `durango-steamboat` → `colorado-roadtrip-2026` (old GitHub URL redirects automatically); local folder renamed to match. Added a sticky "right now" bar above the nav after the user said the timeline made it hard to find today's plan — shows current weekday/date and what's on, taps straight there, and drills into the correct `.subday` for multi-day sections instead of just naming the whole block. Verified the day/sub-day-matching logic directly against the live page; couldn't get a clean visual confirmation of the smooth-scroll animation itself in the sandboxed browser used for testing (scrollIntoView's `smooth` behavior silently no-ops in that specific automated tab — confirmed not a reduced-motion issue, `instant`/`auto` worked fine there) — added a `prefers-reduced-motion` check so it degrades to an instant jump gracefully either way, but the animation on a real phone hasn't been eyeballed.
- **Aug 26** — Added the Aug 29–30 Durango return leg: Baymont by Wyndham Durango, sourced from the actual confirmation email once Gmail access was reconnected to the correct personal account. Flagged (not hidden) a real discrepancy — the email says one night/checkout Sunday, the calendar event built from it shows two nights/checkout Monday — and the hotel's 2.7★ rating. Mileage 781 → 842. Header, nav, footer, and watch list all updated to match; the return section deliberately has no elevation-profile SVG since there's no confirmed pass or notable elevation change on this leg worth fabricating coordinates for.
- **Aug 22** — Added the missing Durango prologue (Aug 15 Clovis, Aug 16–21 Durango lodging) to the guide and "Right now" table — the trip always started here, but the guide never did. First draft wrongly included two unrelated personal calendar entries ("taos?", a show at "Vacancy") that just happened to fall in the same date window; caught because they were logged in Central time, not Mountain, and removed. Only verified hotel bookings are in the guide now.
- **Aug 22** — `index.html` now auto-archives days before today (viewer's local clock, via `data-until` on each `.day` section): collapses to day-head + day-note, with a "Show details" toggle per day and a "Show archived days" summary link in the header. Nav pills for archived days dim.
- **Aug 22** — Extended the same date-driven system to the Watch List: the day-archiving logic was already fully computed from the viewer's real clock (never hardcoded), but the Watch List below it was still plain static HTML — Friday/Saturday-specific reminders (altitude, Red Mountain check, Ore House cash) kept showing after those days passed, which was the actual clutter once the trip was underway. Every `<li>` now carries its own `data-until`; resolved reminders hide with the same "N of M, Show" pattern as the day sections, sharing one `isPast()`/`wireStatus()` helper in the script rather than duplicating the logic. Nothing on the page hardcodes a date anywhere now — it's all computed against the viewer's device clock at load time. This is the shape any future date-scoped content on the page should follow.
- **Aug 22** — Sunday rebuilt: added a Glenwood Springs morning (Daily Bread brunch, Wulfsohn Trail, Casey Brewing) before the drive north. Aspen considered and ruled out — see "Ruled out." Mileage 751 → 781.

- **Aug 23** — Filled in the last 2 of 6 Durango days: Sun (Animas River Trail evening walk) and Tue (Avalanche Bowl Company, 11th Street Station). All six days of the Durango week are now sourced from photo GPS, none guessed.
- **Aug 22** — Filled in 3 of 6 Durango days (Mon/Wed/Thu) from Google Photos GPS data, cross-referenced against Google Maps: Balcony Bar & Grill, Anarchy Brewing, Dallabetta Park. Method documented in "Photo-sourced Durango content" above. Sun/Tue still open. Ruled out gphotos-cli as a bulk alternative (outdated, requires a broad OAuth grant, doesn't parse GPS anyway).
- **Aug 22** — Merged CHANGELOG.md into this file. Added the "Right now" status block at the top.
- **Aug 21** — Friday reverts to overnight at Motel SOCO (one-way, 159mi/2h50). The round-trip version below lasted a few hours before the user corrected it. Mileage: 910 → 751.
- **Aug 21** — Friday split into two days via Buena Vista (see "Ruled out" — briefly a round trip). Thursday added: Steamboat → Buena Vista, meet Carlos at The Slammer. Twin Lakes moved Fri→Thu.
- **Aug 21** — COtrip precheck for all four passes. New finding: Wolf Creek's eastside tunnel closed for maintenance through early October — added to the guide.
- **Aug 21** — Butcherknife Brewing confirmed open (was a call-ahead flag).
- **Aug 21** — Backcountry Provisions patio confirmed dog-friendly via BringFido.
- **Aug 21** — Live music added to the Steamboat week: Timber & Torch (Mon), Snow Bowl Wednesday Sessions (Wed). Steamboat Art Museum added as an optional Thursday stop.
- **Aug 21** — Show time corrected 8pm → 7pm.
- **Aug 21** — Trip extended: Steamboat week (Mon–Thu) and the Aug 28 Pagosa leg added, including the Mike Dillon Band tentpole.
- **Before this repo existed** (exact dates not tracked — drafted in an earlier conversation, then exported in as the repo's first commit): Haviland Lake added to Friday, Andrews Lake moved to the Molas Pass sunset run; Ore House Inn settled over La Quinta Rifle; Silverton chosen for Friday night (Telluride and Glenwood Springs dropped as a result); first full draft was Durango → Fruita → Meeker → Steamboat, killed by the Palisade Peach Festival, the paved-only constraint, and rain.
