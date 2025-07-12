📱 Convert HTML/CSS/JS to Android APK using GitHub Actions

This project allows you to build an Android APK from a simple HTML/CSS/JavaScript frontend without installing Android Studio or the Android SDK locally. All APK builds are done entirely in GitHub Actions.

📁 Project Structure (Example)

my-pwa/
├── index.html
├── styles.css
├── app.js
├── app.png                # Optional icon (512x512 recommended)
├── assets/                # Optional images or media folder
├── package.json           # Optional (if you use Node/bundlers)
└── .github/
    └── workflows/
        └── build-apk.yml  # GitHub Actions workflow

🚀 How to Use This

1. Create a GitHub Repository

Go to github.com, create a new repository (public or private), and name it anything you like (e.g., my-pwa-to-apk).

2. Prepare Your Files

In the root of the repo, include the following:

index.html — Your main HTML file

styles.css, app.js — Your CSS/JavaScript files

Optional:

assets/ — Images or media

app.png — App icon (square, at least 512x512; can be in root or assets/)

package.json — For Node projects with build scripts like React, Vue, etc.

3. Add the GitHub Actions Workflow

Create the following folder structure in your project:

.github/workflows/build-apk.yml

Paste this into build-apk.yml (already included if you cloned this repo):

See build-apk.yml for full script.

4. Push Your Code

Commit and push everything to the main branch:

git add .
git commit -m "Initial commit with build workflow"
git push origin main

Or use GitHub’s "Upload files" → "Commit changes" feature.

5. Run the Workflow

Go to the Actions tab in your repo.

Select Build Android APK.

You’ll see the latest run triggered (automatically or manually).

Wait a few minutes for the build to complete.

6. Download the APK

Once the workflow finishes, scroll to the bottom of the run.

Under Artifacts, download pong-app-release.apk.

You can now sideload it on any Android device!

📲 Sideload APK on Android

Send the APK to your Android device.

Enable Install from Unknown Sources.

Open the APK file to install it.

Launch your app!

🧰 Advanced Options

🔐 Code Signing (Optional)

If you want to publish your APK to the Google Play Store:

You must sign it with a private key.

Uncomment the signing section in build-apk.yml.

Inject your keystore as a GitHub secret (e.g., KEYSTORE_BASE64).

🗉️ Use with Frameworks

If you use React, Vue, Svelte, etc., ensure your build output goes into www/. Example in package.json:

"scripts": {
  "build": "vite build --outDir www"
}

📦 Summary

Step

Description

index.html

Your app's UI

app.png

App icon (auto-resized)

build-apk.yml

GitHub Actions build automation

Actions tab

View builds and download the APK

pong-app-release.apk

Ready-to-install Android app

Let us know if you run into issues or want to contribute improvements!

