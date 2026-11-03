# El Rincón del Queso Cárdenas F.P. — Releases

Public release channel for **El Rincón del Queso Cárdenas F.P.**, an offline-first POS (a white-label
build of the El Catire J.J platform). The application source lives in a **private** repo; this
repository hosts only the **signed Windows installers** and the **Tauri auto-update manifest**
(`latest.json`) for each release.

## ⚠️ Do not delete or rename this repository

Every installed copy checks

```
https://github.com/ThomasRogersF/rincon-queso-releases/releases/latest/download/latest.json
```

on launch. Deleting or renaming this repo — or removing a release's assets — breaks auto-updates for
every install in the field.

## What a release contains

Each release is a GitHub Release tagged `vX.Y.Z` with:

- **`El Rincón del Queso Cárdenas F.P._X.Y.Z_x64-setup.exe`** (and `_x86-setup.exe` for 32-bit) — the
  NSIS installers (also the auto-update artifacts)
- **`…-setup.exe.sig`** — their update signatures (verified against the app's public key)
- **`latest.json`** — the update manifest the app reads (version, notes, signatures, download URLs)

Never upload El Catire J.J bundles here (they have their own channel, `el-catire-jj-releases`).

## Publishing a release

The step-by-step runbook (build → sign → publish → manifest) lives in the private source repo:
`docs/dev/release-process.md` § "White-label builds". Releases are signed with the project's minisign
update key; the public key is baked into the app, so only official builds are accepted as updates.
