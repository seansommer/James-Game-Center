# James Game Center

**Little superheroes. Big adventures.**

A green-and-purple home for Jamesy's superhero games. The first playable app is [Jamesy The Hulk Racer](https://seansommer.github.io/James-Hulk-Racer/), a 3D half-pipe runner in three worlds.

**Intended hub address:** https://seansommer.github.io/James-Game-Center/

## Included

- Responsive Game Center, featured game tile and three world launch links.
- Shared nickname, local progress, hero card, trophies and optional private Firebase backup.
- Original hub badge, phone icons and sharing artwork, generated from the checked-in vector source.
- Actual in-game world renders linked from the racer's deployment, not AI concept screenshots.
- Separate music/effect sliders, gentle effects preference, install instructions and scoped offline shell.
- A simple `src/games.js` catalogue ready for future released James superhero games. Future-adventure cards are clearly marked and do not pretend to be playable games.

No email, public profiles, messaging, ads or analytics. The new hub is separate from the existing family and SUJA Game Centers and uses only the new `james-game-center` Firebase project.

## Launch

For **both** `James-Game-Center` and `James-Hulk-Racer`, open **Settings → Pages → Source → GitHub Actions**. Then run the publish workflow from Actions if it already attempted deployment before Pages was enabled.

The racer must finish its first deployment before its linked 3D preview images appear here. Gradient placeholders keep the hub usable while they load. The hub's own app icon and share image are built independently.

Optional Firebase setup is documented in the racer's [setup guide](https://github.com/seansommer/James-Hulk-Racer/blob/main/docs/SETUP.md). Enable Anonymous Authentication, create the default Cloud Firestore database in production mode, and publish the racer's complete `firestore.rules` file in **james-game-center**. Do not change the existing family or SUJA databases. Local play and saving work without this setup.

Anonymous cloud backup is private to the current anonymous user and is not a cross-device login. Clearing browser credentials can lose access to the old anonymous backup. Keep nicknames non-identifying.

## Development and the shared module

The `shared-racer` Git submodule is pinned to a specific racer commit. It supplies the same profile schema, Firebase adapter, dialogs, music engine and common styles to both apps. The hub does not execute remote source at runtime: Vite bundles these pinned local files into the published hub.

```sh
git clone --recurse-submodules https://github.com/seansommer/James-Game-Center.git
cd James-Game-Center
npm install
npm run dev
```

For an existing checkout, run `git submodule update --init --recursive` before building. To update shared behavior, deliberately update and commit the submodule revision, then run the checks. Do not silently track the latest remote branch.

```sh
npm run build
npx playwright install chromium
npm run test:browser
```

Node 22.12+ is required. Direct dependency versions are pinned; the first CI installation places the resolved `package-lock.json` in the verification artifact. Commit the lock for subsequent `npm ci` builds. Browser checks verify the catalogue, nickname persistence, shared progress format, trophies, and narrow-screen overflow. Physical iPhone Safari testing remains separate.

Created by Sean.
