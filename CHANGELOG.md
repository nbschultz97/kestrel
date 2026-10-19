# KESTREL changelog

Updated October 19, 2026. This file distinguishes downloadable
releases from unreleased work. The updater manifest is separate from this document.
See [README](README.md) for installation and [FEATURES](FEATURES.md) for capability
limits. Older version-specific notes are retained in [RELEASE_NOTES](RELEASE_NOTES.md).


## KESTREL v0.44.4 - Flight Review, controls and presentation

Published on GitHub and Rotopter. The default updater serves this version.
Validation: 218 launcher checks, 31 packaged native checks, 12 reviewed UI
captures, and an installed v0.44.2 upgrade with cold restart, payload verification,
synthetic local-file preservation and a no-reinstall second check passed.

Package version: `v0.44.4-alpha`; release tag: `v0.44.4-alpha.1`.
Source: `a62d0a79ad7de38be18335a5ca61af47ff775ac6`.

- Flight Review clears the previous recording before a failed replacement import,
  avoids identifying custom firmware prefixes as standard vehicles, and explains
  the difference between mission definitions and recorded flight logs.
- Controls adds configurable Mode, Low-light and Launch-point actions, with two
  compact pages and readable gamepad labels. Existing saved assignments take
  precedence over added defaults. Keyboard axes and contextual replay bindings
  are not yet fully configurable.
- Human presentation uses modular character bodies and fitted pilot props.
  Preview framing uses saved pose bounds, with brighter character thumbnails.
  This is not a complete equipment or character-diversity overhaul.
- Free Flight supports changing compatible saved builds during a session.
- The automatic desktop view caps horizontal FOV at 100 degrees while preserving
  explicit user preferences. The compact OSD uses smaller telemetry glyphs.

- Parts libraries replace the inventory label. Work Bench lists only builds
  belonging to the selected library; removing a library warns about its saved builds.
- Import and export parts libraries as JSON or XLSX, and saved builds as
  .build.json. Paired transfers retain library identity; conflicting imports
  are refused without overwriting files. Copy creates a separate library.
- XLSX import supports explicit part roles/categories, stable IDs and supported
  unit headers. Values-only spreadsheets are required; arbitrary third-party
  workbooks are not guaranteed compatible.
- Free Flight search accepts typing reliably. Controller setup and binding
  capture receive focus fixes, and compact settings labels no longer overlap.
- Flight Review removes opaque trail markers and fades the glow near the camera.
  Controls use a graphite panel with clearer button hierarchy and larger text;
  they wrap in smaller windows. FPV hides gap and event markers.
- Data & Catalog restores keyboard focus after form refreshes. Escape and Back
  unwind the current form or confirmation before closing the panel, preserving
  unsaved-draft protection.
- Menus include original music and navigation, confirmation and back sounds.
  Generic sound effects now respect both Master and Effects volume controls.
- Local-scene fallback status no longer claims successful terrain streaming.

- Fixed-wing and rover artwork, replay camera controls, preview corrections and
  persistent terrain request caching are included.
- Flight Review source-status labels use supported punctuation instead of
  characters that could display as missing-glyph boxes.

Mission Planner QGC WPL 110 inspection is read-only; playable mission import
and QGroundControl `.plan` are unsupported. Full input rebinding, physical
two-PC LAN acceptance and broader hardware/visual validation remain incomplete.
Customer layers, recordings and private parts libraries are not bundled.
Windows binaries are unsigned; security policies may block launch.

The release page records exact archive hashes and completed package/upgrade
checks. Historical candidate evidence is not substituted for this archive.


## KESTREL v0.44.2 - compact Controls panel

Package version: `v0.44.2-alpha`; release tag: `v0.44.2-alpha.1`.
Source: `b969778adf2d03f35d0bc6f9ccfc5d39508e9d88`.

The Controls / Bindings panel fits smaller windows with all six existing action
rows, status guidance, Save/Cancel controls and the unsaved-changes dialog on
screen. Standard-size windows retain their layout. This correction does not
add actions or deliver full control rebinding.

Validation passed: 35 focused source checks, 218 launcher tests and three
packaged native controls tests. Rendered checks covered the normal panel at
888x500 and 1280x720 and the unsaved-changes dialog at 888x500.
All 4,453 archive entries, CRCs and extracted file hashes verified.
This is an unsigned Windows alpha. The v0.44.1-to-v0.44.2 installed upgrade passed payload checks, preserved synthetic local files and passed three native controls tests. The default updater now serves v0.44.2. Windows Application Control blocked the new unsigned launcher on this workstation at cold restart; cold-launch acceptance is not claimed.
Existing Flight Review and file-inspection limits remain unchanged.

