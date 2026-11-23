# Installation Guide — MyMoney (លុយខ្ញុំ)

This guide walks you through downloading, verifying, and installing the official **MyMoney** Android APK on your mobile device.

---

## ⚠️ Important Security Notice

- **Official Source Only:** Only download and install APK packages directly from the official MyMoney Releases repository:  
  **`https://github.com/nheanvitou02/mymoney-releases/releases`**
- **Never Download from Unknown Third Parties:** Never install MyMoney from unofficial websites, messaging groups, or unverified file-sharing mirrors.
- **Selective Permissions Only:** Do **NOT** disable Android device security protections globally. Only grant installation permission specifically to the browser or file manager you use to download this release.

---

## 📥 Step-by-Step Installation Instructions

### Step 1: Download the Official APK
1. Open your Android device browser (e.g. Chrome, Firefox, Brave) and navigate to:  
   **[https://github.com/nheanvitou02/mymoney-releases/releases/latest](https://github.com/nheanvitou02/mymoney-releases/releases/latest)**
2. Under the **Assets** section, tap **`mymoney-v1.0.1.apk`** to begin downloading.

### Step 2: Open the Downloaded APK
Once the download is complete:
- Tap the **Download complete** notification in your Android notification drawer, or
- Open your device's **Files** or **Downloads** app and tap **`mymoney-v1.0.1.apk`**.

### Step 3: Allow Installation from this Source (If Prompted)
Because MyMoney is distributed as an independent APK outside the Google Play Store, Android will display a standard security notice:
> *"For your security, your phone is not allowed to install unknown apps from this source."*

1. Tap **Settings** on the prompt dialog.
2. Toggle on **"Allow from this source"** for your specific browser or file manager.
3. Tap the **Back** arrow to return to the installer.

### Step 4: Confirm Installation
1. A dialog will appear asking: *"Do you want to install this app?"*
2. Tap **Install**.
3. Android package manager will verify and install MyMoney.

### Step 5: Open MyMoney
1. Once installation finishes, tap **Open**, or find the **MyMoney** icon in your app drawer.
2. You will be greeted by the 5-step Getting Started guide. Enjoy 100% offline personal finance tracking!

---

## 🔍 How to Verify the APK Checksum (SHA-256)

To guarantee that your downloaded file is authentic, uncorrupted, and unaltered, you can verify its SHA-256 checksum.

### Official SHA-256 Checksum for v1.0.1
```text
1e45b22ab80ac2683e07b68f6ace250684e8bada764325d269aa369885a62a37
```

### Verification on Linux / macOS
Open a terminal in your download folder and run:
```bash
sha256sum mymoney-v1.0.1.apk
```
*(On macOS, use `shasum -a 256 mymoney-v1.0.1.apk`)*

The output must match the official checksum above exactly.

### Verification on Windows (PowerShell)
```powershell
Get-FileHash .\mymoney-v1.0.0.apk -Algorithm SHA256
```

### Verification on Android
You can verify the hash on your Android device using terminal apps like [Termux](https://termux.dev/) or free hash verification tools from F-Droid:
```bash
sha256sum /sdcard/Download/mymoney-v1.0.0.apk
```

---

## ❓ Frequently Asked Questions

### Why does Android warn me that this app is "unknown"?
Android classifies any application installed outside Google Play as an "unknown app". This is standard operating system behavior designed to ensure user awareness. MyMoney is signed with an official cryptographic release key and requests **zero dangerous runtime permissions**.

### Will updating the app erase my financial data?
No. When subsequent updates (`v1.0.1`, `v1.1.0`) are released, simply download and install the new APK over the existing installation. Android will update the application binary while preserving all your local SQLite financial records (`mymoney.db`). We also recommend periodically exporting a JSON backup from **Settings > Data Backup** for safekeeping.
