# Wobble — Made to bend your mind

A 100-stage "mind exercise" puzzle game. Mobile-first, minimalist pastel UI, soothing
**generative jazz**, and an eccentric host — **Professor Wobble** — who taunts, coaches, and
**speaks** (device text-to-speech). This repo is a playable prototype with 4 representative
stages drawn from the 5 cognitive tiers (Logic, Pattern, Spatial, Lateral, Abstract Strategy).

## What's in the build
- **Login** — Google / Facebook / Guest (simulated locally for testing; no real account is contacted).
- **The Lattice** core mechanic — tap a node to toggle it + its neighbours ("lights out"); long-press to **fold** the board (Stage 100).
- **4 stages** — Stage 1 (tutorial), 25 (pattern), 75 (lateral "Read the Room"), 100 (the fold finale).
- **Hint + ad loop** — 5 free hints, 3/stage; extra hints behind a simulated rewarded ad.
- **Professor Wobble speaks** via the device's text-to-speech.
- **Generative jazz** — procedural lo-fi jazz (walking bass, brushed drums, piano comping). Royalty-free, offline.
- **Certificate of Cognitive Excellence** on finishing.

## Run locally (web)
Open `www/index.html` in any browser, or serve the folder:

```powershell
powershell -ExecutionPolicy Bypass -File serve.ps1   # http://localhost:5599
```

## Build the Android APK
The APK is built automatically in the cloud by **GitHub Actions** — no local Android toolchain needed.

1. Push to `main` (or run the **Build Android APK** workflow manually from the Actions tab).
2. When it finishes, grab `wobble-debug.apk` from the generated **Release** (or the run's Artifacts).
3. On your Android phone: download the APK, allow "Install unknown apps" when prompted, and install.

This is a **debug** APK for sideload testing only — not yet signed for the Play Store.

## Tech
Plain HTML/CSS/JS wrapped with [Capacitor](https://capacitorjs.com/). The Android project is
generated fresh in CI (`npx cap add android`) so nothing platform-specific is committed here.

## Roadmap
- Expand from 4 to the full 100 stages across all 5 tiers.
- Real Google / Facebook OAuth via native auth plugins.
- Release signing + Play Store listing.
