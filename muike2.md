Gerne, hier sind die Lösungen für die Aufgaben mit den jeweiligen Begründungen.

Zur Erinnerung die Symbole:
* **$\in$ (Element von):** Ein Objekt ist ein Mitglied einer Menge. (z.B. $3 \in \{1, 2, 3\}$)
* **$\notin$ (Nicht Element von):** Ein Objekt ist kein Mitglied einer Menge. (z.B. $4 \notin \{1, 2, 3\}$)
* **$\subset$ (Teilmenge von):** Jedes Element der linken Menge ist auch in der rechten Menge enthalten. (z.B. $\{1, 2\} \subset \{1, 2, 3\}$)
* **$\not\subset$ (Keine Teilmenge von):** Mindestens ein Element der linken Menge ist nicht in der rechten Menge. (z.B. $\{1, 4\} \not\subset \{1, 2, 3\}$)
* **$=$ (Gleich):** Beide Seiten (Zahlen oder Mengen) sind identisch. (z.B. $\{1, 2\} = \{2, 1\}$)

---

### Lösungen und Begründungen

1.  **$5 = 5$**
    * **Begründung:** Hier werden zwei Zahlen verglichen. Die Zahl 5 ist identisch mit der Zahl 5. Die Symbole $\in$ oder $\subset$ würden eine Menge auf der rechten Seite erfordern, die hier nicht gegeben ist.

2.  **$5 \in \{5\}$**
    * **Begründung:** Wir vergleichen ein Element (die Zahl 5) mit einer Menge (der Menge, die die Zahl 5 enthält). Die Zahl 5 ist ein Mitglied, also ein **Element**, dieser Menge.

3.  **$100.1 \notin \mathbb{Z}$**
    * **Begründung:** $\mathbb{Z}$ ist die Menge der ganzen Zahlen (z.B. ..., -2, -1, 0, 1, 2, ...). Die Zahl 100.1 ist eine Dezimalzahl (eine reelle Zahl), aber **keine ganze Zahl**. Daher ist sie kein Element von $\mathbb{Z}$.

4.  **$\{\pi\} \subset \mathbb{R}$**
    * **Begründung:** Hier wird eine Menge mit einer Menge verglichen. Die linke Seite ist die Menge, die nur die Zahl $\pi$ (Pi) enthält. Die rechte Seite ist $\mathbb{R}$, die Menge aller reellen Zahlen. Da $\pi$ eine reelle Zahl ist, ist jedes Element der linken Menge (also $\pi$ selbst) auch in der rechten Menge $\mathbb{R}$ enthalten. Daher ist die linke Menge eine **Teilmenge** der rechten.

5.  **$\{-1, 0, 1\} \subset \mathbb{Z}$**
    * **Begründung:** Wir vergleichen zwei Mengen. Jedes Element der linken Menge (die Zahlen -1, 0 und 1) ist eine ganze Zahl und somit auch in der Menge der ganzen Zahlen $\mathbb{Z}$ enthalten. Die linke Menge ist also eine **Teilmenge** von $\mathbb{Z}$.

6.  **$\{-1, 0, 1\} \not\subset \mathbb{N}$**
    * **Begründung:** $\mathbb{N}$ ist die Menge der natürlichen Zahlen (je nach Definition $\{1, 2, 3, ...\}$ oder $\{0, 1, 2, ...\}$). In jedem Fall ist die negative Zahl **-1**, die ein Element der linken Menge ist, **kein** Element der natürlichen Zahlen $\mathbb{N}$. Da nicht alle Elemente der linken Menge in der rechten Menge enthalten sind, ist sie **keine Teilmenge**.

7.  **$\{0, 1\} \subset \mathbb{Z} \cap [-10, 1.5]$**
    * **Begründung:** Zuerst bestimmen wir die rechte Menge. $\mathbb{Z} \cap [-10, 1.5]$ ist die Schnittmenge der ganzen Zahlen $\mathbb{Z}$ und dem Intervall aller Zahlen von -10 bis 1.5. Wir suchen also alle *ganzen Zahlen* in diesem Intervall. Das sind: $\{-10, -9, -8, -7, -6, -5, -4, -3, -2, -1, 0, 1\}$.
    * Jetzt vergleichen wir $\{0, 1\}$ mit dieser neuen Menge. Sowohl 0 als auch 1 sind in der Menge $\{-10, ..., 1\}$ enthalten. Daher ist $\{0, 1\}$ eine **Teilmenge** der rechten Menge.

8.  **$\{5\} = [1, 5] \cap [5, 10]$**
    * **Begründung:** Wir bestimmen wieder zuerst die rechte Menge. $[1, 5] \cap [5, 10]$ ist die Schnittmenge des Intervalls von 1 bis 5 (einschließlich) und des Intervalls von 5 bis 10 (einschließlich). Die *einzige* Zahl, die in beiden Intervallen gleichzeitig liegt, ist die Zahl 5.
    * Die rechte Menge ist also identisch mit der Menge $\{5\}$. Da die linke Menge ebenfalls $\{5\}$ ist, sind die beiden Mengen **gleich**.

---

War das verständlich? Soll ich eines der Konzepte, wie "Schnittmenge" oder die verschiedenen Zahlenmengen ($\mathbb{N}, \mathbb{Z}, \mathbb{R}$), genauer erklären?



Die Menge BnB^nBn (also alle Wörter der Länge nnn über BBB) lässt sich als Vereinigung aller Tupel der Länge nnn von Elementen aus BBB darstellen. Formal:

Bn={(b1,b2,...,bn)∣bi∈B}B^n = \{ (b_1, b_2, ..., b_n) \mid b_i \in B \}Bn={(b1,b2,...,bn)∣bi∈B}

