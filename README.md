# James Game Center

**Little superheroes. Big adventures.**

A green-and-purple home for Jamesy's superhero games. The first playable app is [Jamesy The Hulk Racer](https://seansommer.github.io/James-Hulk-Racer/), a 3D half-pipe runner in three worlds.

**Hub:** https://seansommer.github.io/James-Game-Center/

## New: Hall of Fame, Player Cards and protected Master Controls

The shared player headquarters now offers six trophy categories, ranked tables with clickable player names, searchable lifetime player cards, and a protected master account. **Sean is the only initial approved player after private Firebase activation.** No old Game Center users, demo players or sample scores are imported.

The Hall categories are Most Points, Most Adventures, Most Worlds Completed, Highest Average, Highest Single Run and Longest Clean Streak. Little Hero and Superhero records stay separate, ties share a rank, averages require three results, and a new master card is unranked until it earns a result.

Cards include Master/Player role, points, adventures, completions, averages, best run, clean streak, treasures, smashes, bursts, clean finishes, completion rate, and all three worlds' best scores and medals. Only approved members can view shared records. Emails are never shown on cards or copied into shared score documents.

**Activation guide:** [Hall of Fame and master account setup](https://github.com/seansommer/James-Hulk-Racer/blob/main/docs/PLAYER_CENTER.md).

Enable Google Authentication in the new **james-game-center** Firebase project and publish the racer's updated full `firestore.rules`. Sign in on the website, copy your new James User ID, then set the private Firestore document `_admin/launch`, field `masterUid` (string), to that exact UID. Press **Check access**. Only that configured identity may activate the initial **Sean · Master** card. The client cannot claim, reassign, demote or delete the master. No live activation happens merely by publishing code.

Other identities are not automatically approved. Leave **Add a player later** closed to keep the roster master-only. Visitors can practice locally without creating a player card or appearing in rankings. Master Controls can explicitly approve additional players later or pause/restore their access without deleting their records.

## Included

- Responsive Game Center, featured racer tile and three world launch links.
- Shared registered Google identity, account-isolated player progress, Hall of Fame and cards.
- Personal trophy room remains separate from the competitive Hall.
- Original hub badge, phone icons and sharing artwork generated from vector source.
- Actual in-game world renders linked from the racer, not AI concept screenshots.
- Music/effect sliders, gentle effects, install instructions and scoped offline shell.
- A simple `src/games.js` catalogue for future released James superhero games.

The new hub is separate from the family and SUJA centers. It does not import their accounts, roles or scores. There is no messaging, advertising or analytics. Google Authentication knows the chosen account's email; Firestore cards and leaderboards use nicknames only. This is a private approved-family setup, not a public child-account service.

## Publish both repositories

For **both** `James-Game-Center` and `James-Hulk-Racer`, open **Settings → Pages → Source → GitHub Actions**. Run the publish workflow if an earlier attempt occurred before Pages was enabled. Both new builds must deploy so the shared account behavior is consistent.

The racer's deployment supplies the linked game-preview images. Gradient placeholders keep the hub usable while they load. Hub icons and share artwork build independently.

## Saving and migration

Sign in before racing to add registered records. Uploaded results follow the same Google identity across devices. Pending results stay on the original browser/device and retry under the original UID, without double-counting. Practice and registered caches are separate. The original anonymous practice backup remains owner-private but is not guessed into lifetime stats that the old schema did not track.

The full private setup and limitations are in the [activation guide](https://github.com/seansommer/James-Hulk-Racer/blob/main/docs/PLAYER_CENTER.md). Live Google sign-in and Firebase console state must be verified by the owner. App Check enforcement is not enabled by this update. Scores are client-measured for friendly competition, not authoritative anti-cheat rankings.

## Development

The `shared-racer` Git submodule pins the exact shared profile, account, rules-tested model, UI and music source. Vite bundles it locally; the hub never executes an unpinned remote script at runtime.

```sh
git clone --recurse-submodules https://github.com/seansommer/James-Game-Center.git
cd James-Game-Center
npm install
npm run dev
```

For an existing checkout run `git submodule update --init --recursive` before building. Update the submodule deliberately when shared behavior changes.

```sh
npm run build
npx playwright install chromium
npm run test:browser
```

Node 22.12+ is required. Direct dependencies are pinned; CI exports its resolved lock in the verification artifact. Browser checks cover the catalogue, nickname/practice persistence, trophies, phone layout, Hall of Fame and player cards using an in-memory test fixture. Test fixtures never create production accounts. Physical Safari and live authentication tests remain separate.

Created by Sean.
