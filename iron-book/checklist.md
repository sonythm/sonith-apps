# Iron Book: release steps (2026-10-18)

## Done
- [x] App built test-first: 443 Jest tests in 17 suites passing, `npx tsc --noEmit` clean.
- [x] `app.json`:
  - name Iron Book, slug iron-book, package com.sonith.ironbook, version 0.1.0, versionCode 1
  - permissions: POST_NOTIFICATIONS only
  - blocked: INTERNET, SYSTEM_ALERT_WINDOW, RECORD_AUDIO, CAMERA, c2dm RECEIVE
  - `allowBackup: false`
- [x] listing.md, privacy-policy.md (effective 2026-10-18), data-safety.md and play-console-answers.md written from the code.
- [x] Design doc `docs/17-iron-book-design.md`.
- [x] App icons drawn by `store/tools/make-icons.mjs iron-book` (glyph: an iron with steam on blue): `apps/iron-book/assets/icon.png`, adaptive foreground, background and monochrome, and `store/iron-book/icon-512.png`.
- [x] Feature graphic `store/iron-book/feature-graphic.png` (1024 x 500).
- [x] Added to `apps/build-local.ps1`, `apps/verify-release.ps1` and the privacy site (`store/tools/build-privacy-site.mjs`, page generated in `privacy-site/iron-book/`).

## Still to do
- [ ] 1. Publish the privacy site so https://sonythm.github.io/sonith-apps/iron-book/ is live.
- [ ] 2. Build: `build-local.ps1 -Only iron-book` (or `eas init` then `eas build --platform android --profile preview`), then run the app on a real phone, including a low-end one: new order, status flow, payments, share bill to WhatsApp, reminders, backup export and import.
- [ ] 3. Read the merged manifest of the AAB:
  - Must be absent: INTERNET, CAMERA, RECORD_AUDIO, SYSTEM_ALERT_WINDOW, c2dm RECEIVE, SCHEDULE_EXACT_ALARM, READ_MEDIA_*.
  - Must be present: POST_NOTIFICATIONS.
  - `allowBackup="false"`.
- [ ] 4. Screenshots: use the sample data on a phone. Suggested shots: Home (to iron / ready), New order with steppers, Order with Share bill, Customer khata, Reports month, Price list.
- [ ] 5. Play Console: create the app "Iron Book: Press Shop Khata", English, App, Free. Package com.sonith.ironbook cannot be changed later.
- [ ] 6. Store listing from listing.md. Category Business. Contact details.
- [ ] 7. App content: privacy policy URL, ads No, app access (no login, use sample data), content rating per play-console-answers.md, target audience 18+, data safety per data-safety.md, financial features declaration (bookkeeping only).
- [ ] 8. Closed testing track: upload the AAB and add testers. New personal developer accounts need a closed test with enough testers for 14 days before production. Confirm the current numbers in Play Console.
- [ ] 9. Release notes from "What's new" in listing.md, then submit for review.
