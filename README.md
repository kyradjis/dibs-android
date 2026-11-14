# Dibs (Android app)

Your discount cards and where to use them. Everything is stored on the phone, works offline
(except map tiles and place search), and location is only read while the app is open.

## Get the APK without installing anything (GitHub Actions)

1. Create a new **private** repo on github.com (e.g. `dibs`).
2. Upload the contents of this folder to it (drag and drop in the web page works; keep the
   `.github` folder, it is the build recipe).
3. Open the repo's **Actions** tab. The "Build Android APK" run starts by itself (or press
   *Run workflow*). It takes about 5 minutes.
4. Open the finished run, scroll to **Artifacts**, download **Dibs-apk**, unzip it.
5. Send `app-debug.apk` to your phone (Drive, email, USB) and tap it. Samsung will ask to allow
   "Install unknown apps" for the app you opened it from. Allow it once.

## Or build it yourself with Android Studio

1. Install Node 20+ and Android Studio.
2. In this folder run `npm install`, then `npx cap sync android`.
3. `npx cap open android`, wait for Gradle to finish, then **Build > Build APK(s)**.

## Changing the app

The app lives in `www/` (index.html, style.css, app.js). After any change run `npx cap sync android`
and rebuild. With GitHub Actions, just upload the changed files and download the new APK.
Update the app on your phone by installing the new APK over the old one: your data is kept.
