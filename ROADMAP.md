# KESTREL public roadmap

Updated October 8, 2026. This is a work/status plan, not a release announcement
or delivery-date promise. [README](README.md) identifies downloadable builds;
[FEATURES](FEATURES.md) describes capabilities and limits;
[CHANGELOG](CHANGELOG.md) records version-specific evidence.

## Release reality

- **KESTREL v0.44** is published as `v0.44.0-alpha.1`; the package identifies itself as `v0.44.0-alpha`.
- GitHub Latest and automatic updates serve v0.44. The isolated v0.42.11-to-v0.44 upgrade preserved test data, passed a cold rendered launch and reported current on a subsequent check.
- Source `5444e5238f5e884a37adc4e64df150206cd6f643`; ZIP size 679,194,737 bytes;
  SHA-256 `495d62f4f2039a40a7341f483965e7048375f9bce419b8070885c3d41611b69e`.
- Publication does not mean that missing features or manual checks passed.
- Earlier releases retain their original tags and evidence; 0.42.10 remains a historical held candidate.

## v0.44 Flight Review

- [x] Native ArduPilot DataFlash BIN replay, timeline and camera controls, telemetry, trail toggle and duplicate live-aircraft suppression.
- [x] Tab minimizes/expands review controls; Escape opens the normal pause menu. Unavailable playback controls are disabled.
- [x] Read-only Mission Planner QGC WPL 110 inspection in Data & Catalogs. This does not import a playable mission or execute a flight.
- [x] Work Bench inventory-mismatch action, supported simulator OSD layout editing and bounded Betaflight OSD text interchange retained.
- [x] Fresh build/cook/package, 218 launcher tests, all 4,453 archive files/CRCs verified and eight packaged replay/inspection tests passed.
- [x] Synthetic waypoint inspection UI rendered and reviewed from the extracted package.
- [ ] Authored fixed-wing/rover/submersible visual upgrades and exact-airframe identification.
- [ ] Customer raw GIS/point-cloud conversion and validated rendered 3D customer layers. Customer 3D rendering is not established by this release.
- [ ] Broader recording/debrief, hardware and service-failure acceptance beyond the bounded checks above.

Historical sections below retain the evidence and unfinished acceptance from their named release checkpoints.

## v0.42.13 flight controls

- [x] Three-action editor: Map and camera tilt up/down, with keyboard and digital
  gamepad binding, Clear, Restore defaults, Save changes and Cancel.
- [x] Legacy Map migration, unknown-profile-data preservation, checked atomic
  saving and retained drafts after failure.
- [x] Independent menu arrows, one tilt step per fresh press, conflict checks
  and held/reconnect/context suppression.
- [x] Calibration reset preserves action bindings; action defaults preserve
  calibration. Existing digital USB-radio Map support remains.
- [x] Development Editor/Game builds, 136 focused source checks, 13 native
  controller tests and 16 native display regressions.
- [x] Default-state development panel review at 720p and 1080p.
- [x] Fresh v0.42.13 full cook/package and all 218 launcher tests.
- [x] Independent archive/source identity and all 4,451 extracted file hashes;
  packaged controls captures at 720p and 1080p, with unchanged personal profiles.
- [x] Unauthenticated public HTTPS ZIP download matched the exact released size
  and SHA-256 on September 17, 2026; this is not an installed-update test.
- [ ] Physical keyboard/gamepad/radio and unplug/reconnect acceptance.
- [ ] Remaining action editor: arm/disarm, restart, flight mode, view/low-light
  and other existing controls; USB-radio tilt and axis-switch actions.

This slice does not complete the OSD editor, lobby previews or the full input
backlog. Development captures are not packaged or physical-device acceptance.

## Retained v0.42.12 display update

- [x] Separate monitor selection from Windowed/Fullscreen/Borderless mode;
  default Auto chooses the highest-resolution attached panel.
- [x] Fit windowed sizing and mixed-DPI transitions to the chosen work area;
  preserve the selected monitor by identity.
- [x] Keep/Revert confirmation and real-time rollback for Settings changes;
  route Alt+Enter/F11 through the same display and rendering logic.
