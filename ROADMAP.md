# KESTREL public roadmap

Updated September 14, 2026. This is a work/status plan, not a release announcement
or delivery-date promise. [README](README.md) identifies downloadable builds;
[FEATURES](FEATURES.md) describes capabilities and limits;
[CHANGELOG](CHANGELOG.md) records version-specific evidence.

## Release reality

- Default public download and updater: **v0.42.4-alpha-unsigned.1**.
- Optional manual-install public evaluation: **v0.42.9-alpha-eval.1**.
- **v0.42.11-alpha remains an unpublished candidate.** Selected native64 and
  launcher103 checks passed at the recorded code checkpoint. A full package run
  completed with a validated supervisor receipt; source privacy cleanup requires
  a replacement package and fresh acceptance before promotion.

The priority is fixes followed by validation. A code change, passing unit test,
screenshot or successful cook alone does not complete the release. If source
changes again, the relevant acceptance must follow the new source and archive.

## Current release gates

| Gate | Status and required outcome |
|---|---|
| Fresh package identity | Replacement required after source privacy cleanup. Record its exact source/version and ZIP hash; verify cook provenance and all archive entries, then independently extract and hash every file. |
| Public-content boundary | Inspect loose files and cooked containers. Exclude private profiles, inventories, datasets and machine-local editor settings; include only intended public configuration and distribution notices. |
| Complete user flow | Repeat startup, location preview, mission author/save/reopen, aircraft save/select, preflight and flight on the fresh package. A loading timeout or skipped stage is not a pass. |
| Terrain and lifecycle | Repeat cold-cache loading, world travel and teardown. Preserve loading, ground and calibration requirements; a timeout fallback must not earn verified readiness. |
| Controls and display | Validate calibration, binding capture/recovery, saved settings, focus and windowed/fullscreen/borderless transitions with real input/display hardware. |
| Inventory and saved aircraft | Exercise create/import/copy/edit/export/switch and save/reopen/fly. Verify unsaved-work protection, missing-inventory feedback and no silent part substitutions. |
| Multiplayer | Physical two-PC discovery/direct address, lobby/ready/start, terrain loading, input, movement, remote-aircraft parity and leave/rejoin/host loss. One-PC two-process evidence is insufficient. |
| Download and updater | Verify the actual candidate download, normal update, offline behavior, corrupt-download rejection, rollback/recovery and preservation of user data. Unit checks alone do not clear this gate. |
| Publication | Promote only the reviewed artifact with matching notes, checksums, channel metadata and any supported mirrors. No candidate promotion has occurred. |

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
in v0.42.11. The release's actual scope and any explicitly deferred work must be
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
