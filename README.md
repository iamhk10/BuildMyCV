# BuildMyCV — Installable PWA

This package wraps the uploaded BuildMyCV resume builder in a standard Progressive Web App structure.

## Files
- `index.html` — the original app, updated to reference the static manifest and service worker.
- `manifest.webmanifest` — install metadata, icons, and app shortcuts.
- `sw.js` — caches the app shell for offline launch.
- `icons/` — app, maskable, Apple touch, and favicon assets.

## Hosting / installation
1. Extract the ZIP.
2. Upload the **contents** of `BuildMyCV-PWA` to the same directory on your web host.
3. Serve the site over HTTPS (or `localhost` during development). Service workers do not work reliably from a `file://` URL.
4. Open `index.html` online once and allow the service worker to finish installing.
5. On supported Android/desktop browsers, use the app's **Install App** button or the browser's Install option. On iPhone/iPad, open in Safari and use Share → Add to Home Screen.

## Offline notes
The HTML shell and local PWA assets are cached for offline launch. Some features still rely on external resources: Google Fonts and CDN-hosted `html2canvas`, `jsPDF`, and QR-code scripts. Those resources may not be available offline unless separately self-hosted/cached. Export features that depend on them can therefore be limited without a connection.

## Updating
After changing app files, increment `CACHE_VERSION` in `sw.js` so installed users receive the new app shell.
