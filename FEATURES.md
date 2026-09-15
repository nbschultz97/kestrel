# KESTREL features and limits

Status: September 14, 2026. This is a capability inventory, not a claim that every
workflow has passed on every computer. [README](README.md) identifies the current
downloads; [CHANGELOG](CHANGELOG.md) ties changes to versions; [ROADMAP](ROADMAP.md)
tracks unfinished work.

## Which build has what?

| Area | Default public v0.42.4 | Optional public v0.42.9 evaluation | Upcoming v0.42.11 candidate |
|---|---|---|---|
| Flight, parts-based Work Bench, named aircraft, mission library/editor | Existing alpha features | Retained, with later UI/compatibility changes | Retained; fresh full-flow acceptance pending |
| Controller inversion in boot-menu Settings | Shipped fix | Retained | Additional source/input recovery work; physical acceptance pending |
| Targeted ten-inch compatibility and thumbnail repairs | Do not assume later fixes | Included in this exact evaluation | Retained alongside further assembly work |
| City-search preview, offline overview and Free Flight C2 map | Not the newer workflow | Not included | Candidate implementation |
| Data & Catalogs panel and visible inventory switching | Not the newer workflow | Not included | Candidate implementation |
| Full action rebinding and Work Bench OSD editor | Not complete | Not complete | Still unfinished |
| Proven physical two-PC multiplayer or full hardware calibration | Not established | Not established | Still requires acceptance |

The default public release and optional evaluation are unsigned. Candidate
features below are not added to those downloads by updating this repository.

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

The v0.42.11 candidate adds:

- Separate **Current inventory** and saved-aircraft **Source inventory** labels.
- A visible **Switch Inventory** route from the Work Bench/shelf to Data > Parts.
- Protection against silently losing unsaved bench work during an inventory change.
- Source-inventory and stable part-ID checks when reopening saved aircraft;
  unresolved inventories or missing parts are reported instead of silently
  substituting a different build.
- Click-only saved-aircraft selection and predictions derived from the selected
  aircraft, rather than an unrelated editing draft.

These safeguards still need the fresh package's interactive save, reopen,
switch, cancel and fly checks. Older saved files with incomplete provenance may
require an explicit repair or recreation; compatibility is not assumed.

## Data & Catalogs — candidate only

The candidate's **Data > Parts** page exposes the active catalog and provides
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

## Assembly visuals and mounting — candidate additions

The simulator uses generated part families and selected product-specific matches
for aircraft previews and flight meshes. A representative class mesh can differ
from the actual product's shape, connector positions or mounting hardware.

Candidate work adds authored support planes for frame/board placement, visible
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

The candidate adds map-specific binding capture/recovery and input-source
safeguards. **Settings > Map Controls is not full action rebinding**, and binding
a digital map action is not radio-axis calibration. Physical USB radios,
input backends, unplug/reconnect, switch capture and end-to-end latency require
separate device testing.

## FPV cameras and OSD

The existing renderer includes FPV camera framing, selected-camera field of view,
propeller presentation, link effects and Betaflight-style telemetry using MAX7456
font assets. Battery, timer, navigation and flight-status readouts are simulation
telemetry, not readings from external hardware.

The **Work Bench OSD editor is not implemented**. The presence of an OSD renderer
or imported tune is not evidence of editable analog/digital layouts, drag-to-cell
placement, profiles, reset, or layout import/export. Those remain roadmap work.

The full camera/prop/RPM/exposure matrix, exact per-aircraft optical matching and
physical flight-feel comparison are also not accepted as complete.

## Locations, maps and terrain

Public releases support location-based real-world terrain streaming and coordinate
entry. Terrain detail and coverage depend on the configured upstream services,
network, cache, GPU memory and loading progress. The offline Test Range is a
separate environment; it does not provide offline worldwide terrain.

Candidate navigation additions include:

- Offline city-name search plus coordinate entry, with an explicit preview step.
- A movable launch pin and separate Fly here / Build here actions.
- Major-city labels and a coarse land/coastline overview at wider zoom levels.
- A Free Flight C2 map with orientation cues, place labels and a compass.

The coarse overview is not a street map or offline imagery cache. Online
street-address/point-of-interest search is not implemented. A city search hit
is not a guarantee that detailed terrain can load there.

Candidate terrain-lifecycle fixes classify cancelled, stale and failed requests
separately from confirmed missing surfaces, retain the final permitted sample,
and keep strict loading/calibration/ground-readiness checks. They do not justify
claiming that cold starts, world travel or all service failures are resolved.
Fresh full-flow and cold-cache multiplayer acceptance remain required.

## Local layers and connection status — candidate only

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
imagery or collision are ready. The public evaluation includes the intended
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
The candidate still needs a complete packaged author/save/select/preflight/fly
walkthrough; isolated screenshots do not establish that flow.

## Records and debrief

The Records page lists local mission results, grades, duration and available
aircraft/run context, with file-integrity status. A checksum is not a trusted
signature, independent pilot identity or proof of calibrated flight performance.
Records can include personal run information and need review before sharing.

This results browser is not a complete replay system. Deterministic recording,
timeline scrubbing, camera selection, annotations and comparative after-action
review remain unfinished, including complete build/tune/content identity across
recording and playback.

## Environment and audio

Solar position/time-of-day, configurable atmosphere/weather, wind, aircraft sounds
and environmental audio contribute to the flight experience. **Solar/seasonal**
settings describe the model; they are not observations of current local weather.

Candidate audio work corrects per-aircraft teardown ordering while preserving
other aircraft's sound. Wider flight, travel, restart, device-switching and
multiplayer audio behavior still needs acceptance.

## Multiplayer

LAN functionality is experimental. Lobby, discovery/direct-address entry,
aircraft selection/approval, readiness and shared-range code exist, but physical
two-computer discovery, synchronized travel, input, movement, leave/rejoin and
host-loss behavior are not established as complete. Rotating multiplayer
aircraft cards remain unfinished.

Native policy tests and two processes on one PC do not prove two physical
machines, two input devices or independent terrain caches. Do not interpret
these docs as a validated multiplayer deployment claim.

## Settings, packaging and privacy

Settings expose display, audio, environment and input controls. The candidate
adds engine/display-state synchronization and a 1280x720 interactive layout
minimum. This does not close the reported windowed/fullscreen/borderless behavior;
physical display-mode and focus acceptance is still required.

The launcher checks versioned update metadata and validates archives before
installation. Its unit checks cover update-related logic, including rejection
and rollback cases; a new release still needs actual download/update, offline,
corrupt-download, recovery and profile-preservation acceptance.

The current evaluation has no live reporting endpoint. Local reports may contain
personal information and should be reviewed before sharing. Public distributions
must exclude private profiles, inventories and datasets and carry appropriate
third-party notices. Candidate cook policy excludes machine-local editor service
settings; final source and cooked-container inspection remain release gates.
Source privacy cleanup requires a replacement package. These requirements do
not assert that historical source or artifacts have been retroactively sanitized.

## Evidence boundary

The v0.42.11 candidate code checkpoint passed 64 selected native checks (62 clean,
2 with expected warnings) and 103 launcher/update unit checks. A full package run
completed successfully with a validated supervisor receipt, but is not eligible
for promotion: source privacy cleanup requires a replacement. These results do
not establish fresh packaged runtime, hardware, physical two-PC LAN, camera
calibration, public promotion or the whole roadmap. Consult the matching
[change record](CHANGELOG.md) before relying on any version-specific result.
