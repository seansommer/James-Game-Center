# James Game Center — shared storybook art direction v1

This is a documentation-only proposal. The live hub, account flow, game catalogue, shared-racer revision, score history and Firebase rules remain unchanged.

## Canonical art source

The complete editable art bible, first-hero animation contract and staged production plan are versioned in [James-Hulk-Racer art review #1](https://github.com/seansommer/James-Hulk-Racer/pull/1).

Pinned editorial source: [ART_BIBLE.md](https://github.com/seansommer/James-Hulk-Racer/blob/aba2f6f652cfbb4df4e58f54fd2135b91f3bd7d8/production/art-bible-v1/ART_BIBLE.md).

The accompanying 22-page illustrated PDF and full production toolkit are supplied in the conversation. A new visual concept does not imply that the corresponding gameplay sprite, animation or interface has shipped.

## Keep one Jamesy identity

Orange swept hair, blue eyes, friendly child face, open eye mask, white 4 chest shield and white J buckle. Five costume families: Hulk, Spider Style, Captain Style, Iron Style and Super Style. They are one character in different costumes, not five player accounts.

Hulk is the first production hero. Future costumes stay clearly marked in development until their animation and gameplay are ready. The current game title stays **Jamesy The Hulk Racer**.

## Hub treatment

Use the same emerald / purple / cream palette, soft dimensional art, rounded controls and readable labels across the hub, game menus, Hall of Fame and player cards. Keep actual controls as HTML rather than baking them into title art. Keep icons readable at small sizes; do not bake a player's score or current rank into sharing artwork.

The eventual asset set includes 1024-square icon masters; 512, 192 and 180 exports; 1200 x 630 share artwork; consistent player portrait crops; Hall of Fame header and trophy treatment; and all menu focus, pressed, disabled and loading states.

## Preserve the existing player system

The verified baseline is the current v1.3 email/nickname + Anonymous Authentication + Realtime Database model. Preserve Sean as the sole initial Master, explicit master-created additional players, separate practice and registered results, and existing score receipts. Do not import other hubs, add sample players, publish matching credentials, or revive the obsolete Firestore / Google-sign-in prototype.

Keep all six existing Hall of Fame categories, Little Hero / Superhero filters, equal-score ties, clickable player cards and honest empty states. New portrait art does not create a record or seed a leaderboard.

## Review order

1. Five-costume candidate and Hulk identity/pose proof.
2. Eight-frame rear run, then complete Hulk animation package.
3. Emerald composition with minimal portrait/landscape HUD.
4. Isolated playable visual adapter, preserving current rules and account interfaces.
5. Hub/menu/card artwork integration after the hero direction is accepted.
6. Remaining worlds and heroes; device tests and explicit owner approval before main changes.

No new Firebase setup is required for this documentation or asset-review work.
