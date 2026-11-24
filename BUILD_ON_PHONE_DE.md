# APK nur mit dem Smartphone bauen (Cloud-Build)

Du brauchst keinen PC. GitHub baut die APK auf seinen Servern.

## Einmalige Voraussetzungen
- GitHub-Konto (kostenlos reicht für ein öffentliches Repository)
- Browser auf dem Poco F7 Pro

## Schritte am Smartphone
1. Lade `Assassin_D6Pro_Connect_Android_Studio_Projekt_v0.5.0.zip` herunter und entpacke es mit dem Dateimanager oder ZArchiver.
2. Öffne https://github.com im Browser und melde dich an.
3. Erstelle ein neues Repository, z. B. `assassin-d6pro-connect`. Für den einfachsten kostenlosen Workflow wähle Public.
4. Öffne das Repository und wähle `Add file` > `Upload files`.
5. Lade den INHALT des entpackten Projektordners hoch (nicht nur die ZIP-Datei). Achte darauf, dass `.github/workflows/build-apk.yml` mit hochgeladen wird. Falls der Dateimanager versteckte Ordner nicht zeigt, erstelle die Workflow-Datei später direkt in GitHub unter genau diesem Pfad.
6. Tippe `Commit changes`.
7. Öffne im Repository den Reiter `Actions`. Der Workflow `Build Android APK` sollte starten. Falls nicht: Workflow öffnen und `Run workflow` wählen.
8. Warte, bis der Lauf grün abgeschlossen ist.
9. Öffne den abgeschlossenen Workflow-Lauf, scrolle zu `Artifacts` und lade `Assassin-D6Pro-Connect-debug` herunter.
10. Entpacke das heruntergeladene Artifact. Darin liegt `app-debug.apk`.
11. Öffne die APK auf dem Poco und erlaube bei Nachfrage die Installation dieser App aus der verwendeten Quelle.

## Hinweise
- GitHub Actions baut die APK in der Cloud; Android Studio ist auf dem Smartphone nicht nötig.
- Der Build ist erst erfolgreich, wenn der Actions-Lauf grün ist und das APK-Artefakt bereitsteht.
- Die APK ist eine Debug-Version, nicht signiert für eine Veröffentlichung im Play Store.
- Bei einem roten/fehlgeschlagenen Lauf: Öffne den Lauf, kopiere den Fehler aus dem Build-Schritt oder sende einen Screenshot. Dann kann der Buildfehler korrigiert werden.

## Funktioneller Stand
Die App ist weiterhin ein BLE-Diagnoseprototyp. Ein erfolgreicher APK-Build beweist nicht, dass die D6-PRO-Daten bereits dekodiert sind. Für echte Akku-, Fahr- und BMS-Messwerte benötigen wir das Diagnoseprotokoll deines konkreten Scooters.
