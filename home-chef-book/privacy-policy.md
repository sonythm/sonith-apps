# Home Chef Book Privacy Policy

Effective date: 2026-10-18
App: Home Chef Book (com.sonith.homechefbook), version 0.1.0
Developer: Sonith
Contact: sonythm@gmail.com
URL: https://sonythm.github.io/sonith-apps/home-chef-book/

## Short version
Everything you enter stays on your phone. The developer receives none of it. The Android build blocks the internet permission, so the app makes no network calls. There are no accounts, no ads, no analytics and no crash reporting.

## What the app stores on your device
- **Kitchen details**: kitchen or brand name and your name.
- **Customers** (entered by you, the cook): name, phone number (optional), address (optional) and notes, such as likes or allergies you choose to write down.
- **Menu**: item names, sizes, prices and, if you add them, recipes (ingredients and quantities).
- **Ingredients**: names, units and the prices you pay.
- **Orders**: order number, customer (or a name you type), items, sizes and quantities, prices, estimated costs, message on the cake, preferences such as eggless or less sugar, notes, pick-up or delivery, delivery address and charge, discount, status (enquiry, confirmed, preparing, ready, handed over, cancelled), dates and times.
- **Payments**: advances, balances and refunds: amount, date, Cash or UPI, and the order or customer it belongs to. The app records that money was paid or refunded; it does not process payments and stores no bank, card or UPI details.
- **Expenses**: date, amount, type, Cash or UPI and a note.
- **Settings**: week start, daily order limit, delivery charge, usual hand-over time and reminder times.

This data is kept in a local database (SQLite) in the app's private storage. Files you export (CSV, backup JSON) are written to the app's storage before the share sheet opens. The app adds no encryption of its own beyond your phone's storage protection.

## Data types, in plain terms
| Data | Collected by the developer | Shared | Processed on device | Optional | You can delete it |
| --- | --- | --- | --- | --- | --- |
| Kitchen and owner name | No | No (only in messages and files you share) | Yes | Yes | Yes |
| Customer names, phone numbers, addresses, notes | No | No (only in messages and files you share) | Yes | Yes | Yes |
| Orders, payments, expenses, menu and recipes (business records) | No | No (only in files you share) | Yes | Yes | Yes |
| Settings | No | No | Yes | Yes | Yes |
| Location, contacts, photos, audio, device IDs, advertising ID | Not accessed | No | n/a | n/a | n/a |

The app does not read your phone's contacts. Customer details are only what you type in.

## Your customers' information
You enter your customers' details yourself, to run your kitchen. Please only keep what you need, and tell your customers if they ask what you note down. Notes about food preferences or allergies are kept only on your phone. You can edit or delete a customer at any time. A customer with orders is hidden instead of removed so the accounts stay correct; deleting the orders, or Delete all data, removes everything.

## Network calls
None. The internet permission is blocked in the app. There is no account system, analytics, crash reporting, advertising, or third-party SDK that sends data. The font is bundled inside the app. The privacy policy address is shown as text only. The app does not open it.

## Permissions
- **Notifications (POST_NOTIFICATIONS)**: only if you turn on reminders. Reminders are scheduled on the phone, with no push server.
- **Run at start-up, vibrate, wake lock**: added by the notifications library so reminders survive a restart.
- **Blocked**: internet, camera, microphone, drawing over other apps and push messaging.
- For backup import, the app uses the Android system file picker, so it needs no storage permission.

## Notifications
Reminder text is short, for example "3 booked. First: Priya at 11 am", "To make: 2 × Chocolate cake 1 kg", "Order #12 for Priya · Delivery at 5 pm" or "₹1,350 due from 2 after hand-over". Order reminders show the order number and the customer's name on your lock screen. You can turn each reminder off in the app, or hide sensitive content on the lock screen in Android settings.

## Sharing
Order confirmations, bills, customer account statements, shopping lists, WhatsApp summaries, CSV files and backups leave the phone only when you tap share and choose an app. Messages contain the customer's name, the items, the amounts and, for delivery, the address; CSV files and backups contain your business records and customer details. Once shared, the receiving app's privacy policy applies. The developer never receives them.

## Backups
Android's automatic backup is switched off for this app (`allowBackup` is false), so your records are not copied to Google's cloud. To move to a new phone, use Settings, then Export backup, and import the file on the new phone. Keep backup files private: they contain your customers' details.

## How to delete your data
- In the app: delete single orders, payments, expenses, menu items, ingredients or customers, or Settings, then Delete all data. This clears the database and cancels all reminders.
- Turning the sample data off removes only the sample records.
- Uninstalling the app, or clearing its storage in Android settings, removes everything, including exported files kept in app storage.
- Copies you shared to other apps must be deleted there.

The developer holds no copy, so there is nothing to request from the developer.

## Food licences and safety
Home Chef Book is an order book. It does not handle food licences or registration (such as FSSAI), labelling or food-safety checks, and it does not certify anything about your food. Cost and profit figures are estimates from the prices you enter.

## Children
The app is a business tool for adults and is not directed at children. The developer collects no personal information from anyone.

## Changes
If this policy changes, the new version will be posted at the same address with a new effective date.

## Contact
Sonith, sonythm@gmail.com
