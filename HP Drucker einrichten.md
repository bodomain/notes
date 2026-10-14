# HP-Drucker und Scanner unter Linux über WLAN einrichten

Datum: 09.10.2026. Gerät: HP DeskJet 4220e, im Netzwerk als „HP DeskJet 4200 series“ gemeldet.

## Executive Summary

Laptop und HP DeskJet 4220e sind beide mit dem WLAN-Hotspot eines Handys verbunden. Das Handy stellt das gemeinsame lokale Netzwerk bereit, über das Laptop und Multifunktionsgerät miteinander kommunizieren.

Der Scanner ist über SANE und `sane-airscan` eingerichtet und kann in „Dokument-Scanner“ (`simple-scan`) verwendet werden. Der Drucker wurde über IPP Everywhere in CUPS eingerichtet und als Standarddrucker mit A4 festgelegt. Damit ist Drucken aus GUI-Anwendungen über deren Druckdialog möglich. Der direkte Testdruck von `test.pdf` wurde vom HP als erfolgreich abgeschlossen bestätigt: zwei Seiten auf zwei Blättern.

Die Einrichtung bleibt nach einem Neustart erhalten; CUPS und Avahi sind für den automatischen Start aktiviert. Für die Nutzung muss der Handy-Hotspot eingeschaltet sein, und Laptop sowie Drucker müssen damit verbunden und gegenseitig erreichbar sein. Der konfigurierte Gerätename `HP24FBE39B886C.local` vermeidet die Bindung an eine feste IP-Adresse.

## Netzaufbau: Handy als WLAN-Hotspot

```text
Handy mit aktiviertem WLAN-Hotspot
├── Laptop mit Linux
└── HP DeskJet 4220e (Drucker und Scanner)
```

Beide Geräte hängen als WLAN-Teilnehmer am Handy. Der Druck- und Scanverkehr läuft innerhalb dieses lokalen Netzes; dafür ist keine Internetverbindung über Mobilfunk nötig.

Bei der Einrichtung war der HP unter `192.168.58.145` erreichbar. In der älteren Scanner-Konfiguration stand noch `192.168.181.145`. Nach einem erneuten Start des Hotspots oder einer neuen Verbindung kann die zugeteilte IP-Adresse anders sein. Deshalb verwenden die dauerhaften Druck- und Scan-Einträge den `.local`-Hostnamen.

Falls das Gerät später nicht gefunden wird, zuerst prüfen:

- Ist der Handy-Hotspot aktiv, und sind Laptop und HP mit diesem Hotspot verbunden?
- Löst `getent hosts HP24FBE39B886C.local` den Gerätenamen auf?
- Finden `avahi-browse -rt _ipp._tcp` und `airscan-discover` die Dienste?

Der Hotspot muss Kommunikation zwischen seinen WLAN-Teilnehmern zulassen. Eine eventuell aktivierte Client-Isolation kann diese verhindern. Die erfolgreiche Geräteabfrage und der Testdruck zeigen, dass die Kommunikation bei dieser Einrichtung funktionierte.

## 1. Vorhandene Konfiguration als Ausgangspunkt

Der Scanner war bereits eingerichtet. In seiner Konfiguration ließ sich der Gerätename finden:

```bash
rg -n 'HP|192\.' /etc/sane.d/airscan.conf
```

`rg` durchsucht Textdateien; `-n` zeigt die Zeilennummern. Der relevante Eintrag war:

```ini
"HP DeskJet 4220e" = http://HP24FBE39B886C.local/eSCL, eSCL
```

`eSCL` ist das Scan-Protokoll des Geräts. Der Drucker benutzt einen anderen Dienst, aber denselben Hostnamen. Scanner und Drucker müssen deshalb auf dem Rechner getrennt eingerichtet werden. Die Scanner-Konfiguration wurde nicht verändert.

## 2. So ist der Scanner eingerichtet

Die ursprüngliche Scanner-Einrichtung fand vor dieser Druckereinrichtung statt. Die folgenden Angaben sind aus Konfigurationsdateien, Paketprotokoll und aktuellen Geräteabfragen rekonstruiert; die genaue damalige Befehlsfolge ist nicht dokumentiert.

### Komponenten und Zusammenspiel

Der Scan-Weg auf diesem Rechner ist:

```text
Dokument-Scanner (simple-scan) oder scanimage
    → SANE → sane-airscan → eSCL über WLAN → HP
```

SANE ist die Schnittstelle zwischen Scan-Anwendungen und Gerätetreibern, den sogenannten Backends. `sane-airscan` ist hier das Backend für den Netzwerkzugriff. `simple-scan` ist die grafische Anwendung „Dokument-Scanner“; `scanimage` ist das Kommandozeilenprogramm.

