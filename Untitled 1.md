Der Satz von Bolzano–Weierstraß ist ein fundamentales Ergebnis in der Analysis und wird in den Quellen im Abschnitt **1.2 Rückblick und Ergänzungen: Konvergenz** sowie im Rahmen der **Konvergenz in $\mathbb{R}^n$** (Abschnitt 1.5) behandelt. Er ist von zentraler Bedeutung für das Verständnis der **Vollständigkeit** des Körpers der reellen Zahlen $\mathbb{R}$.

Hier ist eine detaillierte Erläuterung des Themas:

### Die Aussage des Satzes

Der Satz von Bolzano–Weierstraß (benannt nach Bernard Bolzano und Karl Weierstraß) wird in Satz 1.2.17(ii) explizit für reelle Folgen formuliert:

> **Jede beschränkte reelle Folge enthält eine konvergente Teilfolge**.

Das bedeutet, wenn eine Folge $f = (a_k)$ im Raum $\omega$ der reellen Folgen liegt und beschränkt ist, d. h., $f \in \ell^\infty$ (oder äquivalent, wenn die Menge der Funktionswerte beschränkt ist), dann existiert eine Teilfolge $(a'_{j})$ dieser Folge, die gegen einen Grenzwert $a \in \mathbb{R}$ konvergiert.

### Kontext und Herleitung in $\mathbb{R}$

Der Satz 1.2.17 ist als **Hilfsmittel** dafür aufgeführt, dass je nach Eigenschaft der Folge $f$ spezielle Teilfolgen existieren. Der Beweis des Satzes beruht typischerweise auf zwei vorangegangenen fundamentalen Aussagen, die ebenfalls in Satz 1.2.17 enthalten sind:

1.  **Monotone Teilfolge:** Jede reelle Folge enthält eine monotone Teilfolge (Satz 1.2.17(i)).
2.  **Monotoniekriterium:** Eine monotone Folge $f$ ist konvergent, wenn sie beschränkt ist (Satz 1.2.16).

Da die Ausgangsfolge $f$ als beschränkt vorausgesetzt wird, ist auch jede ihrer Teilfolgen beschränkt. Wenn nun eine beschränkte Folge eine monotone Teilfolge enthält, muss diese monotone Teilfolge nach dem Monotoniekriterium konvergent sein.

### Bedeutung für die Vollständigkeit

Der Satz von Bolzano–Weierstraß ist eng mit der **Vollständigkeit** von $\mathbb{R}$ verbunden, der Eigenschaft der "Lückenlosigkeit der Zahlengeraden". Diese Vollständigkeit ist die Grundlage für das **Cauchysche Konvergenzkriterium** (Satz 1.2.21).

*   Eine **Cauchyfolge** ist definiert als eine Folge, deren Glieder sich unendlich nahe kommen, ohne dass man einen Grenzwert kennen muss.
*   Jede Cauchyfolge ist beschränkt (Hilfssatz 1.2.20(ii)).
*   Wenn eine Cauchyfolge beschränkt ist, besitzt sie nach dem Satz von Bolzano–Weierstraß eine konvergente Teilfolge.
*   Wenn eine Cauchyfolge eine konvergente Teilfolge besitzt, ist sie selbst konvergent (Hilfssatz 1.2.20(iii)).
tz 1.2.17(ii) ist äquivalent zu der Aussage, dass jede ￼￼beschränkte, unendliche Teilmenge von ￼￼ mindestens einen Häufungspunkt besitzt￼￼ (Satz 2.1.20). In ￼￼ wird eine nichtleere Teilmenge als ￼￼kompakt￼￼ bezeichnet, wenn sie abgeschlossen und beschränkDer Satz von Bolzano–Weierstraß ist ein fundamentales Ergebnis in der Analysis und wird in den Quellen im Abschnitt ￼￼1.2 Rückblick und Ergänzungen: Konvergenz￼￼ sowie im Rahmen der ￼￼Konvergenz in ￼￼￼￼ (Abschnitt 1.5) behandelt. Er ist von zentraler Bedeutung für das Verständnis der ￼￼Vollständigkeit￼￼ des Körpers der reellen Zahlen ￼￼.

Diese Kette von Implikationen führt direkt zum Cauchykriterium in $\mathbb{R}$: Eine reelle Folge ist genau dann konvergent, wenn sie eine Cauchyfolge ist. Der Satz von Bolzano–Weierstraß ist somit ein **zentrales Element zum Nachweis der Vollständigkeit** von $\mathbb{R}$.

### Anwendung im $\mathbb{R}^n$ und Kompaktheit

Der Satz lässt sich auf den Raum $\mathbb{R}^n$ verallgemeinern und ist dort ebenfalls von großer Tragweite.

1.  **Generalisierter Satz von Bolzano–Weierstraß (Satz 1.5.9):**
    Für eine Folge $(x_k)_{k \in \mathbb{N}}$ in $\mathbb{R}^n$, die $\lVert \cdot \rVert_\infty$–beschränkt ist (d. h., es existiert eine Zahl $S$ mit $\lVert x_k \rVert_\infty \leq S$ für jedes $k \in \mathbb{N}$), gibt es eine Teilfolge, die in $(\mathbb{R}^n, \lVert \cdot \rVert_\infty)$ konvergiert. Der Beweis in $\mathbb{R}^n$ erfolgt durch vollständige Induktion, wobei der Fall $n=1$ gerade dem "gewöhnlichen Satz von Bolzano–Weierstraß 1.2.17(ii)" entspricht.
tz 1.2.17(ii) ist äquivalent zu der Aussage, dass jede ￼￼beschränkte, unendliche Teilmenge von ￼￼ mindestens einen Häufungspunkt besitzt￼￼ (Satz 2.1.20). In ￼￼ wird eine nichtleere Teilmenge als ￼￼kompakt￼￼ bezeichnet, wenn sie abgeschlossen und beschränkDer Satz von Bolzano–Weierstraß ist ein fundamentales Ergebnis in der Analysis und wird in den Quellen im Abschnitt ￼￼1.2 Rückblick und Ergänzungen: Konvergenz￼￼ sowie im Rahmen der ￼￼Konvergenz in ￼￼￼￼ (Abschnitt 1.5) behandelt. Er ist von zentraler Bedeutung für das Verständnis der ￼￼Vollständigkeit￼￼ des Körpers der reellen Zahlen ￼￼.
tz 1.2.17(ii) ist äquivalent zu der Aussage, dass jede ￼￼beschränkte, unendliche Teilmenge von ￼￼ mindestens einen Häufungspunkt besitzt￼￼ (Satz 2.1.20). In ￼￼ wird eine nichtleere Teilmenge als ￼￼kompakt￼￼ bezeichnet, wenn sie abgeschlossen und beschränkDer Satz von Bolzano–Weierstraß ist ein fundamentales Ergebnis in der Analysis und wird in den Quellen im Abschnitt ￼￼1.2 Rückblick und Ergänzungen: Konvergenz￼￼ sowie im Rahmen der ￼￼Konvergenz in ￼￼￼￼ (Abschnitt 1.5) behandelt. Er ist von zentraler Bedeutung für das Verständnis der ￼￼Vollständigkeit￼￼ des Körpers der reellen Zahlen ￼￼.
-
2.  **Vollständigkeit von $\mathbb{R}^n$:**
    Mithilfe des Satzes von Bolzano–Weierstraß und der Äquivalenz der Normen in $\mathbb{R}^n$ lässt sich zeigen, dass **$\mathbb{R}^n$ ein vollständiger normierter Raum (Banachraum) ist**.

3.  **Kompaktheit:**
    Der Satz 1.2.17(ii) ist äquivalent zu der Aussage, dass jede **beschränkte, unendliche Teilmenge von $\mathbb{R}$ mindestens einen Häufungspunkt besitzt** (Satz 2.1.20). In $\mathbb{R}$ wird eine nichtleere Teilmenge als **kompakt** bezeichnet, wenn sie abgeschlossen und beschränk. Der Satz von Bolzano–Weierstraß ist ein fundamentales Ergebnis in der Analysis und wird in den Quellen im Abschnitt **1.2 Rückblick und Ergänzungen: Konvergenz** sowie im Rahmen der **Konvergenz in $\mathbb{R}^n$** (Abschnitt 1.5) behandelt. Er ist von zentraler Bedeutung für das Verständnis der **Vollständigkeit** des Körpers der reellen Zahlen $\mathbb{R}$.

Hier ist eine detaillierte Erläuterung des Themas:

### Die Aussage des Satzes

Der Satz von Bolzano–Weierstraß (benannt nach Bernard Bolzano und Karl Weierstraß) wird in Satz 1.2.17(ii) explizit für reelle Folgen formuliert:

> **Jede beschränkte reelle Folge enthält eine konvergente Teilfolge**.

Das bedeutet, wenn eine Folge $f = (a_k)$ im Raum $\omega$ der reellen Folgen liegt und beschränkt ist, d. h., $f \in \ell^\infty$ (oder äquivalent, wenn die Menge der Funktionswerte beschränkt ist), dann existiert eine Teilfolge $(a'_{j})$ dieser Folge, die gegen einen Grenzwert $a \in \mathbb{R}$ konvergiert.

### Kontext und Herleitung in $\mathbb{R}$

Der Satz 1.2.17 ist als **Hilfsmittel** dafür aufgeführt, dass je nach Eigenschaft der Folge $f$ spezielle Teilfolgen existieren. Der Beweis des Satzes beruht typischerweise auf zwei vorangegangenen fundamentalen Aussagen, die ebenfalls in Satz 1.2.17 enthalten sind:

1.  **Monotone Teilfolge:** Jede reelle Folge enthält eine monotone Teilfolge (Satz 1.2.17(i)).
2.  **Monotoniekriterium:** Eine monotone Folge $f$ ist konvergent, wenn sie beschränkt ist (Satz 1.2.16).
tz 1.2.17(ii) ist äquivalent zu der Aussage, dass jede ￼￼beschränkte, unendliche Teilmenge von ￼￼ mindestens einen Häufungspunkt besitzt￼￼ (Satz 2.1.20). In ￼￼ wird eine nichtleere Teilmenge als ￼￼kompakt￼￼ bezeichnet, wenn sie abgeschlossen und beschränkDer Satz von Bolzano–Weierstraß ist ein fundamentales Ergebnis in der Analysis und wird in den Quellen im Abschnitt ￼￼1.2 Rückblick und Ergänzungen: Konvergenz￼￼ sowie im Rahmen der ￼￼Konvergenz in ￼￼￼￼ (Abschnitt 1.5) behandelt. Er ist von zentraler Bedeutung für das Verständnis der ￼￼Vollständigkeit￼￼ des Körpers der reellen Zahlen ￼￼.

Da die Ausgangsfolge $f$ als beschränkt vorausgesetzt wird, ist auch jede ihrer Teilfolgen beschränkt. Wenn nun eine beschränkte Folge eine monotone Teilfolge enthält, muss diese monotone Teilfolge nach dem Monotoniekriterium konvergent sein.

### Bedeutung für die Vollständigkeit

Der Satz von Bolzano–Weierstraß ist eng mit der **Vollständigkeit** von $\mathbb{R}$ verbunden, der Eigenschaft der "Lückenlosigkeit der Zahlengeraden". Diese Vollständigkeit ist die Grundlage für das **Cauchysche Konvergenzkriterium** (Satz 1.2.21).

*   Eine **Cauchyfolge** ist definiert als eine Folge, deren Glieder sich unendlich nahe kommen, ohne dass man einen Grenzwert kennen muss.
*   Jede Cauchyfolge ist beschränkt (Hilfssatz 1.2.20(ii)).
*   Wenn eine Cauchyfolge beschränkt ist, besitzt sie nach dem Satz von Bolzano–Weierstraß eine konvergente Teilfolge.
*   Wenn eine Cauchyfolge eine konvergente Teilfolge besitzt, ist sie selbst konvergent (Hilfssatz 1.2.20(iii)).

Diese Kette von Implikationen führt direkt zum Cauchykriterium in $\mathbb{R}$: Eine reelle Folge ist genau dann konvergent, wenn sie eine Cauchyfolge ist. Der Satz von Bolzano–Weierstraß ist somit ein **zentrales Element zum Nachweis der Vollständigkeit** von $\mathbb{R}$.

### Anwendung im $\mathbb{R}^n$ und Kompaktheit

Der Satz lässt sich auf den Raum $\mathbb{R}^n$ verallgemeinern und ist dort ebenfalls von großer Tragweite.

1.  **Generalisierter Satz von Bolzano–Weierstraß (Satz 1.5.9):**
    Für eine Folge $(x_k)_{k \in \mathbb{N}}$ in $\mathbb{R}^n$, die $\lVert \cdot \rVert_\infty$–beschränkt ist (d. h., es existiert eine Zahl $S$ mit $\lVert x_k \rVert_\infty \leq S$ für jedes $k \in \mathbb{N}$), gibt es eine Teilfolge, die in $(\mathbb{R}^n, \lVert \cdot \rVert_\infty)$ konvergiert. Der Beweis in $\mathbb{R}^n$ erfolgt durch vollständige Induktion, wobei der Fall $n=1$ gerade dem "gewöhnlichen Satz von Bolzano–Weierstraß 1.2.17(ii)" entspricht.

2.  **Vollständigkeit von $\mathbb{R}^n$:**
    Mithilfe des Satzes von Bolzano–Weierstraß und der Äquivalenz der Normen in $\mathbb{R}^n$ lässt sich zeigen, dass **$\mathbb{R}^n$ ein vollständiger normierter Raum (Banachraum) ist**.

3.  **Kompaktheit:**
    Der Satz 1.2.17(ii) ist äquivalent zu der Aussage, dass jede **beschränkte, unendliche Teilmenge von $\mathbb{R}$ mindestens einen Häufungspunkt besitzt** (Satz 2.1.20). In $\mathbb{R}$ wird eine nichtleere Teilmenge als **kompakt** bezeichnet, wenn sie abgeschlossen und beschränkt ist.
    Der Satz von Bolzano–Weierstraß wird außerdem genutzt, um zu zeigen, dass in $\mathbb{R}^n$ Kompaktheit gleichbedeutend mit **Folgenkompaktheit** ist, d. h., dass jede Folge in einer kompakten Menge eine konvergente Teilfolge besitzt, deren Grenzwert in der Menge liegt (Satz 2.5.3). Zudem wird B-W im Beweis verwendet, um zu zeigen, dass das stetige Bild einer kompakten Menge in $\mathbb{R}$ wieder kompakt ist (Satz 2.1.22).t ist.
    Der Satz von Bolzano–Weierstraß wird außerdem genutzt, um zu zeigen, dass in $\mathbb{R}^n$ Kompaktheit gleichbedeutend mit **Folgenkompaktheit** ist, d. h., dass jede Folge in einer kompakten Menge eine konvergente Teilfolge besitzt, deren Grenzwert in der Menge liegt (Satz 2.5.3). Zudem wird B-W im Beweis verwendet, um zu zeigen, dass das stetige Bild einer kompakten Menge in $\mathbb{R}$ wieder kompakt ist (Satz 2.1.22).