# FantasticMC

Ready-to-use Android client UI for Minecraft Bedrock (package: `com.fanstatic.mc`).

## Features

- Full FantasticMC module UI (Combat, Movement, Render, Player, World)
- Live HUD preview + HUD Editor
- **Launch Minecraft** button → launches official Minecraft Bedrock (`com.mojang.minecraftpe`)
- After launch: **floating FMC logo** appears over Minecraft (draggable)
- Tap the floating logo → opens FantasticMC client UI again
- Landscape optimized, dark theme matching your design

## How to get the APK (GitHub)

1. Create a new GitHub repository (public or private).
2. Upload **all files** from this folder (or push via git).
3. Go to **Actions** tab → select **Build APK** workflow → **Run workflow**.
4. Wait ~2–4 minutes.
5. Download the artifact **FantasticMC-APK** (contains `app-debug.apk`).
6. Install on your Android device (enable “Install from unknown sources”).

### First run important steps

1. Open **FantasticMC**.
2. Grant **Display over other apps** permission when asked (required for floating logo).
3. Tap **LAUNCH MINECRAFT**.
4. Minecraft opens → floating blue **FMC** logo appears bottom-right.
5. Tap the logo anytime to return to the client UI.

## Project structure

```
FantasticMC-Android/
├── app/
│   ├── src/main/
│   │   ├── assets/index.html          ← Your full UI
│   │   ├── java/com/fanstatic/mc/
│   │   │   ├── MainActivity.java      ← WebView + JS bridge
│   │   │   └── FloatingLogoService.java ← Overlay logo
│   │   ├── res/                       ← Icons + theme
│   │   └── AndroidManifest.xml
│   └── build.gradle
├── .github/workflows/build-apk.yml    ← Auto build APK
└── README.md
```

## Customization

- Change package name: edit `applicationId` in `app/build.gradle` and `package` in `AndroidManifest.xml` + Java package folders.
- Replace icons: put new PNGs in `app/src/main/res/mipmap-*`.
- Edit UI: modify `app/src/main/assets/index.html`.

## Requirements

- Android 7.0+ (API 24)
- Minecraft Bedrock Edition installed
- Overlay (“Display over other apps”) permission

## Notes

- This is a **UI / launcher companion**. It does not inject into the Minecraft process.
- Floating logo uses `SYSTEM_ALERT_WINDOW` (standard for overlays).
- Debug APK is unsigned for easy testing. For Play Store you need a signed release build.