Archive: 679,200,052 bytes; SHA-256
`bb296c0e8ea5c89753bdf67f8a7b4ce91261ae23154a42c65f7d019681bd57e5`.
Cooked content matches the previously approved v0.44.1 release. Customer
recordings and libraries are excluded. No new models, customer 3D scenery or
playable Mission Planner import are added. The existing Missions subtitle
overlap at 888x500 remains.

## KESTREL v0.44.1 - usability and status corrections

Release tag: `v0.44.1-alpha.1`;
package version: `v0.44.1-alpha`. Source: `1b6c007a878085f4ff59a74e7d47e8124fb6d688`.

- Data & Catalogs: Enter submits a file for inspection; Inspect is disabled when the path is empty.
- Connection checks distinguish endpoint access from loaded imagery without claiming a rendered result.
- Flight Review labels uncertain placement honestly; this update does not change geographic placement behavior.
- Hangar and Work Bench footer metrics and title hints adapt to available screen space.

Adds a concise reviewer first-launch checklist. The final package passed 25 native
tests with no warnings or failures and 218 launcher tests. Rendered checks covered
888x500 and 1280x720 layouts and three Data & Catalogs inspection states.
An existing Missions subtitle overlap remains at 888x500.
Archive: 679,198,814 bytes; SHA-256 `494b18c19f2a50c2f59bcf5543afdc6b66d996755de4d513fd70b69dd9f364f9`.
All 4,453 files and CRCs passed archive verification; cooked asset containers are
unchanged from v0.44. The actual v0.44-to-v0.44.1 upgrade passed, including preserved synthetic local files, menu navigation and a rendered first-run restart. At publication, the default updater was promoted to v0.44.1.
Representative vehicle art and existing hardware/network limitations remain.
Customer libraries and recordings are excluded from public release content.
This update does not add geographic placement behavior, new terrain features,
new models or mission execution through file inspection.

## KESTREL v0.44 - Flight Review

Release tag: `v0.44.0-alpha.1`; package version: `v0.44.0-alpha`.
Source: `5444e5238f5e884a37adc4e64df150206cd6f643`.
Released October 8, 2026. At publication, direct downloads and the automatic updater offered v0.44.
The isolated v0.42.11-to-v0.44 upgrade passed.

- Opens ArduPilot DataFlash BIN logs directly in Flight Review, alongside KESTREL
  flight JSON. Recorded, planned and simulated provenance stays distinct.
- Removes duplicate live simulator aircraft from review; adds Minimize/Expand,
  Tab panel toggle, T trail toggle and normal Escape pause-menu behavior.
- Playback buttons reflect availability/state; camera controls and telemetry
  remain available during review.
- Adds read-only inspection of BIN and Mission Planner QGC WPL 110 waypoint
  exports. Waypoint inspection does not create or execute playable missions.
- Provides an inventory-mismatch action in Work Bench and rejects missing local
  import files. Retains prior OSD and controller improvements.

Existing representative vehicle shapes remain. Detailed replacement vehicle
models, exact-airframe identity, raw geospatial conversion and customer 3D scenery
are not included. Customer libraries and flight logs are not release content.
The package is not publisher-signed. All 4,453 archive files and CRCs were verified;
eight packaged replay/import tests passed with no failures. Source and cooked-content
inventories and known private-file hashes were checked. The old launcher installed
the public HTTPS archive with checksum verification; synthetic Saved/profile
fixtures survived. Cold rendered menu testing passed and a repeat update check
reported up to date. Transient manifest timeouts recovered on retry.
ZIP size: 679,194,737 bytes. SHA-256:
`495d62f4f2039a40a7341f483965e7048375f9bce419b8070885c3d41611b69e`.

## KESTREL v0.43.2 - opt-in controller evaluation

