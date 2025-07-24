![[Pasted image 20250723203643.png]]

![[Pasted image 20250723203951.png]]

### (a) Sortieren der Zahlenfolge mit MergeSort

Die gegebene Zahlenfolge ist: $1, 3, 8, 9, 4, 7, 2, 5$.

MergeSort ist ein Divide-and-Conquer-Algorithmus. Wir teilen die Liste rekursiv in zwei Hälften, bis wir einzelne Elemente haben, und mergen sie dann wieder aufsteigend.

#### **Divide-Schritte**

1.  **Originalfolge:** $[1, 3, 8, 9, 4, 7, 2, 5]$
    * Teilen in: $[1, 3, 8, 9]$ und $[4, 7, 2, 5]$

2.  **Erste Hälfte teilen:** $[1, 3, 8, 9]$
    * Teilen in: $[1, 3]$ und $[8, 9]$
    * Teilen von $[1, 3]$ in: $[1]$ und $[3]$
    * Teilen von $[8, 9]$ in: $[8]$ und $[9]$

3.  **Zweite Hälfte teilen:** $[4, 7, 2, 5]$
    * Teilen in: $[4, 7]$ und $[2, 5]$
    * Teilen von $[4, 7]$ in: $[4]$ und $[7]$
    * Teilen von $[2, 5]$ in: $[2]$ und $[5]$

#### **Merge-Schritte**

1.  **Merge der kleinsten Teile:**
    * Merge $[1]$ und $[3]$ $\rightarrow$ $[1, 3]$
    * Merge $[8]$ und $[9]$ $\rightarrow$ $[8, 9]$
    * Merge $[4]$ und $[7]$ $\rightarrow$ $[4, 7]$
    * Merge $[2]$ und $[5]$ $\rightarrow$ $[2, 5]$

2.  **Merge der nächsten Ebene:**
    * Merge $[1, 3]$ und $[8, 9]$ $\rightarrow$ $[1, 3, 8, 9]$
    * Merge $[4, 7]$ und $[2, 5]$ $\rightarrow$ $[2, 4, 5, 7]$

3.  **Letzter Merge-Schritt:**
    * Merge $[1, 3, 8, 9]$ und $[2, 4, 5, 7]$ $\rightarrow$ $[1, 2, 3, 4, 5, 7, 8, 9]$

**Sortierte Folge:** $[1, 2, 3, 4, 5, 7, 8, 9]$

---

### (b) Ist MergeSort stabil?

Ja, **MergeSort ist stabil**. 🎓

**Begründung:** Die Stabilität von MergeSort ergibt sich aus der Art und Weise, wie der Merge-Schritt implementiert wird. Beim Zusammenführen von zwei Teillisten $L_1$ und $L_2$ wird immer das Element zuerst in die gemergte Liste eingefügt, das den **kleineren Wert** hat. Wenn die Elemente in $L_1$ und $L_2$ **denselben Wert** haben, wird bevorzugt das Element aus $L_1$ zuerst genommen. Dies gewährleistet, dass die relative Reihenfolge von Elementen mit gleichen Werten aus der ursprünglichen Liste erhalten bleibt.


---

### (c) Asymptotische Laufzeit von MergeSort$_3$

MergeSort$_3$ teilt eine Folge $S$ im Divide-Schritt in **drei** Teilfolgen ($S_1, S_2, S_3$) der Größe $n/3$ auf und verschmilzt im Merge-Schritt **drei** Mengen miteinander.

Die Rekurrenzgleichung für MergeSort$_3$ kann wie folgt formuliert werden:

$T(n) = 3 \cdot T(n/3) + f(n)$

Hierbei:
* $T(n)$: Die Laufzeit für eine Liste der Größe $n$.
* $3 \cdot T(n/3)$: Repräsentiert die rekursiven Aufrufe für die drei Drittel der Liste.
* $f(n)$: Die Zeit, die für das Mergen der drei sortierten Teillisten benötigt wird.

Das Mergen von $k$ sortierten Listen der Gesamtlänge $n$ benötigt $O(n)$ Zeit. Beim Mergen von drei Teillisten der Größe $n/3$ müssen wir im schlimmsten Fall jedes der $n$ Elemente einmal anfassen und vergleichen, um sie zu einer sortierten Liste zusammenzufügen. Dies ist vergleichbar mit dem Mergen zweier Listen, nur dass hier drei Zeiger verwaltet werden. Daher ist die Merg-Operation immer noch linear zur Gesamtanzahl der Elemente, also $O(n)$.

Somit lautet die Rekurrenzgleichung:

$T(n) = 3 \cdot T(n/3) + O(n)$

Wir können den Mastersatz (Master Theorem) verwenden, um die asymptotische Laufzeit zu bestimmen. Der Mastersatz hat die Form $T(n) = aT(n/b) + f(n)$.
In unserem Fall:
* $a = 3$ (Anzahl der rekursiven Aufrufe)
* $b = 3$ (Faktor, um den die Eingabe bei jedem rekursiven Aufruf reduziert wird)
* $f(n) = O(n)$

Wir vergleichen $f(n)$ mit $n^{\log_b a}$.
$\log_b a = \log_3 3 = 1$.
Also vergleichen wir $f(n) = O(n)$ mit $n^1$.

Da $f(n) = n^{\log_b a}$, fällt dieser Fall unter den zweiten Fall des Mastersatzes, der besagt:
Wenn $f(n) = \Theta(n^{\log_b a})$, dann ist $T(n) = \Theta(n^{\log_b a} \log n)$.

Daher ist die asymptotische Laufzeit von MergeSort$_3$:

$T(n) = \Theta(n \log n)$

Die asymptotische Laufzeit von MergeSort$_3$ bleibt somit **$O(n \log n)$**, genau wie beim standardmäßigen MergeSort, da der zusätzliche Faktor von 3 in den rekursiven Aufrufen und der Basisfaktor 3 für die Division sich im Logarithmus aufheben.

![[Pasted image 20250723212833.png]]