# apk-factory — STATE

GitHub Pages / PWA URL → signed WebView APK (GitHub Actions). Files: `.github/workflows/build-apk.yml`, `config.json`, `keystore.jks`.

## Version history
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
- [ ] MEXA SCALP ka APK naye workflow se banao aur Voice / Notif / Vibrate / Screen ON test karo
