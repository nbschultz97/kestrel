# KESTREL features and limits

Version: v0.44.4, package `v0.44.4-alpha`, tag `v0.44.4-alpha.1`.
Source: `a62d0a79ad7de38be18335a5ca61af47ff775ac6`.
[README](README.md) links downloads; [CHANGELOG](CHANGELOG.md) records release
history and evidence. Included features do not imply whole-roadmap completion.

## Included in v0.45.0

### Flight Lab

One entry for **Replay a flight** (ArduPilot DataFlash BIN or flight JSON) and
**Run a simulation**. Simulation runs a local Lua script in native ArduPlane
SITL over KESTREL's streamed terrain: terrain prepares automatically, the live
view opens when ready, and firmware messages, script errors, airspeed,
groundspeed, altitude, climb and heading are shown. Selecting a script never
runs it; each run uses fresh working files and stops cleanly on Stop, Back or
exit. You supply the SITL executable. ArduPlane dynamics are ArduPilot's own;
KESTREL does not claim universal SITL or parameter/mission import compatibility.

### Saved areas and local terrain

**Data & Catalogs > Saved areas** builds an offline area around a latitude and
longitude (2, 5 or 10 km wide) and keeps it on this PC:

- Elevation: AWS Terrain Tiles (USGS 3DEP about 10 m in the US, about 30 m
  elsewhere), converted to WGS84 with the bundled EGM96 geoid.
- Imagery: USGS aerial imagery in the US, with per-tile Sentinel-2 cloudless
  2016 fallback where USGS is blank; Sentinel-2 elsewhere. Optional 0.6 m USDA
  NAIP detail over the inner 1.2 km in the US.
- Buildings: OpenStreetMap footprints where mapped, extruded for visuals only.

Saved areas stream through the same terrain system as online tiles, so ground
collision, calibration and insertion behave the same, and they work offline.
Where online terrain has no coverage, a saved area is used first; if none
exists, KESTREL builds a small one automatically before falling back to the
flat floor. Licensed streaming imagery is never cached. Attribution for each
source is shown in game. Build time depends on size and connection (seconds for
a small area, several minutes with US detail).

### Mission Builder

Editing an existing mission keeps its loadout, brief, annotations, jammers,
per-objective settings and unknown fields, and saves back to the file you
opened. Adds Ctrl+Z undo, Ctrl+D duplicate, stacked selection, objective
reordering and a briefing field. Placed hostile jammers become real jammer
emitters, and strikes destroy a jammer whose antenna is inside the blast.
Objective markers, OPFOR target vehicles (with destroyed versions), civilian
cars and SOF/support vehicles use new models.

## Included in v0.44.4

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

## File, hardware and service boundaries

- ArduPilot SITL and Lua script execution are not available in this build; Flight Review plays recorded state.

- Flight Review reads supported ArduPilot DataFlash BIN and KESTREL flight JSON;
  recorded, planned and simulated data remain labeled separately. Representative
  vehicle classification does not identify an exact airframe. Recorded FPV video,
  measured rotor RPM and multi-vehicle timelines remain unavailable.
- Mission Planner QGC WPL 110 inspection preserves commands and reference frames
  without execution or playable import. QGroundControl `.plan` is unsupported.
- Parts-library XLSX transfers require supported values-only tables and headers;
  arbitrary third-party workbooks are not guaranteed compatible. Build transfers
  require the matching library identity. Customer libraries stay local.
- Nine keyboard/digital-gamepad actions are configurable; axes, contextual replay
  controls and full USB-radio action assignment are not all rebindable. Calibration
  and physical-device compatibility remain separate checks.
- Display and window mode controls, saved OSD layouts and their existing draft/
  save behavior remain. Some dense settings text still shortens at small widths.
- Experimental LAN is included, but physical two-PC acceptance remains incomplete.
- Streamed terrain needs provider access, coverage and network availability.
  Cached requests do not provide an offline globe. Raw GIS/point-cloud references
  are not automatically converted into rendered 3D layers; customer layers are
  excluded from public packages. Status text does not prove imagery has loaded.
- Weather is configured rather than live. Address/POI search and TAK/live-C2
  integration are not included. Vehicle art and physics are not calibrated
  real-hardware certification.
- Binaries are unsigned. See the release page for exact-package checks and
  observed Windows launch limitations. Download, runtime and installed-upgrade
  acceptance are separate.

<details>
<summary>Historical feature descriptions and evidence through v0.44.2</summary>

The following is retained history, not the current feature checklist. Where an
older release calls a feature unfinished, the v0.44.4 descriptions above govern.

