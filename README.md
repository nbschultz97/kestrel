<div align="center">

<img src="media/kestrel-lockup-web.png" alt="KESTREL — Advanced sUAS Training Platform" width="720">

**Advanced sUAS training at any coordinate on Earth.**

[**Download →**](../../releases/latest)

*Free · Windows x64 · alpha*

</div>

![KESTREL trailer — fly real cities, build the aircraft, build the mission, fly it](media/gameplay.gif)

<div align="center"><sub>Drop a pin anywhere on Earth and that coordinate loads in photoreal terrain. Build the aircraft from real parts, drop the objective on real ground, and fly the mission you just made.</sub>

[**▶ Watch the full trailer with sound**](https://github.com/nbschultz97/kestrel/releases/download/v0.29.1-alpha/kestrel-trailer-v9.mp4) · [LinkedIn 35 s cut](https://github.com/nbschultz97/kestrel/releases/download/v0.29.1-alpha/kestrel-short-linkedin.mp4) · [Vertical 60 s](https://github.com/nbschultz97/kestrel/releases/download/v0.29.1-alpha/kestrel-short-vertical.mp4)</div>

Choose a training mission, type in a grid, or drop a pin, and that exact area
loads in photoreal terrain. Build an aircraft from real parts and it flies like
those parts: real motor KV, prop, pack, and mass. Import a Betaflight diff to
train on your own rates, tune, modes, and switches; the OSD uses the stock
Betaflight MAX7456 character set—the same glyphs a real analog OSD chip draws.

The point is repeatable mission rehearsal and honest stick time without burning
packs, props, or airspace.

> **This is an alpha and it is rough.** It will crash on you. Bug reports are
> automatic and they genuinely help — see below.

---

## Next release: the realism overhaul

Every part in the sim has been rebuilt from real manufacturer geometry. Not
re-textured — remodelled, measured, and re-wired.

![The same 5-inch build, before and after the asset overhaul](media/next-release/oldnew-build-5in.jpg)

<div align="center"><sub>Same aircraft, same camera. Left is what ships in the current build; right is what comes next.</sub></div>

The part library went from 99 meshes to 169, and every one of them is textured
now: carbon weave that runs the right way, silkscreen and components on the
PCBs, anodised motor bells, printed pack wraps, and wiring that actually goes
somewhere. Airframes are dimensionally calibrated against manufacturer CAD —
the TBS Source family was measured out of the vendor's own STEP files, so the
5-inch on screen is the 5-inch on the bench.

| | |
|---|---|
| ![A 5-inch airframe, old geometry beside the STEP-calibrated rebuild](media/next-release/oldnew-frame-carbon.jpg) | ![The pilot character, old model beside the rebuild](media/next-release/oldnew-pilot.jpg) |
| Airframes measured out of vendor STEP files. | The pilot and twelve mission characters, rebuilt on a corrected skeleton. |

![Six airframes, 1.6-inch whoop through 13-inch heavy-lift, at true relative scale](media/next-release/family-frames.jpg)

![Twelve mission characters on the corrected skeleton](media/next-release/mission-characters.jpg)

Propellers were rebuilt from measurements rather than guessed at — real prop
geometry plus 84 product photos, resolved into ten planform families. Pitch and
blade count read at a glance, and the polycarbonate is translucent the way the
real thing is.

![Ten propeller planform families, 1.6-inch through 13-inch, translucent polycarbonate](media/next-release/family-props.jpg)

Showcase builds are wired end to end: camera looms, VTX coax, receiver antenna
tubes, and XT60s that mate instead of floating near each other.

![A fully wired 5-inch build - camera loom, VTX coax, receiver antennas, mated XT60](media/next-release/build-5in-wired.jpg)

| | |
|---|---|
| ![A 7-inch long-range build carrying a Li-ion cylinder pack](media/next-release/build-7in-liion.jpg) | ![The pack family - LiPo bricks through Li-ion cylinder packs](media/next-release/family-batteries.jpg) |
| Li-ion packs are cylinders now, not bricks with a different label. | The full pack family, 550 mAh through 6S Li-ion. |

Antennas, VTXs, cameras, GPS units and receivers all got their own families, so
the aircraft you build in the HANGAR looks like the parts you picked.

![Camera, VTX, receiver, GPS and antenna part families](media/next-release/family-electronics.jpg)

### In the air

**Props are visible in the FPV view.** The near clip was cutting them out of
frame; it is fixed, and the signature FPV look — blades sweeping the top and
bottom of the picture — is back. The camera you fit drives the flight FOV, so a
narrow analog cam and a wide digital one no longer see the same thing.

| | |
|---|---|
| ![A 5-inch freestyle build, captured in engine](media/next-release/inengine-5in-freestyle.jpg) | ![A 13-inch heavy-lift build, captured in engine](media/next-release/inengine-13in-heavy.jpg) |
| 5-inch freestyle. | 13-inch heavy-lift. Both captured in engine. |

Takeoff lifts prop-wash dust off the pad. A kill swaps in a wrecked airframe
instead of deleting one. The HANGAR spools the props while you build.

![Prop-wash dust lifting off the pad on takeoff](media/next-release/propwash-takeoff.gif)

<div align="center"><sub>Prop-wash on takeoff — offline VFX tuning preview, real sprites and shipped parameters.</sub></div>

Still in work: a full vehicle fleet with civilian traffic, and mission-objective
set pieces.

![The rebuilt part suite - frames, builds, motors, packs, props, electronics and antennas](media/next-release/asset-suite-poster.jpg)

<div align="center"><sub>169 meshes. Fresh off the development branch — none of this is downloadable yet. It ships with the next release.</sub></div>

---

## Get it running

1. [**Download**](../../releases/latest) `KESTREL-alpha-win64.zip` and unzip it
   **to its own folder**.
2. Run **`KESTREL.exe`**. That is the only thing to click — no install, no
   account. Terrain works out of the box.
   SmartScreen will warn (unsigned build) → *More info* → *Run anyway*.
3. If it will not start, run the bundled **`vc_redist.x64.exe`** once. A missing
   Microsoft C++ runtime is the usual cause.
4. **CALIBRATE CONTROLLER → AUTO-DETECT → SAVE → BACK.**
5. **LOCATION** → drop a pin, or type `40.7580, -73.9855` → fly.
   Throttle down, then Enter (or your mapped switch) to arm.

Needs internet for terrain streaming. Keyboard and gamepad work, but a radio in
USB-Joystick mode is the point.

---

## What is actually modelled

![FPV pass through the Taipei 101 district - photoreal tiles, authentic Betaflight OSD](media/hero-taipei.png)

- **Any coordinate on Earth.** Drop a pin, or type MGRS or `lat, lon`. Ground
  elevation gets looked up and the world calibrates against the streamed
  terrain, so you spawn on the actual street.
- **Physics from real parts.** Mass, KV, cells, capacity, prop size. Motors top
  out at the spec sheet's *loaded* rated point, not an impossible no-load
  number, so thrust-to-weight and the feel of weight are honest. Checked against
  a separate reference model with 153 tests.
- **Batteries behave.** Nonlinear LiPo discharge, IR sag, a real voltage cliff.
  Fly the pack down and it browns out — it falls out of the sky.
- **The link is real.** RSSI comes from actual distance *and* line-of-sight
  through the terrain geometry. Get a building between you and the quad at range
  and the video tears and snows, then you lose it.
- **Time of day and weather.** Real solar position for wherever and whenever you
  are flying — dawn in Tucson is actually dawn in Tucson. Wind acts on airspeed,
  so you crab into it. Density altitude is fed to the physics.
- **Damage sticks.** Impacts crack the camera, kill individual motors, or write
  the airframe off. Nothing is on a timer.

---

## Mission training

Three built-in missions cover different skills: **GAUNTLET** is a timed Chicago
river-canyon gate run, **BRIDGE STRIKE** is a low Pittsburgh ingress with a
terminal window, and **RELAY DASH** stretches the RF link across Seattle's
Elliott Bay. Mission scoring grades objective completion, time, link discipline,
power management, and crashes, while personal bests persist between sessions.

A `strike` objective is a one-way attack run: fly the terminal dive onto the
target and the warhead functions. Vehicles in the blast are wrecked rather than
despawned, and the feed hands off to an overhead ISR view for assessment.

![Strike detonation - real fire and a building smoke column over the target](media/strike-fire.png)

<div align="center"><sub>The warhead functions: live fire, dirt, and a smoke column that builds and drifts — rendered in-engine.</sub></div>

![Inside the smoke column seconds after impact](media/strike-smoke.png)

---

## Real time of day

Pick a time and the sky, sun, and lighting move with it — computed from the real
solar position at that coordinate and date, not a canned skybox. Dawn and dusk
are genuine golden hour; noon is hard overhead light; night scales with the real
moon phase, so a new-moon AO is genuinely dark.

![FPV over a real city at midday, flight OSD burned in](media/osd-day.png)

| | |
|---|---|
| ![Dawn over the Grand Canyon](media/canyon-dawn.png) | ![Dusk over Lower Manhattan](media/nyc-dusk.png) |
| Dawn — terrain flying over the Grand Canyon. | Dusk — golden hour over Lower Manhattan. |
| ![Night over the Las Vegas Strip](media/vegas-night.png) | ![Afternoon haze over Dubai Marina](media/dubai-haze.png) |
| Night — moon-phase lighting over the Strip. | Haze — Dubai Marina in desert air. |

<div align="center"><sub>The real MAX7456 OSD burned in — timer, RSSI, home arrow, battery, alt, speed, MGRS — over photoreal terrain at any time of day, anywhere on Earth.</sub></div>

---

## Screens

| | |
|---|---|
| ![Settings](media/settings.png) | ![Low pass](media/flight-lowpass.png) |
| Audio, display, environment, flight. | Low pass over real streets. |

---

## When it breaks

**Reporting is automatic.** Crashes and bugs write their own reports - no
hotkey needed. **F12** toggles a live dev-metrics overlay (audio, flight,
mission state) so you can read off exactly what the sim was doing when
something looked wrong. Reports land in:

```
Documents\KESTREL\reports\
```

Zip that folder and send it — or just open an
[issue](../../issues) here and drag it in. That is everything needed; you do not
have to write it up well.

If you would rather just describe it, three things help most:
1. **Version** — printed top-right on screen.
2. **What you did** — "hit RANDOM AO", "mapped a switch to arm and flipped it".
3. **What happened** vs. what you expected.

Known issues ship in `CHANGELOG.md` inside the zip.

---

## Requirements

| | Minimum | Recommended |
|---|---|---|
| OS | Windows 10 64-bit (1909+) | Windows 11 64-bit |
| CPU | Quad-core 2.5 GHz (i5-8400 / Ryzen 5 2600) | 6-core 3.5 GHz+ |
| RAM | 8 GB | 16 GB |
| GPU | DirectX 12, 4 GB VRAM (GTX 1060 / RX 580) | RTX 2060 / RX 5700+ |
| Disk | 2 GB free | — |
| Controller | Radio in USB-Joystick mode (RadioMaster / EdgeTX / TBS) | Radio |

You need a **discrete GPU** — UE5 will not run acceptably on integrated
graphics. Windows x64 only for now.

---

## License

KESTREL is **free to download and fly, but it is not open source.** The
[KESTREL Evaluation License](LICENSE.txt) covers every copy: free for U.S.
Government personnel for training, familiarization, and evaluation, and free
for personal non-commercial use. No redistribution outside published channels,
no commercial use, and no reverse engineering without a written license —
commercial licensing is available via
[nbschultz97@gmail.com](mailto:nbschultz97@gmail.com).
© 2026 Noah Schultz / Ceradon Systems. All rights reserved.

---

<sub>Built in Unreal Engine 5. Source is private; this repo is releases and docs.
Terrain © Google via Cesium ion · map imagery © Esri.</sub>
