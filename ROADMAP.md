# KESTREL public roadmap

Updated September 16, 2026. This is a work/status plan, not a release announcement
or delivery-date promise. [README](README.md) identifies downloadable builds;
[FEATURES](FEATURES.md) describes capabilities and limits;
[CHANGELOG](CHANGELOG.md) records version-specific evidence.

## Release reality

- **KESTREL v0.42.12** is the display-focused release described here.
- Source `32401cce14394e7eef324be62738c8b813a65a3f`; ZIP size 676,690,392 bytes;
  SHA-256 `5ca8c620c90909f71318a8e5eae5defacf235277ddc15bdaad35abda5895098e`.
- Publication does not mean that missing features or manual checks passed.
- Prior 0.42.4/0.42.9/0.42.11 releases remain historical; 0.42.10 remains held.

## v0.42.12 display update

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
- [ ] Disposable HTTPS installed-update check before default updater promotion.
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
| Controls and display | v0.42.12 adds separate monitor/mode controls and passes bounded rendered transitions, confirmation and restart checks. Still verify human title-bar dragging, actual Alt+Enter/F11 during live and fully paused flight, focus changes and physical monitor unplug/reconnect. Physical-radio/backend availability and reconnect coverage remain separate. |
| Catalogs and saves | Wider interactive CRUD/file-dialog/save/reopen/cancel/fly and legacy-save migration; do not silently substitute parts. |
| Multiplayer | Physical two-PC discovery/direct join, shared travel, input, movement, mission parity, leave/rejoin and host loss. |
| Updater | Real-install detect/download/install/start and user-data preservation; offline, interruption, corrupt download and rollback/recovery acceptance. Unit tests alone are not completion. |
| Mirrors | Preserve verified historical v0.42.11 identities while preparing the next release. Check each new mirror's Git tree and artifact bytes separately; Rotopter anonymous access and MilGit access/parity remain unresolved. |

Unsigned distribution must remain explicitly identified and be used only where
permitted. Production publisher signing has not been established. Do not change
Windows trust, disable protection or relax signed-publication requirements to
make a test or release pass.

## Unfinished user-facing work

### Controls and OSD

- Complete action rebinding, not only the map action: visible action inventory,
  capture/cancel/conflict handling, defaults and reliable save/restart behavior.
- A Work Bench OSD editor with analog/digital grids, element visibility and
  placement, saved layouts/profiles, reset and import/export.
- Preview OSD layouts through the same renderer used in flight, rather than a
  disconnected mock-up. Existing telemetry rendering is not this editor.
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
- Extend records into a coherent replay/debrief timeline with controls, events,
  conditions and build/tune/content identity. Timeline scrubbing and comparative
  review are future work, not capabilities established by the current Records page.
- Add recording/playback and save-migration regressions as those paths are
  implemented, alongside frame-time, memory and load-time budgets.

These are open items, not completed features or a claim that the full list ships
in v0.42.11 or v0.42.12. The release's actual scope and any explicitly deferred work must be
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
