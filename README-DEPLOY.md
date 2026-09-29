# FirstTen web demo deployment

This folder is a separate, clean deployment copy of FirstTen. It contains no local SQLite database, Android APK, API key, Brevo/SMTP credential, or personal outreach data.

## Publish a browser demo

1. Create a new **private GitHub repository** for this preview.
2. Upload these four files from this folder into the repository root: `app.py`, `index.html`, `requirements.txt`, and `render.yaml`. Upload `.gitignore` too if the GitHub page lets you add hidden files.
3. In Render, choose **New → Blueprint**, connect the repository, review the `firstten-hackathon-demo` service, and create it on the **Free** plan.
4. Wait for the first deploy to finish, then open the `onrender.com` URL Render shows. Try the **Try the demo with sample data** button.
5. Open that URL in a private/incognito browser window to confirm judges can reach it without your account. Paste the public `https://...onrender.com` URL into Devpost's **Try it out** links field.

Render supports Python web services and gives each one a public `onrender.com` URL. Its free services sleep after inactivity and have temporary local storage, so the demo database can reset after a restart or redeploy. FirstTen is configured to use fictional guest workspaces and to avoid including your existing local database. See [Render's free-instance limits](https://render.com/docs/free) and [web-service guide](https://render.com/docs/web-services).

## What this public preview does

- Opens a separate guest workspace for each visitor, with clearly fictional starter records. Visitors do not need to supply an email or create a password.
- Uses a temporary SQLite database. Do not enter real customer information or rely on this service to keep data.
- Disables account registration, password reset, and SMTP settings for the public preview.
- Does not include a shared OpenAI key. AI tools require a visitor to connect their own key; the app warns that inputs go to OpenAI, the key passes through this server, and API usage may cost money. Leave AI disconnected if you do not want to use a key.
- Disables background market scans so a public demo cannot trigger unattended AI usage.

This is a time-limited hackathon preview, not a production customer service. It has no managed persistent database, email verification, administrator controls, or production abuse monitoring. Don't put this public URL on a real customer onboarding flow.