September 23, 2026. [Playable ZIP and exact verification notes](https://github.com/nbschultz97/kestrel/releases/tag/v0.43.2-alpha-eval.1);
[Rotopter mirror](https://git.rotopter.com/nschultz/Kestral/releases/tag/v0.43.2-alpha-eval.1).
DirectInput reads eight standard Pocket axes and 24 reported buttons on the
tested radio; Controller setup adds explicit Remap actions, live button state,
and a 720p layout correction. Physical SA/SD binding worked, but SE did not.
The archive was full-cooked and fresh-extraction two-process Offline/Streamed
smokes passed. This evaluation does not move GitHub Latest or the stable updater.

ZIP: 677,225,817 bytes; SHA-256
ac52e4cde9103b9e42fe8684d9d6e6356e65cb1902ce511f264fb366152246f3.
Source commit 70599a3c7929154c517780de24a2cb632a47577f.

## KESTREL v0.42.13 — flight controls

September 17, 2026. [Release and immutable download](https://github.com/nbschultz97/kestrel/releases/tag/v0.42.13-alpha.1).
Source `45974ce74aa9642bcee15c8439808e0cf2102305`. Archive size 676,720,589
bytes; SHA-256 `e3dbdaea14151bf7a6a721b72ea36c494fa698c900e8078c28ecabafc94a5bbe`.

- **Settings > Flight controls** replaces the Map-only editor with Map, Camera
  tilt up and Camera tilt down rows. Each supports keyboard or digital gamepad
  binding, Clear, Restore defaults, Save changes and Cancel.
- Tilt defaults remain Up/Down, with one two-degree step per fresh press and
  the existing 0–55-degree limit. Menu arrows remain available after reassignment.
- Shared conflict checks protect existing flight axes and reserved controls.
  Held/repeated controls, focus/context changes and reconnects do not synthesize
  additional actions.
- A versioned action section shares the existing controller-profile save
  transaction. Legacy Map fields migrate; unknown metadata/actions survive.
  Malformed profiles and failed writes do not publish a partial replacement.
- Calibration reset preserves these action assignments. Restoring action
  defaults leaves calibration intact.
- Existing Map USB-radio digital-button capture remains. Radio tilt and
  axis-switch actions are explicitly unsupported.

Verified development scope: Editor and Game builds; 136 focused source guards;
13 native controller tests covering production persistence, migration, failed
writes, capture arbitration and input edges; 16 native display regressions.
The fresh full cook/package passed 218 launcher tests. Independent complete
stage review and all 4,451 ZIP CRC/extracted-hash checks passed. Actual packaged
default-state offscreen captures at 720p and 1080p exited normally and were
inspected; personal settings/controller files remained unchanged. No new cooked
content was introduced: all five containers match the accepted v0.42.12 bytes.
Physical input and complete interaction checks remain separate; earlier release
images retain their original version labels.

Full action rebinding, the Work Bench OSD editor, rotating lobby aircraft
previews, physical radio/gamepad qualification and physical two-PC LAN remain
unfinished. The automatic updater remains on v0.42.11 pending installed-update
verification. Release publication alone will not complete those checks.

## KESTREL v0.42.12 — display reliability

September 16, 2026. [Release and immutable download](https://github.com/nbschultz97/kestrel/releases/tag/v0.42.12-alpha-unsigned.1).
Package version `v0.42.12-alpha`; source
`32401cce14394e7eef324be62738c8b813a65a3f`.
The unsigned ZIP is 676,690,392 bytes; SHA-256:
`5ca8c620c90909f71318a8e5eae5defacf235277ddc15bdaad35abda5895098e`.

This was the prior GitHub Latest download, now superseded by v0.42.13. The automatic updater
remains on v0.42.11 while the older-install update check is pending.
The immutable v0.42.12 release tag and
assets are unchanged; Latest promotion does not establish end-to-end upgrade success.

- Separate Display and Window mode controls: choose Auto or an attached monitor
  independently of Windowed, Fullscreen or Borderless.
- Auto selects the highest-resolution connected panel. Saved manual choices
  use the monitor identity rather than its temporary enumeration position,
  with a fallback when that monitor is unavailable.
- Windowed sizes fit the selected screen's usable desktop area and retain a
  native title bar. Mixed-DPI transitions account for restored window placement.
- Clickable Keep changes and Revert controls, with a 15-second real-time
  rollback. Unconfirmed choices do not replace saved startup settings.
- Alt+Enter and F11 use the same monitor selection, fitted sizing and flight
  rendering safeguards. Settings-page shortcuts request confirmation; outside
  Settings they retain immediate toggle behavior.
- High-DPI game rendering and shorter display labels improve readability.

Display-focused rendered development and packaged-candidate tests passed
transitions, confirmation and saved-monitor restart on two mixed-DPI monitors.
The restart check preserves only an isolated product profile between processes;
fresh engine settings prevent an unrelated engine preference from masking it.
Timeout tests disable controller ticking, not the entire game's pause state.

The final full build/cook/package completed successfully and all 218 launcher
tests passed. Rendered window-transition, confirmation and saved-monitor restart checks passed
against the final package. The Settings confirmation image is an actual final
packaged-build capture. Independent review, CRC checks and fresh extraction verified
all 4,451 archive files. A fresh public HTTPS download matched the released ZIP's
exact size and SHA-256. That download verification is separate from an installed
upgrade; the end-to-end test has not passed and the automatic updater is held at
v0.42.11 pending installed-update verification.

Human title-bar dragging, actual keyboard shortcuts during live or fully paused
flight, monitor unplug/reconnect, physical radio input and physical two-PC LAN
remain separate acceptance items. Full action rebinding, Work Bench OSD editing,
rotating lobby aircraft cards, broader art fixes and actual-install updater
recovery remain unfinished. Existing v0.42.11 gallery captures stay labeled with
their original build; no new screenshot coverage is implied.

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
