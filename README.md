# Dose Recorder 💊

A zero-friction medication tracker built for ADHD brains. **One tap logs a dose** — no dialogs, no confirmations, no multi-step flows.

Everything is a single `index.html` file: HTML + Tailwind CSS + vanilla JavaScript, with all data stored privately in your browser's LocalStorage. Nothing ever leaves your device.

## How to run

**Option 1 — just open it:**
Download `index.html` and double-click it. It runs entirely in the browser.

**Option 2 — serve it locally** (nicer for phones on the same Wi-Fi):

```bash
python3 -m http.server 8000
# then open http://localhost:8000 on your computer,
# or http://<your-computer-ip>:8000 on your phone
```

**Option 3 — make it feel like a native app:**
Host it anywhere (GitHub Pages works great), open it on your phone, then use *Add to Home Screen* in Safari/Chrome. It opens full-screen with big thumb-reachable buttons.

> Note: LocalStorage is per-browser-per-device. Use the **Export CSV** button to back up or move your history.

## Features

- **Setup mode** — add/edit medications with name, dosage, and an optional time-of-day group (Morning / Afternoon / Evening / Anytime).
- **Dashboard** — each medication is a large, high-contrast button. One tap logs the exact date and time with the preset dose.
- **Instant feedback** — confetti burst, green checkmark, haptic buzz (on supported phones), and an Undo toast for accidental taps.
- **Double-dose guard** — already-taken meds turn green with a ✓ and a ×N counter, but stay tappable for split doses.
- **History** — today's log up top, past days collapsed out of the way, per-entry delete, and one-tap CSV export for your doctor.

## Data & privacy

- Medications: `localStorage["doseRecorder.meds"]`
- Logs: `localStorage["doseRecorder.logs"]`
- No accounts, no servers, no analytics.
