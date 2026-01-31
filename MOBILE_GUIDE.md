# 📱 MOBILE-ONLY GUIDE: Get Your APK in 30 Minutes

**No computer needed! Just your phone's browser.**

## 🎯 What You'll Do

1. Upload project to GitHub (15 min)
2. Let GitHub build APK automatically (10 min)
3. Download and install APK (5 min)

**100% FREE - Works on any phone with internet**

---

## 📋 STEP-BY-STEP INSTRUCTIONS

### STEP 1: Create GitHub Account (5 minutes)

Using your phone's browser:

1. **Go to:** https://github.com/signup
2. **Enter:**
   - Your email
   - Create password
   - Choose username
3. **Verify** your email
4. **Done!** You now have a GitHub account

---

### STEP 2: Create Repository (2 minutes)

1. **Go to:** https://github.com/new
   
2. **Fill in:**
   - Repository name: `InstaDownloader`
   - Description: `Instagram media downloader app`
   - ✅ Keep it **Public** (required for free builds)
   - ❌ **DON'T** check "Add README"

3. **Click:** "Create repository"

4. **You'll see:** Empty repository page

---

### STEP 3: Upload Project Files (5 minutes)

**Important:** Extract the ZIP file I gave you first!

1. **On the repository page, click:** "uploading an existing file"

2. **On your phone:**
   - Open your file manager
   - Navigate to extracted InstaDownloader folder
   - You should see folders: `app`, `.github`, and files: `build.gradle`, `README.md`, etc.

3. **Upload ALL files:**
   
   **For Browser Upload:**
   - Tap and hold to select all files and folders
   - Drag or tap "Upload" 
   - Wait for all files to upload (may take 2-3 minutes)

   **If your browser can't upload folders:**
   - Use GitHub Mobile App (better option!)
   - Download from Play Store: "GitHub"
   - Login
   - Navigate to your repository
   - Use app to upload files

4. **After upload, scroll down:**
   - In "Commit changes" box
   - Type: "Initial commit - InstaDownloader"
   - Click: "Commit changes"

---

### STEP 4: Add Required Files (10 minutes)

**You must add these files or the build will fail!**

#### 4A. Add XML Config Files

**File 1: file_paths.xml**

1. **Click:** "Add file" → "Create new file"
2. **In filename box, type:** `app/src/main/res/xml/file_paths.xml`
3. **Paste this:**
```xml
<?xml version="1.0" encoding="utf-8"?>
<paths>
    <external-files-path name="downloads" path="Downloads/" />
    <external-path name="external_files" path="." />
</paths>
```
4. **Click:** "Commit changes"

**File 2: backup_rules.xml**

1. **Click:** "Add file" → "Create new file"
2. **Filename:** `app/src/main/res/xml/backup_rules.xml`
3. **Paste:**
```xml
<?xml version="1.0" encoding="utf-8"?>
<full-backup-content>
    <include domain="sharedpref" path="." />
</full-backup-content>
```
4. **Click:** "Commit changes"

**File 3: data_extraction_rules.xml**

1. **Click:** "Add file" → "Create new file"
2. **Filename:** `app/src/main/res/xml/data_extraction_rules.xml`
3. **Paste:**
```xml
<?xml version="1.0" encoding="utf-8"?>
<data-extraction-rules>
    <cloud-backup>
        <include domain="sharedpref" path="." />
    </cloud-backup>
</data-extraction-rules>
```
4. **Click:** "Commit changes"

#### 4B. Add Font Files

**Fonts are optional but recommended:**

You can either:
- **Option A:** Skip fonts (app may have default system font)
- **Option B:** Download Poppins from Google Fonts on your phone and upload

To upload fonts:
1. Download Poppins.zip from https://fonts.google.com/specimen/Poppins
2. Extract the ZIP
3. In GitHub: "Add file" → "Upload files"
4. Navigate to: `app/src/main/res/font/`
5. Upload .ttf files
6. Commit

#### 4C. Add Icon Files (Optional)

Icons are included as samples. For now, you can skip this step.

---

### STEP 5: Trigger APK Build (1 minute)

1. **Go to repository page**
2. **Click:** "Actions" tab (at the top)
3. **You'll see:** Workflows list
4. **Click:** "Build Android APK" workflow
5. **Click:** "Run workflow" button (top right)
6. **Select:** "Branch: main"
7. **Click:** "Run workflow" (green button)

**The build starts immediately!**

---

### STEP 6: Wait for Build (5-10 minutes)

1. **You'll see:** A yellow circle (building)
2. **Wait:** Build takes 5-10 minutes
3. **Refresh page** to see progress
4. **When done:** Yellow circle → Green checkmark ✅

**While waiting, you can close the page and come back later!**

