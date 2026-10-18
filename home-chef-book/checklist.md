# Home Chef Book: release steps (2026-10-18)

## Done
- [x] App built test-first: 438 Jest tests in 15 suites passing, `npx tsc --noEmit` clean.
- [x] `app.json`:
  - name Home Chef Book, slug home-chef-book, package com.sonith.homechefbook, version 0.1.0, versionCode 1
  - permissions: POST_NOTIFICATIONS only
  - blocked: INTERNET, SYSTEM_ALERT_WINDOW, RECORD_AUDIO, CAMERA, c2dm RECEIVE
  - `allowBackup: false`
- [x] listing.md, privacy-policy.md (effective 2026-10-18), data-safety.md and play-console-answers.md written from the code. No food-safety or FSSAI claims.
- [x] Design doc `docs/23-home-chef-book-design.md`.
- [x] Icon glyph and palette for `store/tools/make-icons.mjs` in `store/home-chef-book/icon-glyph.txt` (a white chef's hat with a berry heart on a berry gradient). Preview icons were rendered from it into `apps/home-chef-book/assets/` and `store/home-chef-book/icon-512.png`.

## Still to do
- [ ] 1. Add the glyph and OVERRIDE lines from `icon-glyph.txt` to `store/tools/make-icons.mjs`, then run `node store/tools/make-icons.mjs home-chef-book` so the icons come from the shared tool.
- [ ] 2. Feature graphic `store/home-chef-book/feature-graphic.png` (1024 x 500) from `assets.json`.
- [ ] 3. Add home-chef-book to `apps/build-local.ps1`, `apps/verify-release.ps1` and the privacy site (`store/tools/build-privacy-site.mjs`), then publish the site so https://sonythm.github.io/sonith-apps/home-chef-book/ is live.
- [ ] 4. Build: `build-local.ps1 -Only home-chef-book` (or `eas init` then `eas build --platform android --profile preview`), then run the app on a real phone: setup, new order with sizes and advance, calendar load and capacity warning, status flow, cancel with keep and refund, recipe cost on an item, share confirmation to WhatsApp, reminders, backup export and import.
- [ ] 5. Read the merged manifest of the AAB:
  - Must be absent: INTERNET, CAMERA, RECORD_AUDIO, SYSTEM_ALERT_WINDOW, c2dm RECEIVE, SCHEDULE_EXACT_ALARM, READ_MEDIA_*.
  - Must be present: POST_NOTIFICATIONS.
  - `allowBackup="false"`.
- [ ] 6. Screenshots: use the sample data on a phone. Suggested shots: Home (today and tomorrow), New order with size chips, Calendar with a full day, Order with cost and profit, Customer khata, Reports month, Menu item with recipe.
- [ ] 7. Play Console: create the app "Home Chef Book: Order Diary", English, App, Free. Package com.sonith.homechefbook cannot be changed later.
- [ ] 8. Store listing from listing.md. Category Business. Contact details.
- [ ] 9. App content: privacy policy URL, ads No, app access (no login, use sample data), content rating per play-console-answers.md, target audience 18+, data safety per data-safety.md, financial features declaration (bookkeeping only).
- [ ] 10. Closed testing track: upload the AAB and add testers. New personal developer accounts need a closed test with enough testers for 14 days before production. Confirm the current numbers in Play Console.
- [ ] 11. Release notes from "What's new" in listing.md, then submit for review.
