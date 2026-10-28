# Open Camera Lenses

A modified build of [Open Camera](https://sourceforge.net/p/opencamera/code/) (upstream commit in `UPSTREAM_COMMIT`), aimed at Samsung Galaxy phones:

- **All lenses:** camera IDs that the device supports but leaves out of `getCameraIdList()` are found by probing IDs 0–127, and added to the camera/lens switcher. Samsung only lists some of its lenses to third-party apps.
- **No camera-driver noise reduction or sharpening by default:** *Settings → Processing* defaults edge mode and noise reduction mode to *Off*. If a lens can't turn noise reduction off, *Minimal* is used.
- **No digital zoom (crop + upscale) by default:** turn it back on under *Settings → Processing → Allow digital zoom*. Without it, each lens is used at its native field of view.

For fully unprocessed output, also enable RAW (DNG) under *Settings → Photo settings → Image format*.

The app installs as `net.sourceforge.opencamera.lenses`, next to the regular Open Camera. The APK is built by GitHub Actions (*Build APK* workflow → artifact).

Licensed under GPL v3, as is upstream (see `gpl-3.0.txt`).
