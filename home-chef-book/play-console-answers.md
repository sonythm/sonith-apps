# Home Chef Book: Play Console answers (2026-10-18)

Package com.sonith.homechefbook. Developer: Sonith. Contact: sonythm@gmail.com.

## Store settings
- App or game: App. Free.
- Category: **Business**. Tags: Business, Productivity, Food & Drink.
- Ads: **No**, the app contains no ads. No in-app purchases.

## Target audience and content
- Target age: **18 and over**. It is a business tool for home cooks who sell food. Do not select under-13 bands.
- Appeals to children: No. Not in Designed for Families.
- News: No. Government: No. Health: No (food preferences such as "eggless" are order notes, not health features).
- Financial features declaration: the app is a **bookkeeping tool** only. It records orders, advances and refunds the cook received or paid back, but holds no money, gives no loans, processes no payments and makes no trades. The customer "khata" is the cook's own record of who owes what, not a credit product. Answer "My app doesn't provide any financial features". VERIFY the current wording in Play Console.
- Food: the app does not sell or deliver food itself and is not a marketplace. The cook's food licence (FSSAI) is outside the app; the listing makes no food-safety claims.

## Content rating (IARC questionnaire)
Category: Utility, Productivity, Communication or Other.
- Violence, blood, sexual content, nudity, profanity, crude humour: No.
- Controlled substances (alcohol, tobacco, drugs): No.
- Gambling or simulated gambling: No.
- Fear or horror: No.
- Users can interact or exchange content with each other: No.
- Shares user location: No.
- Digital purchases: No.
- Unrestricted web access: No.

Expected result: Everyone / PEGI 3 / USK 0. Target age in Play is still set to 18+ because of the audience.

## App access
No login, and every function is open. Steps for the reviewer:
1. Open the app: splash, then Setup.
2. Tap "Try with sample data". This opens a sample home kitchen, "Meena's Kitchen", with two months of orders, ten days of bookings ahead, twelve customers, advances, payments and expenses.
3. Home: tap New order, tap a size chip (for example "1 kg ₹850"), pick a customer or type a name, choose Half advance and Save order. On Home, tap the next-step button on an order (Undo appears).
4. Calendar: see each day's orders against the daily limit; tap + on a day to add an order for it.
5. Open an order: estimated cost and profit, Send confirmation (opens the share sheet), Cancel order (keep or refund the advance).
6. Customers: open a customer to see orders, payments and the balance; Record payment; Share.
7. Reports: switch Day, Week, Month and Year, and tap any number to see the list behind it. CSV and WhatsApp open the share sheet.
8. Settings (gear on Home), Menu and prices, Ingredients, Reminders (switching them on shows the notification permission prompt), Delete all data.

## Data safety summary
- Collects or shares user data: **No**. INTERNET is blocked and the app has no network code.
- On device only: kitchen name, customer names with optional phone numbers, addresses and notes, menu and recipes, orders, payments, expenses, settings.
- Outbound only when the user starts it: share sheet text and files.
- Deletion: in-app delete, Delete all data, or uninstall.
- Details: data-safety.md. Policy: https://sonythm.github.io/sonith-apps/home-chef-book/

## Permission declaration notes
- Requested: POST_NOTIFICATIONS (runtime, Android 13+).
- Added by libraries: RECEIVE_BOOT_COMPLETED, VIBRATE, WAKE_LOCK.
- Blocked: INTERNET, CAMERA, RECORD_AUDIO, SYSTEM_ALERT_WINDOW, c2dm RECEIVE.
- POST_NOTIFICATIONS: "Optional local reminders the cook switches on: an evening summary of tomorrow's orders, a shopping reminder for tomorrow, a reminder before each order's hand-over time, and a follow-up while balances are unpaid. Scheduled on the device, no server."
- No exact alarm, foreground service, full-screen intent, SMS, call log, contacts, location, photos or all-files access. No declaration forms are needed. VERIFY ON DEVICE: the merged manifest has no SCHEDULE_EXACT_ALARM and no READ_MEDIA_*.
