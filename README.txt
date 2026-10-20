WAYFOLD - make it a real phone app

OPTION A: Installable app (easiest, free, ~5 minutes)
1. Upload this whole folder to any free HTTPS host (Netlify Drop: app.netlify.com/drop, or GitHub Pages / Cloudflare Pages).
2. Open the link in Chrome on your Android phone -> menu (3 dots) -> "Install app".
   (iPhone: Safari -> Share -> Add to Home Screen)
3. It now has its own icon, opens full screen, works offline.
   Share the link on WhatsApp so others can install it the same way.

OPTION B: Real APK file (to share on WhatsApp or upload to Google Play)
1. Do Option A first so you have your https link.
2. Go to pwabuilder.com, paste your link, click Start -> Package for stores -> Android.
3. Download the zip. It contains a signed .apk (install/share directly) and a .aab (upload to Google Play).
   Keep the signing key file safe - you need it for every future update.

OPTION C: Build it yourself with Capacitor (needs Android Studio)
  npm init -y
  npm i @capacitor/core @capacitor/cli @capacitor/android
  npx cap init Wayfold com.yourname.wayfold --web-dir=www
  mkdir www && cp -r index.html manifest.json sw.js icons www/
  npx cap add android && npx cap sync
  npx cap open android      (then Build > Build APK in Android Studio)
