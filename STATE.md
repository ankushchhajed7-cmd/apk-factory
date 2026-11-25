# apk-factory — STATE

GitHub Pages / PWA URL → signed WebView APK (GitHub Actions). Files: `.github/workflows/build-apk.yml`, `config.json`, `keystore.jks`.

## Version history
- **2026-11-26 — Mic runtime permission fix** (VOICE RATE ke liye, sab apps me): web page `getUserMedia` se mic/camera maange to APK pehle Android runtime permission (RECORD_AUDIO / CAMERA) maangta hai, phir WebView ko grant karta hai. Pehle sirf WebView grant hota tha, Android permission kabhi nahi maangi jaati thi → mic "NotAllowed". Mana karne par toast.
- **2026-10-18 — intent:// links fix**: `intent://…#Intent;package=…;end` ab `Intent.parseUri` se khulta hai (doosra app jaise MT5 kholne ke liye); app na ho to `browser_fallback_url` ya Play Store. Pehle ACTION_VIEW se "App nahi mila" aata tha.
- **2026-10-18 — ANVAlert bridge** (MEXA SCALP ke liye, sab apps me available)
  - WebView me Web Speech / Notification API nahi hote — isliye native bridge `ANVAlert`:
    `speak()` (Android TextToSpeech, Hindi → English-India fallback), `notify()` (high-priority "Alerts" channel, tap par app khule),
    `vibrate()`, `notifPerm()` / `requestNotif()` (Android 13+ POST_NOTIFICATIONS)
  - Manifest me `VIBRATE` permission add
  - TTS lazy start hota hai (pehli call par) — jo apps use nahi karte unpar koi load nahi
- Pehle se: ANVSaver, ANVScreen (keep screen on), ANVSteps, ANVGeo + background GPS service, license option

## Decisions
- Naye bridges hamesha "opt-in by call": page call kare tabhi kaam, warna kuch nahi.

## Pending
- [ ] VOICE RATE ka APK naye workflow se banao (URL https://ankushchhajed7-cmd.github.io/VOICE-RATE/, package com.ankushnewvision.voicerate) aur Sarvam mic test karo
- [ ] MEXA SCALP ka APK naye workflow se banao aur Voice / Notif / Vibrate / Screen ON test karo
