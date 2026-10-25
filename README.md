# HRM Leave Management

A browser-based HRM leave management prototype with calendar, employee records, leave applications, leave-type colours, reports, English/Malay interface, and Admin / Editor / Viewer roles.

## Run locally

Open `index.html` in a modern browser.

## Publish with GitHub Pages

1. Sign in to GitHub and create a new repository, for example `hrm-leave-management`.
2. Upload `index.html` and this `README.md` to the repository root.
3. Open the repository's **Settings → Pages**.
4. Under **Build and deployment**, select **Deploy from a branch**.
5. Select the `main` branch and `/ (root)` folder, then click **Save**.
6. Wait for the deployment to finish. GitHub will show the published website URL in **Settings → Pages**.

## Important limitations

- This is a static, browser-based prototype. Data is saved in the browser's local storage, so it is not automatically shared between users or devices.
- User accounts and passwords are handled client-side. This is **not secure authentication** and should not be used for sensitive or production HR data.
- Do not publish real employee personal data, IC numbers, medical details, or leave records in the repository.
- Use the system's export/backup feature regularly and store backups securely.
- If you need a real multi-user HR system, use a backend with proper authentication, access controls, encrypted storage, and backups.

## Updating the site

Replace `index.html` with the newer version, commit the change, and push it to the `main` branch. GitHub Pages will redeploy the site.