- [x] Rendered development and packaged-candidate transitions, confirmation and
  saved-monitor restart checks on two mixed-DPI monitors.
- [x] Final archive identity, fresh full build/cook/package and 218 launcher tests.
- [x] Final-package rendered window-transition, confirmation and restart checks.
- [x] Independent final-archive review, CRC validation and all 4,451 extracted hashes.
- [x] Public HTTPS ZIP download matched the exact released size and SHA-256.
- [ ] A passing disposable installed-update test
  before automatic updater promotion. Download verification is not an installed upgrade.
- [ ] Human dragging, live/fully paused-flight shortcut input and physical
  monitor unplug/reconnect acceptance. Disabled controller ticking in a timeout
  test is not proof of fully paused gameplay.

These results do not complete physical-controller or multiplayer acceptance.
Release publication and updater promotion are verified separately from these tests.

## Historical v0.42.11 artifact evidence

- [x] Fresh full cook, source/provenance and reviewed staged/container inventory.
- [x] All 4,451 archive files independently extracted and hashed.
- [x] 70 native and 218 launcher tests; focused packaged UI captures.
- [x] 110-frame/14-stage packaged tour; selected frames manually reviewed.
- [x] One-PC streamed LAN: lobby/Ready/start, distinct spawns, owned input and
  reciprocal movement. This is not a physical two-PC result.

## Known defects and remaining acceptance

| Area | Still required |
|---|---|
| Live C2 markers | Fix missing launch/objective symbols, labels and route in live C2; compare loading brief and sustained in-flight map with actual pixel checks. Root cause remains unproven. |
| UI and art | Fix overlapping preflight/help text, clipped/crowded stats and builder controls, provider-footer crowding without removing attribution, dark battery labels/thumbnails and overly bright/glossy carbon. |
| Aircraft | Review frame-specific supports, straps, wiring, exact camera/RX/VTX seating and full camera/prop/RPM matrix. Catalog compatibility is not mechanical-fit certification. |
| Low-light visuals | Investigate the overbright dusk horizon and horizontal band visible in dusk/night FPV captures. Cause is not established; verify the correction without retouching captures or hiding problem geometry. |
| Effect presentation | Review flat-looking fire cards in the strike capture and preserve the distinction between a scripted visual effect, physical contact and the actual objective verdict. |
| Terrain and lifecycle | Broader cold-network/service-error, constrained-memory, world-travel and material checks; preserve strict loading/ground readiness. |
| Controls and display | The v0.42.13 editor covers Map and camera tilt up/down; full action mapping, radio tilt and radio axis-switch actions remain open. v0.42.12 separate monitor/mode controls retain their bounded display evidence. Still verify physical controller/backend/reconnect behavior, human title-bar dragging, actual Alt+Enter/F11 during live and fully paused flight, focus changes and monitor unplug/reconnect. |
| Catalogs and saves | Wider interactive CRUD/file-dialog/save/reopen/cancel/fly and legacy-save migration; do not silently substitute parts. |
| Multiplayer | Physical two-PC discovery/direct join, shared travel, input, movement, mission parity, leave/rejoin and host loss. |
| Updater | The isolated v0.42.11-to-v0.44 upgrade, test-data preservation, cold rendered launch and subsequent no-reinstall check passed. Broader offline, interruption, corrupt-download and rollback/recovery acceptance remain separate. |
| Mirrors | GitHub and Rotopter publish v0.44; the Rotopter ZIP was downloaded back and matched the release size and SHA-256. Rotopter currently requires sign-in for asset downloads, so GitHub remains the primary public download. Preserve each repository's history and verify new artifact bytes independently. MilGit access/parity remains unresolved. |

Unsigned distribution must remain explicitly identified and be used only where
permitted. Production publisher signing has not been established. Do not change
Windows trust, disable protection or relax signed-publication requirements to
make a test or release pass.

## Unfinished user-facing work

### Controls and OSD

- Warn before leaving a controls draft with unapplied changes, keeping capture
  cancellation separate from discarding edits. This follow-up is not in v0.42.13.
