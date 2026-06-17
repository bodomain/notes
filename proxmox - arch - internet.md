# Warum hatte mein Proxmox keinen Internetzugang?

## Das Setup

Wir hatten folgendes Netzwerk:

```text
Internet
    |
 WLAN-Router
    |
   wlan0
+---------+
|  Arch   |
|  Linux  |
+---------+
   enp5s0
    |
    |
+---------+
| Proxmox |
+---------+
```

IP-Adressen:

```text
Arch WLAN:     192.168.125.79
Router:        192.168.125.12

Arch LAN:      10.42.0.1
Proxmox:       10.42.0.101
```

---

# Was funktionierte?

## Proxmox konnte Arch erreichen

```bash
ping 10.42.0.1
```

funktionierte.

Das bedeutet:

* Kabel OK
* Switch OK
* Interface OK
* IP-Adressen OK

---

## Arch konnte das Internet erreichen

```bash
ping 8.8.8.8
```

funktionierte.

Das bedeutet:

* WLAN OK
* Router OK
* DNS vermutlich OK

---

## Proxmox konnte NICHT ins Internet

```bash
ping 8.8.8.8
```

funktionierte nicht.

Damit blieb nur noch:

```text
Proxmox -> Arch -> Internet
```

also der Routing-Pfad über Arch.

---

# Routing vs NAT

Viele Anfänger verwechseln diese beiden Begriffe.

---

## Routing

Routing bedeutet:

> Wohin muss ein Paket geschickt werden?

Proxmox hatte:

```bash
ip route
```

```text
default via 10.42.0.1
```

Das bedeutet:

> Alles, was ich nicht kenne, schicke ich an Arch.

Das war korrekt.

---

## NAT

Jetzt kommt der wichtige Teil.

Proxmox schickt:

```text
Quelle: 10.42.0.101
Ziel:   8.8.8.8
```

an Arch.

Arch leitet das weiter.

Der Router im WLAN sieht nun:

```text
Von: 10.42.0.101
Nach: 8.8.8.8
```

und denkt:

> Was zum Teufel ist 10.42.0.101?

Denn er kennt nur:

```text
192.168.125.x
```

also verwirft er die Antwort.

---

# Lösung: NAT

Arch muss die Adresse umschreiben.

Aus:

```text
10.42.0.101
```

wird:

```text
192.168.125.79
```

Das nennt man:

```text
NAT
Network Address Translation
```

bzw.

```text
MASQUERADE
```

unter Linux.

Regel:

```bash
iptables -t nat \
  -A POSTROUTING \
  -s 10.42.0.0/24 \
  -o wlan0 \
  -j MASQUERADE
```

---

# Warum funktionierte es trotzdem nicht?

Hier wurde es interessant.

Wir hatten NAT korrekt eingerichtet.

Trotzdem:

```text
Proxmox -> Internet
```

funktionierte nicht.

---

# Die Firewall

Linux hat mehrere Schichten:

```text
Routing
   ↓
Forwarding
   ↓
NAT
   ↓
Internet
```

Bei uns existierte:

```text
table inet filter
```

mit:

```text
chain forward {
    policy drop;
}
```

Das bedeutet:

> Alles wird verworfen.

---

# Was ist FORWARD?

Linux kann drei Arten von Traffic sehen.

---

## INPUT

```text
Internet
   ↓
Arch
```

Pakete FÜR den Rechner.

---

## OUTPUT

```text
Arch
   ↓
Internet
```

Pakete VOM Rechner.

---

## FORWARD

```text
Proxmox
   ↓
Arch
   ↓
Internet
```

Pakete DURCH den Rechner.

Genau das wollten wir.

---

# Der Fehler

Unsere nftables-Regel sagte:

```text
FORWARD = DROP
```

also:

```text
Proxmox
   ↓
Arch
   X
```

Ende.

Die Pakete wurden verworfen.

Sie erreichten niemals NAT.

---

# Die Lösung

Wir erlaubten Weiterleitung.

```nft
chain forward {
    policy drop;

    iifname "enp5s0" \
        oifname "wlan0" \
        ip saddr 10.42.0.0/24 \
        accept

    iifname "wlan0" \
        oifname "enp5s0" \
        ip daddr 10.42.0.0/24 \
        ct state established,related \
        accept
}
```

---

# Warum braucht man zwei Regeln?

## Hinweg

```text
Proxmox -> Internet
```

muss erlaubt sein.

---

## Rückweg

```text
Internet -> Proxmox
```

muss ebenfalls erlaubt sein.

Deshalb:

```text
established,related
```

---

# nftables vs iptables

Historisch:

```text
iptables
```

war die Firewall.

Heute:

```text
nftables
```

ist die moderne Variante.

Auf Arch verwendet man meist:

```text
iptables-nft
```

also:

```text
iptables
    ↓
Übersetzung
    ↓
nftables
```

Deshalb waren wir kurz verwirrt.

---

# Wie debuggt man sowas?

Immer Schicht für Schicht.

---

## Schritt 1

Kann Proxmox Arch erreichen?

```bash
ping 10.42.0.1
```

Ja.

---

## Schritt 2

Kann Arch Internet erreichen?

```bash
ping 8.8.8.8
```

Ja.

---

## Schritt 3

Ist Routing aktiv?

```bash
sysctl net.ipv4.ip_forward
```

```text
= 1
```

Ja.

---

## Schritt 4

Existiert NAT?

```bash
iptables -t nat -L
```

Ja.

---

## Schritt 5

Existiert eine Firewall?

```bash
nft list ruleset
```

Ja.

---

## Schritt 6

Suche nach:

```text
policy drop
```

Bingo.

---

# Merksatz

Wenn

```text
Client -> Gateway      funktioniert
Gateway -> Internet    funktioniert
Client -> Internet     funktioniert NICHT
```

dann sind die häufigsten Ursachen:

1. NAT fehlt
2. IP-Forwarding fehlt
3. FORWARD-Policy blockiert
4. Rückroute fehlt

In genau dieser Reihenfolge sollte man suchen.

---

# Was wir am Ende gebaut haben

Arch ist jetzt ein kleiner Linux-Router:

```text
Internet
    |
 WLAN
    |
+---------+
|  Arch   |
| Router  |
+---------+
    |
 Ethernet
    |
+---------+
| Proxmox |
+---------+
```

mit:

* Routing ✅
* NAT/Masquerading ✅
* Stateful Firewall ✅
* Persistenter nftables-Konfiguration ✅

Das ist im Prinzip dieselbe Grundidee, die auch in Heimroutern, Firewalls, pfSense, OPNsense und vielen Cloud-Gateways verwendet wird.
