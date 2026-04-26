# 🛕 Amman Temple Management — Android App

Converts the Temple Management System HTML into an Android APK using **Capacitor** and **GitHub Actions**.  
No Android Studio or local SDK needed — GitHub builds the APK for you automatically.

---

## 📁 Folder Structure

```
temple-apk/
├── .github/
│   └── workflows/
│       └── build-apk.yml     ← GitHub Actions build pipeline
├── www/
│   └── index.html            ← Temple HTML app (replace with latest version)
├── android-res/
│   └── ic_launcher.png       ← (Optional) Your custom app icon — 512×512 PNG
├── capacitor.config.json     ← App ID, name, and settings
├── package.json              ← Capacitor dependencies
└── README.md
```

---

## 🚀 Step-by-Step: First Time Setup

### Step 1 — Create a GitHub Account
Go to [github.com](https://github.com) and sign up (free).

### Step 2 — Create a New Repository
1. Click **+** → **New repository**
2. Name it: `temple-app` (or anything you like)
3. Set it to **Private** (recommended — your data configs are here)
4. Click **Create repository**

### Step 3 — Upload These Files
Click **uploading an existing file** and drag-and-drop the entire contents of this folder:
- `.github/` folder (with workflows inside)
- `www/` folder (with `index.html` inside)
- `android-res/` folder
- `capacitor.config.json`
- `package.json`
- `README.md`

Click **Commit changes**.

### Step 4 — Watch the Build
1. Go to the **Actions** tab in your repository
2. You will see **"Build Android APK"** running automatically
3. Wait 5–8 minutes for it to complete (green ✅)

### Step 5 — Download the APK
1. Click the completed workflow run
2. Scroll down to **Artifacts**
3. Click **AmmanTemple-APK-build-1** to download a `.zip`
4. Extract the zip — inside is `AmmanTemple-v1.apk`

### Step 6 — Install on Android Phone
1. Transfer the APK to your phone (WhatsApp, USB, Google Drive, etc.)
2. On your phone: **Settings → Security → Install Unknown Apps → Allow**
3. Open the APK file and tap **Install**

---

## 🔄 Updating the App

Whenever you get a new version of `temple_v*.html`:
1. Rename it to `index.html`
2. Go to your GitHub repo → `www/` folder
3. Click `index.html` → pencil icon (Edit) → paste contents OR use **Upload file**
4. Commit — the build starts automatically
5. Download the new APK from Actions → Artifacts

---

## 🎨 Custom App Icon (Optional)

To give the app a temple icon instead of the default Capacitor logo:
1. Create a **512×512 PNG** image of your temple icon
2. Name it `ic_launcher.png`
3. Place it in the `android-res/` folder in your GitHub repo
4. The next build will use your icon automatically

---

## ⚙️ Changing App Name or ID

Edit `capacitor.config.json`:
```json
{
  "appId": "com.ammantemple.management",   ← unique ID (don't change after install)
  "appName": "Amman Temple",               ← name shown on phone home screen
  ...
}
```
Commit the change and a new APK will be built.

---

## 📱 App Features on Android

- ✅ Works **offline** — all data stored on the device
- ✅ **Full screen** — no browser address bar
- ✅ Syncs with Google Sheets when internet is available
- ✅ localStorage persists between app restarts
- ✅ Back button supported
- ✅ Can be added to home screen like a native app

---

## ❓ Troubleshooting

| Problem | Solution |
|---|---|
| Build fails with "SDK not found" | Re-run the workflow from Actions → Run workflow |
| APK won't install | Enable "Install unknown apps" in Android Settings |
| App shows blank screen | Check that `www/index.html` exists in the repo |
| Data lost after update | Data is in localStorage — it persists across APK updates as long as you don't uninstall |
| Can't find the Actions tab | Make sure you uploaded the `.github/workflows/build-apk.yml` file correctly |