- Complete action rebinding beyond Map and camera tilt up/down: arm/disarm,
  restart, flight mode, camera view/low-light and other implemented actions,
  with contexts, capture/cancel/conflicts and reliable save/restart behavior.
- Add supported USB-radio tilt and radio axis-switch actions with explicit
  device ownership and activation semantics.
- Extend the shipped Work Bench OSD editor beyond its supported simulator readouts and bounded Betaflight text interchange; complete Configurator parity and exact-hardware behavior remain unverified.
- Broaden saved-layout, preview and physical-display acceptance across supported configurations.
- Broader physical controller/backend, reconnect and latency coverage.

### Aircraft confidence and Work Bench

- Wider exact-product and representative-class distinction, mounting/support
  coverage and placement-conflict feedback across the catalog.
- Real geometry/contact/clearance checks rather than bounding-box assumptions.
- Complete camera/prop/RPM/exposure acceptance and exact-aircraft flight-feel
  comparisons, with calibration limits stated explicitly.
- Remaining thumbnail latency, dark labels, battery/strap, wiring and restraint
  polish. Targeted fixes are not whole-catalog acceptance.
- More accessible structured catalog editing beyond the current JSON draft editor.

- Structured per-part catalog forms and dependency-aware catalog/SKU deletion.

### World, navigation and data

- Reliable complete flows under cold caches, service errors and constrained
  memory; clear feedback without weakening terrain readiness.
- Wider customer-supplied dataset conversion and validation. Raw GIS/point-cloud
  import must not be described as ready terrain before conversion succeeds.
- Online street-address/point-of-interest search and live observed weather are
  not included; the present offline overview and modeled weather are separate.

### Multiplayer

- Complete physical two-PC acceptance before describing LAN as dependable.
- Rotating aircraft cards/previews in multiplayer, with correct identity and
  resource ownership.
- Broader shared-world, audio, reconnect and host-loss behavior, followed by
  clearly scoped multiplayer mission support rather than implied parity.

### Characters, vehicles, environments and effects

- Complete character materials, rig/retarget validation, locomotion and reliable
  foot/ground contact; production animation and visible peer parity remain open.
- Animate vehicle motion and authored moving parts consistently with game state,
  rather than treating a posed mesh as a working animation system.
- Improve terrain-adjacent environments, tunnels, interiors and vegetation:
  connected entrances, collision, material/lighting quality and performance need
  rendered checks. Imported or generated assets alone do not clear those gates.
- Finish game-only visual and audio effects with coherent event timing,
  occlusion, finite lifetimes and near/far performance budgets. Validate daylight,
  night, interior, FPV and multiplayer presentation; these are fictional game
  effects, not real-world effects models.
- Retain asset-specific provenance and distribution review before packaging;
  this roadmap does not assert that all planned assets have been acquired or licensed.

### Capture, records and replay regression coverage

- Expand isolated packaged visual tours across supported resolutions and full
  user flows. Missing/stale screenshots, timeouts and skipped stages must fail,
  with source/package identity retained beside the evidence.
- Extend the shipped Flight Review timeline and playback controls into broader comparative debrief, conditions and build/tune/content identity. The Records page is separate; replay inspection does not establish full recording/debrief parity.
- Add recording/playback and save-migration regressions as those paths are
  implemented, alongside frame-time, memory and load-time budgets.

These are open items, not completed features or a claim that the full list ships
in v0.44 or earlier releases. The release's actual scope and any explicitly deferred work must be
stated before promotion.

## What counts as done

A feature needs a reachable user workflow, honest failure/cancel behavior,
persistence where promised, and validation on the actual package. A regression
fix needs a check that exercises the failure, not just successful compilation.
A visual change needs rendered review; hardware behavior needs hardware testing;
network claims need the corresponding machines and network conditions.

Evidence stays attached to its exact source, package and test scope. Tests from
older archives remain historical. Private user content is never evidence to
copy into public docs or artifacts. Dates and counts here are checkpoints, not
an invitation to mark the rest of the roadmap complete.
