# 🎲 QuicKniff

Der schnelle digitale Kniff-Block für 1–6 Spieler, direkt im Browser.

## Funktionen

- **Spielzettel:** Feld antippen, Punkte auswählen oder streichen; ausgefüllte Felder lassen sich jederzeit ändern
- **Automatische Summen:** Zwischensumme, Bonus (+35 ab 63 Punkten im oberen Block), Gesamtpunkte
- **Zusatz-Kniff:** je +50 Punkte, sobald ein Kniff eingetragen ist
- **Spieler:** hinzufügen, umbenennen, entfernen
- **Sichern:** Spielstand bleibt im Local Storage; Export und Import als JSON-Datei
- **Hell/Dunkel-Modus:** gemeinsame Einstellung mit dem Dashboard (`overall-theme`)
- **PWA:** installierbar (Icons für iPhone und Android) und offline nutzbar; beim ersten Besuch ein Hinweis zum Installieren (Testen mit `?install=1`)

## Aufbau

- `index.html`: die komplette App (HTML, CSS, JS)
- `sw.js`: Service Worker; bei neuen oder umbenannten Dateien die Cache-Version erhöhen
- `shared/ios-nav.js`: gemeinsame Navigation wie in den anderen Apps
- `icon.svg`, `icon-maskable.svg`, `icons/`: App-Icon im gemeinsamen Stil (Akzent Ziegelrot `#a63a32`)

Teil des Dashboards [mvs2-bot.github.io](https://mvs2-bot.github.io/).

## Android-App (APK)

`android/twa-manifest.json` beschreibt die App (Trusted Web Activity: die Webseite läuft in Chrome, ohne Browserleiste).
Der Workflow `.github/workflows/android-apk.yml` baut sie mit Bubblewrap und legt die APK als Release ab:
[QuicKniff.apk](https://github.com/mvs2-bot/QuicKniff/releases/latest/download/QuicKniff.apk).
Neu bauen: Actions → „Android-APK bauen“ → „Run workflow“. Für gleichbleibende Signatur die Secrets
`ANDROID_KEYSTORE_BASE64` und `ANDROID_KEYSTORE_PASSWORD` setzen (Details im Workflow).
