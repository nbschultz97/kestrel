# KESTREL v0.26.0-alpha

This release refreshes KESTREL's identity and makes missions calmer, clearer,
and more forgiving without softening the underlying flight model.

## Highlights

- New KESTREL emblem, title lockup, and **ADVANCED sUAS TRAINING PLATFORM**
  positioning across the splash, main menu, and mission loading screen.
- Title/menu music restored as a verified, indefinitely looping release asset.
- Mission progress now moves forward monotonically through terrain loading,
  ground alignment, and flight-area verification instead of dropping backward.
- Small waypoint gates now use a 20 m horizontal corridor and a separate 12 m
  altitude band; larger authored radii remain unchanged.
- Synthetic throttle- and RSSI-driven camera shake removed. Physical airframe
  motion and restrained head lag remain, while RF degradation stays in the
  video-link effects.
- Corrupted punctuation and warning symbols repaired in documentation, with
  explicit UTF-8 handling added to release-note generation.

## Install or update

Existing installations update automatically the next time `KESTREL.exe` is
launched. For a new installation, download `KESTREL-alpha-win64.zip`, extract it
to its own folder, and run `KESTREL.exe`.

The archive is Windows x64 and requires a discrete GPU for practical UE5
performance. This remains an alpha release; report crashes or unexpected
behavior through the repository issues page.