Auf diesem Arch-basierten System sind die Pakete `sane`, `sane-airscan`, `simple-scan`, `avahi` und `nss-mdns` installiert. Das lässt sich prüfen mit:

```bash
pacman -Q sane sane-airscan simple-scan avahi nss-mdns
```

Das Paketprotokoll `/var/log/pacman.log` belegt die Installation von `sane-airscan` und `nss-mdns` am 08.10.2026. Für eine entsprechende Neueinrichtung auf Arch wären diese Befehle vorgesehen; sie wurden bei der Dokumentation nicht erneut ausgeführt:

```bash
sudo pacman -Syu --needed sane sane-airscan simple-scan avahi nss-mdns
sudo systemctl enable --now avahi-daemon.service
```

Hier ist Avahi bereits aktiviert und läuft. CUPS ist für diesen Scan-Weg nicht erforderlich, ebenso wenig ein lokaler `saned`-Server.

### Scanner im Netzwerk entdecken

```bash
airscan-discover
avahi-browse -rt _uscan._tcp
avahi-browse -rt _uscans._tcp
```

`airscan-discover` liefert gefundene Scanneradressen im Format für die Konfigurationsdatei. Die Avahi-Abfragen zeigen die unverschlüsselten beziehungsweise TLS-geschützten eSCL-Dienste einschließlich Port und Ressourcenpfad. Hier wurden unter anderem diese Adressen gefunden:

```text
http://192.168.58.145:8080/eSCL/
https://192.168.58.145:443/eSCL/
```

Zusätzlich funktioniert der bereits manuell konfigurierte Zugang über HTTP-Port 80: Die Abfrage `http://HP24FBE39B886C.local/eSCL/ScannerCapabilities` lieferte HTTP 200. Ein Gerät kann denselben Scan-Dienst auf mehreren Ports anbieten.

### Manuelle Konfiguration und Namensauflösung

In `/etc/sane.d/airscan.conf` steht unter `[devices]`:

```ini
[devices]
# "HP DeskJet 4220e" = http://192.168.181.145/eSCL, eSCL
"HP DeskJet 4220e" = http://HP24FBE39B886C.local/eSCL, eSCL
```

Das `#` deaktiviert die alte IP-basierte Zeile. Die aktive Zeile legt einen Anzeigenamen, die Scan-Adresse und das Protokoll fest. Zum Nachbauen würde man die bestehende Datei etwa mit `sudoedit /etc/sane.d/airscan.conf` bearbeiten und den Eintrag in deren vorhandenen Abschnitt `[devices]` aufnehmen.

Das Backend ist durch `/etc/sane.d/dll.d/airscan` in SANE eingebunden:

```text
# sane-dll entry for sane-airscan
airscan
```

Für die `.local`-Namensauflösung enthält die `hosts:`-Zeile in `/etc/nsswitch.conf` hier bereits `mdns4_minimal [NOTFOUND=return]`. Zusammen mit dem installierten `nss-mdns` und Avahi kann so auch `getent hosts HP24FBE39B886C.local` den Namen auflösen. Diese bestehende Zeile muss nicht nochmals geändert werden.

### Erkennung und Scan-Optionen prüfen

```bash
scanimage -L
scanimage -d 'airscan:e0:HP DeskJet 4220e' --help
```

`-L` listet die von SANE erkannten Geräte auf. Die zweite Abfrage zeigt Optionen für genau diesen Scanner, ohne einen Scan auszulösen. Bei dieser Prüfung wurde unter anderem gemeldet:

```text
device:     airscan:e0:HP DeskJet 4220e
resolution: 75, 100, 150, 200, 300, 400, 600, 1200 dpi
mode:       Color oder Gray
source:     Flatbed oder ADF
```

`Flatbed` bezeichnet das Vorlagenglas, `ADF` den automatischen Dokumenteneinzug. 300 dpi ist ein sinnvoller Ausgangspunkt für Dokumente. Die Gerätekennung sollte auf einem anderen Rechner aus dessen eigener `scanimage -L`-Ausgabe übernommen werden.

Der HP erscheint hier mehrfach: einmal als manueller `airscan`-Eintrag, einmal automatisch über `airscan` und teilweise zusätzlich über das ebenfalls aktivierte `escl`-Backend. Das sind Zugänge zu demselben Gerät. In der Anwendung kann der Eintrag „HP DeskJet 4220e“ gewählt werden. Auch Kameraeinträge mit `v4l:` können in der SANE-Liste auftauchen; sie gehören nicht zum HP.

### Scannen in GUI und Terminal

Die grafische Anwendung lässt sich über das Anwendungsmenü oder mit folgendem Befehl öffnen:

```bash
simple-scan
```

