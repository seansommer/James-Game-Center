# James Game Center — shared storybook art direction v1.1

This is an art-production specification on the review branch. The live hub, account flow, game catalogue, shared-racer revision, score history and Firebase rules remain unchanged.

## Canonical art source

The complete editable art bible, first-hero animation contract and staged production plan are versioned in [James-Hulk-Racer art review #1](https://github.com/seansommer/James-Hulk-Racer/pull/1).

**Current identity revision:** [EMBLEM_REVISION_v1.1.md](https://github.com/seansommer/James-Hulk-Racer/blob/740efdbc10fb72cdc81ac9624b7928c587f23b48/production/art-bible-v1/EMBLEM_REVISION_v1.1.md). The owner approved the five-costume lineup, then requested **J instead of the age-based 4** on the chest. This revision supersedes the earlier numeral-emblem instructions.

Original editorial baseline: [ART_BIBLE.md](https://github.com/seansommer/James-Hulk-Racer/blob/aba2f6f652cfbb4df4e58f54fd2135b91f3bd7d8/production/art-bible-v1/ART_BIBLE.md). Read the v1.1 revision first; any earlier PDF/kit or reference image showing an age numeral is historical for that detail and has not been re-exported by this commit.

A new visual concept does not imply that the corresponding gameplay sprite, animation or interface has shipped.

## Keep one Jamesy identity

Orange swept hair, blue eyes, friendly child face, open eye mask, upright white **J chest emblem** and existing white **J belt buckle**. Preserve the approved shield shapes, costume colors and trim. The Captain-style circular shield also uses **J** in place of the age numeral. Do not add a new emblem to the rear cape or mirror any lettering.

Five costume families: Hulk, Spider Style, Captain Style, Iron Style and Super Style. They are one character in different costumes, not five player accounts. The approved lineup remains the visual reference except for the J-emblem correction. Turnarounds and animation frames still need review.

Hulk is the first production hero. Future costumes stay clearly marked in development until their animation and gameplay are ready. The current game title stays **Jamesy The Hulk Racer**.

## Hub treatment

Use the same emerald / purple / cream palette, soft dimensional art, rounded controls and readable labels across the hub, game menus, Hall of Fame and player cards. Keep actual controls as HTML rather than baking them into title art. Use the age-independent J identity for new app badges, hero portraits and sharing artwork; do not bake a player's score or current rank into them.

The eventual asset set includes 1024-square icon masters; 512, 192 and 180 exports; 1200 x 630 share artwork; consistent player portrait crops; Hall of Fame header and trophy treatment; and all menu focus, pressed, disabled and loading states. These are production targets, not assets claimed as finished in this documentation change.

## Preserve the existing player system

Preserve the existing v1.3 email/nickname + Anonymous Authentication + Realtime Database model. Keep Sean as the sole initial Master, explicit master-created additional players, separate practice and registered results, and existing score receipts. Do not import other hubs, add sample players, publish matching credentials, or revive the obsolete Firestore / Google-sign-in prototype.

Keep all six existing Hall of Fame categories, Little Hero / Superhero filters, equal-score ties, clickable player cards and honest empty states. New portrait art does not create a record or seed a leaderboard.

## Review order

1. Approved five-costume lineup with J correction; next, Hulk front-three-quarter, rear, left/right rear leans and Smash-contact proof.
2. Eight-frame rear run, then the complete Hulk animation package after the proof is accepted.
3. Emerald composition with minimal portrait/landscape HUD.
4. Isolated playable visual adapter, preserving current rules and account interfaces.
5. Hub/menu/card artwork integration using the same approved J identity.
6. Remaining worlds and heroes; device tests and explicit owner approval before main changes.

No new Firebase setup is required for this documentation or asset-review work.
