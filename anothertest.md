# 🚀 Space Weather Alerts

Stay one step ahead of the Sun!  
**Space Weather Alerts** is a sleek, retro-futuristic mobile and web app that displays real-time space weather alerts pulled directly from NASA's DONKI API.

Whether you're an aurora hunter, a satellite enthusiast, or just a curious space dreamer, this app brings solar activity data to your fingertips.

---

## 🌟 Features

- 🧲 **Geomagnetic K-Index**  
- 🔥 **Solar Flare Class**  
- 🌪️ **Geomagnetic Storm Severity**  
- 💨 **CME (Coronal Mass Ejection) Speed**  
- ⏰ **Timestamped NASA-issued alerts**  
- 🔗 **Clickable NASA links (fully functional on Android and Web)**  
- 🖥️ **Cross-platform:** Android & Web  
- 🎨 **Retro-terminal aesthetic** (Orbitron font, glow-style interface)  
- 🔄 **Pull-to-refresh**  
- 📴 **Offline-first behavior** for cached info  

---

## 📲 Download & Install (Android APK)

1. **Download** the latest `.apk` file from [itch.io](https://dobybaxter127.itch.io/space-weather-app).
2. Transfer to your Android device (if downloaded on desktop) or open directly on your phone.
3. Tap to open the APK file.
4. If you see a warning like:
   > "Installation blocked from unknown source"

   ➤ Go to **Settings → Security** and enable **"Install from unknown sources"**.  
   ➤ Then return and install the app.
5. Tap **Open** and enjoy live space weather updates!

> 💡 This app uses the developer’s integrated NASA API key – no setup needed.

---

## 💥 Troubleshooting Notes

### ✅ Web Version at - https://space-weather-app-988f88.gitlab.io

- Works fully with GitLab Pages and Flutter Web build.
- API key is securely passed using `--dart-define=NASA_API_KEY=YOUR_KEY`.
- Message content is sanitized to remove markdown symbols like `**`, `_`, etc.
- No exit button on web version (it's platform-aware).

---

### ⚠️ Android Version Fixes

I tracked and tackled a few Android-specific issues:

- **Data not displaying** on mobile was resolved by:
  - Ensuring all message fields (like `'messageBody'`) were properly included and parsed.
  - Updating `Text()` widget container with a fallback for null or empty values.
  - Adding a **sanitizer** function to remove markdown formatting from the alert message for Android rendering.

- **Links not clickable on Android**:
  - Resolved by replacing `Text` and `GestureDetector` with `SelectableText.rich` and individual `TapGestureRecognizer`s.
  - Now all long NASA URLs render properly and launch externally when tapped.

- **App icon not showing**:
  - Fixed via `flutter_launcher_icons` with correct `image_path` and YAML setup.

- **Floating Action Button**:
  - Now **only shows on Android** (uses platform check) to exit the app via `SystemNavigator.pop()`.

- **UI Footer**:
  - Footer now floats above system controls for visibility.

---

## 🔧 Technical Stack

- Built with **Flutter 3.8**  
- API: [NASA DONKI Notifications](https://api.nasa.gov/)  
- Fonts: Orbitron (Google Fonts)  
- Packages used:
  - `http`
  - `intl`
  - `google_fonts`
  - `flutter_launcher_icons`
  - `cupertino_icons`
  - `url_launcher`

---

## 🧠 Attribution

- NASA API data courtesy of [NASA's Heliophysics Division](https://heliophysics.nasa.gov)
- Fonts by [Orbitron](https://fonts.google.com/specimen/Orbitron)

---

© Doby Baxter 2025 — Space Weather Alerts 🚨☀️🌍