Dort den HP auswählen, Vorlagenglas oder Einzug einstellen, scannen und als PDF speichern. Die Metadaten der vorhandenen `test.pdf` nennen tatsächlich `Simple Scan 50.0` als Erzeuger; sie enthält zwei Seiten. Die Metadaten allein belegen jedoch nicht, welcher Scanner dafür verwendet wurde.

Ein Beispiel für einen neuen Scan vom Vorlagenglas:

```bash
# Löst tatsächlich einen Scan aus; speichert in einem neuen temporären Ordner.
scan_dir=$(mktemp -d /tmp/hp-scan.XXXXXX)
scanimage -d 'airscan:e0:HP DeskJet 4220e' \
  --source Flatbed --mode Color --resolution 300 \
  -x 210 -y 297 --format=png \
  --output-file="$scan_dir/scan.png"
printf 'Scan gespeichert: %s\n' "$scan_dir/scan.png"
```

`-x` und `-y` legen die Scanfläche in Millimetern fest, hier A4. Für den Einzug unterstützt das Gerät `--source ADF`; mehrseitige PDFs lassen sich bequem in der GUI erstellen. Das Beispiel wurde zur Dokumentation nicht ausgeführt, es wurde kein zusätzlicher Scan gestartet.

Die Scanner-Einstellungen sind dauerhaft in `/etc/sane.d/` gespeichert. Nach einem Neustart müssen der HP erreichbar, Avahi aktiv und der `.local`-Name auflösbar sein. Eine Neuinstallation oder manuelle Aktivierung des Scanners pro Sitzung ist nicht erforderlich.

## 3. Druckdienste im WLAN finden

Viele Netzwerkdrucker veröffentlichen ihre Dienste über mDNS/DNS-SD, häufig „Bonjour“ genannt. Unter Linux übernimmt das hier Avahi:

```bash
systemctl is-active avahi-daemon
avahi-browse -rt _ipp._tcp
avahi-browse -rt _ipps._tcp
```

`_ipp._tcp` sucht nach IPP-Druckdiensten, `_ipps._tcp` nach deren TLS-geschützter Variante. Bei `avahi-browse` löst `-r` die gefundenen Dienste in Hostname, Adresse und Port auf; `-t` beendet die Abfrage nach dem Durchlauf.

Beim HP ergab die Suche:

```text
hostname = HP24FBE39B886C.local
address  = 192.168.58.145
port     = 631
rp       = ipp/print
```

Aus Hostname, Port und dem Ressourcenpfad `rp` ergibt sich die Druckadresse:

```text
ipp://HP24FBE39B886C.local:631/ipp/print
```

Die aktuelle Adresse eines bekannten Namens lässt sich auch separat abfragen:

```bash
getent hosts HP24FBE39B886C.local
```

Die IP-Adresse kann sich durch DHCP ändern. Deshalb verwendet die Einrichtung den `.local`-Namen. In der Scanner-Datei stand noch eine ältere, auskommentierte IP-Adresse.

Diese Suche findet Geräte, die entsprechende Dienste im lokalen Netz bekanntgeben, nicht sämtliche WLAN-Geräte. Gastnetze, Client-Isolation oder getrennte Netzsegmente können die Erkennung verhindern.

## 4. Drucker direkt befragen

Mit `ipptool` lässt sich prüfen, ob der Druckdienst antwortet und welche Fähigkeiten er meldet:

```bash
ipptool -tv \
  ipp://HP24FBE39B886C.local:631/ipp/print \
  /usr/share/cups/ipptool/get-printer-attributes.test
```

`-t` zeigt das Testergebnis, `-v` zusätzlich die Protokolldetails. Die `.test`-Datei beschreibt hier eine reine Statusabfrage; sie druckt nichts.

Der HP meldete `idle`, `printer-is-accepting-jobs=true`, A4-Papier und Unterstützung für IPP Everywhere. Außerdem zeigte die Abfrage: PDF wird nicht direkt unterstützt, unter anderem aber PWG-Raster und Apple Raster. Diese Formatangabe ist entscheidend, wenn man ohne lokalen Druckdienst drucken möchte.

## 5. CUPS dauerhaft aktivieren

CUPS verwaltet unter Linux Druckerwarteschlangen und verarbeitet Druckaufträge für Anwendungen. Zu Beginn war es deaktiviert:

```bash
lpstat -t
systemctl is-active cups.service
systemctl is-enabled cups.service
```

`lpstat -t` zeigt den Druckdienst, Standarddrucker, Warteschlangen und Aufträge. Anfangs erschien `scheduler is not running`.

Aktiviert wurde CUPS mit Administratorrechten:

```bash
sudo systemctl enable --now cups.service
```

