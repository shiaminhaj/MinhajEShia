# Minhaj e Shia — Public Assets

Public static assets for the **Minhaj e Shia** app (`com.minhajeshia`).
Served via GitHub Pages at `https://shiaminhaj.github.io/MinhajEShia/`.

---

## Azan Audio

MP3 files for downloadable azan reciters. Drop files here and push — the app
fetches them via raw GitHub URLs.

| File | Reciter |
|------|---------|
| `azan/halawachi.mp3` | Abather Alhalwachi |
| `azan/javed-raza.mp3` | Javed Raza Zaidi |
| `azan/rezaeeian.mp3` | Hasan Rezaeeian |

Raw URL pattern:
```
https://raw.githubusercontent.com/shiaminhaj/MinhajEShia/main/azan/<filename>.mp3
```

---

## Deep Links

### Android App Links

`/.well-known/assetlinks.json` enables Android App Links for `https://shiaminhaj.github.io/open` paths.

**⚠️ Important:** Android App Link verification fetches `assetlinks.json` from the
**root** of the host domain (`https://shiaminhaj.github.io/.well-known/assetlinks.json`),
not from the project subdirectory. To make App Links work:

**Option A (recommended):** Create a separate `shiaminhaj.github.io` repo (user GitHub Pages)
and place `.well-known/assetlinks.json` there. It will be served at the root.

**Option B:** Use a custom domain (e.g. `app.minhajeshia.com`) pointed at this GitHub Pages
repo, then update `android:host` in `AndroidManifest.xml` to match.

Before going live, replace the placeholder SHA-256 fingerprint in `assetlinks.json`:
```bash
keytool -list -v -keystore your-release.jks -alias your-key-alias
```

### iOS Universal Links

`/.well-known/apple-app-site-association` enables iOS Universal Links.
Replace `TEAMID` with your Apple Developer Team ID from developer.apple.com.

Add the associated domain to `ios/Runner/Runner.entitlements`:
```xml
<key>com.apple.developer.associated-domains</key>
<array>
  <string>applinks:shiaminhaj.github.io</string>
</array>
```

---

## Contact

shiaminhaj@gmail.com
