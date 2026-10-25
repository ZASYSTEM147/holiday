# HRM Leave Management — new Firebase project

This package is configured for Firebase project `holiday-15b66` and Cloud Firestore. It saves records when users save changes; it does not use Realtime Database for HRM records.

## Firebase setup
1. In Firebase Console, open project `holiday-15b66`.
2. Authentication → Sign-in method → enable Google. Add `zasystem147.github.io` under Authentication Settings → Authorized domains.
3. Build → Firestore Database → create the database if needed.
4. Firestore Database → Rules: publish the included `firestore.rules`.
5. Authentication → Users: sign in to the HRM once with the Gmail account intended to be Admin, then copy its exact UID.
6. Firestore → Data: create collection `access`, with a document ID equal to that exact Firebase Auth UID. Add fields:
   - `active` (Boolean): `true`
   - `email` (String): your Gmail address
   - `name` (String): `HRM Administrator`
   - `role` (String): `Admin`
7. Replace `index.html` in the GitHub repository with this package's `index.html` and commit. GitHub Pages should then serve the new version.

## Data location
The app stores the main HRM data at `appData/main`; approved roles at `access/{uid}`; and first-time access requests at `accessRequests/{uid}`.

## Important
- This package does not migrate old data from the previous Firebase project. Export/backup old records before switching and transfer them separately if needed.
- Do not publish permissive rules. The included rules expect users to have an active `access/{uid}` role record.
- Test with sample data first. I cannot publish to your Firebase or GitHub account from this package.
