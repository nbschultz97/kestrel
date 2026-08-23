# KESTREL v0.31.0-alpha — the current public release

Published. v0.29.2, v0.30.0 and v0.31.0 are out to testers through the
auto-updater; this page summarizes the three waves. The headline of v0.30 is
visual — the aircraft you build finally looks like the parts you picked — while
v0.29.2 and v0.31.0 carried the flight-model honesty work underneath it.

![The same 5-inch build, before and after the asset overhaul](media/next-release/oldnew-build-5in.jpg)

### Flight model

- **A 10-inch is not a heavy 5-inch.** One factory tune went to every aircraft
  in the sim; rates and feed-forward are now scheduled off airframe authority
  (667/422/299 deg/s; F = 120/65/41), and the WORK BENCH prints what a build
  got.
- **Missions fly what was authored.** A leg's authored speed is a contract now —
  the altitude floor's gentle climb ramp no longer quietly clamps the forward
  stick.
- **Rendered footage stopped lying twice.** The virtual pilot's yaw hunt (a
  relay measured in the wrong unit) is dead, and so is its avoidance chatter on
  the other axis: the pilot holds an attitude like a pilot does instead of
  arguing with gusts through a speed loop.
- **Impact you can read** — thresholds moved so a belly-slide, a real auger-in,
  and a catastrophic slam are three different outcomes instead of two silent
  ones.

### Aircraft & parts

- **169 part meshes, up from 99, and all of them textured.** Carbon weave
  oriented per part, silkscreen and components on the PCBs, anodised motor
  bells, printed battery wraps. No untextured placeholder geometry remains in
  the build catalogue.
- **Airframes calibrated against manufacturer CAD.** The TBS Source family was
  measured out of the vendor's own STEP files — plate outline, arm taper, stack
  mounting, standoff heights — and the rest of the airframe classes were scaled
  to sit correctly against them.
- **Propellers rebuilt from measurement.** Real prop geometry plus 84 product
  photos, resolved into ten planform families. Pitch and blade count are visual
  axes now, and the blades are translucent polycarbonate rather than opaque
  slabs.
- **Li-ion packs are cylinder banks, LiPo packs are bricks.** They were the same
  mesh with a different label; they are now different objects with different
  silhouettes and wraps.
- **Full antenna, VTX, camera, GPS and receiver families**, each with the
  pigtails and connectors the real part carries.
- **Showcase builds are wired end to end** — camera looms, VTX coax, receiver
  antenna tubes, and XT60s that mate to their counterpart instead of floating
  beside it.

### In flight

- **Props are visible in the FPV view.** The camera near clip was culling the
  blades out of frame; it now sits inside the disc, which restores the sweep
  across the top and bottom of the picture that defines the FPV look.
- **The fitted camera drives the flight FOV.** Choosing a narrow analog cam and
  a wide digital cam changes what you see out the front, not just the part list.
- **Prop-wash dust on takeoff** — a ring and puffs lifted off the pad, scaled by
  thrust over hover; visible from the pilot's seat in v0.31, with faint rotor
  arcs on the lens at steep nose-down.
- **Kills swap in a wrecked airframe** rather than deleting the aircraft.
- **The HANGAR spools the props** while you build.

### World & characters

- **New pilot and twelve mission characters**, rebuilt on a corrected skeleton —
  the old rig had joint orientations that broke every pose it was given. v0.31
  shipped all thirteen fully textured.
- **The range remembers which venue it is** — flying again right after bench
  work brings up the range you asked for, not the one you were last in.
- **The vehicle fleet rebuilt** — twenty military vehicles with real role
  silhouettes and wheels/doors as separate parts, plus the first civilian
  traffic set (sedan, hatchback, van, pickup) for the road network. Wrecks
  regenerated to match.
- **Twelve mission-objective set pieces and the support props re-authored** —
  sandbagged bunker, camo-net command post, radar, fuel depot, helipad, and
  the rest, each readable from recon altitude.

### Under the hood

- Part meshes re-authored and re-exported through a single generator, so the
  catalogue, the HANGAR preview, and the flight mesh all read the same source.
- Materials consolidated onto shared textured masters (weave, silkscreen,
  anodise, wrap) instead of per-part flat colours.
- Reference measurement set — vendor STEP files, prop geometry, and product
  photography — captured alongside the generator so parts can be re-derived
  rather than re-eyeballed.

### Preview gallery