# KESTREL features and limits

Version: v0.44.2, package `v0.44.2-alpha`, tag `v0.44.2-alpha.1`,
source `b969778adf2d03f35d0bc6f9ccfc5d39508e9d88`.
This update fits the existing six-action Controls panel into small windows;
it does not add actions or complete input rebinding. The final package passed
35 focused source checks, 218 launcher tests and three native controls tests.
Rendered checks covered 888x500 and 1280x720, including the small-window
unsaved-changes dialog. The existing Missions subtitle overlap at 888x500 remains.
The prior v0.44-to-v0.44.1 installed upgrade passed. The v0.44.1-to-v0.44.2 installed upgrade passed payload checks, preserved synthetic local files and passed three native controls tests. The default updater now serves v0.44.2. Windows Application Control blocked the new unsigned launcher on this workstation at cold restart; cold-launch acceptance is not claimed.

[README](README.md) identifies downloads; [CHANGELOG](CHANGELOG.md) ties changes
to versions. Historical screenshots and version-specific tests retain their original scope.

## Flight Review and native flight files - v0.44

Flight Review opens ArduPilot DataFlash BIN and KESTREL flight JSON in-game.
Recorded, planned and simulated timelines retain distinct provenance labels.
It hides live simulator aircraft during review, provides camera controls and
telemetry, and allows the controls panel and trail to be toggled independently.
Tab minimizes/expands controls, T toggles the trail, and Escape opens the normal
pause menu. Playback controls reflect availability and state.

Vehicle firmware banners select existing representative fixed-wing, rover or
submersible visuals. They do not identify an exact airframe; detailed replacement
vehicle art is not included. Recorded FPV video, measured rotor RPM and
multi-vehicle timelines remain unavailable. Replay elevation is launch-relative,
not a surveyed reconstruction.

Data & Catalogs inspects native BIN logs and Mission Planner QGC WPL 110 exports
(.waypoints, .wpl and .txt). This read-only inspection preserves mission commands
and reference frames; it does not execute a mission or create a playable flight.
Customer libraries stay local. Raw LiDAR and GeoPackage references are not
converted or rendered as customer 3D scenery.

The v0.44 Work Bench adds an inventory-mismatch action for saved aircraft with
unavailable required parts. Earlier display, controller, OSD and catalog features
remain, subject to the limits below.

## Earlier release comparison

| Area | Earlier v0.42.4 | Earlier v0.42.9 evaluation | Public v0.42.11 release |
|---|---|---|---|
| Flight, parts-based Work Bench, named aircraft, mission library/editor | Existing alpha features | Retained, with later UI/compatibility changes | Included; bounded packaged author-to-flight tour passes |
| Controller inversion in boot-menu Settings | Shipped fix | Retained | Additional save/Confirm routing and input recovery fixes; physical acceptance pending |
| Targeted ten-inch compatibility and thumbnail repairs | Do not assume later fixes | Included in this exact evaluation | Retained alongside further assembly work |
| City-search preview, offline overview and Free Flight C2 map | Not the newer workflow | Not included | Included; live mission C2 overlay regression remains open |
| Data & Catalogs panel and visible inventory switching | Not the newer workflow | Not included | Included; full interactive coverage remains open |
| Full action rebinding and Work Bench OSD editor | Not complete | Not complete | Still unfinished |
| Proven physical two-PC multiplayer or full hardware calibration | Not established | Not established | Still requires acceptance |

These versions are unsigned. Features included in the 0.42.11 package
are not retroactively added to earlier downloads by updating this repository.

## Display settings — v0.42.12 update

Display and Window mode are separate controls. Auto chooses the highest-resolution
attached panel; an explicit monitor choice is saved by identity and falls back
when that monitor is absent. Choose Windowed, Fullscreen or Borderless independently.

Windowed sizing fits the selected screen's usable desktop area and retains a
native title bar. Mixed-DPI transitions account for the engine's remembered
restore position. Settings changes offer Keep changes and Revert, with a
15-second real-time rollback that does not commit an unconfirmed startup choice.
Alt+Enter/F11 use the same monitor/sizing logic; Settings-page shortcuts request
confirmation while shortcuts outside Settings remain immediate.

Rendered development and packaged-candidate checks passed on two mixed-DPI
monitors, including saved-monitor startup in a second process with fresh engine
settings. Final-package window-transition, confirmation and restart checks passed too.
Human dragging, live/fully paused-flight key input, monitor hotplug and
wider physical hardware remain separate acceptance work. Existing v0.42.11
marketing captures are retained with their original provenance.

