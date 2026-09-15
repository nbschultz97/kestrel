<div align="center">

<img src="media/kestrel-lockup-web.png" alt="KESTREL — Small UAS Mission Simulation" width="720">

**Build an aircraft. Choose a location. Practise the flight.**

Windows x64 · Alpha · Proprietary evaluation software

[Download v0.42.11](https://github.com/nbschultz97/kestrel/releases/tag/v0.42.11-alpha-unsigned.1) · [Features](FEATURES.md) · [Changelog](CHANGELOG.md) · [Roadmap](ROADMAP.md)

</div>

KESTREL is an Unreal Engine small-UAS flight simulator with a parts-based Work
Bench, saved aircraft, FPV flight, a mission library and editor, and streamed
real-world terrain. It is for simulation and evaluation, not certified navigation,
engineering validation or real-aircraft flight testing.

## Current release

**v0.42.11-alpha-unsigned.1 — September 15, 2026.** This is the default public
download and updater release. The package identifies itself as v0.42.11-alpha.
It supersedes the 0.42.4 default and 0.42.9 optional evaluation. The held 0.42.10
candidate is not a public release.

This is an **unsigned alpha with known defects**, not whole-roadmap completion.
Windows or organization policy may warn or block it. Use only where unsigned
applications are permitted; do not disable protections. “Latest” identifies the
download channel, not production certification.

## Start here

1. [Download KESTREL-alpha-win64.zip](https://github.com/nbschultz97/kestrel/releases/download/v0.42.11-alpha-unsigned.1/KESTREL-alpha-win64.zip).
2. Check its SHA-256 against the release page or attached checksum. Extract into
   a new folder; do not mix versions or run from inside the ZIP.
3. Start **KESTREL.exe**, the player-facing launcher. Keep the entire extracted
   tree beside it; the nested game executable is not the normal entry point.
4. Check controller calibration, input source and axis directions, then save.
   Compatibility with every USB radio has not been established.
5. Choose Free Flight or the Test Range, select a saved aircraft and review the
   displayed controls before arming.

The intended public Cesium configuration is included. Streamed terrain needs
Internet access, service availability and loading time. The offline Test Range
is not a cached copy of the globe; there is no offline worldwide street map.

Windows x64 is supported. Plan for a modern discrete GPU, adequate memory and
space for game extraction, update staging and terrain caches. Exact minimum/
recommended hardware performance is not certified. The ZIP is not a Windows
runtime installer; retain the exact error if launch fails.

## Added and improved in v0.42.11

- **Data & Catalogs:** create, import, export, copy, rename, switch and edit custom
  catalogs using validated JSON. The base catalog stays read-only.
- **Work Bench:** current/source inventory labels, Switch Inventory, saved-build
  identity checks, click-only aircraft selection and selected-aircraft predictions.
- **Navigation:** city/coordinate search previews a movable pin before launch;
  major-city labels, a coarse offline overview, Free Flight C2, place labels
  and a compass aid orientation.
- **Local data:** named collections, placed image overlays and a Cesium connection
  check. Raw GIS/point clouds still need conversion.
- **Aircraft:** stock starters, targeted ten-inch prop compatibility, frame-grounded
  support metadata, stack spacers and selected receiver/video-board supports.
- **Reliability:** controller failed-save preservation, clearer Settings values,
  targeted thumbnail residency, per-aircraft audio teardown, terrain request
  handling and Cesium world/component lifecycle fixes.
- **Distribution:** public notices and font licenses, bundled public terrain
  configuration, HTTPS-only updater redirects and bounded request timing.

Existing flight, Work Bench, named builds, missions/editor, ranges, records,
modeled weather and wind remain. See [FEATURES.md](FEATURES.md) for boundaries.
Configured weather is not a live weather service.

## Known issues and unfinished work

- **Live C2 regression:** launch/objective symbols, labels and the connecting route
  can be absent in flight even when the loading brief displays them.
- Some menu/help text overlaps or clips; battery labels/thumbnails, carbon-fiber
  appearance, straps, wiring and exact part mounting still need visual work.
- LAN passed a streamed two-process test on one PC, but **physical two-PC LAN is
  not yet accepted**. Mission networking, reconnect and host-loss need further tests.
- Full action rebinding, the Work Bench OSD editor and rotating lobby aircraft
  cards are **not included**. Map Controls is only map-action binding.
- Physical radio/display-mode checks, the full camera/prop matrix and calibrated
  flight-feel comparisons remain open. No universal parts-fit claim is made.
- Online street-address/POI search and live weather are not included.

The [roadmap](ROADMAP.md) retains the rest of the asset, animation, mission,
UI, replay and acceptance work. This release does not complete that backlog.

## Verification and updates

Exact source: `008b4834b9e62d166fafec5ba31aebe5746eb261`.
The fresh full cook and package passed; all **4,451** archived files were checked
against the reviewed staged inventory and independently extracted.

**70 native tests** passed (67 clean, 3 expected-warning results), and **218
launcher tests** passed. Packaged checks included 16 focused UI captures, a
110-frame/14-stage tour and streamed one-PC LAN with distinct spawns, Ready/start,
armed input and reciprocal movement. Only selected tour images were manually
reviewed. This does not prove physical controller, two-PC or whole-game acceptance.

The unchanged tested ZIP is 676,635,054 bytes. SHA-256:
`b051168de33fc48afff99af7afdd635ae42a6e61650951d4d7ff8b031fc24016`.

Existing launchers check the default updater manifest for this numerically newer
release. Back up local settings and aircraft before updating. Complete real-install
update/start/rollback and user-profile preservation acceptance remains tracked;
unit tests are not a substitute for it. Embedded build notes retain historical
“candidate” wording because the validated ZIP was promoted unchanged.

## Reports, privacy and credits

No live reporting endpoint is bundled. Reports remain local, normally under
`Documents/KESTREL/reports`. Review logs and screenshots before sharing: they may
contain personal paths or locations. [Report issues](https://github.com/nbschultz97/kestrel/issues)
with version, reproduction steps, expected and actual results. Never post tokens.

Customer inventories, missions, datasets and personal profiles are not bundled.
Generic data/catalog tools do not authorize redistribution of customer inputs.

![Historical KESTREL gameplay](media/gameplay.gif)

[Historical trailer with sound](https://github.com/nbschultz97/kestrel/releases/download/v0.29.1-alpha/kestrel-trailer-v9.mp4).
These older images are illustrations, not current-release acceptance evidence.

KESTREL is not open source. See the [Evaluation License](LICENSE.txt) and shipped
third-party notices. Unreal Engine, Cesium and imagery, map, font, audio and asset
providers retain their rights and attribution. For licensing contact
[Ceradon Systems](mailto:nbschultz97@gmail.com). Older notes: [RELEASE_NOTES.md](RELEASE_NOTES.md).
