![[Pasted image 20250724153147.png]]


Die zu sortierenden Wörter sind:
**Pike, Kirk, Picard, Data, Janeway, Riker, Archer, Burnham, Worf, Spock**

Radixsort sortiert Elemente basierend auf einzelnen Ziffern (oder Zeichen) beginnend von der niedrigstwertigsten Position (rechts) bis zur höchstwertigsten Position (links). Da es sich um Wörter handelt, betrachten wir die Zeichen als unsere "Ziffern" und das Alphabet als unsere "Basis". Wir müssen die Wörter zuerst auf die gleiche Länge bringen, indem wir kürzere Wörter mit einem speziellen "Padding"-Zeichen (oft ein Leerzeichen oder ein leeres Zeichen, das alphabetisch vor allen Buchstaben steht) auffüllen.

Die längsten Wörter in unserer Liste haben 7 Buchstaben ("Janeway", "Burnham", "Picard", "Archer"). Wir werden alle Wörter auf 7 Zeichen auffüllen. Wir verwenden '_' als Padding-Zeichen, das als kleiner als jeder Buchstabe behandelt wird.

**Initialer Zustand (aufgefüllt):**
PIKE___
KIRK___
PICARD_
DATA___
JANEWAY
RIKER__
ARCHER_
BURNHAM
WORF___
SPOCK__

Wir sortieren von rechts nach links, d.h., beginnend mit dem 7. Zeichen, dann dem 6. Zeichen, usw., bis zum 1. Zeichen.

---

### **Phase 1: Sortieren nach dem 7. Zeichen (rechteste Position)**

Wir haben 27 Behälter (26 für Buchstaben A-Z, 1 für '_').

* **Pike:** $E \rightarrow$ Behälter 'E'
* **Kirk:** $K \rightarrow$ Behälter 'K'
* **Picard:** $D \rightarrow$ Behälter 'D'
* **Data:** $A \rightarrow$ Behälter 'A'
* **Janeway:** $Y \rightarrow$ Behälter 'Y'
* **Riker:** $R \rightarrow$ Behälter 'R'
* **Archer:** $R \rightarrow$ Behälter 'R'
* **Burnham:** $M \rightarrow$ Behälter 'M'
* **Worf:** $F \rightarrow$ Behälter 'F'
* **Spock:** $K \rightarrow$ Behälter 'K'

**Inhalte der nicht-leeren Behälter nach Phase 1:**
* **Behälter 'A':** [Data]
* **Behälter 'D':** [Picard]
* **Behälter 'E':** [Pike]
* **Behälter 'F':** [Worf]
* **Behälter 'K':** [Kirk, Spock]  *(Stabilität ist hier wichtig: Kirk kam vor Spock)*
* **Behälter 'M':** [Burnham]
* **Behälter 'R':** [Riker, Archer] *(Stabilität: Riker kam vor Archer)*
* **Behälter 'Y':** [Janeway]

**Reihenfolge nach Phase 1:**
DATA, PICARD, PIKE, WORF, KIRK, SPOCK, BURNHAM, RIKER, ARCHER, JANEWAY

---

### **Phase 2: Sortieren nach dem 6. Zeichen**

Wir verwenden die Reihenfolge aus Phase 1 und sortieren nach dem 6. Zeichen.

* **Data:** $A \rightarrow$ Behälter 'A'
* **Picard:** $R \rightarrow$ Behälter 'R'
* **Pike:** $K \rightarrow$ Behälter 'K'
* **Worf:** $F \rightarrow$ Behälter 'F'
* **Kirk:** $K \rightarrow$ Behälter 'K'
* **Spock:** $C \rightarrow$ Behälter 'C'
* **Burnham:** $H \rightarrow$ Behälter 'H'
* **Riker:** $E \rightarrow$ Behälter 'E'
* **Archer:** $E \rightarrow$ Behälter 'E'
* **Janeway:** $A \rightarrow$ Behälter 'A'

**Inhalte der nicht-leeren Behälter nach Phase 2:**
* **Behälter 'A':** [Data, Janeway] *(Stabilität: Data vor Janeway)*
* **Behälter 'C':** [Spock]
* **Behälter 'E':** [Riker, Archer] *(Stabilität: Riker vor Archer)*
* **Behälter 'F':** [Worf]
* **Behälter 'H':** [Burnham]
* **Behälter 'K':** [Pike, Kirk] *(Stabilität: Pike vor Kirk)*
* **Behälter 'R':** [Picard]

**Reihenfolge nach Phase 2:**
DATA, JANEWAY, SPOCK, RIKER, ARCHER, WORF, BURNHAM, PIKE, KIRK, PICARD

---

### **Phase 3: Sortieren nach dem 5. Zeichen**

