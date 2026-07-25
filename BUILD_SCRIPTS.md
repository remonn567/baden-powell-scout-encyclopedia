# Quick Build Scripts

## 🚀 Easy One-Command Build

Instead of running multiple commands, use the quick-build scripts:

### **On Linux/Mac:**
```bash
chmod +x build.sh
./build.sh
```

### **On Windows:**
```cmd
build.bat
```

## What These Scripts Do

✅ Pull latest changes from GitHub
✅ Clean previous builds  
✅ Build debug APK
✅ Check for connected devices
✅ Automatically install on device (if connected)
✅ Display APK location and size
✅ Show helpful next steps

## Output Example

```
================================
🚀 Scout Encyclopedia Build Tool
================================

✓ In project directory

Step 1: Pulling latest changes from GitHub...
✓ Latest changes pulled

Step 2: Cleaning previous builds...
✓ Clean complete

Step 3: Building debug APK...
This may take 2-5 minutes...
✓ APK built successfully!

✓ APK created: app/build/outputs/apk/debug/app-debug.apk
  Size: 12.5M

Step 4: Checking for connected devices...
✓ Device(s) detected

Step 5: Installing APK...
✓ APK installed successfully!

🎉 Your app is ready!
Look for '⚜️ الموسوعة الكشفية' in your app drawer

================================
✓ Build Complete!
================================

APK Location:
  app/build/outputs/apk/debug/app-debug.apk

To uninstall: adb uninstall com.remonnady.scoutencyclopedia
To view logs: adb logcat
```

## Manual Commands (If Scripts Don't Work)

```bash
# Navigate to project
cd baden-powell-scout-encyclopedia

# Pull latest
git pull origin main

# Clean build
./gradlew clean

# Build APK
./gradlew assembleDebug

# Install on device
./gradlew installDebug
```

## Troubleshooting Scripts

### **Permission Denied (Linux/Mac)**
```bash
chmod +x build.sh
```

### **Windows Script Won't Run**
- Open Command Prompt as Administrator
- Navigate to project directory
- Run: `build.bat`

### **adb Not Found**
- Ensure Android SDK is installed
- Add Android SDK to PATH
- Restart terminal/command prompt

---

**Use the scripts for fast, automated building!** 🚀
