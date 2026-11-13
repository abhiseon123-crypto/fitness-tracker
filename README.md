# Logbook — standalone Android app (PWA)

This folder is a self-contained web app. To use it on your phone as an
installed, app-icon experience, it needs to be served over **https** (Chrome
won't offer the "Install app" / add-to-home-screen prompt with full offline
support for a `file://` page). The fastest free ways to do that:

## Option A — Netlify Drop (no account needed)
1. Go to https://app.netlify.com/drop on your computer.
2. Drag this whole folder onto the page.
3. You'll get a URL like `https://random-name-123.netlify.app`.
4. Open that URL on your Android phone in Chrome.
5. Tap the Chrome menu (⋮) → **Install app** (or you'll see an automatic
   install banner). It installs to your home screen with its own icon and
   opens full-screen, no browser address bar.

## Option B — GitHub Pages
1. Create a new GitHub repo and upload these files (`index.html`,
   `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png`).
2. In the repo Settings → Pages, set the source to the main branch.
3. Visit the published `https://<you>.github.io/<repo>/` URL on your phone
   and install it the same way as above.

## Setting up your API key
1. Open the installed app.
2. Go to the **Profile** tab.
3. Paste a free Google Gemini API key from https://aistudio.google.com
   (Get API key → Create API key).
4. Tap **Save key**.

The key is stored only in this browser's local storage on your phone — it's
never sent anywhere except directly to Google's Gemini API when you use the
calorie estimator or workout plan generator. Because it lives in this page's
storage, don't share your hosted link with anyone else while your key is
saved, and don't commit a key into a public GitHub repo.

## What works offline
Your logged weights, steps, exercises, meals, and any saved plan are stored on your
device and open instantly, even offline. The AI features (calorie
estimation, calorie-burn estimates, workout plan generation) need an internet
connection, since they call Google's Gemini API directly from your phone.

## Notes
- All data lives in this browser only. Use the **Export all data** button in
  Profile to back it up, since clearing Chrome's site data (or uninstalling)
  will erase it.
- API usage runs under your own Gemini key — check https://aistudio.google.com
  for current limits and usage.
- The app follows your phone's light/dark setting; you can override it under
  **Profile → Appearance**.
