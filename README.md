<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="media/brand/kestrel-lockup-instrument.svg">
  <source media="(prefers-color-scheme: light)" srcset="media/brand/kestrel-lockup-graphite.svg">
  <img src="media/brand/kestrel-lockup-graphite.svg" alt="KESTREL" width="420">
</picture>

**Build the aircraft from real parts. Pick any place on Earth. Fly it first.**

Windows x64 · Free public alpha · Proprietary software

[Download](https://github.com/nbschultz97/kestrel/releases/latest) · [Features](FEATURES.md) · [Changelog](CHANGELOG.md) · [Roadmap](ROADMAP.md)

</div>

## What KESTREL is

KESTREL is a small-UAS and FPV training simulator that flies over real-world
terrain. You build an aircraft on the Work Bench from real catalog parts, and
the flight model comes from those parts: mass, motors, props and battery. So a
5-inch quad and a 13-inch heavy-lifter fly differently, and they run out of
battery differently. Then you pick a place, streamed in photoreal 3D where
coverage exists, and fly a free flight or a mission. You get a record of the
flight at the end.

That is the loop: **configure a specific aircraft, fly that exact aircraft on a
real task, and get a record out the other end.** It is built in Unreal Engine 5
and ships as one Windows download. You don't need an engine install or an
account.

![First-person view of a fiber run over a city street, with the HD goggle display showing FIB 4.8K, meters of fiber left on the reel, next to VIDEO 50 MBPS](media/v0.46/stills/02-fiber-fpv-fib-readout.jpg)

<sub>Fiber run, FPV with the HD OSD: `FIB 4.8K` (meters left on the reel) next to `VIDEO 50 MBPS`. Fiber links have no RF fade.</sub>

![KESTREL main menu with the stoop-chevron mark and the menu list: Free Flight, Missions, LAN Multiplayer, Records, Flight Lab, Work Bench, Data and Catalogs, Settings, Quit](media/v0.46/stills/09-main-menu-logo.jpg)

<sub>Main menu with the KESTREL stoop-chevron mark.</sub>

## Feature tour

### Work Bench: build the real aircraft

Fit frames, motors, props, batteries, ESCs, flight controllers, cameras, video
transmitters and receivers from a parts catalog. Each part is checked for
compatibility, and the bench predicts thrust-to-weight, hover throttle and
endurance before you fly. Builds save, rename, duplicate and reopen. Parts
libraries import and export as JSON or XLSX. **New in v0.46:** a fiber reel
slot with 5, 10 and 20 km reels. Bigger reels need bigger airframes (7", 10" and
13" props).

![Work Bench on a valid 5-inch build, showing all-up weight, thrust, thrust-to-weight, hover percent, hover current and time, cost and the scheduled tune](media/v0.46/stills/10-workbench-specs.jpg)

<sub>Work Bench, valid 5" build: AUW, thrust, T:W, hover %, hover current and time, cost, and the scheduled tune.</sub>

![Work Bench Fiber Reel slot with the 5 km reel fitted and compatible, and the 10 km and 20 km reels marked not compatible for this frame](media/v0.46/stills/01-fiber-workbench.jpg)

<sub>Work Bench, Fiber Reel slot, on a valid 8" fiber build (RJX Mark4 8" frame, XING 2806.5 1300KV motors, HQ 8x4x3 props, 6S 2900 mAh pack) with the 5 km reel fitted and compatible: 2506 g all-up, 4.7:1 thrust-to-weight, 5:49 hover, Save enabled. The 10 and 20 km reels are marked NOT COMPATIBLE for this frame.</sub>

### Flight: it flies like the build

- Betaflight-style rates and PID control, with import of supported Betaflight
  diff settings. It is not a complete firmware emulator.
- ACRO, ANGLE and HORIZON modes, FPV and line-of-sight views.
- Battery discharge and voltage sag under load, motor response, wind that acts
  on airspeed, and collision damage.
- **Analog or HD goggles.** Digital air units get the HD goggle OSD: the full
  16:9 picture, a 53x20 grid and smooth glyphs. Analog cameras keep the 4:3
  MAX7456 look. A lost video feed breaks up the way goggles do. An OSD layout
  editor moves the elements, including the horizon and compass bar.

![First-person KESTREL run westbound across Monument Valley with the HD goggle OSD](media/v0.46/kestrel-hero-monument-valley.webp)

<sub>Monument Valley, westbound, climbing from 20 to 70 m. KESTREL's virtual pilot flies an authored line under the real flight model. Recorded at 1920x1080 in the v0.45.1 test build, whose HD OSD ships in v0.46.</sub>

![The same Monument Valley line through an analog 4:3 feed and the HD digital OSD](media/v0.46/goggles-analog-vs-hd.jpg)

### World: fly the real place

- Search a city or enter coordinates, place the launch pin, set the time and
  the weather. The sun is placed for the site and date.
- Photoreal 3D terrain streams where the provider has coverage, and the world
  sits on true north. Where nothing streams, KESTREL builds a small local area
  on the spot instead of a flat floor.
- **Saved areas** build offline terrain for a 2, 5 or 10 km area from public
  data: about 10 m elevation in the US (30 m elsewhere), USGS or Sentinel-2
  imagery and OpenStreetMap buildings. Since v0.46 they also have trees, pitched
  roofs, building collision and water. If you land on water, you ditch.

![First-person view over San Francisco's Telegraph Hill with downtown ahead](media/v0.46/world-san-francisco.jpg)

![Free Flight location search for Los Angeles showing six matches and the pin on a map of the US West Coast](media/v0.46/stills/12-location-search.jpg)

<sub>Free Flight location search: offline city lookup ("Los Angeles", 6 matches) and the pin on the map.</sub>

### RF and EW

- The video and control link depend on distance and on line of sight from
  the pilot's eyes through the terrain and buildings. Fly behind a ridge at range
  and the picture breaks up, then the link drops and the aircraft goes to
  failsafe.
- Hostile jammers placed in a mission really emit, and a strike inside the blast
  takes one out.
- **Predicted RF coverage** on the map and the loading map, from public
  elevation data. It is a prediction, not a measurement.
- **Fiber reels (new in v0.46).** While the fiber is whole the link is perfect: any
  range, behind any terrain, through any jammer. The reel spends the route you
  actually fly. The fiber parts if the reel runs out, if you hold a speed above
  its payout limit, or on a hard wrap round an edge. When it parts, the
  aircraft goes to failsafe. The OSD shows fiber left (`FIB 7.4K`) and flashes
  FIBER CUT.

![Chase camera view of a quad flying over a city street with the fiber strand trailing behind it as a thin white line](media/v0.46/stills/03-fiber-strand-chase.jpg)

<sub>Chase cam on the Santa Monica pier run. The fiber strand stays visible behind the quad as it pays out.</sub>

| | |
|---|---|
| ![Analog goggle view with FIB CUT on the display and the video breaking up in horizontal bands](media/v0.46/stills/04-fiber-cut-analog-breakup.jpg) | ![Analog goggle view a second after the cut, showing NO RF LINK - CHECK TRANSMITTER and DISARMED](media/v0.46/stills/04b-fiber-cut-failsafe.jpg) |
| Analog fiber build flown too fast for the reel. `FIB CUT` appears and the video breaks up as the strand parts. | A second after the cut: `NO RF LINK - CHECK TRANSMITTER`, failsafe disarm, and the last frame fading out. |

### Missions: build, brief, fly

Mission Builder places targets, jammers and objectives over a real area, writes
the brief, and saves back to the same mission file, with undo and duplicate.
There are 32 mission models: seven OPFOR target vehicles, each with a destroyed
version, plus an FPV drone-team position, a radar, an EW mast, a fuel point, and
civilian, SOF and support vehicles. Wheeled vehicles stay on drivable roads.
Fly recon, ISR overwatch or a strike run, and the Records page keeps the
result.

![Pittsburgh mission brief card with friendly and hostile MIL-STD-2525 symbols over a satellite map, waypoints, and the recon and strike tasking](media/v0.46/stills/13-mission-brief-card.jpg)

<sub>Pittsburgh mission brief card: MIL-STD-2525 friendly and hostile symbols, waypoints, and the recon/strike tasking.</sub>

| | |
|---|---|
| <img src="media/v0.46/stills/05-missions-preview-map.jpg" alt="Missions screen with the North Shore Interdiction card selected, showing objectives, target picture, launch points and the area preview map" width="300"> | ![Mission loading card with RF coverage colours over satellite imagery, a waypoint, the mission brief and a loading progress bar](media/v0.46/stills/09b-loading-card.jpg) |
| Missions screen, selected mission card (North Shore Interdiction, Pittsburgh): objectives, target picture, launch points, and the AO preview map. | Mission loading card: RF coverage over satellite imagery, waypoint, mission brief, and a loading progress bar. |

| | |
|---|---|
| ![Recon pass along an OPFOR column on a desert road](media/v0.46/missions-column-recon.jpg) | ![Overhead ISR view of struck vehicles; the game reads EFFECT NOT CONFIRMED](media/v0.46/missions-isr-bda.jpg) |
| Recon pass on the COLUMN HALT demo mission | Overhead ISR after the strike. The banner reads EFFECT NOT CONFIRMED. |

![All 32 mission models added in v0.45](media/v0.45/kestrel-v045-all-models.jpg)

### Flight Review and Flight Lab

- Replay ArduPilot DataFlash logs and flight files in 3D over the streamed
  terrain, with chase, orbit, FPV-at-recorded-attitude and free cameras.
- **New in v0.46:** a multi-log timeline puts several flights on one UTC clock,
  with a vehicle selector. Attitude-only logs open, and KESTREL never invents
  attitude a log does not have. A converter turns a Betaflight blackbox log
  into a flight KESTREL can open.
- Flight Lab runs a Lua script, unchanged, in ArduPlane SITL over real terrain,
  with live firmware messages and telemetry. You supply the SITL executable.
  Scripts, logs and results stay on your computer.

![Flight Review replay screen with the ground track over satellite imagery, a timeline with event ticks, the sample readout and the event list](media/v0.46/stills/17-flight-review-map.jpg)

<sub>Flight Review: replay ground track, timeline with event ticks, sample readout, and the event list.</sub>

### Controllers

Keyboard, gamepad or an RC radio in USB-joystick mode. Channels CH1-CH8 are
numbered the way your radio numbers them, so switches on 7 and 8 work.
Stick-end calibration lets a throttle that rests above zero arm. Bindings cover
every flight control, and the reset switch can't fire in flight by accident.
**Settings > Controller > DIAGNOSTICS** shows every channel and switch the game
sees, with plain findings and a COPY REPORT button.

![Controller Diagnostics with no radio connected: per-channel bars, a USB dropout counter, plain-language findings and a Copy Report button](media/v0.46/stills/08-controller-diagnostics.jpg)

<sub>Controller Diagnostics with no radio connected: per-channel bars, a USB dropout counter, plain-language findings, and Copy Report.</sub>

### LAN multiplayer (experimental)

Host or join on one network, approve each aircraft, ready up and fly the same
sortie. It passes a one-PC, two-process test. Play across two physical PCs is
not fully tested yet.

![LAN lobby, v0.42 capture](media/v0.42.11/multiplayer.png)

## Latest release: v0.46.0

Fiber-optic reels, the HD goggle OSD, predicted RF coverage, a true-north
photoreal world, saved areas with trees, roofs and water, a multi-log Flight
Review timeline, the Betaflight blackbox converter, and the radio fixes from the
unreleased v0.45.1 (CH7/CH8, stick-end calibration, no disarm on a brief radio
dropout, controller diagnostics). The KESTREL logo is now the stoop-chevron mark
in the game too.

Full notes, checksums and test status are on the
[v0.46.0 release page](https://github.com/nbschultz97/kestrel/releases/tag/v0.46.0-alpha).
Older versions are in [CHANGELOG.md](CHANGELOG.md).

## Coming next (in development, not in v0.46)

These are being built now and are **not in the current download**. Each one
ships in a numbered release with its own notes.

- **Works with your real ATAK.** KESTREL sends Cursor-on-Target over your
  network, so your simulated drone, marks, waypoints and target grids show up on
  your own ATAK, WinTAK or iTAK device. Points you drop in ATAK can become
  waypoints in the sim.
- **A map in your pocket.** Pan and zoom the flight map, measure distance and
  azimuth in metres and mils, drop marks with their MGRS grid, and plan your own
  waypoints. It shows your position while your GPS is healthy.
- **Real and Training modes.** Real keeps the goggle view one-to-one with what
  your flight controller can draw. Training adds a minimap, a waypoint compass
  strip and 3D waypoint markers. Train with aids, qualify without them.
- **U.S. military units by default.** MGRS, metres, mils, feet and knots, each
  changeable in Settings.

Planned after that: **land navigation**, with a topographic map, the local
magnetic declination, GPS-denied flying where the position degrades as real
receivers do, and find-and-report-the-target-grid missions scored by error in
metres.

## Download and start

1. [Download KESTREL-alpha-win64.zip](https://github.com/nbschultz97/kestrel/releases/latest/download/KESTREL-alpha-win64.zip)
   (about 1.1 GB) from the [latest release](https://github.com/nbschultz97/kestrel/releases/latest).
   No sign-in is needed.
2. Check the SHA-256 against the release page, then extract the whole ZIP into a
   new folder. Don't run it from inside the ZIP or mix versions.
3. Start **KESTREL.exe**. It is the launcher and updater: it checks the official
   update manifest, verifies a new build's size and SHA-256 before installing,
   and starts the game.
4. Open **Settings > Controller**, calibrate your input and check the axis
   directions. Pick a starter aircraft on the Work Bench, then choose
   **Free Flight**.

Settings, aircraft, records and crash reports live in `Documents\KESTREL`.
Review them before sharing, because they can contain paths and locations.

## System requirements

These are guidance figures, not a certified minimum.

| | Guidance |
|---|---|
| OS | Windows 10 or 11, 64-bit |
| GPU | A modern discrete DirectX 12 GPU. Integrated graphics are not expected to run acceptably. |
| RAM | 16 GB recommended |
| Disk | About 1.1 GB to download and about 2.1 GB extracted |
| Network | Internet for streamed photoreal terrain. Saved areas work offline. |
| Input | RC radio in USB-joystick mode, gamepad or keyboard |

## Honest limits

- **The Windows binaries are unsigned.** SmartScreen may warn, and Smart App
  Control or organization policy may block them. A checksum verifies the
  archive. It is not a publisher signature.
- **Terrain coverage is partial.** Photoreal 3D depends on the provider's
  coverage, your connection and loading time. Detailed buildings are not
  everywhere. Saved-area imagery is public data and looks soft at very low
  altitude.
- **The flight model is not validated against real flights.** It is fitted to
  published thrust-stand and wind-tunnel data. A good simulated flight is not
  proof of how a real aircraft will perform.
- **Fiber reels** have not been flown by a person in the v0.46 package. Payout
  and snag limits are tuning values, not published figures. Crossing your own
  fiber, rotor strike on the fiber and wind drift are not modelled. Other LAN
  players don't see your strand.
- **Radios:** only the RadioMaster Pocket (ELRS, USB joystick mode) is verified
  on real hardware. Keys held by menus (C, F, P, T, U, Y and a few others) can't
  be bound to flight controls yet.
- **Not included:** live weather, online street-address search, TAK or live C2
  integration, and two-PC LAN acceptance.

[ROADMAP.md](ROADMAP.md) tracks unfinished work, and [FEATURES.md](FEATURES.md)
describes scope and evidence in detail.

## Reports, privacy and credits

There is no live reporting endpoint. Crash reports stay local under
`Documents\KESTREL\reports`. [Report issues](https://github.com/nbschultz97/kestrel/issues)
with the version, the steps to reproduce, and what you expected and saw. Never
post tokens.

Unreal Engine, Cesium, and the imagery, map, font, audio and asset providers
keep their rights and attribution. The full notices ship with the game.

## License

KESTREL is proprietary software, not open source. It is free for U.S.
Government personnel and contractors supporting a U.S. Government activity, and
for personal use, under the [KESTREL Evaluation License](LICENSE.txt). For other
licensing, contact [Ceradon Systems](mailto:nbschultz97@gmail.com).