Wir verwenden die Reihenfolge aus Phase 2 und sortieren nach dem 5. Zeichen.

* **Data:** $T \rightarrow$ Behälter 'T'
* **Janeway:** $W \rightarrow$ Behälter 'W'
* **Spock:** $O \rightarrow$ Behälter 'O'
* **Riker:** $R \rightarrow$ Behälter 'R'
* **Archer:** $E \rightarrow$ Behälter 'E'
* **Worf:** $F \rightarrow$ Behälter 'F'
* **Burnham:** $H \rightarrow$ Behälter 'H'
* **Pike:** $E \rightarrow$ Behälter 'E'
* **Kirk:** $K \rightarrow$ Behälter 'K'
* **Picard:** $A \rightarrow$ Behälter 'A'

**Inhalte der nicht-leeren Behälter nach Phase 3:**
* **Behälter 'A':** [Picard]
* **Behälter 'E':** [Archer, Pike] *(Stabilität: Archer vor Pike)*
* **Behälter 'F':** [Worf]
* **Behälter 'H':** [Burnham]
* **Behälter 'K':** [Kirk]
* **Behälter 'O':** [Spock]
* **Behälter 'R':** [Riker]
* **Behälter 'T':** [Data]
* **Behälter 'W':** [Janeway]

**Reihenfolge nach Phase 3:**
PICARD, ARCHER, PIKE, WORF, BURNHAM, KIRK, SPOCK, RIKER, DATA, JANEWAY

---

### **Phase 4: Sortieren nach dem 4. Zeichen**

Wir verwenden die Reihenfolge aus Phase 3 und sortieren nach dem 4. Zeichen.

* **Picard:** $A \rightarrow$ Behälter 'A'
* **Archer:** $H \rightarrow$ Behälter 'H'
* **Pike:** $E \rightarrow$ Behälter 'E'
* **Worf:** $F \rightarrow$ Behälter 'F'
* **Burnham:** $N \rightarrow$ Behälter 'N'
* **Kirk:** $K \rightarrow$ Behälter 'K'
* **Spock:** $C \rightarrow$ Behälter 'C'
* **Riker:** $K \rightarrow$ Behälter 'K'
* **Data:** $A \rightarrow$ Behälter 'A'
* **Janeway:** $E \rightarrow$ Behälter 'E'

**Inhalte der nicht-leeren Behälter nach Phase 4:**
* **Behälter 'A':** [Picard, Data] *(Stabilität: Picard vor Data)*
* **Behälter 'C':** [Spock]
* **Behälter 'E':** [Pike, Janeway] *(Stabilität: Pike vor Janeway)*
* **Behälter 'F':** [Worf]
* **Behälter 'H':** [Archer]
* **Behälter 'K':** [Kirk, Riker] *(Stabilität: Kirk vor Riker)*
* **Behälter 'N':** [Burnham]

**Reihenfolge nach Phase 4:**
PICARD, DATA, SPOCK, PIKE, JANEWAY, WORF, ARCHER, KIRK, RIKER, BURNHAM

---

### **Phase 5: Sortieren nach dem 3. Zeichen**

Wir verwenden die Reihenfolge aus Phase 4 und sortieren nach dem 3. Zeichen.

* **Picard:** $C \rightarrow$ Behälter 'C'
* **Data:** $T \rightarrow$ Behälter 'T'
* **Spock:** $O \rightarrow$ Behälter 'O'
* **Pike:** $K \rightarrow$ Behälter 'K'
* **Janeway:** $N \rightarrow$ Behälter 'N'
* **Worf:** $R \rightarrow$ Behälter 'R'
* **Archer:** $C \rightarrow$ Behälter 'C'
* **Kirk:** $R \rightarrow$ Behälter 'R'
* **Riker:** $K \rightarrow$ Behälter 'K'
* **Burnham:** $R \rightarrow$ Behälter 'R'

**Inhalte der nicht-leeren Behälter nach Phase 5:**
* **Behälter 'C':** [Picard, Archer] *(Stabilität: Picard vor Archer)*
* **Behälter 'K':** [Pike, Riker] *(Stabilität: Pike vor Riker)*
* **Behälter 'N':** [Janeway]
* **Behälter 'O':** [Spock]
* **Behälter 'R':** [Worf, Kirk, Burnham] *(Stabilität: Worf vor Kirk vor Burnham)*
* **Behälter 'T':** [Data]

**Reihenfolge nach Phase 5:**
PICARD, ARCHER, PIKE, RIKER, JANEWAY, SPOCK, WORF, KIRK, BURNHAM, DATA

---

### **Phase 6: Sortieren nach dem 2. Zeichen**

