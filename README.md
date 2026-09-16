# Sugar diary – your own app (no Claude needed)

This folder is the complete app. Once it is on a free website link, it:
- installs on the phone like an app (own icon, opens full screen),
- works **without internet** after the first open,
- keeps all readings **only on that phone** (nothing is sent anywhere),
- downloads Excel/PDF reports and can **share the PDF** (WhatsApp, email).

## What is in the folder
| File | What it does (plain words) |
|---|---|
| `index.html` | The app itself |
| `sw.js` | The "offline helper": saves a copy of the app on the phone so it opens without internet |
| `manifest.webmanifest` | The "app card": name, icon and colours used when installing |
| `icons/` | The app icon |
| `lib/` | The Excel and PDF makers, stored locally so reports work offline |

## Put it online for free (GitHub Pages) – one time, about 10 minutes, on a computer
1. Go to github.com and create a free account.
2. Click **+** (top right) → **New repository**. Name: `sugar-diary`. Choose **Public**. Click **Create repository**.
   (Public means the app's code is visible. Her readings are never in this code – they stay on her phone.)
3. On the new page click **uploading an existing file**. Drag in **everything inside** this folder
   (`index.html`, `sw.js`, `manifest.webmanifest`, and the `icons` and `lib` folders). Click **Commit changes**.
4. Click **Settings** → **Pages** (left menu). Under "Branch" choose **main** and **/(root)** → **Save**.
5. Wait 1–2 minutes. Your link will be: `https://YOUR-USERNAME.github.io/sugar-diary/`

## Install on her phone
1. Open the link in **Chrome** (with internet, the first time only).
2. Tap the **Install app** button at the top, or Chrome menu **⋮ → Install app / Add to Home screen**.
3. From now on open it from the icon. It works offline.

## Moving her existing readings from the Claude version
The two versions do not share storage. In the old (Claude) version: **Diary → Settings → Backup and restore → Save backup now**.
In the new app: **Diary → Settings → Backup and restore → Restore from backup** and pick that file.

## Keeping data safe
- The app asks the phone to keep its data permanently, but clearing Chrome's data or uninstalling Chrome still erases it.
- Tap **Save backup** when asked each day. The file goes to Downloads.

## Updating the app later
1. Upload the new `index.html` to the same GitHub repository (it replaces the old one).
2. Open `sw.js`, change `sugar-diary-v1` to `sugar-diary-v2` (then v3, and so on), upload it too.
3. On the phone, open the app once with internet, close it, and open it again.

## Test on a computer before uploading (optional)
In a plain command window, inside this folder: `python -m http.server 8000`, then open http://localhost:8000
