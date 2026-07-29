# Dose Recorder 💊

A zero-friction medication tracker built for ADHD brains, packaged as an **installable phone app (PWA)**. **One tap logs a dose** — no dialogs, no confirmations, no multi-step flows.

Plain HTML + CSS + vanilla JavaScript, no frameworks and no build step. All data stays in your browser's LocalStorage — no accounts, no servers, no analytics. Works fully offline once installed.

## Put it on your phone (recommended)

1. **Host it** — easiest is GitHub Pages: repo **Settings → Pages → Deploy from a branch → `main` / root**. Your app appears at `https://<username>.github.io/Dose-Recorder/`.
2. **Open that link on your phone**, then:
   - **iPhone:** Share button → *Add to Home Screen*
   - **Android:** browser menu → *Install app*
3. It now launches full-screen from its own icon, with a splash screen, and **works with no internet** thanks to the service worker.

You can also just open `index.html` directly on a computer — everything works except offline caching (which needs http hosting).

> LocalStorage is per-browser-per-device. Use **Settings → Export backup** to move your data between devices.

## Features

- **Home tab** — each medication is a large, high-contrast button grouped by time of day. One tap logs the exact timestamp and preset dose, with confetti, a green checkmark, haptics, and an Undo toast. Each button shows **"Last taken 2h 15m ago"** — the answer to *"wait, did I already take it?"*
- **Double-dose guard** — logged meds turn green with a ✓ and ×N counter but stay tappable for split doses; resets automatically at midnight.
- **Quick-select meds & doses** — ~120 common medications (all ADHD meds plus everyday prescriptions and supplements) with typical strengths as one-tap chips. Free text works for anything else.
- **Flexible schedules** — Daily, Weekly (pick days), or As Needed. Weekly meds appear only on their scheduled days; off-day meds collapse under a toggle but stay tappable.
- **History tab** — today's log up top, past days collapsed, per-entry delete, and one-tap CSV export for your doctor.
- **Settings tab** — manage medications and full JSON backup/restore (meds + entire history) for device migration.
- **Native-feel polish** — bottom tab bar, automatic dark mode, safe-area support for notches, reduced-motion support, offline-first service worker.

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire app (UI, styles, logic) |
| `manifest.json` | Install metadata (name, icon, standalone display) |
| `sw.js` | Service worker — offline caching |
| `icons/` | App icons (home screen, splash, maskable) |

## Data & privacy

- Medications: `localStorage["doseRecorder.meds"]`
- Logs: `localStorage["doseRecorder.logs"]`
- Nothing ever leaves your device. The dose quick-select lists are commonly available strengths for convenience — not dosing guidance; always follow the prescription label.
