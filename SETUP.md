# IPM's CommBadge — Setup Guide

A standalone two-way video call and chat PWA.

---

## Step 1 — Host on GitHub Pages

1. Create a new GitHub repository (e.g. `commbadge`)
2. Upload all files from this folder to the repository root
3. Go to **Settings → Pages**, set source to **Deploy from a branch → main → / (root)**
4. Your app will be live at `https://yourusername.github.io/commbadge`

---

## Step 2 — Supabase

CommBadge uses the same Supabase project as the main MurDough Matrix app for
signalling. The `stream_session` table must exist (created during main app setup).

CommBadge uses a separate Realtime channel (`commbadge-stream`) so it does not
interfere with the main app's stream tab.

---

## Step 3 — Add to home screen

### iPhone/iPad (Safari):
Tap Share → Add to Home Screen

### Android (Chrome):
Tap menu → Add to Home Screen

### Desktop Chrome:
Click the ⊕ install icon in the address bar

---

## How to use

1. Open the app on both devices
2. First user taps **Start Call** — their camera starts, app waits
3. Second user opens the app — sees **Join Call** button, taps it
4. Call connects — both users see each other in picture-in-picture
5. Chat is available during the call, cleared when call ends
6. Tap **End Call** to finish

---

## Roadmap

- Move signalling to a separate dedicated Supabase project to keep
  primary database credentials more private, while preserving the
  seamless one-button connection experience.