## Flight and vehicle modeling

KESTREL models an aircraft assembled from catalog parts rather than treating all
sizes as one preset with a different mesh. Relevant specifications include mass,
motor characteristics, propeller dimensions, pack voltage/capacity and aerodynamic
parameters. The Work Bench presents predicted performance such as thrust-to-weight,
hover demand and endurance estimates.

The flight simulation includes motor response, battery discharge and voltage sag,
wind-relative aerodynamic behavior, attitude control, collision and damage. FPV
and line-of-sight views support different ways to practise. These are model
outputs: a manufacturer specification, catalog match or successful simulation
is not proof of real-aircraft flight performance, structural safety or a calibrated
digital twin. Predictions depend on the completeness and quality of the supplied data.

## Work Bench and saved aircraft

Existing public builds provide catalog part selection, an assembled preview,
compatibility feedback and named aircraft management. Builds can be saved,
renamed, duplicated and reopened. Incomplete or incompatible configurations need
correction before they can be treated as usable aircraft.

The v0.42.9 evaluation specifically includes later frame/motor/prop compatibility
feedback, click-time validation and targeted complete ten-inch combinations. Its
verification does not cover every possible catalog combination or all artwork.

The v0.42.11 release includes:

- Separate **Current inventory** and saved-aircraft **Source inventory** labels.
- A visible **Switch Inventory** route from the Work Bench/shelf to Data > Parts.
- Protection against silently losing unsaved bench work during an inventory change.
- Source-inventory and stable part-ID checks when reopening saved aircraft;
  unresolved inventories or missing parts are reported instead of silently
  substituting a different build.
- Click-only saved-aircraft selection and predictions derived from the selected
  aircraft, rather than an unrelated editing draft.

The packaged UI tour passes aircraft save and mission preflight/launch for its
bounded fixture. Inventory-switch/cancel/reopen permutations and user-driven
interaction still need broader coverage. Older files with incomplete provenance may
require an explicit repair or recreation; compatibility is not assumed.

## Data & Catalogs — included in v0.42.11

The **Data > Parts** page exposes the active catalog and provides
Create catalog, Import catalog, Use catalog, Copy catalog, Export, Rename and
Edit controls. The bundled base is read-only: copy it into a custom catalog
before editing. The current editor is a validated JSON draft with Save/Cancel,
not a spreadsheet-style per-part editor.

Imports and copies protect existing catalog identities and destinations. Editing
preserves stable existing part IDs and checks stale drafts. Catalog selection
and saved-aircraft identity remain separate; choosing a different inventory
must not silently change the parts of a saved aircraft.

A catalog may contain incomplete or incompatible entries. “Imported” does not
mean every part is selectable, every assembly is mechanically valid, or the
simulation has measurements for that product. Custom inventories are local
runtime data; public release packages must exclude them.

## Assembly visuals and mounting — v0.42.11 additions

The simulator uses generated part families and selected product-specific matches
for aircraft previews and flight meshes. A representative class mesh can differ
from the actual product's shape, connector positions or mounting hardware.

This release includes authored support planes for frame/board placement, visible
stack spacers, targeted receiver cradles and video-board supports on three
generated tube-frame profiles, and receiver-supplied antenna ownership/mass
labels. The Work Bench distinguishes representative support, unverified geometry
and placement conflicts from electrical/catalog compatibility.

This is not full mechanical-fit certification. All-frame/all-part mounting
coverage, exact product geometry, hardware clearance, wiring/restraint detail,
battery/strap presentation and broader art polish remain open. A “representative”
mount is not a recommendation for building real hardware.

## Input, calibration and tuning

Public builds include keyboard/gamepad input and controller calibration, with
axis direction/inversion settings and an arm-switch workflow. v0.42.4 repaired
boot-menu inversion loading, save-failure behavior and persistence.

Betaflight-style control and supported diff/settings import help reproduce
selected rates and tune values in the simulator. This is not a complete
Betaflight firmware emulator or an import of every CLI option. Supported rate
families and parameters differ in fidelity; some rate curves are approximations.
Importing a tune does not validate the real aircraft or write its hardware.

The current **Settings > Controls / Bindings** panel exposes six existing
actions. Earlier v0.42.12/v0.42.13 releases introduced the Map and tilt subset:

| Action | Keyboard default | Editable controller input |
|---|---|---|
| Map | F6 | Digital gamepad button or existing USB-radio digital button |
| Camera tilt up | Up arrow | Digital gamepad button |
| Camera tilt down | Down arrow | Digital gamepad button |
| Restart | R | Digital gamepad button |
| View / LOS | V | Digital gamepad button |
| Arm / disarm | Enter | Digital gamepad button |

