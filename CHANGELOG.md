# KESTREL changelog

Public status checked September 15, 2026. This file distinguishes downloadable
releases from unreleased work. The updater manifest is separate from this document.
See [README](README.md) for installation and [FEATURES](FEATURES.md) for capability
limits. Older version-specific notes are retained in [RELEASE_NOTES](RELEASE_NOTES.md).

## KESTREL v0.42.11 — public release

Published September 15, 2026. [Release and immutable download](https://github.com/nbschultz97/kestrel/releases/tag/v0.42.11-alpha-unsigned.1).
Promoted unchanged from the tested v0.42.11-alpha package, with known defects.
The ZIP's embedded build notes retain the original candidate status.

### Included capabilities and corrections

- Data & Catalogs provides visible custom-catalog creation, import, copy, rename,
  export, selection and validated JSON editing. The bundled base remains read-only.
- Work Bench/shelf shows current and source inventories, exposes Switch Inventory,
  protects unsaved work and reports unresolved saved-aircraft identities.
- Local data collections support placed image overlays and explicit activation.
  Raw GIS, point-cloud and archive inputs remain conversion work, not loaded terrain.
- Cesium configuration status is separate from an explicit connection check;
  the panel does not expose the raw token.
- City/coordinate search previews a movable pin before launch. Coarse offline
  map orientation, city labels and Free Flight C2 map/compass additions are included
  in this release, not the historical v0.42.9 evaluation.
- Click-only aircraft selection, selected-aircraft predictions, exact stock
  starter identities, targeted prop compatibility and loading hints.
- Frame/board support metadata, visible stack spacers and targeted receiver/video
  mounting, with representative/unverified/conflict labels. No universal physical-fit claim.
- Receiver-supplied antenna ownership and mass scope are shown explicitly.
- Targeted thumbnail residency, inventory-header layout and display-state
  synchronization changes; 1280x720 interactive layout minimum.
- Per-aircraft audio teardown ordering and Cesium component/world-lifecycle guards.
- Terrain height-request lifetime/result classification, final-attempt retention
  and sample consumption fixes; stronger full-tour failure diagnostics without
  relaxing terrain readiness.
- Clearer launcher missing-terrain-configuration wording, curated public notes,
  third-party notices and font/source licenses; machine-local editor service
  settings excluded from cooking.

### Verification and identity

Source: `008b4834b9e62d166fafec5ba31aebe5746eb261`.
Archive: `KESTREL-alpha-win64.zip`, **676,635,054 bytes**.
SHA-256: `b051168de33fc48afff99af7afdd635ae42a6e61650951d4d7ff8b031fc24016`.

- Fresh Editor build, full Game cook/package and reviewed public-content boundary.
- All **4,451** staged/archive/extracted file identities matched.
- **70 native tests**: 67 clean plus 3 expected-warning results.
- **218 launcher tests**, including failed-save and HTTPS redirect/time-budget checks.
- **16 focused UI captures**; **110-frame/14-stage** full packaged UI tour.
  All focused images and selected full-tour frames visually reviewed.
- Streamed **one-PC two-process LAN** passed discovery, lobby approval/Ready/start,
  separate spawns, armed input and reciprocal motion. Not physical two-PC acceptance.
- Settings current-value readability at 720p, actual selected-aircraft preflight
  capture and complete battery-list capture coverage corrected. Capture coverage
  does not certify the appearance of every part.

### Known defects and unfinished work

Live C2 can omit launch/objective labels, symbols and the connecting route even
when they appear in the loading brief; root cause is still under investigation.
Remaining preflight/help overlap, clipped/crowded UI, dark battery artwork,
carbon appearance and exact mounts/straps/wiring are not fixed by this release.

Full action rebinding, Work Bench OSD editing and rotating lobby aircraft cards
are deferred. Physical USB-radio/display checks, two-PC LAN and mission/host-loss
acceptance, calibrated camera/prop/flight-feel comparisons, broader terrain stress
and actual-install updater/rollback/profile checks remain open. Online
street-address/POI lookup and live weather are not included. See [ROADMAP](ROADMAP.md).

The intended public Cesium configuration is bundled; no live reporting endpoint
or customer content is bundled. Unsigned software must be permitted by the
user's environment; do not disable protections.

## Unreleased — v0.42.10 candidate line

Held after playtesting exposed controller capture, aircraft-selection and catalog
compatibility defects; additional input/display and OSD scope remained open.
There is no public 0.42.10 release or automatic-update promotion. Historical
candidate notes and test records are not proof that the upcoming package is fixed.

## v0.42.9-alpha-eval.1 — public optional evaluation

Published September 9, 2026. [Exact release and verification record](https://github.com/nbschultz97/kestrel/releases/tag/v0.42.9-alpha-eval.1).

- Accumulated Work Bench/UI and launch-readiness work through source `0635ef56`.
- Targeted frame/motor/prop compatibility feedback and click-time validation,
  with six complete ten-inch combinations validated for that package.
- Visible-category thumbnail scheduling, render-readiness guards and a targeted
  blank motor-thumbnail repair.
- Work Bench, preflight and mission-list presentation corrections.
- Intended public Cesium configuration bundled; no live reporting endpoint.

Unsigned, separate-folder manual install. The city-search preview, coarse overview,
Free Flight C2 map, new map bindings and Data & Catalogs workflow described above
are **not included**. Physical controller/two-PC LAN and broader visual acceptance
were not declared complete. It did not change the default updater channel.

Archive: `KESTREL-alpha-win64.zip`, 676,170,597 bytes.
SHA-256: `6354f20edec20db81244fcd4f9572e13d5cf27a84a01e46428b6e93f7aa1c89a`.

## v0.42.4-alpha-unsigned.1 — previous default public release

Published September 1, 2026. [Exact release and verification record](https://github.com/nbschultz97/kestrel/releases/tag/v0.42.4-alpha-unsigned.1).
Former GitHub Latest/updater artifact, superseded by v0.42.11 on September 15.
The package version is `v0.42.4-alpha`.

- Boot-menu Settings loads all four controller inversion values before a flight
  pawn exists.
- Each toggle saves once; failed saves restore the prior value and report a warning.
- Live-aircraft changes and calibration refresh the displayed Settings values.

That release's record includes its native/launcher tests, packaged smoke and
interactive inversion/restart-persistence check. Those checks do not validate
newer candidate code or establish support for every physical input device.

Archive: `KESTREL-alpha-win64.zip`, 673,206,885 bytes.
SHA-256: `f651a3598d524f1354dfec1ea7667206e014284fe7d74625129ac444f05ae3a4`.

The build is unsigned. Use only where unsigned software is permitted; do not
weaken Windows or organization security. The launcher compares numeric
major.minor.patch, so a future update must have a higher numeric version; a
new suffix on the same version is not an upgrade path.

## Earlier releases

The [official release history](https://github.com/nbschultz97/kestrel/releases)
and [historical notes](RELEASE_NOTES.md) retain older changes. Experimental LAN
test packages and held candidates are not substitutes for the current default
release or evidence of successful physical two-PC acceptance.
