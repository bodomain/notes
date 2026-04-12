
---

## 1. Das Schichten-Modell (Die Hierarchie)
In Linux fließt ein Datenpaket nicht einfach durch ein Kabel, es durchläuft eine Kette von Entscheidungen:

1.  **Physische Ebene (`wlan0`, `enp5s0`):** Deine echten Netzwerkkarten.
2.  **Virtuelle Ebene (`virbr0`, `docker0`):** Software-basierte Switches (Bridges), die im Kernel leben.
3.  **Routing-Tabelle (`ip route`):** Das "Navigationsgerät", das entscheidet: "Geht dieses Paket an die VM oder ins Internet?"



---

## 2. Die Firewall-Wächter (iptables & nftables)
Stell dir `iptables` wie eine Checkliste für Pakete vor. Es gibt drei Haupt-Listen (Chains):

* **INPUT:** Pakete, die direkt an deinen Arch-Host gerichtet sind.
* **OUTPUT:** Pakete, die dein Arch-Host selbst verschickt.
* **FORWARD:** (Wichtig für VMs!) Pakete, die nur "durchreisen" wollen (vom VM-Netz ins Internet).

### Die "NAT"-Tabelle (Network Address Translation)
Damit deine VM (z. B. `192.168.122.189`) ins Internet kann, muss der Host sie "maskieren". Das Internet kennt deine interne VM-IP nicht.
* **Masquerade:** Der Host ersetzt die Absender-IP der VM durch seine eigene (`wlan0`-IP).

> **Merksatz:** Ohne `MASQUERADE` finden Pakete zwar den Weg nach draußen, aber die Antwort weiß nicht, wohin sie zurückkehren soll.

---

## 3. Die Werkzeugkiste (Commands)

| Befehl | Zweck |
| :--- | :--- |
| `ip a` | Zeigt alle IP-Adressen und den Status (UP/DOWN) der Interfaces. |
| `ip route` | Zeigt, welches Interface das "Standard-Tor" (`default`) zur Welt ist. |
| `sudo sysctl -w net.ipv4.ip_forward=1` | Schaltet die "Durchreise-Erlaubnis" im Kernel ein. |
| `sudo iptables -L -v -n` | Listet alle Firewall-Regeln (sehr detailliert mit Paket-Zählern). |
| `sudo virsh net-list --all` | Zeigt den Status des VM-Netzwerks an. |



---

## 4. Häufige Fallstricke auf Arch Linux
Arch ist minimalistisch, daher werden Dienste oft nicht automatisch gestartet:

* **Dienst-Abhängigkeit:** Wenn `libvirtd` läuft, aber `dnsmasq` fehlt, bekommt die VM keine IP (DHCP schlägt fehl).
* **Modul-Laden:** Manchmal vergisst der Kernel das `bridge`-Modul. Ein `sudo modprobe bridge` hilft.
* **Der "Docker-Effekt":** Docker setzt die `FORWARD`-Policy oft global auf `DROP`. Das blockiert Virt-Manager. Die Lösung ist, die VM-Regel ganz oben einzufügen (`-I` statt `-A`).

---

## 5. Profi-Workflow für Fehlerdiagnose
Wenn der Ping mal wieder stirbt, folge dieser Kette:
1.  **VM zu Host:** `ping 192.168.122.1` (Ist das Kabel virtuell eingesteckt?)
2.  **Host zu Außen:** `ping 8.8.8.8` auf Arch (Hat der Host selbst Internet?)
3.  **VM zu Außen (IP):** `ping 8.8.8.8` in der VM (Funktioniert das Routing/NAT?)
4.  **VM zu Außen (DNS):** `ping google.com` (Funktioniert die Namensauflösung?)

---
