# Daily Study Task Manager — PWA

## Files
- `index.html`: your existing study tracker, with PWA metadata and service-worker registration added.
- `manifest.json`: app name, icon, launch mode, and theme.
- `sw.js`: caches the app shell for offline opening.
- `icon-192.png` and `icon-512.png`: install icons.

## Publish using GitHub Pages (Android-friendly)
1. Sign in at https://github.com/ and create a new repository (Public is simplest for GitHub Pages).
2. Open the repository, choose **Add file → Upload files**.
3. Upload the five files from this ZIP's root (not the ZIP itself): `index.html`, `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png`.
4. Commit the upload.
5. Open **Settings → Pages**. Under build/deployment, select **Deploy from a branch**, choose `main` and `/(root)`, then Save.
6. Wait for GitHub Pages to publish, then open the URL shown on the Pages screen using Chrome.
7. Open the site online once and wait a few seconds for the service worker to install and cache the files.
8. In Chrome's menu, choose **Install app** or **Add to Home screen**.

## Offline test
After opening the published site online and letting it finish loading, switch on Airplane mode and reopen the installed app. Test adding/checking a sample task. The app shell is cached and the existing tracker uses localStorage.

## Important data note
Tasks and history are stored in the browser's localStorage. This usually keeps data on that browser/device, but it does not sync between your phone and tablet and can be lost if site data is cleared. The service worker caches app files; it does not back up task data.

## Updates
If you replace app files later, update `CACHE_NAME` in `sw.js` (for example, from `v1` to `v2`) so the browser fetches the new cached app shell.
