# Iron Book: Data safety form, question by question

Basis: code review on 2026-10-18 of `apps/iron-book`.
- `app.json` requests only `android.permission.POST_NOTIFICATIONS`.
- It blocks INTERNET, SYSTEM_ALERT_WINDOW, RECORD_AUDIO, CAMERA and `com.google.android.c2dm.permission.RECEIVE`, and sets `allowBackup: false`.
- `src` and `app` contain no fetch, socket, URL opening, analytics, ads or crash SDK. `manifest-a11y.test.ts` enforces this.
- Native libraries: expo-sqlite, expo-notifications (local only), expo-sharing, expo-file-system and expo-document-picker (system picker). None of them sends data.

## Section 1: Data collection and security
| Question | Answer | Why |
| --- | --- | --- |
| Does your app collect or share any of the required user data types? | **No** | Nothing is transmitted. Records, including the customer details the owner types in, stay in a local database. Bills and files leave only through the share sheet, when the user starts it. Google treats this as user-initiated sharing, not app collection. |
| Is all of the user data collected encrypted in transit? | Not shown once "No" is chosen | Nothing is transmitted. |
| Do you provide a way for users to request that their data is deleted? | Not shown once "No" is chosen | In the app: delete orders, payments, customers and expenses, or Settings, Delete all data. Or uninstall. |

## Section 2: Every data type
| Data type | Collected | Shared | Processed on device | Optional | Purpose | User can delete |
| --- | --- | --- | --- | --- | --- | --- |
| Location | No | No | n/a | n/a | n/a | n/a |
| Personal info: name (shop owner, and the shop's customers, typed by the owner) | **No** (stays on device) | No | **Yes** | Yes | App functionality | Yes |
| Personal info: phone number (customers, optional, typed by the owner) | **No** (stays on device) | No | **Yes** | Yes | App functionality | Yes |
| Personal info: address (area or house number, optional, typed by the owner) | **No** (stays on device) | No | **Yes** | Yes | App functionality | Yes |
| Email, user IDs, other personal info | No | No | n/a | n/a | n/a | n/a |
| **Financial info: purchase history / other financial info** (the shop's orders, payments received, customer balances and expenses; no card, bank or UPI details) | **No** (stays on device) | No | **Yes** | Yes | App functionality | Yes |
| Health and fitness | No | No | n/a | n/a | n/a | n/a |
| Messages | No | No | n/a | n/a | n/a | n/a |
| Photos and videos | No | No | n/a | n/a | n/a | n/a |
| Audio | No | No | n/a | n/a | n/a | n/a |
| Files and docs | No (the backup file the user picks is read once, on device) | No | Yes | Yes | Restore backup | n/a |
| Calendar, contacts | No (phone contacts are never read) | No | n/a | n/a | n/a | n/a |
| App activity | No | No | Yes | n/a | n/a | Yes |
| Web browsing | No | No | n/a | n/a | n/a | n/a |
| App info and performance (crash logs, diagnostics) | No | No | n/a | n/a | n/a | n/a |
| Device or other IDs | No | No | n/a | n/a | n/a | n/a |

## Section 3: Facts to keep in step with the policy
- Network: none. VERIFY ON DEVICE: airplane-mode flow, and the merged manifest has no INTERNET, CAMERA or RECORD_AUDIO.
- Customer names, optional phone numbers, addresses and notes are stored on the device only. They are typed by the shop owner; the app does not read phone contacts.
- User-started outbound: order bill text, customer statement text, report summary text, CSV and backup JSON, all through the share sheet. Bills and statements contain the customer's name.
- Lock-screen notifications can show an order number and a customer's name, and the total dues (the policy says so).
- `allowBackup` is false: no Android cloud backup of the records.
- Privacy policy URL: https://sonythm.github.io/sonith-apps/iron-book/
