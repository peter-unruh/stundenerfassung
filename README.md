# Stundenwerk

Kostenlose Zeiterfassung für Handwerk, Garten- und Gebäudeservice, Kleinbetriebe und Selbstständige.
Läuft im Browser und offline auf dem Handy. Kein eigener Server: Daten bleiben im Browser oder im Google Drive des Nutzers.

**App:** https://peter-unruh.github.io/stundenerfassung/

## Funktionen
- Start/Stopp-Timer, Zeiten nachtragen, Pausen
- Kunden, Aufträge, Tätigkeiten, Stundensätze (Eintrag › Auftrag › Kunde › Tätigkeit › Standard)
- Anfahrt und Material je Einsatz
- Leistungsnachweis mit Unterschrift, druckbar als PDF
- Auswertung, CSV-Export für Excel, Backup
- Optional: Google-Tabelle im eigenen Drive, Team mit eigenen Google-Konten

## Dateien
| Datei | Zweck |
|---|---|
| `index.html` | die App (alles in einer Datei) |
| `info.html`, `impressum.html`, `datenschutz.html` | Startseite und Rechtliches |
| `manifest.webmanifest`, `sw.js`, `icon-*.png`, `apple-touch-icon.png` | Installation als App, Offline-Betrieb |

## Einrichtung Google Drive (Betreiber, einmalig)
In der Google Cloud Console (Projekt „Stundenwerk“):
1. **APIs aktivieren:** Google Sheets API, Google Drive API, Google Picker API.
2. **Google Auth Platform:** Branding ausfüllen, Zielgruppe „Extern“, Testnutzer eintragen, Datenzugriff: nur `drive.file`.
3. **Clients › Client erstellen:** Webanwendung, JavaScript-Ursprung `https://peter-unruh.github.io`. Client-ID kopieren.
4. **APIs & Dienste › Anmeldedaten › API-Schlüssel erstellen.** Einschränken auf Websites `https://peter-unruh.github.io/*` und auf die API „Google Picker API“.
5. **Projektnummer:** Startseite der Cloud Console › Projektinformationen.
6. In `index.html` oben unter `KONFIG` eintragen: `googleClientId`, `googleApiKey`, `googleProjektNummer`.

Für die Freigabe an alle (Testmodus beenden): Zielgruppe › „App veröffentlichen“. Google verlangt dafür Startseite und Datenschutzerklärung auf einer eigenen, bestätigten Domain. Danach in `KONFIG` `testbetrieb:false` setzen.

## Lizenz der Schriften
Big Shoulders, Instrument Sans, IBM Plex Mono – SIL Open Font License 1.1, eingebettet.
