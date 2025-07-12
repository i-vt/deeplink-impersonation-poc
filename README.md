# Android Deep Link Impersonation - Proof of Concept

This repository contains the source code for a Proof-of-Concept (PoC) demonstrating how a malicious Android application can impersonate a trusted application by exploiting the deep link handling mechanism.

This code accompanies the Medium blog post: [How Malicious Android Apps Can Impersonate Yours Using Deep Links](https://medium.com/@frankheat/how-malicious-android-apps-can-impersonate-yours-using-deep-links-8eac7f245aaf).

## How to Reproduce the Attack

### Prerequisites

* Android Studio
* An Android device or emulator

### Steps

**1. Clone the repository**

```
git clone https://github.com/frankheat/deeplink-impersonation-poc.git
```

**2. Install the legitimate app (SafeBank)**:

* Open the SafeBank project directory in Android Studio
* Build and run the app on your device/emulator

**3. Install the malicious app (RecipeShare)**:
* Open the RecipeShare project directory in a new Android Studio window
* Build and run the app on the same device/emulator

**4. Trigger the deep link**:

* Open a terminal or command prompt
* Run the following ADB command to simulate clicking the deep link:

```
adb shell am start -a android.intent.action.VIEW -d "safebank://"
```

**5. Observe the result**
* The Android disambiguation dialog will appear on your device, showing two identical "SafeBank" options.

<img width="2416" height="14894" alt="Screenshot 2025-07-12 at 01-30-37 How Malicious Android Apps Can Impersonate Yours Using Deep Links by Frankheat Jul 2025 Medium" src="https://github.com/user-attachments/assets/370bd377-6c37-4341-bdcb-8e6b667365bb" />