Wenn du besonders die Vereinigung betonen möchtest, kann man dies so schreiben:

$Bn=⋃(b1,...,bn)∈B×...×B{(b1,...,bn)}B^n = \bigcup_{(b_1, ..., b_n) \in B \times ... \times B} \{ (b_1, ..., b_n) \}Bn=(b1,...,bn)∈B×...×B⋃{(b1,...,bn)}$

Das heißt, BnB^nBn ist die Vereinigung aller einzelner nnn-Tupel, wobei jedes bib_ibi aus BBB stammt. In der Praxis ist dies jedoch die direkte Produktmenge (das kartesische Produkt) von BBB mit sich selbst, nnn-mal.[informatik.uni-hamburg+1](https://www2.informatik.uni-hamburg.de/TGI/lehre/vl/SS14/FGI1/Lesestoff/Lesestoff1_DFA.pdf)​

Im Standard wird BnB^nBn meist als das nnn-fache kartesische Produkt geschrieben und enthält alle möglichen nnn-Tupel mit Einträgen aus BBB, also:

Bn=B×B×⋯×BB^n = B \times B \times \cdots \times BBn=B×B×⋯×B

Die einzelne Vereinigungsschreibweise wie oben ist ein formalisierter Zugang, wird aber selten genutzt, da das Produkt klarer und kompakter ist.

1. [https://www2.informatik.uni-hamburg.de/TGI/lehre/vl/SS14/FGI1/Lesestoff/Lesestoff1_DFA.pdf](https://www2.informatik.uni-hamburg.de/TGI/lehre/vl/SS14/FGI1/Lesestoff/Lesestoff1_DFA.pdf)
2. [https://de.wikipedia.org/wiki/Formale_Sprache](https://de.wikipedia.org/wiki/Formale_Sprache)
3. [http://www.lernhelfer.de/schuelerlexikon/mathematik/artikel/vereinigungsmenge](http://www.lernhelfer.de/schuelerlexikon/mathematik/artikel/vereinigungsmenge)
4. [http://www.informatik.uni-leipzig.de/~brewka/papers/1-2.EndlicheAutomaten.pdf](http://www.informatik.uni-leipzig.de/~brewka/papers/1-2.EndlicheAutomaten.pdf)
5. [https://de.wikipedia.org/wiki/Alphabet_(Informatik)](https://de.wikipedia.org/wiki/Alphabet_\(Informatik\))
6. [https://wp-prd.let.ethz.ch/analysis19/chapter/mengenlehre-und-abbildungen/](https://wp-prd.let.ethz.ch/analysis19/chapter/mengenlehre-und-abbildungen/)
7. [https://www.mathematik.uni-muenchen.de/~pareigis/Vorlesungen/98WS/linalg1.pdf](https://www.mathematik.uni-muenchen.de/~pareigis/Vorlesungen/98WS/linalg1.pdf)
8. [https://user.phil.hhu.de/~petersen/Einf_CL_WiSe1011/material/EinfCL_2_handout.pdf](https://user.phil.hhu.de/~petersen/Einf_CL_WiSe1011/material/EinfCL_2_handout.pdf)
9. [https://mathepedia.de/Vereinigung.html](https://mathepedia.de/Vereinigung.html)
10. [https://www.studydrive.net/de/flashcards/formale-sprachen-und-automaten/19833](https://www.studydrive.net/de/flashcards/formale-sprachen-und-automaten/19833)

$\times$
Hier ist eine Musterantwort, wie sie in einem Skript oder einer Übung stehen könnte.

## Musterantwort Teil b)

**Behauptung:** Die Menge $S$ aller Sätze (definiert als endliche Folgen von Wörtern aus $W$) ist abzählbar unendlich.

**Beweis:**

1. Sei $W$ die Menge aller Wörter. Nach Teil (a) ist die Menge $W$ **abzählbar**.
    
2. Wir definieren für jedes $n \in \mathbb{N}$ die Menge $S_n$ als die Menge aller Sätze der exakten Länge $n$. Ein Satz der Länge $n$ ist ein geordnetes $n$-Tupel von Wörtern, also ein Element des kartesischen Produkts:
    
    $$S_n = W^n = W \times W \times \dots \times W \quad \text{(n-mal)}$$
    
    Da $W$ abzählbar ist, ist auch das endliche kartesische Produkt $S_n$ für jedes $n \in \mathbb{N}$ eine abzählbare Menge. (Dies folgt induktiv aus der Abzählbarkeit von $W \times W$, vgl. Proposition 2.3.16).
    
3. Die Menge $S$ aller Sätze ist die Vereinigung aller Sätze aller endlichen Längen:
    
    $$S = S_1 \cup S_2 \cup S_3 \cup \dots = \bigcup_{n=1}^{\infty} S_n$$
    
4. $S$ ist somit eine **abzählbare Vereinigung** (da der Index $n$ die abzählbare Menge $\mathbb{N}$ durchläuft) von **abzählbaren Mengen** (den $S_n$, wie in Schritt 2 gezeigt).
    
5. Nach **Satz 2.3.18** ("Eine abzählbare Vereinigung von abzählbaren Mengen ist abzählbar") ist die Menge $S$ folglich selbst **abzählbar**.
    
6. Da bereits die Teilmenge $S_1 = W$ (die Sätze der Länge 1) nach (a) unendlich ist, muss die Obermenge $S$ ebenfalls unendlich sein.
    

Aus (5) und (6) folgt: $S$ ist abzählbar und unendlich, also **abzählbar unendlich**. q.e.d.