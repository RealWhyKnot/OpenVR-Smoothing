# WKOpenVR-Smoothing

One-Euro finger-curl smoothing and per-tracker pose-prediction control for Valve Index Knuckles, packaged as a one-feature install of the WKOpenVR umbrella.

## What this is for

Index Knuckles capsense is great, but the per-finger axes are noisy -- especially under light contact pressure. The result is shaky fingers on your avatar, visible to everyone you stand next to. SteamVR's pose prediction makes it worse: it extrapolates ahead of the actual sensor reading, so finger curls overshoot whenever the controller is moving.

What you get:

- **One-Euro filter** on each finger axis, per controller. Cuts jitter without dragging behind the way a flat low-pass would.
- **Per-tracker pose-prediction suppression**. Disable forward prediction on the controllers (or other devices) where you don't want it, without forcing the rest of the system to give up prediction.
- **State replay on reconnect** -- toggling things in the overlay, restarting SteamVR, or swapping a controller out doesn't lose your saved per-tracker values.
- **Driver-level skeletal hook** so the smoothed values feed every consumer (VRChat hand gestures, the SteamVR shell, IK middleware, animations), not just one app.

## Get it

Latest builds are on the [Releases page](https://github.com/RealWhyKnot/WKOpenVR-Smoothing/releases):

- `WKOpenVR-Smoothing-<version>.zip` -- the WKOpenVR umbrella build with `enable_smoothing.flag` pre-dropped so smoothing activates immediately on install.
- `WKOpenVR-Smoothing-v<version>-Setup.exe` -- NSIS installer that does the same, plus a Start Menu shortcut and an uninstaller.

## Source

Source lives in [WKOpenVR](https://github.com/RealWhyKnot/WKOpenVR), the umbrella repository for the WKOpenVR feature modules. This repo is a release mirror.

This module has no upstream -- it was authored in the umbrella. Pre-monorepo source state is preserved in the umbrella's git history.

## Issues and contributions

Open them at [WKOpenVR/issues](https://github.com/RealWhyKnot/WKOpenVR/issues).

## License

GPL-3.0 (see LICENSE).