Wir verwenden die Reihenfolge aus Phase 5 und sortieren nach dem 2. Zeichen.

* **Picard:** $I \rightarrow$ Behälter 'I'
* **Archer:** $R \rightarrow$ Behälter 'R'
* **Pike:** $I \rightarrow$ Behälter 'I'
* **Riker:** $I \rightarrow$ Behälter 'I'
* **Janeway:** $A \rightarrow$ Behälter 'A'
* **Spock:** $P \rightarrow$ Behälter 'P'
* **Worf:** $O \rightarrow$ Behälter 'O'
* **Kirk:** $I \rightarrow$ Behälter 'I'
* **Burnham:** $U \rightarrow$ Behälter 'U'
* **Data:** $A \rightarrow$ Behälter 'A'

**Inhalte der nicht-leeren Behälter nach Phase 6:**
* **Behälter 'A':** [Janeway, Data] *(Stabilität: Janeway vor Data)*
* **Behälter 'I':** [Picard, Pike, Riker, Kirk] *(Stabilität: Picard vor Pike vor Riker vor Kirk)*
* **Behälter 'O':** [Worf]
* **Behälter 'P':** [Spock]
* **Behälter 'R':** [Archer]
* **Behälter 'U':** [Burnham]

**Reihenfolge nach Phase 6:**
JANEWAY, DATA, PICARD, PIKE, RIKER, KIRK, WORF, SPOCK, ARCHER, BURNHAM

---

### **Phase 7: Sortieren nach dem 1. Zeichen (linkeste Position)**

Wir verwenden die Reihenfolge aus Phase 6 und sortieren nach dem 1. Zeichen.

* **Janeway:** $J \rightarrow$ Behälter 'J'
* **Data:** $D \rightarrow$ Behälter 'D'
* **Picard:** $P \rightarrow$ Behälter 'P'
* **Pike:** $P \rightarrow$ Behälter 'P'
* **Riker:** $R \rightarrow$ Behälter 'R'
* **Kirk:** $K \rightarrow$ Behälter 'K'
* **Worf:** $W \rightarrow$ Behälter 'W'
* **Spock:** $S \rightarrow$ Behälter 'S'
* **Archer:** $A \rightarrow$ Behälter 'A'
* **Burnham:** $B \rightarrow$ Behälter 'B'

**Inhalte der nicht-leeren Behälter nach Phase 7:**
* **Behälter 'A':** [Archer]
* **Behälter 'B':** [Burnham]
* **Behälter 'D':** [Data]
* **Behälter 'J':** [Janeway]
* **Behälter 'K':** [Kirk]
* **Behälter 'P':** [Picard, Pike] *(Stabilität: Picard vor Pike)*
* **Behälter 'R':** [Riker]
* **Behälter 'S':** [Spock]
* **Behälter 'W':** [Worf]

**Endgültig sortierte Reihenfolge:**
**ARCHER, BURNHAM, DATA, JANEWAY, KIRK, PICARD, PIKE, RIKER, SPOCK, WORF**



Gerne, hier ist eine vergleichbare Aufgabe mit Uhrzeiten, die ebenfalls mit Radixsort gelöst werden kann.

---

## **Aufgabe: Sortieren von Uhrzeiten mittels Radixsort**

Sie erhalten die folgende Liste von Uhrzeiten im 24-Stunden-Format ($HH:MM:SS$):

**14:30:15, 08:05:40, 23:59:01, 00:00:00, 14:25:10, 08:10:40, 07:00:00, 20:15:30**

Sortieren Sie diese Uhrzeiten aufsteigend mittels **Radixsort**. Geben Sie dabei die Inhalte der nicht-leeren Behälter (Buckets) nach jeder Phase an.

---

### **Hinweise zur Bearbeitung:**

1.  **Stellen Sie die Uhrzeiten als eine Art "Zahl" dar, bei der jede Zifferngruppe (Sekunden, Minuten, Stunden) eine "Stelle" bildet.** Die Sortierung erfolgt von der niedrigstwertigsten zur höchstwertigsten Stelle.
2.  Die **niedrigstwertigste Stelle** sind die **Sekunden (SS)**.
3.  Die **mittlere Stelle** sind die **Minuten (MM)**.
4.  Die **höchstwertigste Stelle** sind die **Stunden (HH)**.
5.  Für jede Phase sortieren Sie die Uhrzeiten basierend auf den Werten der jeweiligen Stelle (00-59 für Sekunden/Minuten, 00-23 für Stunden). Verwenden Sie dafür 60 Behälter (0-59) für die Sekunden- und Minuten-Phasen und 24 Behälter (0-23) für die Stunden-Phase.
6.  Achten Sie auf die **Stabilität** des Sortierverfahrens innerhalb der Behälter.

