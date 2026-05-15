# Fragen – Konfiguration und Umgebungsvariablen (DL11)

Name: <Nachname> <Vorname>
Klasse: <Klasse>

---

## 1. Konfiguration

Welche Werte waren ursprünglich hardcoded in `compose.yml` und `app/main.py`?

Antwort:
Datenbankname (POSTGRES_DB)
Benutzername (POSTGRES_USER)
Passwort (POSTGRES_PASSWORD)
Host (db)
Port (5432)
DATABASE_URL direkt im Code
---

Warum ist es ein Problem, Passwörter direkt in `compose.yml` einzutragen?

Antwort:
Weil sie im Git-Repository gespeichert werden und damit dauerhaft sichtbar und unsicher sind. Zudem ist die Konfiguration nicht flexibel für verschiedene Umgebungen.
---

Was ist der Unterschied zwischen `.env` und `.env.example`?

Antwort:
.env enthält echte Werte (Passwörter, Konfiguration)
.env.example enthält nur Beispielwerte ohne echte Secrets zur Vorlage für andere Entwickler
---

Warum muss `.env` in `.gitignore` eingetragen sein?

Antwort:
Damit sensible Daten wie Passwörter nicht ins Git-Repository gelangen und nicht öffentlich oder dauerhaft gespeichert werden.
---

## 2. Variablen in Compose

Wie referenziert man eine Variable aus `.env` in `compose.yml`?

Antwort:
${VARIABLE_NAME}
---

Was passiert, wenn eine Variable in `.env` fehlt, aber in `compose.yml` verwendet wird?

Antwort:
Docker ersetzt sie nicht → es kann zu Fehlern kommen oder leere/ungültige Werte werden verwendet.
---

Was zeigt der Befehl `docker compose config`? Wann ist er nützlich?

Antwort:
Es zeigt die vollständig aufgelöste Konfiguration, also alle Variablen ersetzt durch echte Werte.

Nützlich für:

Fehleranalyse
Kontrolle der .env-Einbindung
Debugging
---

## 3. Dockerfile und Build

Warum wird `requirements.txt` in einem eigenen `COPY`-Schritt vor dem App-Code kopiert?

Antwort:
Damit Docker Layer Caching nutzen kann. Wenn sich nur der Code ändert, müssen die Dependencies nicht jedes Mal neu installiert werden.
---

Was bewirkt `.dockerignore`? Welche Dateien sollten darin stehen?

Antwort:
Es verhindert, dass unnötige Dateien in das Docker-Image kopiert werden.
---

## 4. Systemtest

Funktioniert `/db-check` nach Ihrer Konfigurationsanpassung?

Antwort:
Ja, wenn die Datenbank korrekt verbunden ist.
---

Was zeigt der Endpunkt `/db-check` an, wenn die Verbindung funktioniert?

Antwort:
{"db": "connected"}
---

## 5. Reflexion

Was war der wichtigste Schritt in dieser Woche?

Antwort:
Das Auslagern von sensiblen Daten (Passwörter und Konfiguration) in .env und das Entfernen von Hardcoding aus Code und Compose-Datei.
---

Was ist noch unklar oder möchten Sie besser verstehen?

Antwort:
