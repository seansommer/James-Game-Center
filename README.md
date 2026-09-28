# James Game Center

**Little superheroes. Big adventures.**

The green-and-purple home for Jamesy's games, with Jamesy The Hulk Racer, Hall of Fame, Player Cards and protected Master Controls.

**Hub:** https://seansommer.github.io/James-Game-Center/  
**Racer:** https://seansommer.github.io/James-Hulk-Racer/

## Realtime Database — v1.2

The hub and racer now use **Firebase Realtime Database** at:

`https://james-game-center-default-rtdb.firebaseio.com/`

Only the new **james-game-center** Firebase project is used. Firestore and Google sign-in are no longer required by the runtime. Email-plus-nickname entry uses Anonymous Authentication, as in the other Game Centers. No raw email is stored in the database or displayed on player cards. This is trust-based matching, not email verification.

## One initial master, no imported players

Enable Anonymous Authentication. Publish this version's full **firebase-database.rules.json** in **Realtime Database → Rules**, not Firestore. On the hub, enter your email and **Sean** as the sign-in nickname. Copy the displayed User ID. In Realtime Database → Data add `_admin/masterUid` as a string with that exact ID. Return and press Check access. Only the privately designated identity can activate **Sean · Master**.

The rule file is generated from `shared-racer/scripts/database-rules.mjs`, tested by the racer's emulator suite, and published at `firebase-database.rules.json` on both sites. It does not publish itself to the Firebase console.

Complete activation/recovery guide:
https://github.com/seansommer/James-Hulk-Racer/blob/main/docs/PLAYER_CENTER.md

No first-visitor claim, default admin password, automatic player signup, sample scores or imported family users. Leave Add a player later closed to keep the approved roster master-only. Knowing the master's email/nickname is not enough on another browser: privately authorize its User ID at `_admin/masterDevices/<authUid>` (boolean true) to use the SAME master card. Keep the original `masterUid` unchanged.

## Hall of Fame and cards

Six categories: Most Points, Most Adventures, Most Worlds Completed, Highest Average, Highest Single Run and Longest Clean Streak. Ties share a rank; the average category requires three attempts. Little Hero and Superhero stay separate. Cards show roles, lifetime totals, world bests and medals. Only approved members can view shared records.

Both apps use immutable per-player run receipts from Realtime Database to derive totals. Retry uploads are idempotent. Local practice, account caches and pending results remain isolated. Old Firestore data is left intact but NOT automatically migrated. Do not delete it if it contains records you need. Signed-in results from this version go only to Realtime Database. A display-nickname change does not change the original sign-in pair.

The source still includes responsive game/world tiles, original icons/share artwork, actual racer preview images, a trophy room, music settings, gentle effects, install directions and the scoped offline shell. Existing family/SUJA databases and accounts are not modified.

## Development

The shared-racer Git submodule pins tested shared profile/account/UI source. Vite bundles that source locally; the published hub does not execute unpinned remote code.

```sh
git clone --recurse-submodules https://github.com/seansommer/James-Game-Center.git
cd James-Game-Center
npm install
npm run build
npx playwright install chromium
npm run test:browser
```

Existing checkouts: `git submodule update --init --recursive`. Use Node 22.12+. Deploy both repositories through GitHub Actions Pages so account behavior matches. Browser fixtures never create production accounts. Physical iPhone/Safari and live Firebase console setup still require owner testing. Scores are for friendly family play, not authoritative anti-cheat competition.

Created by Sean.
