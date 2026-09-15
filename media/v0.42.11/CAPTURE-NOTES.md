# v0.42.11 feature-gallery provenance

Captured September 15, 2026 from the released `v0.42.11-alpha` package,
source `008b4834b9e62d166fafec5ba31aebe5746eb261`.

The four feature images below are original, unedited 1920 x 1080 PNGs.
They use stock aircraft and public terrain, with isolated capture profiles;
customer catalogs, missions, datasets and credentials are not shown.

| Image | SHA-256 |
| --- | --- |
| `flight.png` | `8cadfed35e73e4d9976ec94401c77a9bf84eccd13618aed01eaf62a8e779db3f` |
| `workbench.png` | `df7fe9fe3252c9e46ebc3fd87a9bcfd1249eef936205fe466514b15ab45b6fb5` |
| `mission-builder.png` | `0fb2a28236f473eb16eedc7d22424599f15bf3086e4ea71ab6fc31ddeca088c2` |
| `multiplayer.png` | `582c65042f0dfe561a2f747c46629be62676e9089e48e637f00ca8d1901948a2` |

The flight image is actual simulated FPV flight controlled by the capture
pipeline's virtual pilot, not a manual pilot comparison. Its analog presentation
comes from the stock aircraft's selected video hardware.

The Work Bench image shows a saved stock build and antenna-focused component
inspection. It is not proof of real-world mounting accuracy or finished artwork.

The multiplayer image shows two real game processes on one computer, both ready
and approved. That run also passed shared launch, separate spawns and reciprocal
movement checks. Matching computer names are expected in this same-PC run;
physical two-PC and natural-shutdown acceptance remain open.

The release ZIP and all 4,451 extracted file identities were verified unchanged
after capture. This gallery refresh does not change the executable, updater,
release tag or package checksum. Existing UI and model defects remain visible.

The additional preflight and loading-brief images in the README are also from
this release. A loading brief is not evidence that the live C2 missing-marker
defect is fixed. See the release roadmap for outstanding work.

## Additional weather, time-of-day and scenario views

These six original 1920 x 1080 PNGs were captured on September 15 from the same
immutable released package and source listed above. Hashes below were verified
against the gallery copies; no retouching, generated imagery or game rebuild was
used. Profiles and scenarios were isolated and stock-only.

| Image | Capture | SHA-256 |
| --- | --- | --- |
| `flight-morning.png` | Morning, clear; frame 150 | `08e03faed50e4f19e3af522820969dbe54122d103efc6a1e3976c2bf433e5f59` |
| `flight-daylight.png` | Noon, clear; frame 150 | `c3146690093d987bb1776808448c92c174b8e5edae3ad795e468900b9fcf5ad9` |
| `flight-afternoon.png` | Afternoon, clear; frame 150 | `b5533ab26d299109c3e6dd28ee818e3b994127cbb772628486d2ae28a77bdf7f` |
| `flight-rain.png` | Noon, rain; frame 150 | `53657bf4095ec0bec510458592eae7412001af8070adede25526f31658d92538` |
| `strike.png` | Scripted stock scenario; frame 500 | `ee38299940100e3347059180a05d74bb0527c6caba6c7baa6a66aa2bb5d41ad7` |
| `isr.png` | Same scenario, ISR view; frame 660 | `d76651b5eb7c659c543c4200956b230167d4b643b8a5cfbdcff2ea64cb1a2028` |

The four weather/time views use the same stock-parts aircraft, public area,
physical flight route and optics. Each comes from a 301-frame automated flight.
Configured morning/noon/afternoon correspond to 09:00/12:00/15:00 local solar
time; the lighting differences are subtle. Rain is the game's configured preset,
not observed live weather. The shipped rain uses its fallback streak field and
wet-lens grade, not newly added Niagara or droplet artwork. Dusk/night captures
were withheld because dark terrain, a bright horizon and horizontal banding did
not meet the visual bar; the cause is unconfirmed, and nothing was retouched to
hide those issues.

The strike director stages a near-pass effect, not a verified physical hit.
The visible "Effect not confirmed" verdict is retained. The strike and ISR
images therefore do not establish confirmed damage or objective completion.
These weather and scenario runs exited naturally and preserved release file
identities. The images document current behavior, not completion of the roadmap.
