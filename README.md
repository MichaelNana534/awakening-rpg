# AWAKENING — PWA package

## Included
- `index.html` — app interface
- `app.js` — progression, quests, finance, rewards, backup logic and personal theme store
- `manifest.webmanifest` — install metadata
- `service-worker.js` — offline app-shell cache\n- Immersive boot sequence, System notification panel, hunter evolution profile, equipment unlocks and ability unlocks
- `icons/` — 192px, 512px and maskable PWA icons
- Personal Theme Store — eight built-in palettes (Midnight, Ocean, Blossom, Nature, Lavender, Sunrise, Minimal and Galaxy), plus custom themes
- Theme selection and custom palettes are saved in the existing local progress backup

## Deploy free with GitHub Pages
1. Sign in to GitHub and create a new **public** repository named `awakening` (or another name).
2. Upload every item inside this folder. `index.html` must be at the repository root, not inside another nested folder.
3. In the repository open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**; choose `main` and `/ (root)`, then Save.
5. Wait for GitHub Pages to publish. The address will look like `https://YOUR-USERNAME.github.io/awakening/`.
6. Open that HTTPS address in **Safari** on your iPhone. Tap **Share** (square with upward arrow), scroll and choose **Add to Home Screen**, then tap **Add**.
7. Launch AWAKENING from the new Home Screen icon. Open it once while online so the service worker can cache the app shell.

## Updating
Edit the files locally, then upload/commit the changed files to the same repository. Keep the same browser storage key in `app.js` (`awakening_rpg_v2`) so ordinary app updates do not reset progress. The service-worker cache has been advanced to v3 for this update. The service worker cache version can be incremented when changing the offline shell. Export a JSON backup before major updates.

## Where data lives
Progress is stored in the browser's `localStorage` on the device and browser origin. It is not synced to a server and is not automatically shared between Safari and other browsers/devices. Clearing Safari website data, removing site data, or changing the hosted domain can make the local save inaccessible. Use **Settings → Export backup** regularly. To restore, use **Import backup** on the same app origin.

## Important limitations
- Offline use works after the first successful online visit and service-worker caching, but browser storage can still be cleared by iOS.
- A secure HTTPS host is required for service workers and PWA installation (localhost is the development exception).
- iPhone installation is performed through Safari's Share → Add to Home Screen. The exact wording can vary by iOS version.
- Quest completion is self-reported; the app does not verify activities.
- This package is prepared for deployment, but it has not been published to a hosting account. You must create/use your own GitHub account and publish it.
