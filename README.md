<div align="center">

<img src="media/kestrel-lockup-web.png" alt="KESTREL — Small UAS Mission Simulation" width="720">

**Build an aircraft. Choose a location. Practise the flight.**

Windows x64 · Alpha · Proprietary software

[Download v0.44.4](https://github.com/nbschultz97/kestrel/releases/tag/v0.44.4-alpha.1) · [Features](FEATURES.md) · [Changelog](CHANGELOG.md) · [Roadmap](ROADMAP.md)

</div>

KESTREL is an Unreal Engine small-UAS flight simulator with a parts-based Work
Bench, saved aircraft, FPV flight and Flight Review. This repository distributes
the public Windows alpha; it does not distribute the private source repository.

![Fixed-wing flight replay in KESTREL](media/v0.44/kestrel-fixed-wing-replay.gif)

Previously authorized user-recorded Flight Review footage from v0.44; retained unchanged.

## KESTREL v0.44.4 - Flight Review, controls and presentation

Package version: `v0.44.4-alpha`. Release tag: `v0.44.4-alpha.1`.
See the [release page](https://github.com/nbschultz97/kestrel/releases/tag/v0.44.4-alpha.1) for the exact source revision, archive checksum,
package checks and remaining acceptance limits.

- Open ArduPilot DataFlash BIN recordings in **Flight Review**. Tab expands or
  minimizes controls; Escape opens the normal pause menu. Review telemetry,
  switch cameras and toggle the trail. The simulator aircraft is hidden during
  review to avoid a duplicate vehicle.
- Flight Review includes detailed representative fixed-wing and rover visuals,
  clearer controls, corrected FPV visibility and softer trails. Failed replacement
  imports clear the previous recording, and status labels avoid missing-glyph boxes.
- **Parts libraries** keep saved aircraft in their owning library. Transfer
  libraries as JSON or XLSX and builds as `.build.json`. Paired transfers retain
  library identity; conflicting imports are refused without overwriting files.
  Removing a library warns about its saved builds.
- Configure nine keyboard or digital-gamepad actions across two compact pages:
  Map, camera tilt up/down, Restart, View, Arm/disarm, Mode, Low-light and Launch
  point. Existing assignments take precedence over new defaults. This is not
  complete axis or contextual-control rebinding.
- Change compatible saved builds during Free Flight. The automatic desktop view
  caps horizontal FOV at 100 degrees while preserving explicit user preferences;
  the flight OSD uses smaller glyphs.
- Modular character presentation, fitted pilot props, brighter framed previews,
  menu music and navigation sounds improve the presentation. Generic effects
  respect Master and Effects volume.
- Inspect Mission Planner **QGC WPL 110** exports in **Data & Catalogs > Flight
  files**. This is read-only inspection, not playable mission import or execution.
  QGroundControl `.plan` files are not supported.

Earlier features and release evidence remain in [CHANGELOG.md](CHANGELOG.md).
[FEATURES.md](FEATURES.md) describes scope; [ROADMAP.md](ROADMAP.md) tracks unfinished work.

## Download and start

GitHub downloads are available without signing in. The Rotopter host currently
requires a signed-in account; both packages use the GitHub updater channel.

1. [Download KESTREL-alpha-win64.zip](https://github.com/nbschultz97/kestrel/releases/download/v0.44.4-alpha.1/KESTREL-alpha-win64.zip). The same release is available on
   [GitHub](https://github.com/nbschultz97/kestrel/releases/tag/v0.44.4-alpha.1)
   and [Rotopter](https://git.rotopter.com/nschultz/Kestral/releases/tag/v0.44.4-alpha.1).
2. Check SHA-256 against the release page or attached checksum, then extract the
   entire ZIP into a new folder. Do not mix versions or run from inside the ZIP.
3. Start **KESTREL.exe**, the player-facing launcher. Keep the extracted tree
   intact; the nested game executable is not the normal entry point.
4. Check input source, calibration and axis directions, then save. Choose a
   starter aircraft in Work Bench and review controls before Free Flight.

Windows binaries are unsigned. Windows or organization policy may block them.
Checksums verify archive identity; they are not publisher signatures.
Windows x64 and a modern discrete GPU are expected; exact minimum hardware
performance and compatibility with every USB radio are not certified.

## Updates and local data

The current update channel serves **v0.44.4-alpha**. An isolated update from
v0.44.2 passed all 4,456 payload hashes, preserved synthetic local files,
started successfully after restart, and correctly reported current on a second
check. This does not certify every user profile or Windows policy.

The launcher checks the official GitHub-hosted update manifest. GitHub and
Rotopter packages use the same updater channel. A versioned release link and
GitHub Latest/default-updater promotion are separate steps: the release page
records which upgrade checks have passed. The launcher downloads the version
selected by the manifest and verifies its size and SHA-256 before installation.
A published ZIP alone does not prove that an installed upgrade passed.

Back up local settings and aircraft before updating. Local profiles and reports
normally live under `Documents/KESTREL`; do not publish them accidentally.
The public build includes the approved public terrain configuration. Streaming
requires Internet access, provider availability, coverage and loading time.
The offline Test Range is not an offline copy of the globe.

## Known limits

- Full rebinding and physical two-PC LAN acceptance remain incomplete;
  experimental LAN is included.
- Some dense settings rows still shorten long text. The character/equipment and
  vehicle presentation is not a complete diversity or exact-hardware overhaul.
- Raw GIS and point-cloud inputs need conversion; merely adding a reference
  does not render customer 3D scenery. Customer layers, recordings and private
  parts libraries are not bundled.
- Configured weather is not live weather. Online street-address/POI search and
  TAK/live-C2 integration are not included.
- This alpha does not establish calibrated real-aircraft behavior, universal
  component fit, whole-roadmap completion or production certification.

## Historical gameplay images

These existing images are from v0.42.11, not new v0.44.4 acceptance captures.

![FPV view in KESTREL v0.42.11](media/v0.42.11/flight.png)

Actual in-engine footage captured by a virtual pilot, not a manual-flight test.

![Work Bench in KESTREL v0.42.11](media/v0.42.11/workbench.png)

Inspect fitted components and saved aircraft. This older view does not establish
real-world component fit or show the latest interface.

## Reports, privacy and credits

No live reporting endpoint is bundled. Reports remain local, normally under
`Documents/KESTREL/reports`. Review logs and screenshots before sharing: they may
contain personal paths or locations. [Report issues](https://github.com/nbschultz97/kestrel/issues)
with version, reproduction steps, expected and actual results. Never post tokens.

KESTREL is not open source. See the [License](LICENSE.txt) and shipped
third-party notices. Unreal Engine, Cesium and imagery, map, font, audio and asset
providers retain their rights and attribution. For licensing contact
[Ceradon Systems](mailto:nbschultz97@gmail.com). Older notes: [RELEASE_NOTES.md](RELEASE_NOTES.md).
