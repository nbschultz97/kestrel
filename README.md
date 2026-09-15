<div align="center">

<img src="media/kestrel-lockup-web.png" alt="KESTREL — Small UAS Mission Simulation" width="720">

**Build an aircraft. Choose a location. Practise the flight.**

Windows x64 · Alpha · Proprietary evaluation software

[Default download](https://github.com/nbschultz97/kestrel/releases/tag/v0.42.4-alpha-unsigned.1) · [Optional evaluation](https://github.com/nbschultz97/kestrel/releases/tag/v0.42.9-alpha-eval.1) · [Features](FEATURES.md) · [Changelog](CHANGELOG.md) · [Roadmap](ROADMAP.md)

</div>

KESTREL is an Unreal Engine small-UAS flight simulator with a parts-based Work
Bench, saved aircraft, FPV flight, a mission library and editor, and streamed
real-world terrain. It is built for repeatable practice and evaluation, not
certified navigation, engineering validation or real-aircraft flight testing.

## Download status

Verified September 14, 2026. A higher candidate version does not mean a newer
public download is available.

| Channel | Version | What it means |
|---|---|---|
| Default download / in-app updater | [v0.42.4-alpha-unsigned.1](https://github.com/nbschultz97/kestrel/releases/tag/v0.42.4-alpha-unsigned.1) | Current GitHub Latest release. The package identifies itself as v0.42.4-alpha. |
| Optional public evaluation | [v0.42.9-alpha-eval.1](https://github.com/nbschultz97/kestrel/releases/tag/v0.42.9-alpha-eval.1) | Separate-folder manual installation; not an updater promotion. |
| Upcoming candidate | v0.42.11-alpha | Not publicly released. Selected native and launcher tests passed; a replacement package and fresh acceptance are required. |

The 0.42.10 candidate was held after playtesting. It is not a public release.
Newer candidate work must pass its own checks; old ZIPs and test results are not
relabelled as proof of the current build.

Both published downloads above are **unsigned**. Windows or organization policy
may warn or block them. Use only where unsigned applications are permitted; do
not disable security protections to run KESTREL. “Latest” identifies the default
release channel, not production certification.

## Start here

1. Choose a channel above and download its `KESTREL-alpha-win64.zip`.
2. Check the archive's SHA-256 against that exact release page. Extract it into
   a new folder; do not mix files from different versions or run from inside the ZIP.
3. Start **KESTREL.exe**, the player-facing launcher. Keep the rest of the
   extracted tree beside it; the nested game executable is not the normal entry point.
4. Open controller calibration, check the input source and axis directions, then
   save. Keyboard/gamepad support does not establish compatibility with every USB radio.
5. Use Free Flight or the Test Range and select a saved aircraft. Review the
   displayed controls before arming; menu wording can differ between releases.

The published evaluation includes the intended public Cesium configuration.
Streamed terrain still needs Internet access, service availability and local
loading time. An offline Test Range is not a cached copy of the streamed world.
There is no general offline globe or street-map download.

Windows x64 is the supported package platform. Plan for a modern discrete GPU,
adequate memory, and space for the extracted game, update staging and terrain
cache. Exact minimum/recommended hardware performance has not been certified.
The ZIP is not a Windows runtime installer. If launch fails, retain the exact
error; a security-policy block is not evidence that a runtime is missing.

## What you can explore

- **Aircraft and Work Bench:** choose catalog parts, view the assembled aircraft,
  inspect compatibility and predicted performance, and save named builds.
- **Flight:** FPV and line-of-sight views, Betaflight-style control/rate behavior,
  simulated battery discharge, aerodynamic response and damage.
- **World:** location-based terrain streaming, solar lighting, configurable
  weather and wind. These are simulation inputs, not a live weather service.
- **Practice:** Free Flight, an offline Test Range, a mission library and mission
  authoring. Feature presence is not proof that every mission or full workflow
  passes on every machine.

See [FEATURES.md](FEATURES.md) for the full capability inventory, version
boundaries and modeling limits. Screenshots and trailers below are historical
illustrations, not acceptance evidence for the upcoming candidate.

![Historical KESTREL gameplay](media/gameplay.gif)

[Watch the historical trailer with sound](https://github.com/nbschultz97/kestrel/releases/download/v0.29.1-alpha/kestrel-trailer-v9.mp4)

## Upcoming: v0.42.11

The candidate adds visible Data & Catalogs management, Work Bench inventory
switching and saved-aircraft provenance, local image collections, city-search
preview and map orientation tools, plus targeted assembly, input/display,
audio and terrain-lifecycle corrections. These are **candidate capabilities**,
not features of the current default download or the 0.42.9 evaluation.

At this checkpoint, the selected native suite passed **64 tests** (62 clean,
2 with expected warnings), and **103 launcher/update unit checks** passed.
A full cook/package run completed with a normal zero exit and a validated
supervisor receipt. That package is **not eligible for promotion**: source
privacy cleanup requires a replacement build, then archive/content checks and
fresh packaged-runtime acceptance. No public promotion is claimed.

Full action rebinding, the Work Bench OSD editor and rotating multiplayer
aircraft cards remain unfinished. Physical USB-radio testing, reliable window
mode switching, physical two-PC LAN, the complete camera/prop matrix and the
new release's download/update path still need acceptance. The [roadmap](ROADMAP.md)
keeps those gaps visible.

## Updates, local data and bug reports

The default updater currently advertises v0.42.4-alpha-unsigned.1. The evaluation
channel is a manual opt-in; neither an evaluation suffix nor this documentation
moves existing installations to a candidate. Back up your local settings and
saved aircraft before testing another version.

The 0.42.9 evaluation has no bundled live reporting endpoint. Its reports remain
local, normally under `Documents/KESTREL/reports`. Do not post that folder
unreviewed: logs and screenshots can contain personal paths, locations or data.
When opening an [issue](https://github.com/nbschultz97/kestrel/issues), include the
version, steps to reproduce, expected result and actual result. Attach only
reviewed, redacted evidence; never include tokens or private inventories.

Custom inventories and user-supplied datasets are local runtime inputs. Public
release packages must exclude them; final source and cooked-content inspection
remain release gates. Data panel support does not authorize bundling those inputs.

## License and credits

KESTREL is not open source. See the [Evaluation License](LICENSE.txt) for
permitted uses and restrictions, and the notices shipped with the selected
release for third-party terms. Unreal Engine, Cesium and the relevant imagery,
map, font, audio and asset providers retain their own rights and attribution.

For commercial licensing, contact [Ceradon Systems](mailto:nbschultz97@gmail.com).
Historical, version-specific detail remains in [RELEASE_NOTES.md](RELEASE_NOTES.md).
