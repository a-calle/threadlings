# Threadlings (Android)

Capacitor wrapper around the web game in `www/index.html`.

1. Edit `capacitor.config.json` and set `appId` (e.g. `com.educacc.threadlings`) BEFORE the first Play upload. It can't change after publishing.
2. Push to GitHub. The "Build Android AAB" workflow produces `threadlings-aab` under the Actions tab.
3. Signing: add repo secrets KEYSTORE_BASE64, KEYSTORE_PASSWORD, KEY_ALIAS (see below). Keep the keystore file safe: losing it means you can't update the app (or use Play App Signing and keep an upload key).
   keytool -genkey -v -keystore release.keystore -alias threadlings -keyalg RSA -keysize 2048 -validity 10000
   base64 -w0 release.keystore   # paste as KEYSTORE_BASE64
