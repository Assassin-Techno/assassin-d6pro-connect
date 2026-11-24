# ASSASSIN D6 PRO CONNECT – Version 0.5.0

Android-Studio-Projekt für TODIMART D6 PRO / Poco F7 Pro.

## Änderungen in 0.5.0
- BLE-Suche, Geräteauswahl und Verbindung
- Wiederverbindung nach unerwartetem Abbruch (maximal fünf Versuche)
- GATT-Service- und Characteristic-Erkennung
- sequenzielle READ- und Notify/Indicate-Einrichtung
- lokale Protokollspeicherung über App-Neustarts
- TXT- und CSV-Export
- Dashboard-Grundgerüst; nicht dekodierte Werte werden ausdrücklich als solche markiert

## Noch nicht implementiert / nicht verifiziert
Es gibt noch keinen bestätigten D6-PRO-Protokollparser. Akku-Prozent, Spannung, Strom, Geschwindigkeit, ODO, TRIP, Zellspannungen, BMS-Zustand und Fehlercodes dürfen erst nach Analyse echter Scooter-Daten als Messwerte dargestellt werden.

## Installation / Test
1. ZIP entpacken und Projekt in Android Studio öffnen.
2. Gradle-Synchronisierung abwarten.
3. Poco F7 Pro mit USB-Debugging verbinden und App starten.
4. Vicont vollständig beenden, Scooter einschalten und BLE-Suche starten.
5. Das passende Gerät antippen und mindestens 60 Sekunden verbunden lassen.
6. Diagnoseprotokoll als TXT oder CSV exportieren und zur Analyse bereitstellen.

## APK bauen
Android Studio: Build > Build Bundle(s) / APK(s) > Build APK(s).
Debug-APK: `app/build/outputs/apk/debug/app-debug.apk` nach erfolgreichem Build.

## Sicherheit
Die App sendet keine Scooter-Steuerbefehle und verändert keine Konfiguration. Sie liest ausschließlich als READ markierte GATT-Merkmale und abonniert vorhandene Notifications/Indications. Verhalten und Kompatibilität sind auf dem konkreten D6 PRO noch zu testen.
