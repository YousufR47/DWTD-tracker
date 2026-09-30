# Don't Waste the Day

A one-question daily tracker: *did I deliberately use today?* Single-page app,
no backend, all data stored in your browser via localStorage.

## Deploy to GitHub Pages

1. Create a new GitHub repo (public, or private with Pages enabled on your plan) and upload
   every file in this folder to the repo root: `index.html`, `manifest.json`, `sw.js`,
   `icon-192.png`, `icon-512.png`, `icon-192-maskable.png`, `icon-512-maskable.png`,
   `apple-touch-icon.png`.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to "Deploy from a branch", pick your
   default branch (e.g. `main`) and folder `/ (root)`, then **Save**.
4. Wait a minute or two, then open the URL GitHub shows you
   (usually `https://<your-username>.github.io/<repo-name>/`).

That URL is now a real HTTPS site, which is required for a PWA (service workers only
work over HTTPS or localhost).

## Install it on your phone

**iPhone (Safari)**
1. Open the GitHub Pages URL in Safari (must be Safari, not Chrome, for the install step).
2. Tap the Share icon → **Add to Home Screen** → **Add**.
3. It now opens full-screen from your home screen, with no browser bar.

**Android (Chrome)**
1. Open the URL in Chrome.
2. Tap the **⋮** menu → **Add to Home screen** / **Install app**.
3. Same result — a standalone app icon.

## Notes

- **Data stays on-device.** Each browser (and each of Safari vs. Chrome, if you try both)
  has its own separate storage. Once installed as a home-screen app, that installed copy
  keeps its own data too — export from Settings occasionally as a backup.
- **Offline use**: `sw.js` caches the app shell, so it opens even with no signal. It
  fetches a fresh copy when online and falls back to the cached one when offline.
- **Updating later**: if you ask Claude for more changes, just replace `index.html` in the
  repo (the other files rarely need to change) and push. Your phone will pick up the new
  version next time it opens with a connection; a service worker update can take one extra
  reopen to fully take effect, which is normal PWA behaviour.
- The icon is a simple hourglass in the app's purple, generated to match the theme —
  swap the PNGs for your own art any time if you'd like something different.
