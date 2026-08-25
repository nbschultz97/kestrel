<div align="center">

<img src="media/kestrel-lockup-web.png" alt="KESTREL — Small UAS Mission Simulation" width="720">

**Small UAS mission simulation at any coordinate on Earth.**

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

## Current release — v0.37.0-alpha

v0.37 finishes the connected-aircraft and WORK BENCH presentation pass:

- Cameras, batteries, motors, VTX hardware, and imported frame sockets now share
  the correct coordinate system. The locked True-X build seats the Foxeer Micro
  Cat 4 inside its cage instead of several inches in front of the frame.
- Live compatible builds include battery straps, mated red/black battery leads,
  and three inboard-routed phase wires per motor. Battery labels remain legible
  and black carbon stays dark over the new soft-focus technician workbench.
- Named/editable builds, selectable saved electronics, explicit compatibility,
  ATAK-style mission briefs, and mission creation inside MISSIONS remain part of
  the shipped release.
- Launcher 1.1 asks for each pilot's Cesium token on first launch and stores it
  privately; no shared terrain or reporting credential is embedded in the ZIP.

Existing installations update automatically when `KESTREL.exe` starts. See the
[full release notes](RELEASE_NOTES.md) for the complete v0.37 and historical
release record.

---

## Get it running

1. [**Download**](../../releases/latest) `KESTREL-alpha-win64.zip` and unzip it
   **to its own folder**.
2. Run **`KESTREL.exe`**. That is the only thing to click — no installer.
   SmartScreen will warn (unsigned build) → *More info* → *Run anyway*.
3. Photoreal terrain requires a Cesium ion access token. On first launch, paste
   yours into the launcher's hidden prompt; it is stored only in
   **`Documents\KESTREL\cesium_token.txt`**. Press Enter to use offline terrain.
4. If it will not start, run the bundled **`vc_redist.x64.exe`** once. A missing
   Microsoft C++ runtime is the usual cause.
5. **CALIBRATE CONTROLLER → AUTO-DETECT → SAVE → BACK.**
6. **LOCATION** → drop a pin, or type `40.7580, -73.9855` → fly.
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
