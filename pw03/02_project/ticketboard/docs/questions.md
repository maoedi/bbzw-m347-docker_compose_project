# Fragen – Konfiguration und Umgebungsvariablen (DL11)

Name: <Duss> <Lucy>
Klasse: <Klasse>

---

## 1. Konfiguration

Welche Werte sind aktuell hardcoded in `compose.yml` und `app/main.py`?

Antwort:
in `compose.yml`: 
  - DATABASE_URL
  - POSTGRES_DB
  - POSTGRES_USER
  - POSTGRES_PASSWORD
in `app/main.py`:
  - DATABASE_URL
---

Warum ist es ein Problem, Passwörter direkt in `compose.yml` einzutragen?

Antwort:
Sicherheitsrisiko: Wenn es in ein öffentliches Repo hochgeladen wird, kann jeder das Passwort sehen.
---

Was ist der Unterschied zwischen `.env` und `.env.example`?

Antwort:
kann alles enthalten, was in .env steht, aber keine echten Passwörter. Zeigt anderen Entwicklern, welche Variablen benötigt werden.
---

Warum muss `.env` in `.gitignore` eingetragen sein?

Antwort:
dass die Datei nicht ins Git-Repo hochgeladen wird
---

## 2. Variablen in Compose

Wie referenziert man eine Variable aus `.env` in `compose.yml`?

Antwort:
`${VARIAVLE}`
---

Was passiert, wenn eine Variable in `.env` fehlt, aber in `compose.yml` verwendet wird?

Antwort:
Docker Compose wirft einen Fehler und stoppt den Startprozess, da die Variable nicht aufgelöst werden kann.
---

Was zeigt der Befehl `docker compose config`? Wann ist er nützlich?

Antwort:
die vollständig aufgelöste Compose-Konfiguration, mit allen Variablen ersetzt. Nützlich, um zu überprüfen, ob alle Variablen korrekt gesetzt und aufgelöst wurden, bevor man die Container startet. 
---

## 3. Dockerfile und Build

Warum wird `requirements.txt` in einem eigenen `COPY`-Schritt vor dem App-Code kopiert?

Antwort:
requirements.txt ändert sich selten → Dependencies werden nicht jedes Mal neu installiert
Code ändert sich oft → nur dieser Teil wird neu gebaut
---

Was bewirkt `.dockerignore`? Welche Dateien sollten darin stehen?

Antwort:
alles, was nicht im Container gebraucht wird, gehört in `.dockerignore`
---

## 4. Systemtest

Funktioniert `/db-check` nach Ihrer Konfigurationsanpassung?

Antwort:
Ja
---

Was zeigt der Endpunkt `/db-check` an, wenn die Verbindung funktioniert?

Antwort:
`{"db": "connected"}`
---

## 5. Reflexion

Was war der wichtigste Schritt in dieser Woche?

Antwort:
eigene Variablen in .env zu setzten und zu benützen
---

Was ist noch unklar oder möchten Sie besser verstehen?

Antwort:
-