| | |
|---|---|
| ![A 5-inch airframe, old geometry beside the STEP-calibrated rebuild](media/next-release/oldnew-frame-carbon.jpg) | ![The pilot character, old model beside the rebuild](media/next-release/oldnew-pilot.jpg) |
| Airframes measured out of vendor STEP files. | The pilot, rebuilt on the corrected skeleton. |

![Six airframes, 1.6-inch whoop through 13-inch heavy-lift, at true relative scale](media/next-release/family-frames.jpg)

![Ten propeller planform families, 1.6-inch through 13-inch, translucent polycarbonate](media/next-release/family-props.jpg)

![A fully wired 5-inch build - camera loom, VTX coax, receiver antennas, mated XT60](media/next-release/build-5in-wired.jpg)

| | |
|---|---|
| ![A 7-inch long-range build carrying a Li-ion cylinder pack](media/next-release/build-7in-liion.jpg) | ![The pack family - LiPo bricks through Li-ion cylinder packs](media/next-release/family-batteries.jpg) |
| A 7-inch long-range build on a Li-ion cylinder pack. | The pack family, 550 mAh through 6S Li-ion. |

![Camera, VTX, receiver, GPS and antenna part families](media/next-release/family-electronics.jpg)

![Twelve mission characters on the corrected skeleton](media/next-release/mission-characters.jpg)

| | |
|---|---|
| ![A 5-inch freestyle build, captured in engine](media/next-release/inengine-5in-freestyle.jpg) | ![A 13-inch heavy-lift build, captured in engine](media/next-release/inengine-13in-heavy.jpg) |
| 5-inch freestyle, captured in engine. | 13-inch heavy-lift, captured in engine. |

![Prop-wash dust lifting off the pad on takeoff - offline VFX tuning preview](media/next-release/propwash-takeoff.gif)

![The rebuilt part suite - frames, builds, motors, packs, props, electronics and antennas](media/next-release/asset-suite-poster.jpg)

---

# KESTREL v0.29.1-alpha (historical)

The release before the current one — the strike line, the analog FPV feed, the
test range, and the nineteen-item play-test wave. Kept for reference; the
full per-build history is in `CHANGELOG.md` inside the zip.

## What shipped in it

- **The strike is a one-way attack, and the pilot now flies it like one.** On the
  terminal leg the avoidance response and the AGL speed brake come off: the thing
  filling the look-ahead IS the aim point, so every avoidance reaction was a miss,
  and the brake's premise — *"this aircraft has to still be flying in two seconds"*
  — is false for a munition. Left in, the dive sat inside the floor band for its
  whole length and bled back the forward stick producing it, so the aircraft
  settled into a controlled descent and arrived at walking pace. Impact speed
  is now logged.
- **Analog FPV feed** — a 4:3 window with deterministic noise, framed last over
  everything, because an element that lands in the pillarbox was never
  transmitted on a real analog link.
- **Convoy placement that survives contact with the map** — the column was in
  the median because its heading came from OSM, and the warhead fired on a
  radius instead of on the hull.
- **A play-test wave** — nineteen reports from v0.28.3 (black inventory tiles,
  spawning underground, the 10–20 s launch freeze, black bars in fullscreen,
  the minus key eating the MGRS northing, the weather clamp, etc.). See the
  changelog for the long form.
- **Test range with user-set wind / weather / atmosphere** — controls live in
  the flight view, sliders drive the same atmosphere the physics reads.
- **New markers** (waypoints, spawn, strike) replacing the old black platforms.
- **WORK BENCH renamed to HANGAR** and reorganized.
- **Flight controller on its own 1 kHz clock** instead of the render clock, with
  per-airframe rate scaling.

## Install or update

Existing installations update automatically the next time `KESTREL.exe` is
launched. For a new installation, download `KESTREL-alpha-win64.zip`, extract it
to its own folder, and run `KESTREL.exe`.

The archive is Windows x64 and requires a discrete GPU for practical UE5
performance. This remains an alpha release; report crashes or unexpected
behavior through the repository issues page.

## Trailer and clips

- [Full trailer (v9, 92 s, 1080p)](https://github.com/nbschultz97/kestrel/releases/download/v0.29.1-alpha/kestrel-trailer-v9.mp4)
- [LinkedIn 35 s cut](https://github.com/nbschultz97/kestrel/releases/download/v0.29.1-alpha/kestrel-short-linkedin.mp4)
- [Vertical 60 s cut (IG / TikTok)](https://github.com/nbschultz97/kestrel/releases/download/v0.29.1-alpha/kestrel-short-vertical.mp4)