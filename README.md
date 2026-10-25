# Holiday – HRM Leave Management (GitHub Pages + Firebase)

Live site: https://zasystem147.github.io/holiday/
Data is stored in Firebase (project "holiday"). Never commit CSV/backups of staff data to this repo.

## One-time Firebase setup (console.firebase.google.com → project "holiday")

1. **Web app config**: Project settings → General → Your apps → `</>` (Web) → copy the config into `firebase-config.js`.
2. **Authentication** → Get started → Sign-in method → enable **Email/Password**.
   Leave "Enable create (sign-up)" ON – the in-app *User management* tab uses it to create logins.
   Access is still controlled by the `access` list below, so a stranger who registers cannot open any data.
3. **Firestore Database** → Create database (production mode, e.g. asia-southeast1).
4. **Firestore → Rules** → paste `firestore.rules` → Publish.
5. **Create the first admin by hand** (after this, manage users inside the app):
   - Authentication → Users → Add user (your email + password).
   - Firestore → Start collection `access` → Document ID = your email in lowercase →
     fields: `role` (string) = `Admin`, `name` (string) = your name.
6. Commit all files to the `holiday` GitHub repo (index.html, firebase-config.js, .nojekyll, README.md).

## Roles
- **Admin** – everything, plus User management and Leave types.
- **Editor** – add/edit/delete employees and leave.
- **Viewer** – view only.

## First run
Sign in as the admin → the app creates `holiday/main`. Use **Import** to restore your backup/CSV
(data already saved in that browser by the old version is uploaded automatically on the first admin login).
Old in-browser user accounts are not migrated – re-create them in *User management*.

## Notes
- All leave data is one Firestore document (`holiday/main`, 1 MB limit ≈ several thousand records).
- Two people saving at the same moment: last save wins; other open screens update automatically.
- Removing a user in the app removes their access; their login remains under Authentication (delete it there if needed).