---

### STEP 7: Download APK (2 minutes)

1. **After build completes (green checkmark)**
2. **Click on:** The completed workflow (click the commit message)
3. **Scroll down** to "Artifacts" section
4. **You'll see:** "InstaDownloader-Debug-APK"
5. **Click it** to download
6. **File downloads** as a ZIP (app-debug.zip)

---

### STEP 8: Extract and Install (3 minutes)

**On your phone:**

1. **Find the downloaded file:**
   - Usually in "Downloads" folder
   - File name: `InstaDownloader-Debug-APK.zip`

2. **Extract the ZIP:**
   - Tap the ZIP file
   - Select "Extract" or "Unzip"
   - You'll get: `app-debug.apk`

3. **Install the APK:**
   - Tap `app-debug.apk`
   - If prompted: "Install from Unknown Sources"
     - Go to Settings → Security
     - Enable "Unknown Sources" or "Install Unknown Apps"
     - Go back and tap APK again
   - Click "Install"
   - Wait for installation
   - Click "Open"

**🎉 DONE! Your app is installed!**

---

## ⚠️ Troubleshooting

### "Build failed" - Red X instead of green checkmark

**Most common reasons:**

1. **Missing XML files**
   - Make sure you added all 3 XML files in Step 4
   - Check file names are exactly correct
   - Check they're in the right folders

2. **Missing gradlew file**
   - Make sure you uploaded ALL files from ZIP
   - Check `gradlew` file exists in root

**To fix:**
- Click on the failed build
- Read the error message
- Usually tells you what's missing
- Add the missing file and try again

### "Can't upload folders from browser"

**Solutions:**
1. Use GitHub Mobile App (recommended)
2. Upload files individually (slow but works)
3. Use Desktop mode in browser settings

### "Repository not found"

- Make sure repository is **Public** not Private
- Private repos don't get free Actions minutes

### "Workflow not appearing"

- Make sure you uploaded the `.github` folder
- File should be at: `.github/workflows/android.yml`
- If missing, the workflow won't show

### "Can't install APK - Installation blocked"

1. **Go to:** Settings → Security
2. **Enable:** "Install from Unknown Sources"
3. **Or on newer Android:**
   - Settings → Apps → Special Access
   - Install Unknown Apps
   - Enable for your browser/file manager

---

## 📊 What Each Step Does

| Step | What Happens | Time |
|------|--------------|------|
| 1-2 | Setup GitHub | 5 min |
| 3 | Upload code | 5 min |
| 4 | Add required files | 10 min |
| 5 | Start build | 1 min |
| 6 | GitHub builds APK | 10 min |
| 7 | Download APK | 2 min |
| 8 | Install on phone | 3 min |
| **TOTAL** | | **~36 min** |

---

## ✅ Checklist

Before starting, make sure you have:

- [ ] Phone with internet connection
- [ ] Web browser (Chrome, Firefox, Safari)
- [ ] Email address (for GitHub account)
- [ ] The ZIP file I gave you (extracted)
- [ ] 30-40 minutes of time

---

## 💡 Pro Tips

1. **Use WiFi** - Uploading uses data
2. **Keep screen on** - During uploads
3. **Don't close browser** - While uploading
4. **Bookmark repo** - For easy access
5. **GitHub Mobile App** - Easier than browser

---

## 🎯 Alternative: Quick Service

If this seems too complex, you can:

1. **Ask a friend** with computer to build it
2. **Use Fiverr** - Pay $5-10 for someone to build
3. **Go to computer cafe** - Use their computer (10 min)
4. **Wait until you have computer access**

---

## 📱 After Installation

Once app is installed:

1. **Open the app**
2. **Grant permissions** if asked
3. **Paste Instagram URL**
4. **Select quality**
5. **Download!**

**Note:** App needs API integration to work fully. See IMPLEMENTATION_GUIDE.md for adding API support.

---

## 🆘 Still Stuck?

**Get help here:**

1. **Reddit:** r/androiddev - Post your issue
2. **Stack Overflow:** Tag: android, github-actions
3. **GitHub Discussions:** On your repository
4. **YouTube:** Search "GitHub Actions build Android APK"

**Include in your help request:**
- Link to your GitHub repository
- Screenshot of error
- Which step you're stuck on

---

## 🎉 Success!

**You now have:**
- ✅ Instagram Downloader APK
- ✅ GitHub repository (for updates)
- ✅ Automatic builds (rebuild anytime)
- ✅ Full source code access

**Next steps:**
- Customize the app
- Add API key (see IMPLEMENTATION_GUIDE.md)
- Share with friends
- Upload to Play Store (requires signing)

---

**You did it without a computer! Great job! 🚀**