`--now` startet den Dienst sofort; `enable` aktiviert ihn für folgende Systemstarts. Die Administrator-Authentifizierung erfolgte im Terminal des Benutzers.

## 6. Druckerwarteschlange einrichten

```bash
sudo lpadmin -p HP_DeskJet_4220e -E \
  -D 'HP DeskJet 4220e (WLAN)' \
  -v ipp://HP24FBE39B886C.local:631/ipp/print \
  -m everywhere \
  -o media-default=iso_a4_210x297mm \
  -o printer-is-shared=false

lpoptions -d HP_DeskJet_4220e
```

Die Optionen bedeuten:

- `-p`: Name der lokalen Warteschlange.
- `-E` an dieser Position nach `-p`: Drucker aktivieren und Aufträge annehmen.
- `-D`: Lesbare Beschreibung für Druckdialoge.
- `-v`: Netzwerkadresse des Druckdienstes.
- `-m everywhere`: IPP Everywhere verwenden; CUPS ermittelt die Fähigkeiten vom Gerät, ohne ein separates HP-Treiberpaket.
- `media-default`: A4 als Papierformat voreinstellen.
- `printer-is-shared=false`: Diese lokale Warteschlange nicht zusätzlich für andere Rechner freigeben.
- `lpoptions -d`: Standarddrucker für den aktuellen Benutzer festlegen.

Die Befehle wurden als Einrichtungsskript vorbereitet und anschließend vom Benutzer ausgeführt. Die Warteschlange und ihre Einstellungen werden von CUPS dauerhaft gespeichert; die Benutzervorgaben von `lpoptions` bleiben ebenfalls erhalten.

## 7. Testdruck und normaler Druckweg

Der bestätigte Testdruck erfolgte schon vor der CUPS-Einrichtung direkt über IPP. Dazu wurde `test.pdf` mit Ghostscript in PWG-Raster mit 300 dpi und sRGB-Farben umgewandelt und mit `ipptool` gesendet. Der HP bestätigte Auftrag 2 als `completed`, mit zwei Seiten auf zwei Blättern.

Der erfolgreiche direkte Druckweg war:

```bash
# Nur zur Nachvollziehbarkeit: Der zweite Befehl druckt erneut!
gs -q -dSAFER -dBATCH -dNOPAUSE \
  -sDEVICE=cups -sMediaClass=PwgRaster -r300 \
  -sPAPERSIZE=a4 -dPDFFitPage \
  -dcupsBitsPerColor=8 -dcupsColorSpace=19 -dcupsColorOrder=0 \
  -sOutputFile=/tmp/hp-test-20261009-rgb.pwg test.pdf

ipptool -tv -T 30 -d filetype=image/pwg-raster \
  -f /tmp/hp-test-20261009-rgb.pwg \
  ipp://HP24FBE39B886C.local:631/ipp/print \
  /usr/share/cups/ipptool/print-job-and-wait.test
```

Ghostscript rendert die PDF-Seiten in das vom HP unterstützte Rasterformat; die Farboptionen wählen 8 Bit pro Farbkanal und sRGB. `ipptool` sendet die Datei mit ihrem Format und wartet anschließend auf einen Endzustand. Entscheidend war die Rückmeldung `job-state=completed` zusammen mit `job-media-sheets-completed=2`. Ein erster Versuch mit ungeeigneten Rastereinstellungen war vom Gerät als `document-format-error` abgewiesen worden.

Nach der Einrichtung übernimmt CUPS die nötige Formatumwandlung. Der normale Druckbefehl lautet:

```bash
# Sendet tatsächlich einen neuen Druckauftrag:
lp -d HP_DeskJet_4220e -o media=A4 test.pdf
```

Dieser Befehl ist hier als Anleitung dokumentiert; nach der Einrichtung wurde kein weiterer Testdruck ausgelöst. GUI-Anwendungen können über ihren Druckdialog, meist `Strg+P`, dieselbe Warteschlange verwenden.

## 8. Ergebnis kontrollieren – auch nach einem Neustart

```bash
systemctl is-enabled cups.service
systemctl is-active cups.service
lpstat -t
```

Die abschließende Prüfung ergab:

```text
enabled
active
scheduler is running
system default destination: HP_DeskJet_4220e
HP_DeskJet_4220e accepting requests
printer HP_DeskJet_4220e is idle
```

Damit ist die Einrichtung dauerhaft. Nach einem Neustart den Handy-Hotspot einschalten und Laptop sowie Drucker wieder damit verbinden. Sobald beide im Hotspot-Netz gegenseitig erreichbar sind, können die gespeicherten Druck- und Scan-Einträge wieder verwendet werden. Ein tatsächlicher Neustart wurde im Rahmen der Einrichtung nicht durchgeführt.