---

Viel Erfolg beim Sortieren!


Gerne, hier ist die Musterlösung für die Sortierung der Uhrzeiten mittels Radixsort.

---

## **Musterlösung: Sortieren von Uhrzeiten mittels Radixsort**

**Gegebene Uhrzeiten:**
$14:30:15, 08:05:40, 23:59:01, 00:00:00, 14:25:10, 08:10:40, 07:00:00, 20:15:30$

### **Phase 1: Sortieren nach Sekunden (SS)**

Wir betrachten die letzten zwei Ziffern (SS). Es gibt 60 mögliche Werte (00-59), daher verwenden wir 60 Behälter.

* $14:30:\underline{15} \rightarrow$ Behälter 15
* $08:05:\underline{40} \rightarrow$ Behälter 40
* $23:59:\underline{01} \rightarrow$ Behälter 01
* $00:00:\underline{00} \rightarrow$ Behälter 00
* $14:25:\underline{10} \rightarrow$ Behälter 10
* $08:10:\underline{40} \rightarrow$ Behälter 40 (bleibt hinter 08:05:40 aufgrund der Stabilität)
* $07:00:\underline{00} \rightarrow$ Behälter 00 (bleibt hinter 00:00:00 aufgrund der Stabilität)
* $20:15:\underline{30} \rightarrow$ Behälter 30

**Inhalte der nicht-leeren Behälter nach Phase 1 (in aufsteigender Reihenfolge der Behälter-Nummern):**

* **Behälter 00:**
* **Behälter 01:**
* **Behälter 10:**
* **Behälter 15:**
* **Behälter 30:**
* **Behälter 40:**

**Reihenfolge nach Phase 1:**
$00:00:00, 07:00:00, 23:59:01, 14:25:10, 14:30:15, 20:15:30, 08:05:40, 08:10:40$

---

### **Phase 2: Sortieren nach Minuten (MM)**

Wir verwenden die Reihenfolge aus Phase 1 und sortieren nach den mittleren zwei Ziffern (MM). Es gibt 60 mögliche Werte (00-59), daher verwenden wir 60 Behälter.

* $00:\underline{00}:00 \rightarrow$ Behälter 00
* $07:\underline{00}:00 \rightarrow$ Behälter 00 (bleibt hinter 00:00:00)
* $23:\underline{59}:01 \rightarrow$ Behälter 59
* $14:\underline{25}:10 \rightarrow$ Behälter 25
* $14:\underline{30}:15 \rightarrow$ Behälter 30
* $20:\underline{15}:30 \rightarrow$ Behälter 15
* $08:\underline{05}:40 \rightarrow$ Behälter 05
* $08:\underline{10}:40 \rightarrow$ Behälter 10

**Inhalte der nicht-leeren Behälter nach Phase 2 (in aufsteigender Reihenfolge der Behälter-Nummern):**

* **Behälter 00:**
* **Behälter 05:**
* **Behälter 10:**
* **Behälter 15:**
* **Behälter 25:**
* **Behälter 30:**
* **Behälter 59:**

**Reihenfolge nach Phase 2:**
$00:00:00, 07:00:00, 08:05:40, 08:10:40, 20:15:30, 14:25:10, 14:30:15, 23:59:01$

---

### **Phase 3: Sortieren nach Stunden (HH)**

Wir verwenden die Reihenfolge aus Phase 2 und sortieren nach den ersten zwei Ziffern (HH). Es gibt 24 mögliche Werte (00-23), daher verwenden wir 24 Behälter.

* $\underline{00}:00:00 \rightarrow$ Behälter 00
* $\underline{07}:00:00 \rightarrow$ Behälter 07
* $\underline{08}:05:40 \rightarrow$ Behälter 08
* $\underline{08}:10:40 \rightarrow$ Behälter 08 (bleibt hinter 08:05:40)
* $\underline{20}:15:30 \rightarrow$ Behälter 20
* $\underline{14}:25:10 \rightarrow$ Behälter 14
* $\underline{14}:30:15 \rightarrow$ Behälter 14 (bleibt hinter 14:25:10)
* $\underline{23}:59:01 \rightarrow$ Behälter 23

**Inhalte der nicht-leeren Behälter nach Phase 3 (in aufsteigender Reihenfolge der Behälter-Nummern):**

* **Behälter 00:**
* **Behälter 07:**
* **Behälter 08:**
* **Behälter 14:** 
* **Behälter 20:**
* **Behälter 23:**

**Endgültig sortierte Reihenfolge:**
$00:00:00, 07:00:00, 08:05:40, 08:10:40, 14:25:10, 14:30:15, 20:15:30, 23:59:01$