All six actions support keyboard reassignment, Clear, Restore defaults,
Save changes and Cancel. Conflicting controls are rejected before saving.
Camera tilt takes one two-degree step per fresh press within 0–55 degrees;
held/repeated controls do not add steps. Menu Up/Down remain navigation controls
when the flight assignment changes.

Bindings share the existing controller profile and save transaction. Legacy
Map settings migrate, unrelated profile metadata survives, and failed saves
retain both the active profile and the editable draft. Resetting controller
axes/switches preserves these action assignments; action defaults preserve
calibration.

This is a six-action editor, not full control rebinding. Flight-mode and low-light
shortcuts, menu navigation and flight-axis keys are not editable here.
USB-radio tilt and action bindings on radio axes are unsupported. Physical
radios/gamepads, input backends, unplug/reconnect, switch capture and end-to-end
latency require separate device testing. Development panel captures are not
packaged interaction or physical-controller acceptance.

## FPV cameras and OSD

The existing renderer includes FPV camera framing, selected-camera field of view,
propeller presentation, link effects and Betaflight-style telemetry using MAX7456
font assets. Battery, timer, navigation and flight-status readouts are simulation
telemetry, not readings from external hardware.

The **Work Bench OSD editor** edits supported simulator readouts. Its bounded
Betaflight OSD text import/export preserves unsupported settings. This is not
complete Betaflight Configurator parity or exact-hardware OSD validation.

The full camera/prop/RPM/exposure matrix, exact per-aircraft optical matching and
physical flight-feel comparison are also not accepted as complete.

## Locations, maps and terrain

Public releases support location-based real-world terrain streaming and coordinate
entry. Terrain detail and coverage depend on the configured upstream services,
network, cache, GPU memory and loading progress. The offline Test Range is a
separate environment; it does not provide offline worldwide terrain.

Navigation additions included in v0.42.11:

- Offline city-name search plus coordinate entry, with an explicit preview step.
- A movable launch pin and separate Fly here / Build here actions.
- Major-city labels and a coarse land/coastline overview at wider zoom levels.
- A Free Flight C2 map with orientation cues, place labels and a compass.

The coarse overview is not a street map or offline imagery cache. Online
street-address/point-of-interest search is not implemented. A city search hit
is not a guarantee that detailed terrain can load there.

Terrain-lifecycle fixes classify cancelled, stale and failed requests
separately from confirmed missing surfaces, retain the final permitted sample,
and keep strict loading/calibration/ground-readiness checks. They do not justify
claiming that cold starts, world travel or all service failures are resolved.
The new packaged author-to-flight tour and one-PC streamed LAN flow pass.
Broader cold-start, service-failure and physical two-PC acceptance remain open.

Known live mission C2 regression: the loading brief shows launch/LCC and objective
symbols/labels plus the connecting route, but those overlays are missing in a
sampled live C2 view of the same area; the mission title and compass remain.
The cause is not established and no fix is included. A successful tour reaching
the C2 screen is not proof that its mission overlays render correctly.

## Local layers and connection status — included in v0.42.11

**Data > Layers** manages named local collections and item enable/disable state.
Supported placed raster overlays require an image and placement sidecar. A flat
image overlay is not a terrain mesh and does not create elevation or collision.

Raw GIS files, point clouds and archives are not automatically converted into
flyable terrain. The panel reports inputs that need conversion rather than
pretending they loaded. General dataset conversion/tiling and geospatial validation
remain separate work.

**Data > Cesium** shows configuration source and status without displaying the raw
token. Check connection makes an explicit service-access check. “Configured” is
not “Connected,” and a passed access check does not prove all requested tiles,
imagery or collision are ready. The release includes the intended
public configuration; do not post personal tokens in issues or screenshots.

## Missions and practice

The existing mission library separates bundled content from user-authored or
imported missions. Free Flight and the Test Range support lower-friction practice;
the mission editor supplies location-based authoring and save/reopen workflows.
Authored objectives, navigation cues and scoring provide scenario structure.
Work Bench offers both Test Range and Proving Ground launch routes. Mission
Builder also supports an embedded tunnel venue with a georeferenced exterior
and a procedural collidable interior. This is not a general interior-generation
system: portal seating, terrain intersections, material quality and varied
terrain/collision cases still need broader acceptance.

