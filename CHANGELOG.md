# KESTREL changelog

Public status checked September 14, 2026. This file distinguishes downloadable
releases from unreleased work. The updater manifest is separate from this document.
See [README](README.md) for installation and [FEATURES](FEATURES.md) for capability
limits. Older version-specific notes are retained in [RELEASE_NOTES](RELEASE_NOTES.md).

## Unreleased — v0.42.11-alpha candidate

Not a public release, not GitHub Latest and not an in-app update. A full
cook/package run completed successfully, but source privacy cleanup requires a
replacement package before promotion. The replacement needs its own source,
archive/content and packaged-runtime acceptance.

### Candidate capabilities and corrections

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
  in candidate source, not the v0.42.9 public evaluation.
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

### Evidence at this checkpoint

Candidate code checkpoint `a586f767ae24e98104b78f78e8d6f8a3ebace5c1`:

- Selected native automation: **64 passed**, comprising 62 clean results and
  2 results with expected warnings.
- Launcher/update unit checks: **103 passed, 0 failed**.
- The full cook/package run exited normally with code zero, and its supervisor
  receipt was validated. This package is not eligible for promotion because
  source privacy cleanup requires a replacement build.
- No completed fresh packaged-runtime, whole-app walkthrough or public
  download/update acceptance is claimed. The replacement must pass those gates.

These results belong to this code checkpoint, not every later source change.
They do not turn prior package tests into acceptance of a new ZIP.

### Still open

Full action rebinding; a Work Bench OSD editor; rotating multiplayer aircraft
cards; physical USB-radio and window-mode testing; physical two-PC LAN; cold-cache
terrain/world-travel validation; complete camera/prop/flight-feel acceptance;
whole-catalog mechanical/artwork coverage; and the actual release download/update
and profile-preservation path. See [ROADMAP](ROADMAP.md).

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

## v0.42.4-alpha-unsigned.1 — current default public release

Published September 1, 2026. [Exact release and verification record](https://github.com/nbschultz97/kestrel/releases/tag/v0.42.4-alpha-unsigned.1).
GitHub Latest and the current in-app updater point to this artifact; the package
version is `v0.42.4-alpha`.

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
