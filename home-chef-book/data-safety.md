# Home Chef Book: Data safety form, question by question

Basis: code review on 2026-10-18 of `apps/home-chef-book`.
- `app.json` requests only `android.permission.POST_NOTIFICATIONS`.
- It blocks INTERNET, SYSTEM_ALERT_WINDOW, RECORD_AUDIO, CAMERA and `com.google.android.c2dm.permission.RECEIVE`, and sets `allowBackup: false`.
- `src` and `app` contain no fetch, socket, URL opening, analytics, ads or crash SDK. `manifest-a11y.test.ts` enforces this.
- Native libraries: expo-sqlite, expo-notifications (local only), expo-sharing, expo-file-system and expo-document-picker (system picker). None of them sends data.

## Section 1: Data collection and security
| Question | Answer | Why |
| --- | --- | --- |
| Does your app collect or share any of the required user data types? | **No** | Nothing is transmitted. Records, including the customer details the cook types in, stay in a local database. Messages and files leave only through the share sheet, when the user starts it. Google treats this as user-initiated sharing, not app collection. |
| Is all of the user data collected encrypted in transit? | Not shown once "No" is chosen | Nothing is transmitted. |
| Do you provide a way for users to request that their data is deleted? | Not shown once "No" is chosen | In the app: delete orders, payments, customers, menu items and expenses, or Settings, Delete all data. Or uninstall. |

## Section 2: Every data type
| Data type | Collected | Shared | Processed on device | Optional | Purpose | User can delete |
| --- | --- | --- | --- | --- | --- | --- |
| Location | No | No | n/a | n/a | n/a | n/a |
| Personal info: name (the cook, and the cook's customers, typed by the cook) | **No** (stays on device) | No | **Yes** | Yes | App functionality | Yes |
| Personal info: phone number (customers, optional, typed by the cook) | **No** (stays on device) | No | **Yes** | Yes | App functionality | Yes |
| Personal info: address (delivery address, optional, typed by the cook) | **No** (stays on device) | No | **Yes** | Yes | App functionality | Yes |
| Personal info: other (customer notes such as food preferences, typed by the cook) | **No** (stays on device) | No | **Yes** | Yes | App functionality | Yes |
| Email, user IDs | No | No | n/a | n/a | n/a | n/a |
| **Financial info: purchase history / other financial info** (the kitchen's orders, advances, payments received, refunds, customer balances, expenses and estimated costs; no card, bank or UPI details) | **No** (stays on device) | No | **Yes** | Yes | App functionality | Yes |
| Health and fitness | No (an "eggless" or "less sugar" preference is an order detail, not health data, and stays on device) | No | n/a | n/a | n/a | n/a |
| Messages | No | No | n/a | n/a | n/a | n/a |
| Photos and videos | No | No | n/a | n/a | n/a | n/a |
| Audio | No | No | n/a | n/a | n/a | n/a |
| Files and docs | No (the backup file the user picks is read once, on device) | No | Yes | Yes | Restore backup | n/a |
| Calendar, contacts | No (phone contacts and the phone calendar are never read; the in-app calendar is the app's own) | No | n/a | n/a | n/a | n/a |
| App activity | No | No | Yes | n/a | n/a | Yes |
| Web browsing | No | No | n/a | n/a | n/a | n/a |
| App info and performance (crash logs, diagnostics) | No | No | n/a | n/a | n/a | n/a |
| Device or other IDs | No | No | n/a | n/a | n/a | n/a |

## Section 3: Facts to keep in step with the policy
- Network: none. VERIFY ON DEVICE: airplane-mode flow, and the merged manifest has no INTERNET, CAMERA or RECORD_AUDIO.
- Customer names, optional phone numbers, addresses and notes are stored on the device only. They are typed by the cook; the app does not read phone contacts.
- User-started outbound: order confirmation and bill text, customer statement text, shopping list text, report summary text, CSV and backup JSON, all through the share sheet. Messages contain the customer's name and, for delivery, the address.
- Lock-screen notifications can show an order number, a customer's name, items to make and total balances due (the policy says so).
- `allowBackup` is false: no Android cloud backup of the records.
- The app makes no food-safety or licence claims (FSSAI is the cook's own responsibility; the policy and About say so).
- Privacy policy URL: https://sonythm.github.io/sonith-apps/home-chef-book/
