# Logbook — standalone Android app (PWA)

This folder is a self-contained web app. To use it on your phone as an
installed, app-icon experience, it needs to be served over **https**. The
fastest free way: GitHub Pages, or drag-and-drop onto
https://app.netlify.com/drop.

## Setting up your free AI key (no credit card)

This app uses **Google Gemini's free API tier** for the calorie estimator,
exercise calorie-burn estimates, and workout plan generator — no billing,
no credit card required.

1. Go to **aistudio.google.com** and sign in with any Google account.
2. Click **Get API key** (top left or in the menu) -> **Create API key**.
3. Copy the key -- it starts with `AIza...`.
4. Open the installed app -> Settings tab (05) -> paste the key -> Save key.

The key is stored only in this browser's local storage on your phone -- it's
never sent anywhere except directly to Google's Gemini API when you use the
calorie estimator or workout plan generator. Because it lives in this page's
storage, don't share your hosted link with anyone else while your key is
saved, and don't commit a key into a public GitHub repo.

Google's free tier has daily/per-minute request limits (generous for
personal use -- roughly a few hundred requests a day). If you ever hit a
limit, the app will show an error and you can just try again shortly after.

## What works offline
Your logged weights, exercises, meals, and any saved plan are stored on your
device and open instantly, even offline. The AI features (calorie
estimation, calorie-burn estimates, workout plan generation) need an internet
connection, since they call Google's API directly from your phone.

## Notes
- All data lives in this browser only. Use the Export all data button in
  Settings to back it up, since clearing Chrome's site data (or uninstalling)
  will erase it.
- If Google changes free-tier terms or limits in the future, check
  ai.google.dev/pricing for the current policy.
