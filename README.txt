MFILM MOBILE APP (v64) – install MFilm on Android / iPhone like a normal app
==========================================================================
What it is: a small app "shell" (this folder). It opens your MFilm Apps Script pages full-screen with a
bottom bar (Entry / Dashboard / Printers / Admin), no Google banner, its own icon, and it remembers who
uses the phone (Engineer, Technician, Supervisor, Admin, Director) so it opens straight on their sign-in.
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
  First start: choose who uses the phone → sign in with the normal MFilm name + password.
  Change later: bottom bar "⋯ More" → Change who uses this phone. Tap an open tab again to refresh it.

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
