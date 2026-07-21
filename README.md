<div align="center">

# K E S T R E L

**sUAS flight trainer — fly any coordinate on Earth, on physics derived from real part specs.**

[**Download the latest build →**](../../releases/latest)

*a Ceradon Systems product · Windows x64 · alpha*

</div>

![KESTREL — banked FPV pass over photoreal terrain](media/flight-banked.png)

KESTREL is an FPV/sUAS simulator built in Unreal Engine 5. Build a drone from
**real component specifications**, fly it with faithful Betaflight feel and a
Betaflight-style OSD on your own RC radio, over **photoreal real-world terrain
streamed at any GPS coordinate you type in.**

It is not a game about drones. It is an attempt at a *training device*: the loop
runs **configure a specific aircraft → fly that exact aircraft on a meaningful
task → get a record out the other end.**

> **Alpha.** It is playable and it is rough. Things will break. Bug reports are
> automatic — see below — and genuinely useful.

---

## Get it running

1. [**Download**](../../releases/latest) `KESTREL-alpha-win64.zip` and unzip it
   **to its own folder**.
2. Run **`KESTREL.exe`**. That is the only thing to click — no install, no
   account, no setup. Photoreal terrain works out of the box.
   SmartScreen will warn (the build is unsigned) → *More info* → *Run anyway*.
3. If it will not start, run the bundled **`vc_redist.x64.exe`** once. A missing
   Microsoft C++ runtime is the most common cause.
4. **CALIBRATE CONTROLLER → AUTO-DETECT → SAVE → BACK.**
5. **LOCATION** → drop a pin on the map, or type `40.7580, -73.9855` → fly.
   Throttle down, then Enter (or your mapped switch) to arm.

Needs a network connection for tile streaming. Keyboard and gamepad work, but an
RC radio in USB-Joystick mode is the point.

---

## What makes it real

- **Fly any coordinate on Earth.** Drop a pin, or type MGRS or `lat, lon`, and
  that exact spot loads in photoreal 3D tiles. Ground elevation is looked up and
  the world self-calibrates against the streamed terrain, so you spawn on the
  actual street.
- **Physics from real specs.** Mass, KV, cell count, capacity and prop size come
  from the loadout. Motors top out at the spec sheet's *loaded* rated point, not
  an impossible no-load speed — so thrust-to-weight and the feel of weight are
  honest. Checked against an independent reference model with 125 tests.
- **Battery reality.** Nonlinear LiPo discharge, IR sag, a real voltage cliff.
  Fly the pack down and it browns out — the aircraft falls out of the sky.
- **RF link that means something.** RSSI is computed from real distance *and*
  line-of-sight through the photoreal geometry. Fly behind a building at range
  and the video tears and snows, then the link fails.
- **Conditions from where and when.** Real solar position for the site's
  latitude, longitude and date. Weather you can see. Wind that acts on
  **airspeed**, so you crab into it. Density altitude fed to the physics.
- **Failure is modelled, not scripted.** Impacts crack the camera, kill
  individual motors, or destroy the airframe. Nothing is on a timer.

---

## Screens

| | |
|---|---|
| ![Title](media/title-backdrop.png) | ![Main menu](media/main-menu.png) |
| Title, while the world streams in. | Front end, over the live AO. |
| ![Settings](media/settings.png) | ![Low pass](media/flight-lowpass.png) |
| Audio, display, environment, flight. | Low pass over real streets. |

---

## Found a bug?

**Reporting is automatic.** Crashes write their own report, and **F12** captures
one on any screen. Everything lands in:

```
Documents\KESTREL\reports\
```

Zip that folder and send it to **contact@ceradonsystems.com** — subject
`KESTREL bug`. That is everything needed; you do not have to describe it well.

If you would rather write it up, three things help most:
1. **Version** — printed top-right on screen.
2. **What you did** — "hit RANDOM AO", "mapped a switch to arm and flipped it".
3. **What happened** vs. what you expected.

Known issues ship in `CHANGELOG.md` inside the zip.

---

## Requirements

| | Minimum | Recommended |
|---|---|---|
| OS | Windows 10 64-bit (1909+) | Windows 11 64-bit |
| CPU | Quad-core 2.5 GHz (i5-8400 / Ryzen 5 2600) | 6-core 3.5 GHz+ |
| RAM | 8 GB | 16 GB |
| GPU | DirectX 12, 4 GB VRAM (GTX 1060 / RX 580) | RTX 2060 / RX 5700+ |
| Disk | 2 GB free | — |
| Controller | RC radio in USB-Joystick mode (RadioMaster / EdgeTX / TBS) | RC radio |

A **discrete GPU is effectively required** — UE5 will not run acceptably on
basic integrated graphics. Windows x64 only for now; no Mac or Linux build.

---

## About

KESTREL is developed by [Ceradon Systems](https://ceradonsystems.com).

This repository hosts **releases and documentation only** — the engine source is
private. Issues and feedback are welcome here.

*Photoreal terrain © Google, streamed via Cesium ion. Map imagery © Esri.*
