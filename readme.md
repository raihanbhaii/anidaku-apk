Full Guide: How to Push an Update

Step 1 — Make your code changes
Do whatever changes you want in Android Studio. Fix bugs, add features, whatever.

Step 2 — Bump the version in app/build.gradle
Open app/build.gradle and find this section:
gradledefaultConfig {
    versionCode 1        // increase by 1 every update
    versionName "1.0.0"  // this must match your GitHub release tag
}
Change it like this for every update:
UpdateversionCodeversionNameFirst release1"1.0.0"Second release2"1.0.1"Third release3"1.0.2"

Step 3 — Build the APK
In Android Studio:

Click Build in the top menu
Click Generate Signed App Bundle / APK
Choose APK
Use your keystore (or create one if first time)
Select release build
Click Finish

Your APK will be at:
app/release/app-release.apk

Step 4 — Upload to GitHub Releases

Go to github.com/raihanbhaii/anidaku-apk
Click Releases on the right side
Click Draft a new release
Set Tag to match your versionName exactly → e.g. v1.0.1
Set Title → e.g. Anidaku v1.0.1
Write what changed in the description (optional)
Scroll down → Attach binaries → drag your app-release.apk there
Click Publish release ✅


Step 5 — Done. That's it.
Now when any user opens the app:

App hits GitHub API → sees tag v1.0.1
Compares with their installed version 1.0.0
Different → update screen appears
They tap Update → downloads your APK → installs ✅
