# Merry Menace: Daily Run Sheet

The user runs AI organic dropshipping products. This repo holds the code for their daily posting checklist.
They are the creative director. Claude plans each day's list, writes prompts, and keeps the sheet up to date.

## The sheet
- Live page: https://claude.ai/artifact/6opBQWfkVpaLcV2k8wEAq7 (code: `run-sheet.html`)
- Data lives in the page's database. Read and write it with the ArtifactData tool (pass the URL above). Never hardcode data into the HTML.
- To change the page itself: edit `run-sheet.html`, then publish with `url` set to the link above so the link stays the same.

## Data shape
- `settings/main`: `{perProduct: 3, minPerProduct: 2, minNew: 2}`
- `products/<id>`: `{name, code, status: testing|scaling|paused, accounts, link, notes, color 0-5, order, lineup: [{concept, kind, notes}], outliers: [{id, videoId, label, link, views, notes}]}`
- `videos/<id>`: `{productId, date: "YYYY-MM-DD", n, t, made, posted, kind: new|style|split|repost, concept, notes, ref (source post URL), outlierId, variable: visual|text|sound|other, change, views}`
- Video ids used by Claude: `<code lowercase>-<MMDD>-<n>`, e.g. `hp-0925-1`. The file code shown in the app is `HP-0925-1`.

## Account
- Products currently running: Holiday Passenger (HP, animatronic car seat cover, Christmas angle, $90) and Grumpy Crawler (GC). Both post on the same account.
- Instagram: https://www.instagram.com/mymerrymenace/reels/
- Facebook: https://www.facebook.com/profile.php?id=61593258261955&sk=reels_tab (currently the stronger platform)
- Store: https://merrymenace.shop
- Claude Code cloud sessions cannot open Instagram or Facebook (the network blocks them and there is no login). Get data from the user: post links + views, or screenshots.

## Rules for building a day's list
- Per product per day: 3 is the standard, 2 is the bare minimum, 4+ is extra volume. Treat every product equally unless the user says otherwise.
- At least 2 new concepts or new styles across the day. The rest are split tests of outliers.
- Prioritize Facebook and Instagram outliers. Double down on what works: styles of the winning concept, visual hooks, text hooks, sounds.
- A split test changes ONE variable (visual hook, text hook or sound). Before adding one, check which variables that outlier has already had split tested (videos with that `outlierId` and `variable`). Never repeat a tested variable unless it's a brand-new version.
- Every video gets a source post in `ref`: the exact video being swiped. It must be a proven viral one (high views), never a random low-view example. It can come from any product or niche, Christmas or not; what matters is that the concept went viral. Write its view count in `notes`.
- Be specific in `notes`: hook, clips, on-screen text, sound.
- Low views on a video are just data. Never call the account dead. Keep volume and quality up.
- Posting time barely matters. The app shows a post order that alternates products on the shared account.
