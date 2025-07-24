Die **Stabilität** eines Sortierverfahrens beschreibt eine Eigenschaft, bei der die **relative Reihenfolge** von Elementen mit **gleichen Werten** im sortierten Array beibehalten wird. Das bedeutet, wenn zwei Elemente im ursprünglichen Array denselben Wert haben, aber in unterschiedlichen Positionen vorkommen, dann müssen sie nach dem Sortieren immer noch in derselben Reihenfolge zueinander stehen wie vor dem Sortieren.

---

## **Beispiel zur Veranschaulichung**

Stellen Sie sich eine Liste von Objekten vor, die nach einem bestimmten Kriterium (z.B. Alter) sortiert werden sollen. Jedes Objekt hat zusätzlich eine eindeutige ID:

**Unsortiertes Array:**
$[(A, 25), (B, 30), (C, 25)]$

Hierbei ist der erste Wert (A, B, C) eine ID und der zweite Wert (25, 30, 25) das Sortierkriterium (Alter). Wir wollen nach Alter aufsteigend sortieren.

**1. Stabiles Sortierverfahren:**
Wenn ein **stabiles** Sortierverfahren verwendet wird, wäre das Ergebnis:
$[(A, 25), (C, 25), (B, 30)]$
Beachten Sie, dass $(A, 25)$ vor $(C, 25)$ stand und diese Reihenfolge beibehalten wurde, da beide das Alter 25 haben.

**2. Instabiles Sortierverfahren:**
Ein **instabiles** Sortierverfahren könnte folgendes Ergebnis liefern:
$[(C, 25), (A, 25), (B, 30)]$
Hier wurde die ursprüngliche relative Reihenfolge von $(A, 25)$ und $(C, 25)$ vertauscht, obwohl sie denselben Sortierwert (25) haben.

---

## **Bedeutung der Stabilität**

Die Stabilität ist besonders wichtig, wenn:

* **Mehrere Sortierschlüssel** vorhanden sind: Wenn Daten nach mehreren Kriterien sortiert werden, kann ein stabiles Sortierverfahren sicherstellen, dass vorherige Sortierungen für gleiche Werte nicht aufgehoben werden.
* **Zusätzliche Informationen** mit den Werten verknüpft sind: Wenn die Reihenfolge von Elementen mit gleichen Werten eine semantische Bedeutung hat (wie im obigen Beispiel mit den IDs), ist Stabilität unerlässlich, um diese Bedeutung zu erhalten.

---

## **Beispiele für stabile und instabile Sortierverfahren**

**Stabile Sortierverfahren:**
* **Merge Sort**
* **Insertion Sort**
* **Bubble Sort**
* **Counting Sort**
* **Radix Sort**

**Instabile Sortierverfahren:**
* **Quick Sort** (Standard-Implementierung)
* **Heap Sort**
* **Selection Sort**

Es ist wichtig zu beachten, dass viele instabile Sortierverfahren durch Modifikationen oder spezielle Implementierungen **stabil gemacht werden können**, oft jedoch auf Kosten einer erhöhten Zeit- oder Platzkomplexität. 