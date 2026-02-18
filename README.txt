Armstrong Pull-up Tracker (Offline + Autosave + Mobile)

FILES
- index.html        (the app)
- manifest.json     (PWA install metadata)
- sw.js             (offline caching / service worker)
- icon-192.png / icon-512.png  (app icons)

1) EASIEST "APP" ON ANDROID (PWA / Add to Home Screen)
This is the closest to an app without building an APK.

A) Put these files somewhere your phone's browser can load them from:
   - Best: upload the folder to any simple web hosting (GitHub Pages, Netlify, etc.)
   - Or: open index.html from a local file manager (works), but installability can vary by browser.

B) Open index.html in Chrome
C) Tap (⋮) menu → "Add to Home screen" (or "Install app" if it appears)
D) Launch it from your home screen

Autosave:
- Your entries are saved automatically to localStorage.
- It works offline after the first load (when hosted and opened once).

2) OPTIONAL: MAKE A REAL APK (Trusted Web Activity)
If you want a true APK that installs like a normal app:
- Host the app (HTTPS required). Example: https://yourdomain.com/armstrong/
- Then build an Android APK using Bubblewrap (Google's tool for TWAs).

High-level steps (PC required):
A) Install Node.js
B) Install Bubblewrap:
   npm i -g @bubblewrap/cli
C) Initialize:
   bubblewrap init --manifest=https://yourdomain.com/armstrong/manifest.json
D) Build APK:
   bubblewrap build
E) Install on phone:
   bubblewrap install (or manually install the generated APK)

Notes:
- TWA requires HTTPS hosting + a valid manifest.
- You'll also need Android Studio / Java if Bubblewrap prompts for it.
