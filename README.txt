MFILM MOBILE APP (app v121 – for MFilm web app v121-Nov) – install MFilm on Android / iPhone like a normal app
==========================================================================
What it is: a small app "shell" (this folder). It opens your MFilm Apps Script pages full-screen with a
bottom bar (Entry / Dashboard / Master data / Settings), no Google banner and its own icon. Everybody signs in
on the ONE MFilm sign-in page; the app then shows the tiles and tabs of that person's role by itself.
All data stays live in your Google Sheet – nothing is stored in the app.

STEP 1 – check the web app link (1 minute)
  Open index.html in Notepad. Near the top: const APP = '...../exec'
  It already holds your current link. If you ever make a NEW deployment, paste the new /exec link here.
  Apps Script → Deploy → Manage deployments → "Who has access" must be "Anyone" (MFilm has its own logins).

STEP 2 – put the folder online (free, once) – GitHub Pages
  1. github.com → sign in → New repository → name: mfilm-app → Public → Create.
  2. "uploading an existing file" → drag EVERYTHING inside this folder (index.html, manifest.webmanifest,
     sw.js and the icons folder) → Commit changes.
  3. Settings → Pages → Branch: main, folder / (root) → Save. After ~1 minute you get a link like
     https://<your-name>.github.io/mfilm-app/   ← this is the app link to send to your team.
  (Netlify Drop – app.netlify.com/drop – also works: drag the folder, you get a link at once.)

STEP 2b – allow the app address in MFilm (v69 security)
  MFilm now refuses to open inside any other website. Tell it your app address once:
  Admin → Settings (Super Admin) → Roles → "Phone app address" → https://<your-name>.github.io → Save.
  (Only the address, no /mfilm-app path.) Without this the app shows "MFilm cannot open here".

STEP 3 – install on each phone
  Android (Chrome): open the app link → menu ⋮ → "Install app" / "Add to Home screen".
  iPhone (Safari):  open the app link → Share ⬆ → "Add to Home Screen".
  First start: sign in with the normal MFilm username (full name, mobile or e-mail) + password.
  Another person on the same phone: Profile → Sign out / switch user. Tap an open tab again to refresh it.

OPTIONAL – a real Android .apk / Play Store app
  pwabuilder.com → paste your app link from step 2 → Package for stores → Android → Download.
  You get an .apk to share with engineers (or an .aab for the Play Store).

Notes
  - Updates to MFilm itself (new Apps Script version) reach every phone at once – no app update needed.
  - Engineers on slow mobile data: the app opens only the page they tap (no background loading).
  - Offline: the app still opens and shows "You are offline"; readings can be entered when back online.

NEW IN APP v64 – NEW HOME SCREEN
  - App Home with greeting, date, role and online status.
  - One big button for the main job (Engineer: New reading) + Quick action tiles:
    My entries · My printers · Add printer · Remote PCs · Dashboard (per role).
    Tiles open the right tab inside MFilm directly. Tiles not switched on for the person are greyed.
  - Modern bottom bar (Home · Entry · Dashboard · More), light + dark mode, splash screen.
  - Security: the app only listens to Google's Apps Script pages it opened itself; the pages only tell
    the app on/off switches (never names or data).
  UPDATE: replace index.html and sw.js on GitHub (Add file → Upload files → Commit). Phones pick it up
  on the next start.

WHAT'S NEW IN APP v121 (matches MFilm web app v121-Nov)
  - Works with the single sign-in of MFilm v120+: every tab now opens the real MFilm page
    (Entry, Dashboard, Master data). Older app versions opened the sign-in page in every tab.
  - New "Summary" tile (month view + month-end checklist) for Admin, Director and Supervisor.
  - Director: "Master data" (view) instead of the old Director page; no Administration.
  - Forgot password, Continue as <name>, Caps Lock warning – all from the MFilm sign-in page.
  - Phones pick up the new app by themselves the next time it is opened online.

UPDATE THE APP ON GITHUB (2 minutes)
  github.com → your app repository → "Add file" → "Upload files" → drag index.html and sw.js from this
  folder (replace the old ones) → Commit changes. After ~1 minute every phone gets app v121.
