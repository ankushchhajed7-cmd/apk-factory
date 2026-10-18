# apk-factory
## Native bridges (page ke JavaScript se)
| Object | Kaam |
|---|---|
| `ANVSaver.save(dataUrl, name, mime)` | File download/save |
| `ANVScreen.keepOn(true/false)` | Screen ON rakho |
| `ANVSteps.*` | Step counter |
| `ANVGeo.*` | Background GPS |
| `ANVAlert.speak(text)` / `stopSpeak()` / `prepare()` / `ttsReady()` | Voice (phone ka TTS, Hindi) |
| `ANVAlert.notify(title, body)` / `notifPerm()` / `requestNotif()` | Notification (Android 13+ permission) → `window.onAnvNotifPerm(ok)` |
| `ANVAlert.vibrate("250,120,250")` | Vibrate pattern (ms) |

`ANVAlert` sirf tab kuch karta hai jab page use call kare — jo apps ise use nahi karte unpar koi asar nahi.