Private user missions and datasets must not be copied into public packages. A
scenario shown in a trailer is not a statement that its content is bundled with
every version.
The new packaged UI tour completes its authored mission/aircraft save, selection,
preflight, launch and live C2 sequence. This is a bounded automated fixture,
not acceptance of every authored mission, natural shutdown or manual interaction.
The live C2 overlay defect described above remains open.

## Records and debrief

The Records page lists local mission results, grades, duration and available
aircraft/run context, with file-integrity status. A checksum is not a trusted
signature, independent pilot identity or proof of calibrated flight performance.
Records can include personal run information and need review before sharing.

Flight Review is a separate surface for recorded telemetry and labeled planned
or simulated timelines. The Records browser is not deterministic replay. Complete
build/tune/content identity, annotations and comparative after-action review
remain unfinished.

## Environment and audio

Solar position/time-of-day, configurable atmosphere/weather, wind, aircraft sounds
and environmental audio contribute to the flight experience. **Solar/seasonal**
settings describe the model; they are not observations of current local weather.
Live observed weather with source/time/staleness information and civil timezone/
DST display remain unfinished; longitude-derived solar time is not a civil clock.

Included audio work corrects per-aircraft teardown ordering while preserving
other aircraft's sound. Wider flight, travel, restart, device-switching and
multiplayer audio behavior still needs acceptance.

## Multiplayer

LAN functionality is experimental. The exact new package passes a two-process,
one-PC streamed-range test: discovery, aircraft/revision approval, Ready, shared
travel, owned-pawn/server-applied input and reciprocal aircraft movement. Separate
terrain cache databases were verified, with no fatal/ensure, SQLite or readiness-
backstop findings in that run. The harness intentionally cleaned up its processes.

This does not establish two physical computers/controllers, every network,
leave/rejoin, natural shutdown or host loss. Network missions/shared C2,
collaborative mission building, host migration and rotating multiplayer aircraft
cards remain unfinished. Do not interpret the one-PC result as a complete
multiplayer deployment or hardware-acceptance claim.

## Settings, packaging and privacy

Settings expose display, audio, environment and input controls. The v0.42.12
display work above extends the earlier mode synchronization and layout handling.
Its bounded rendered tests do not replace physical display/focus acceptance or
complete the separate action-binding and controller-backend work.

The selected Settings value has a readable full-value row, verified in a
v0.42.11 720p capture; compact cells still ellipsize intentionally. Remaining UI/art
issues include builder help/property text contrast and clipping, keyboard hints
overlapping headers, crowded prediction rows and loading attribution, dark
battery/part labels, glossy carbon and unfinished strap/material presentation.
Required map attribution must remain visible when its layout is corrected.

The launcher checks versioned update metadata and validates archives before
installation. Its unit checks cover update-related logic, including rejection
and rollback cases; a new release still needs actual download/update, offline,
corrupt-download, recovery and profile-preservation acceptance.

The release has no live reporting endpoint. Local reports may contain
personal information and should be reviewed before sharing. Public distributions
must exclude private profiles, inventories and datasets and carry appropriate
third-party notices. Cook policy excludes machine-local editor service settings.
Both v0.42.11 and v0.42.12 passed independent stage/container review and fresh
archive verification. Those checks retain their opaque-content/property and
asset-rights limitations; they do not certify every asset or assert that
historical source/artifacts have been retroactively sanitized.

## Historical v0.42.11 evidence boundary

The public v0.42.11 package uses source
`008b4834b9e62d166fafec5ba31aebe5746eb261`. Its recorded checks include:

- 70 native tests: 67 clean and three with expected warnings; no failures/skips.
- 218 launcher/update checks and a completed full cook/package.
- All 4,451 reviewed archive files checked by CRC/hash, exact topology and fresh
  extraction; protected contents remained unchanged after runtime tests.
- 16 focused UI screenshots, all visually reviewed. Stock preflight shows the
  selected aircraft/Continue; battery windows cover all 22 products plus NONE.
- A naturally completed 110-frame, 14-stage packaged UI tour. Only selected tour
  keyframes were visually reviewed; the live C2 and other visual defects remain.
- A passing one-PC, two-process streamed LAN flow, not a physical two-PC test.

These are bounded results, not complete controller/display, multiplayer,
camera/flight calibration, whole-catalog art or older-install updater acceptance.
The owner approved publication with known limitations; publication confirmation
and remote artifact parity remain separate. Full OSD editing, full action
rebinding and rotating lobby cards are not included as completed features.
Consult [CHANGELOG](CHANGELOG.md) and [ROADMAP](ROADMAP.md) for the matching
release record and unfinished work.

</details>
