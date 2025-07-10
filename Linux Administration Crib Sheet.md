## Testumgebung einrichten


## Systemstatistiken erfassen und auswerten

- Host Informationen sammeln
- Hardware Informationen sammeln
- Prozesse auflisten
- Protokoll Informationen anzeigen
- Sysstat für die Systemüberwachung und Leistungsanalyse
- Berichte über die System Auslastung erstellen
- Performance Co-Pilot (PCP)
# Grundlegende Systemkonfiguration verwalten
## Verwalten von systemd-Diensten
Systemd ist ein leistungsstarkes System- und Diensteverwaltungstool unter Linux. Die folgenden Befehle helfen bei der Verwaltung von Diensten, insbesondere am Beispiel des `bluetooth.service`:
- **Auflisten aller Dienstdateien**:  
    Um eine Übersicht aller verfügbaren systemd-Dienste zu erhalten, einschließlich ihres Aktivierungsstatus:
    ```bash
    sudo systemctl list-unit-files -t service
    ```
- **Status eines Dienstes prüfen**:  
    Zeigt detaillierte Informationen zum Status des `bluetooth.service`, einschließlich Laufzeit, Speicherverbrauch und Fehler:
    ```bash
    sudo systemctl status bluetooth.service
    ```
- **Dienst stoppen**:  
    Beendet den laufenden `bluetooth.service`:
    ```bash
    sudo systemctl stop bluetooth.service
    ```
- **Laufende Einheiten filtern**:  
    Überprüft, ob der `bluetooth.service` in der Liste der aktiven Einheiten vorhanden ist:
    ```bash
    sudo systemctl list-units | grep bluetooth.service
    ```
- **Aktivitätsstatus prüfen**:  
    Ermittelt, ob der `bluetooth.service` aktiv ist (Antwort: `active` oder `inactive`):
    ```bash
    sudo systemctl is-active bluetooth
    ```

**Hinweis**: Weitere nützliche Befehle sind `start`, `enable`, `disable`, und `restart`, um Dienste zu starten, automatisch zu aktivieren/deaktivieren oder neu zu starten.
## Einmalige Aufgaben mit `at` planen
Das `at`-Kommando ermöglicht die Planung von einmaligen Aufgaben zu einem bestimmten Zeitpunkt. Im Folgenden ein Beispiel zur Planung und Verwaltung:
- **Aufgabe planen**:  
    Führt um 19:00 Uhr den Befehl `ls /etc > tmp/attest` aus, der den Inhalt des `/etc`-Verzeichnisses in die Datei `tmp/attest` schreibt:
    ```bash
    at 19:00
    ls /etc > tmp/attest
    <Ctrl+D>
    ```
- **Geplante Aufgaben anzeigen**:  
    Listet alle mit `at` geplanten Aufgaben auf:
    ```bash
    atq
    ```
**Hinweis**: Verwenden Sie `atrm <Job-ID>`, um geplante Aufgaben zu löschen. Stellen Sie sicher, dass der `atd`-Dienst läuft (`sudo systemctl status atd`).

