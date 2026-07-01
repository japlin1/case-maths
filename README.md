# CM

An offline-first PWA for consulting case-interview mental maths. Seven categories, timed and untimed modes, score tracking by category and mode, and a weak-spot view. Runs on an Android home screen with no signal once installed.

## Files

All five files sit at the repository root. Do not nest them in a subfolder, or the relative paths break.

- `index.html` the whole app, no build step
- `sw.js` service worker for offline caching
- `manifest.webmanifest` install metadata
- `icon-192.png`, `icon-512.png` app icons

## Deploy to GitHub Pages

1. Create a new GitHub repository, for example `case-maths`.
2. Put these five files in the repository root, commit, and push to `main`.
3. In the repo, go to Settings, then Pages. Under Build and deployment set Source to "Deploy from a branch", branch `main`, folder `/ (root)`. Save.
4. Wait a minute, then reload the Pages settings. Your URL appears as `https://YOUR-USERNAME.github.io/case-maths/`.

## Install on Android

1. Open that URL in Chrome on your phone.
2. Open the Chrome menu and choose "Add to Home screen" or "Install app", then confirm.
3. Launch it from the new home-screen icon. It opens full screen with no browser bar.
4. To confirm offline use, turn on aeroplane mode and reopen it. Everything should work.

## Change it later and redeploy

1. Edit the files and push to `main`. Pages redeploys automatically.
2. Bump the version in `sw.js`, changing `const VERSION = 'v1'` to `'v2'` and so on, every time you change the app. The service worker only fetches a fresh copy when this string changes, so without the bump your phone keeps serving the old cached build.
3. On the phone, close and reopen the app once after a redeploy to pick up the new version.

## Notes

Scores are stored locally on the device with no account and no network. Clearing Chrome site data, or the app's storage, wipes your stats. The Reset button on the stats screen clears them deliberately.
