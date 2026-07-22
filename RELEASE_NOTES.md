First public build.

**Download `KESTREL-alpha-win64.zip`, unzip it to its own folder, and run
`KESTREL.exe`.** No install, no account. Photoreal terrain works out of the box.

If it will not start, run the bundled `vc_redist.x64.exe` once — a missing
Microsoft C++ runtime is the most common cause.

### What is in this build

- Fly any coordinate on Earth over photoreal terrain — drop a pin, or type MGRS
  / `lat, lon`
- Physics from real component specs, checked against a separate reference model
  with 125 tests
- Betaflight-faithful rates, PID and OSD, including TPA
- Selectable time of day using real solar position, and weather you can see
- Battery brownout, RF failsafe with true line-of-sight, and damage that sticks
- A bundled demo mission with a briefing, radio talk-on and scoring

### Known rough edges

This is an **alpha**. Expect crashes.

- **Reporting is automatic.** Crashes write their own report, and **F12**
  captures one on any screen, to `Documents\KESTREL\reports\`. Zip that folder and
  attach it to an issue here — that is genuinely the most useful thing you can
  do.
- The **no-coverage fallback** — flying somewhere Google has no 3D tiles — is
  implemented but has never been observed firing in testing. If you pick a
  mid-ocean coordinate and it hangs, that is the likely cause; please report it.
- **Missions can express four objective types** (gate, hover, recon, land). The
  scenario layer is the next major piece of work, not a finished feature.
- Controller binding works but is rough, and one report of the arm binding not
  taking has not been reproduced. If it happens to you, F12 immediately.

Windows x64 only. A discrete GPU is effectively required — UE5 will not run
acceptably on integrated graphics.
