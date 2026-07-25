# Baden-Powell Scout Encyclopedia - Build Guide

## 🚀 Complete APK Build Instructions

### Prerequisites
Before building, ensure you have:
- ✅ Android Studio installed
- ✅ Android SDK (API Level 21 or higher)
- ✅ JDK 11 or higher
- ✅ Gradle installed (or use bundled gradlew)

---

## Step-by-Step Build Process

### **Step 1: Pull Latest Changes**
```bash
cd baden-powell-scout-encyclopedia
git pull origin main
```
This ensures you have all the latest files including:
- ✅ MainActivity.kt
- ✅ EncyclopediaActivity.kt
- ✅ encyclopedia.html
- ✅ All layout files
- ✅ GitHub Actions workflow

---

### **Step 2: Build Debug APK**
```bash
./gradlew assembleDebug
```

**What this does:**
- Compiles all Kotlin code
- Processes all resources (layouts, drawables, strings)
- Bundles the encyclopedia.html asset
- Creates a debug-signed APK (auto-signed for testing)
- No production signing key needed

**Build time:** ~2-5 minutes (first build may be longer)

---

### **Step 3: APK Output Location**
After successful build, your APK will be at:
```
app/build/outputs/apk/debug/app-debug.apk
```

**File size:** Usually 5-15 MB depending on dependencies

---

### **Step 4a: Install on Connected Device/Emulator**
```bash
./gradlew installDebug
```

**Prerequisites:**
- ✅ Device connected via USB with USB debugging enabled, OR
- ✅ Android Emulator running

**What happens:**
- APK is automatically installed on the device
- App appears in your app drawer
- Ready to test immediately

---

### **Step 4b: Install Manually**
If you don't have a device connected, you can install later:

```bash
# Using adb (Android Debug Bridge)
adb install app/build/outputs/apk/debug/app-debug.apk

# Or transfer the APK file manually to your device
```

---

## 📦 Full Build Workflow

```bash
# Complete workflow in one session
cd baden-powell-scout-encyclopedia
git pull origin main
./gradlew clean assembleDebug
./gradlew installDebug
```

---

## ✅ Verification Checklist

After building, verify:

- [ ] Build completed successfully (check console output)
- [ ] APK file exists at `app/build/outputs/apk/debug/app-debug.apk`
- [ ] APK size is reasonable (5-15 MB)
- [ ] No build errors in console
- [ ] App installs on device/emulator
- [ ] App launches without crashing
- [ ] Encyclopedia loads when you click the button
- [ ] Arabic text displays correctly

---

## 🐛 Troubleshooting

### **Build fails with "gradle not found"**
```bash
# Make gradlew executable (Linux/Mac)
chmod +x gradlew

# Then try building again
./gradlew assembleDebug
```

### **Build fails with Java version error**
```bash
# Check Java version
java -version

# Should be 11 or higher. If not, install JDK 11:
# https://www.oracle.com/java/technologies/downloads/#java11
```

### **APK not installing on device**
```bash
# Check if device is connected
adb devices

# Enable USB debugging on your Android device:
# Settings → Developer Options → USB Debugging
```

### **App crashes on startup**
- Check Android Studio Logcat for errors
- Ensure all files were pulled correctly with `git pull`
- Check that encyclopedia.html exists in assets folder

### **Encyclopedia doesn't load**
- Verify `app/src/main/assets/encyclopedia.html` exists
- Check that EncyclopediaActivity is registered in AndroidManifest.xml
- Check Logcat for WebView errors

---

## 📊 Build Output Information

When you run `./gradlew assembleDebug`, you'll see output like:

```
> Task :app:compileDebugKotlin
> Task :app:mergeDebugResources
> Task :app:processDebugResources
> Task :app:assembleDebug

BUILD SUCCESSFUL in 2m 30s
```

**Key files created:**
```
app/build/
├── intermediates/          # Intermediate build files
├── outputs/apk/
│   └── debug/
│       ├── app-debug.apk  ← YOUR APK!
│       └── output.json
└── tmp/
```

---

## 🎯 Testing Your App

### **Test on Emulator:**
1. Open Android Studio
2. Open AVD Manager (Tools → Device Manager)
3. Start an emulator
4. Run `./gradlew installDebug`
5. App will install and launch automatically

### **Test on Physical Device:**
1. Connect Android device via USB
2. Enable USB Debugging (Settings → Developer Options)
3. Run `./gradlew installDebug`
4. Grant permissions when prompted
5. App will install on your device

---

## 📱 First Launch Checklist

When you first launch the app:

- [ ] **Home Screen Loads** - See the main buttons
- [ ] **Encyclopedia Button Works** - Opens encyclopedia HTML
- [ ] **Arabic Text Displays** - Text appears right-to-left
- [ ] **Content Scrolls** - Can scroll through all 5 sections
- [ ] **Back Button Works** - Returns to main activity
- [ ] **No Crashes** - App runs smoothly

---

## 🔄 Automated Building with GitHub Actions

The APK is also built automatically with each push:

1. Push code to GitHub
2. GitHub Actions runs the build workflow
3. APK artifact is uploaded
4. Download from Actions tab

**To download from GitHub Actions:**
1. Go to https://github.com/remonn567/baden-powell-scout-encyclopedia/actions
2. Click latest workflow run
3. Scroll to "Artifacts"
4. Download `debug-apk`

---

## 📝 Build Variants

### **Debug APK (Testing)**
```bash
./gradlew assembleDebug
# Output: app-debug.apk
# Purpose: Development and testing
# Signing: Auto-signed
# Size: Smaller, contains debug symbols
```

### **Release APK (Production)**
```bash
./gradlew assembleRelease
# Output: app-release-unsigned.apk
# Purpose: Distribution to Google Play Store
# Signing: Requires signing key
# Size: Larger, optimized
```

---

## 🎉 Next Steps After Building

1. **Test the app** on your device/emulator
2. **Add more features** (search, database, etc.)
3. **Optimize for release** (obfuscation, signing)
4. **Publish to Google Play Store** (requires signing key)
5. **Collect user feedback** and iterate

---

## 📞 Quick Reference

| Task | Command |
|------|---------|
| Build Debug APK | `./gradlew assembleDebug` |
| Install on Device | `./gradlew installDebug` |
| Clean Build | `./gradlew clean assembleDebug` |
| Build Release | `./gradlew assembleRelease` |
| Check Devices | `adb devices` |
| View Logs | `adb logcat` |
| Uninstall App | `adb uninstall com.remonnady.scoutencyclopedia` |

---

## ✨ Success!

Once your APK is built and installed:

✅ You have a fully functional Android app
✅ With complete Arabic Scout Encyclopedia
✅ Offline access to all content
✅ Material Design UI
✅ RTL support for Arabic

**Happy building! 🚀**

---

**Version:** 1.0
**Last Updated:** 2026-07-25
**Repository:** https://github.com/remonn567/baden-powell-scout-encyclopedia
