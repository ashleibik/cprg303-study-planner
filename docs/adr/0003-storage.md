# ADR 3 — Database Storage

## Status
Accepted

## Context
The app saves tasks, due dates, completion status, course tags, and reminders between sessions. The data is structured (multiple fields per task, queried by date for the calendar) and personal (assignment names, courses, study habits — a student might share or lose their phone).

Three options were considered:
- **Local unencrypted** (AsyncStorage or plain SQLite): easiest, but readable to anyone with file access.
- **Local encrypted** (SQLite + SQLCipher, key in iOS Keychain / Android Keystore): protects on-device data.
- **Remote** (Firebase, Supabase): enables sync but needs accounts, login, and a backend — out of scope for this phase.

## Decision
Use Expo SQLite with the database encrypted using SQLCipher. The encryption key is generated on first launch and saved in Expo SecureStore (iOS Keychain / Android Keystore under the hood). All data stays on the device.

## Consequences

**Easier:**
- No backend, no accounts, no login flow.
- Personal data is protected if the phone is lost or shared.
- SQLite handles the date-range queries the calendar view needs.
- App works fully offline.

**More difficult:**
- Each phone has its own database; installing on a second device starts from empty.
- Uninstalling the app deletes the database and the key — no recovery.
- Slightly more setup than plain SQLite (generate, save, and load the key).
- SQLCipher adds a tiny CPU cost per query, but unnoticeable at our data sizes.
