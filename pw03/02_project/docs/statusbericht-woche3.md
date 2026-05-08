# Statusbericht Woche 3

## Umgesetzte Arbeiten
- Analyse der hardcodierten Konfiguration in compose.yml und main.py
- Einführung einer .env-Datei für alle Konfigurationswerte
- Anpassung der compose.yml auf Umgebungsvariablen (${...})
- Anpassung der Datenbankverbindung in app/main.py
- Erstellung einer .gitignore zum Schutz sensibler Daten
- Testen des Systems mit Docker Compose

## Aktueller Stand
Das System läuft erfolgreich mit Docker Compose.
Alle Services (API, Datenbank, Frontend und Adminer) starten korrekt.
Die Datenbankverbindung funktioniert über Umgebungsvariablen.

## Probleme
- Anfangs wurde Docker in WSL nicht erkannt (Integration fehlte)
- Initial war die DATABASE_URL noch hardcoded
- Verständnis der Variablen-Ersetzung in Docker Compose war anfänglich unklar

## Nächste Schritte
- Weitere Tests der API-Endpunkte durchführen
- Verständnis von Docker Networking vertiefen
- Logging und Fehlerhandling verbessern
