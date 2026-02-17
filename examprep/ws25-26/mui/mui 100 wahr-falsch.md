Hier sind die 100 Wahr/Falsch-Fragen mit ausführlicheren Erklärungen (2-3 Sätze) und den entsprechenden Quellenangaben aus dem Skript.

### Riemann-Integral & Das Maßproblem

1. **Das Riemann-Integral basiert auf der Unterteilung des Wertebereichs (y-Achse).**
    
    - **Antwort: Falsch.** Das Riemann-Integral unterteilt die Definitionsmenge (x-Achse) in Partitionen und nutzt Infimum und Supremum auf diesen Bereichen. Die Idee, die y-Achse (den Wertebereich) zu unterteilen, ist das fundamentale Konzept des Lebesgue-Integrals.
        
2. **Jede beschränkte Funktion auf einem kompakten Intervall ist Riemann-integrierbar.**
    
    - **Antwort: Falsch.** Beschränktheit ist notwendig, aber nicht hinreichend. Ein klassisches Gegenbeispiel ist die Dirichlet-Funktion (Indikatorfunktion der rationalen Zahlen), die beschränkt ist, aber deren Ober- und Untersummen nicht übereinstimmen.
        
3. **Die Dirichlet-Funktion ist Riemann-integrierbar.**
    
    - **Antwort: Falsch.** Für jede Partition des Intervalls ist die Untersumme 0 und die Obersumme 1, da in jedem Teilintervall sowohl rationale als auch irrationale Zahlen liegen. Da Ober- und Untersumme nicht gleich sind, existiert das Riemann-Integral nicht.
        
4. **Jede stetige Funktion auf $[a,b]$ ist Riemann-integrierbar.**
    
    - **Antwort: Wahr.** Dies ist ein positives Resultat der Integrationstheorie: Stetigkeit auf einem kompakten Intervall garantiert die Riemann-Integrierbarkeit. Solche Funktionen lassen sich durch Treppenfunktionen beliebig genau approximieren.
        
5. **Jede monotone Funktion auf $[a,b]$ ist Riemann-integrierbar.**
    
    - **Antwort: Wahr.** Auch dies ist ein hinreichendes Kriterium: Jede (stückweise) monotone Funktion (steigend oder fallend) ist Riemann-integrierbar. Unstetigkeitsstellen spielen hierbei keine Rolle, solange die Monotonie gewahrt bleibt.
        
6. **Punktweise Konvergenz einer Folge Riemann-integrierbarer Funktionen impliziert immer, dass die Grenzfunktion Riemann-integrierbar ist.**
    
    - **Antwort: Falsch.** Die punktweise Konvergenz ist ein zu schwacher Begriff für das Riemann-Integral. Der punktweise Grenzwert von Riemann-integrierbaren Funktionen kann eine Funktion sein, die nicht mehr Riemann-integrierbar ist, wie etwa die Dirichlet-Funktion.
        
7. **Gleichmäßige Konvergenz erlaubt das Vertauschen von Limes und Riemann-Integral.**
    
    - **Antwort: Wahr.** Wenn eine Folge Riemann-integrierbarer Funktionen gleichmäßig gegen $f$ konvergiert, ist $f$ Riemann-integrierbar und die Integrale konvergieren gegen das Integral von $f$. Allerdings ist die Forderung der gleichmäßigen Konvergenz in vielen Anwendungen zu restriktiv.
        
8. **Das Maßproblem fordert Normiertheit, Bewegungsinvarianz und $\sigma$-Additivität.**
    
    - **Antwort: Wahr.** Eine Lösung des Maßproblems für $\mathbb{R}^d$ müsste dem Einheitswürfel das Volumen 1 zuordnen (Normiertheit), invariant gegenüber Drehungen und Verschiebungen sein und das Volumen abzählbarer Vereinigungen disjunkter Mengen korrekt summieren ($\sigma$-Additivität).
        
9. **Das Maßproblem ist für jede Teilmenge des $\mathbb{R}^d$ lösbar.**
    
    - **Antwort: Falsch.** Es gibt keine Abbildung, die jeder Teilmenge des $\mathbb{R}^d$ ein sinnvolles Volumen zuordnet und dabei alle geforderten Eigenschaften erfüllt. Der Beweis nutzt Äquivalenzklassen und Auswahlaxiome, um widersprüchliche Mengen (Vitali-Mengen) zu konstruieren.
        
10. **Aus der $\sigma$-Additivität folgt die endliche Additivität.**
    
    - **Antwort: Wahr.** Wenn man eine endliche Anzahl disjunkter Mengen $A_1, ..., A_n$ betrachtet, kann man die Folge mit leeren Mengen $A_{n+1} = \emptyset, ...$ auffüllen. Da das Maß der leeren Menge 0 ist, ergibt die unendliche Summe genau die endliche Summe.
        

### Mengensysteme (Halbringe, Ringe)

11. **Ein Mengensystem ist eine Menge von Teilmengen einer Obermenge.**
    
    - **Antwort: Wahr.** Ein Mengensystem ist formal definiert als eine nichtleere Menge $\mathcal{H}$, deren Elemente Teilmengen einer Grundmenge (oft $M$ oder $\Omega$ genannt) sind.
        
12. **Die Potenzmenge ist das kleinste Mengensystem.**
    
    - **Antwort: Falsch.** Die Potenzmenge $\mathcal{P}(M)$ ist das größte Mengensystem, da sie alle möglichen Teilmengen enthält. Das kleinste Mengensystem wäre beispielsweise $\{ \emptyset \}$ oder $\{ \emptyset, M \}$ (als kleinste $\sigma$-Algebra).
        
13. **Ein Halbring enthält immer die leere Menge.**
    
    - **Antwort: Wahr.** In einem Halbring $\mathcal{H}$ ist definitionsgemäß $\emptyset \in \mathcal{H}$ enthalten. Dies folgt oft daraus, dass Differenzen gebildet werden können ($A \setminus A = \emptyset$) und das System nichtleer ist.
        
14. **Ein Halbring ist abgeschlossen bezüglich beliebiger Vereinigungen.**
    
    - **Antwort: Falsch.** Ein Halbring fordert nur Abgeschlossenheit bezüglich Durchschnitten und eine spezielle Eigenschaft für Differenzen, die als disjunkte Vereinigung dargestellt werden können. Er ist im Allgemeinen nicht einmal bezüglich endlicher Vereinigungen abgeschlossen.
        
15. **Das System der halboffenen Rechtecke im $\mathbb{R}^d$ bildet einen Halbring.**
    
    - **Antwort: Wahr.** Die Menge $\mathcal{I}(\mathbb{R}^d)$ der halboffenen Rechtecke $(a, b]$ ist das wichtigste Beispiel für einen Halbring in der Maßtheorie. Darauf wird das $d$-dimensionale Volumen definiert.
        
16. **Ein Ring ist abgeschlossen bezüglich Durchschnitten und Vereinigungen.**
    
    - **Antwort: Wahr.** Ein Ring $\mathcal{R}$ ist so definiert, dass aus $A, B \in \mathcal{R}$ folgt, dass sowohl $A \cap B \in \mathcal{R}$ als auch $A \cup B \in \mathcal{R}$ gilt.
        
17. **Ein Ring ist immer abgeschlossen bezüglich der Mengendifferenz.**
    
    - **Antwort: Wahr.** Neben Durchschnitten und Vereinigungen ist die Abgeschlossenheit bezüglich der Differenzbildung ($A \setminus B \in \mathcal{R}$) eine der drei definierenden Eigenschaften eines Rings.
        
18. **Jeder Ring ist auch ein Halbring.**
    
    - **Antwort: Wahr.** Da Ringe stärkere Abgeschlossenheitseigenschaften besitzen (insbesondere Vereinigungen und Differenzen), erfüllen sie automatisch die Bedingungen eines Halbrings.
        
19. **Der Durchschnitt von Ringen ist wieder ein Ring.**
    
    - **Antwort: Wahr.** Wenn man den Durchschnitt über eine beliebige Indexmenge von Ringen bildet, bleibt die Struktur erhalten. Sind $A, B$ im Durchschnitt enthalten, sind sie in jedem einzelnen Ring enthalten, und somit sind auch ihre Verknüpfungen in jedem Ring und damit im Durchschnitt enthalten.
        
20. **Der von einem Halbring erzeugte Ring besteht aus endlichen Vereinigungen von Halbring-Elementen.**
    
    - **Antwort: Wahr.** $\mathcal{R}(\mathcal{H})$ lässt sich explizit beschreiben als die Menge aller endlichen Vereinigungen von Mengen aus dem Halbring. Man kann sogar zeigen, dass diese Vereinigungen disjunkt gewählt werden können.
        

### $\sigma$-Algebren & Borel-Mengen

21. **Eine $\sigma$-Algebra ist abgeschlossen bezüglich abzählbarer Vereinigungen.**
    
    - **Antwort: Wahr.** Dies ist die zentrale Eigenschaft, die eine $\sigma$-Algebra von einem Ring unterscheidet: Sind $A_1, A_2, ... \in \mathcal{A}$, so muss auch deren Vereinigung in $\mathcal{A}$ liegen.
        
22. **Die kleinste $\sigma$-Algebra auf $M$ ist die Potenzmenge.**
    
    - **Antwort: Falsch.** Die kleinste $\sigma$-Algebra ist $\{ \emptyset, M \}$, also das System, das nur die leere Menge und die Grundmenge enthält. Die Potenzmenge ist die größte mögliche $\sigma$-Algebra.
        
23. **Eine $\sigma$-Algebra ist stabil bezüglich Komplementbildung.**
    
    - **Antwort: Wahr.** Wenn eine Menge $A$ in der $\sigma$-Algebra enthalten ist, muss auch ihr Komplement $A^c = M \setminus A$ enthalten sein. Dies ist eine der definierenden Eigenschaften.
        
24. **Borel-Mengen im $\mathbb{R}^d$ werden von den offenen Mengen erzeugt.**
    
    - **Antwort: Wahr.** Die Borel-$\sigma$-Algebra $\mathcal{B}(\mathbb{R}^d)$ ist definiert als die kleinste $\sigma$-Algebra, die alle offenen Mengen (oder äquivalent die halboffenen Rechtecke) enthält.
        
25. **Jede Teilmenge von $\mathbb{R}$ ist eine Borel-Menge.**
    
    - **Antwort: Falsch.** Obwohl die Borel-$\sigma$-Algebra sehr groß ist, enthält sie nicht alle Teilmengen von $\mathbb{R}$. Es existieren Mengen, die keine Borel-Mengen sind, wie z.B. die Vitali-Mengen (obwohl deren Konstruktion das Auswahlaxiom benötigt).
        
26. **Kugeln sind Borel-Mengen.**
    
    - **Antwort: Wahr.** Kugeln können als abzählbare Vereinigungen von halboffenen Rechtecken dargestellt werden. Da Borel-Mengen unter abzählbaren Vereinigungen abgeschlossen sind, gehören Kugeln dazu.
        
27. **$\sigma(\mathcal{R}_d)$ ist gleich der Borel-$\sigma$-Algebra $\mathcal{B}(\mathbb{R}^d)$.**
    
    - **Antwort: Wahr.** Es gilt $\mathcal{B}(\mathbb{R}^d) = \sigma(\mathcal{R}_d)$, wobei $\mathcal{R}_d$ der von den Rechtecken erzeugte Ring ist. Dies liegt daran, dass der Ring $\mathcal{R}_d$ die Rechtecke enthält, welche die Borel-$\sigma$-Algebra erzeugen.
        
28. **Ein Dynkin-System ist abgeschlossen bezüglich beliebiger Vereinigungen.**
    
    - **Antwort: Falsch.** Ein Dynkin-System fordert nur die Abgeschlossenheit bezüglich _disjunkter_ abzählbarer Vereinigungen. Für beliebige Vereinigungen ist es im Allgemeinen nicht abgeschlossen.
        
29. **Jede $\sigma$-Algebra ist ein Dynkin-System.**
    
    - **Antwort: Wahr.** Da eine $\sigma$-Algebra unter beliebigen abzählbaren Vereinigungen abgeschlossen ist, ist sie erst recht unter disjunkten abzählbaren Vereinigungen abgeschlossen. Auch die anderen Eigenschaften (Grundmenge, Komplement) sind erfüllt.
        
30. **Jedes Dynkin-System ist eine $\sigma$-Algebra.**
    
    - **Antwort: Falsch.** Die Umkehrung gilt nicht, da einem Dynkin-System im Allgemeinen die Schnittstabilität fehlt. Ein Dynkin-System ist genau dann eine $\sigma$-Algebra, wenn es durchschnittsstabil ist.
        
31. **Der Satz von Dynkin besagt: Ist ein Mengensystem schnittstabil, so stimmen erzeugtes Dynkin-System und erzeugte $\sigma$-Algebra überein.**
    
    - **Antwort: Wahr.** Wenn ein Erzeugendensystem $\mathcal{E}$ durchschnittsstabil ($\cap$-stabil) ist, dann gilt $\delta(\mathcal{E}) = \sigma(\mathcal{E})$. Dies ist ein wichtiges Werkzeug für Eindeutigkeitsbeweise in der Maßtheorie.
        

### Maße und Erweiterungssätze

32. **Ein Prämaß ist auf einem Ring definiert.**
    
    - **Antwort: Wahr.** Ein Prämaß ist eine $\sigma$-additive Mengenfunktion, die auf einem Halbring oder Ring definiert ist. Es dient als Vorstufe zur Konstruktion eines Vollmaßes auf einer $\sigma$-Algebra.
        
33. **Ein Inhalt muss $\sigma$-additiv sein.**
    
    - **Antwort: Falsch.** Ein Inhalt ist definiert als eine Mengenfunktion, die nur endlich additiv ist. Wenn zusätzlich die $\sigma$-Additivität (abzählbar unendlich) gilt, spricht man von einem Prämaß.
        
34. **Das $d$-dimensionale Volumen auf halboffenen Rechtecken ist ein Prämaß.**
    
    - **Antwort: Wahr.** Das Volumen $V_d$ auf dem Halbring der Rechtecke ist $\sigma$-additiv. Es ist somit ein finites Prämaß.
        
35. **Ein Maß $\mu$ erfüllt immer $\mu(\emptyset) = 0$.**
    
    - **Antwort: Wahr.** Dies ist die erste definierende Eigenschaft eines Maßes. Zudem müssen die Werte nicht-negativ sein.
        
36. **Der erste Maßerweiterungssatz besagt, dass sich ein Inhalt auf einem Halbring eindeutig zu einem Inhalt auf dem erzeugten Ring fortsetzen lässt.**
    
    - **Antwort: Wahr.** Jedes Prämaß (oder jeder Inhalt) auf einem Halbring $\mathcal{H}$ kann eindeutig zu einem Prämaß (bzw. Inhalt) auf dem erzeugten Ring $\mathcal{R}(\mathcal{H})$ fortgesetzt werden.
        
37. **Ein äußeres Maß ist immer $\sigma$-additiv.**
    
    - **Antwort: Falsch.** Ein äußeres Maß $F$ ist im Allgemeinen nur $\sigma$-subadditiv, d.h. $F(\cup A_i) \le \sum F(A_i)$. Die volle $\sigma$-Additivität gilt erst eingeschränkt auf die $\sigma$-Algebra der messbaren Mengen.
        
38. **Carathéodory-Messbarkeit definiert eine $\sigma$-Algebra.**
    
    - **Antwort: Wahr.** Die Menge aller $\mu$-messbaren Mengen $\mathcal{A}_\mu$ (definiert über das Carathéodory-Kriterium) bildet immer eine $\sigma$-Algebra. Auf dieser Menge ist das äußere Maß ein echtes Maß.
        
39. **Wenn ein Prämaß $\sigma$-endlich ist, ist seine Fortsetzung auf die $\sigma$-Algebra eindeutig.**
    
    - **Antwort: Wahr.** Dies ist der zweite Maßerweiterungssatz: Ist das ursprüngliche Prämaß $\sigma$-endlich, so ist die Fortsetzung auf $\mathcal{A}_\mu$ eindeutig bestimmt.
        
40. **Das Zählmaß auf $\mathbb{R}$ ist $\sigma$-endlich.**
    
    - **Antwort: Falsch.** $\mathbb{R}$ ist überabzählbar und kann nicht als abzählbare Vereinigung von endlichen Mengen dargestellt werden. Daher gibt es keine Folge von Mengen mit endlichem Maß, die $\mathbb{R}$ ausschöpft.
        
41. **Das Lebesgue-Maß ist die Vervollständigung des Borel-Maßes.**
    
    - **Antwort: Wahr.** Das Lebesgue-Maß $\lambda_d$ ist auf einer $\sigma$-Algebra definiert, die $\mathcal{B}(\mathbb{R}^d)$ umfasst und zusätzlich alle Teilmengen von Nullmengen enthält. Es entsteht durch die Carathéodory-Konstruktion aus dem Volumen auf Rechtecken.
        
42. **Das Lebesgue-Maß ist bewegungsinvariant.**
    
    - **Antwort: Wahr.** Dies war eine der ursprünglichen Anforderungen des Maßproblems: Eine Verschiebung, Drehung oder Spiegelung einer Menge ändert ihr Volumen nicht. Das Lebesgue-Maß erfüllt diese Eigenschaft.
        

### Messbare Funktionen

43. **Eine Funktion ist messbar, wenn Urbilder messbarer Mengen messbar sind.**
    
    - **Antwort: Wahr.** Eine Funktion $f: \Omega_1 \to \Omega_2$ heißt messbar, wenn für jede messbare Menge $A_2$ im Zielraum das Urbild $f^{-1}(A_2)$ im Definitionsraum messbar ist.
        
44. **Jede stetige Funktion $f: \mathbb{R}^d \to \mathbb{R}^m$ ist Borel-messbar.**
    
    - **Antwort: Wahr.** Da stetige Funktionen Urbilder offener Mengen auf offene Mengen abbilden und offene Mengen die Borel-$\sigma$-Algebra erzeugen, sind sie messbar.
        
45. **Die Summe zweier messbarer Funktionen ist im Allgemeinen nicht messbar.**
    
    - **Antwort: Falsch.** Wenn $f$ und $g$ messbar sind, ist auch ihre Summe $f+g$ messbar. Dies gilt ebenso für Produkte, Maxima und Minima.
        
46. **Die Komposition messbarer Funktionen ist messbar.**
    
    - **Antwort: Wahr.** Die Hintereinanderschaltung $f \circ g$ messbarer Funktionen ist wieder messbar, da $(f \circ g)^{-1}(A) = g^{-1}(f^{-1}(A))$ gilt.
        
47. **Das punktweise Supremum einer Folge messbarer Funktionen ist messbar.**
    
    - **Antwort: Wahr.** Für eine Folge reellwertiger messbarer Funktionen $(f_n)$ ist $\sup_{n} f_n$ messbar. Dies ist eine wichtige Eigenschaft, die $\sigma$-Algebren von anderen Systemen unterscheidet.
        
48. **Der punktweise Limes einer Folge messbarer Funktionen ist messbar.**
    
    - **Antwort: Wahr.** Sofern der Grenzwert existiert, ist $\lim_{n \to \infty} f_n$ messbar. Dies ist ein wesentlicher Vorteil gegenüber stetigen oder Riemann-integrierbaren Funktionen.
        
49. **Eine Treppenfunktion nimmt nur endlich viele Werte an.**
    
    - **Antwort: Wahr.** Eine Treppenfunktion ist definiert als endliche Linearkombination von Indikatorfunktionen $\sum c_i \chi_{A_i}$. Ihr Bildbereich ist daher endlich.
        
50. **Jede nichtnegative messbare Funktion kann durch eine monotone Folge von Treppenfunktionen approximiert werden.**
    
    - **Antwort: Wahr.** Zu jedem messbaren $f \ge 0$ existiert eine isotone Folge nichtnegativer Treppenfunktionen, die punktweise gegen $f$ konvergiert. Dies wird zur Definition des Integrals genutzt.
        

### Konstruktion des Integrals

51. **Das Integral einer nichtnegativen Treppenfunktion ist unabhängig von ihrer Darstellung.**
    
    - **Antwort: Wahr.** Da die Darstellung als Summe $\sum c_i \chi_{A_i}$ nicht eindeutig ist, muss die Wohldefiniertheit des Integrals $\sum c_i \mu(A_i)$ bewiesen werden. Dies ist jedoch sichergestellt.
        
52. **Das Lebesgue-Integral einer nichtnegativen Funktion kann den Wert $\infty$ annehmen.**
    
    - **Antwort: Wahr.** Der Wertebereich des Integrals für nichtnegative Treppenfunktionen (und deren Grenzwerte) ist $[0, \infty]$. Es ist zulässig, dass das Integral divergiert.
        
53. **Das Integral einer messbaren Funktion $f$ ist definiert als $\sup \int f_n d\mu$, wobei $f_n$ beliebige Treppenfunktionen sind.**
    
    - **Antwort: Falsch.** Die Definition für $f \ge 0$ verlangt eine _isotone_ Folge _nichtnegativer_ Treppenfunktionen, die gegen $f$ konvergiert. Das Integral ist dann der Grenzwert dieser Folge.
        
54. **Für $f$ integrierbar muss $\int |f| d\mu < \infty$ gelten.**
    
    - **Antwort: Wahr.** Eine Funktion heißt integrierbar, wenn Integrale über Positiv- und Negativteil beide endlich sind. Dies ist äquivalent dazu, dass das Integral über den Betrag endlich ist.
        
55. **Der Positivteil $f_+$ einer Funktion ist definiert als $\max\{-f(x), 0\}$.**
    
    - **Antwort: Falsch.** Der Positivteil ist definiert als $f_+(x) := \max\{f(x), 0\}$. Der Ausdruck $\max\{-f(x), 0\}$ beschreibt den Negativteil $f_-$.
        
56. **Es gilt $f = f_+ + f_-$.**
    
    - **Antwort: Falsch.** Die korrekte Zerlegung ist $f(x) = f_+(x) - f_-(x)$. Man subtrahiert den (positiven) Wert des Negativteils vom Positivteil.
        
57. **Es gilt $|f| = f_+ + f_-$.**
    
    - **Antwort: Wahr.** Der Betrag setzt sich additiv aus den beiden Komponenten zusammen: $|f(x)| [cite_start]= f_+(x) + f_-(x)$.
        
58. **Das Lebesgue-Integral ist linear.**
    
    - **Antwort: Wahr.** Für integrierbare Funktionen $f, g$ und Konstanten $a, b$ gilt $\int (af + bg) d\mu = a \int f d\mu + b \int g d\mu$. Dies gilt auch für nichtnegative messbare Funktionen mit nichtnegativen Koeffizienten.
        
59. **Aus $f \le g$ folgt $\int f d\mu \le \int g d\mu$.**
    
    - **Antwort: Wahr.** Das Integral ist monoton: Wenn $f(x) \le g(x)$ für alle $x$ (oder fast alle $x$), dann ist das Integral von $f$ kleiner oder gleich dem von $g$.
        

### Konvergenzsätze

60. **Der Satz von Beppo Levi fordert gleichmäßige Konvergenz.**
    
    - **Antwort: Falsch.** Der Satz von der monotonen Konvergenz (Beppo Levi) fordert lediglich, dass die Folge $(f_n)$ isoton (monoton wachsend) ist und aus nichtnegativen messbaren Funktionen besteht. Gleichmäßige Konvergenz ist nicht nötig.
        
61. **Beim Satz über monotone Konvergenz (Beppo Levi) dürfen Limes und Integral vertauscht werden.**
    
    - **Antwort: Wahr.** Unter den Voraussetzungen des Satzes gilt $\lim \int f_n d\mu = \int \lim f_n d\mu$. Dies gilt auch, wenn das Integral den Wert $\infty$ annimmt.
        
62. **Das Lemma von Fatou besagt $\int \liminf f_n \le \liminf \int f_n$.**
    
    - **Antwort: Wahr.** Das Lemma von Fatou liefert eine Ungleichung für den Limes Inferior: Das Integral des Limes ist kleiner oder gleich dem Limes der Integrale.
        
63. **Beim Lemma von Fatou gilt im Allgemeinen Gleichheit.**
    
    - **Antwort: Falsch.** Es gilt im Allgemeinen _keine_ Gleichheit. Ein Gegenbeispiel ist die Folge von Indikatorfunktionen $f_n = \chi_{[n, n+1]}$, deren punktweiser Limes 0 ist (Integral 0), während die Integrale der Folgenglieder alle 1 sind.
        
64. **Der Satz von Lebesgue (dominierte Konvergenz) benötigt eine integrierbare Majorante.**
    
    - **Antwort: Wahr.** Damit Limes und Integral vertauscht werden dürfen, muss eine integrierbare Funktion $g$ existieren, sodass $|f_n(x)| [cite_start]\le g(x)$ für alle $n$ und $x$ gilt.
        
65. **Der Satz von Lebesgue gilt nur für gleichmäßige Konvergenz.**
    
    - **Antwort: Falsch.** Der Satz gilt für punktweise konvergente Folgen $f_n \to f$. Die Existenz der integrierbaren Majorante ersetzt die starke Forderung der gleichmäßigen Konvergenz.
        
66. **Der Satz von Lebesgue beweist, dass Riemann- und Lebesgue-Integral immer übereinstimmen.**
    
    - **Antwort: Falsch.** Der Satz von Lebesgue ist ein Konvergenzsatz. Er wird jedoch genutzt, um zu zeigen, dass für Riemann-integrierbare Funktionen auf kompakten Intervallen das Lebesgue-Integral denselben Wert liefert, indem man eine gleichmäßig konvergente Folge konstruiert.
        

### Produktmaße & Fubini

67. **Ein Produktmaß $\nu$ erfüllt $\nu(A \times B) = \mu_1(A) \cdot \mu_2(B)$.**
    
    - **Antwort: Wahr.** Ein Produktmaß ist genau dadurch definiert, dass es auf den Rechtecken $A_1 \times A_2$ das Produkt der Einzelmaße annimmt.
        
68. **Das Produktmaß existiert immer eindeutig.**
    
    - **Antwort: Falsch.** Die Eindeutigkeit des Produktmaßes $\mu_1 \otimes \mu_2$ ist nur garantiert, wenn die ursprünglichen Maße $\mu_1$ und $\mu_2$ $\sigma$-endlich sind.
        
69. **$\mathcal{B}(\mathbb{R}^2) = \mathcal{B}(\mathbb{R}) \otimes \mathcal{B}(\mathbb{R})$.**
    
    - **Antwort: Wahr.** Die Borel-$\sigma$-Algebra des $\mathbb{R}^2$ entspricht dem Produkt der Borel-$\sigma$-Algebren von $\mathbb{R}$. Dies lässt sich auf höhere Dimensionen verallgemeinern.
        
70. **Der Satz von Fubini erlaubt Vertauschung der Integrationsreihenfolge für alle messbaren Funktionen.**
    
    - **Antwort: Falsch.** Der Satz von Fubini gilt nur unter bestimmten Voraussetzungen: Die Funktion muss entweder nichtnegativ sein (Satz von Tonelli) oder bezüglich des Produktmaßes integrierbar sein ($f \in \mathcal{L}^1$).
        
71. **Der Satz von Fubini (Teil 1) gilt für nichtnegative messbare Funktionen (Tonelli).**
    
    - **Antwort: Wahr.** Wenn $f$ nichtnegativ und messbar ist, können die Integrale immer vertauscht werden, selbst wenn der Wert $\infty$ herauskommt.
        
72. **$\lambda_2 = \lambda \otimes \lambda$.**
    
    - **Antwort: Wahr.** Das 2-dimensionale Lebesgue-Maß $\lambda_2$ ist genau das Produktmaß des 1-dimensionalen Lebesgue-Maßes $\lambda$ mit sich selbst.
        

### Transformationssatz

73. **Das Bildmaß $\phi(\mu)$ ist definiert durch $\phi(\mu)(B) = \mu(\phi^{-1}(B))$.**
    
    - **Antwort: Wahr.** Das Bildmaß verlagert das Maß einer Menge im Zielraum zurück auf das Maß ihres Urbilds im Ausgangsraum.
        
74. **Beim Transformationssatz für Integrale tritt der Faktor $|\det \Phi'(x)|$ auf.**
    
    - **Antwort: Wahr.** Wenn man Koordinaten transformiert (z.B. durch eine Abbildung $\Phi$), muss die lokale Volumenverzerrung berücksichtigt werden. Diese wird durch den Betrag der Determinante der Jacobi-Matrix $\Phi'(x)$ beschrieben.
        
75. **Der Transformationssatz verallgemeinert die Substitutionsregel.**
    
    - **Antwort: Wahr.** Im Eindimensionalen entspricht der Term $|\det \Phi'(x)|$ dem Betrag der Ableitung $|g'(x)|$ in der bekannten Substitutionsregel. Der Transformationssatz erweitert dies auf den $\mathbb{R}^d$.
        
76. **Die Determinante der Polarkoordinaten-Abbildung ist $r^2$.**
    
    - **Antwort: Falsch.** Für die Polarkoordinatenabbildung $\Phi(r, \vartheta) = (r \cos \vartheta, r \sin \vartheta)$ im $\mathbb{R}^2$ ist die Determinante der Jacobi-Matrix $r$.
        
77. **Das Integral $\int_{-\infty}^{\infty} e^{-x^2/2} dx$ lässt sich mit Polarkoordinaten berechnen.**
    
    - **Antwort: Wahr.** Man quadriert das Integral, fasst es als Integral über $\mathbb{R}^2$ auf und wendet dann Polarkoordinaten an, wodurch das Integral lösbar wird. Das Ergebnis ist $\sqrt{2\pi}$.
        
78. **Wenn $\nu = f\mu$ (Dichte), dann ist $\int g d\nu = \int g \cdot f d\mu$.**
    
    - **Antwort: Wahr.** Wenn ein Maß $\nu$ durch eine Dichte $f$ bezüglich $\mu$ definiert ist, berechnet sich das Integral einer Funktion $g$ bezüglich $\nu$ durch Integration von $g \cdot f$ bezüglich $\mu$.
        

### Konvergenzarten & $L^p$-Räume

79. **$\mu$-fast sichere Konvergenz bedeutet Konvergenz überall außer auf einer Nullmenge.**
    
    - **Antwort: Wahr.** Eine Folge konvergiert $\mu$-fast sicher, wenn die Menge der Punkte, an denen sie nicht konvergiert, das Maß 0 hat: $\mu(\{x: f_n(x) \not\to f(x)\}) = 0$.
        
80. **Konvergenz im $p$-ten Mittel impliziert immer $\mu$-fast sichere Konvergenz.**
    
    - **Antwort: Falsch.** $L^p$-Konvergenz impliziert Konvergenz dem Maße nach, aber nicht direkt fast sichere Konvergenz. Fast sichere Konvergenz folgt nur für eine Teilfolge oder unter Zusatzbedingungen wie der schnellen Konvergenz einer Reihe.
        
81. **$\mu$-fast sichere Konvergenz impliziert immer Konvergenz dem Maße nach.**
    
    - **Antwort: Falsch.** Diese Implikation gilt nur, wenn das Maß des Gesamtraums endlich ist ($\mu(\Omega) < \infty$). Auf unendlichen Maßräumen (wie $\mathbb{R}$) gilt dies im Allgemeinen nicht.
        
82. **Konvergenz in $L^p$ impliziert Konvergenz dem Maße nach.**
    
    - **Antwort: Wahr.** Dies lässt sich mithilfe der Markow-Ungleichung zeigen: Aus der Konvergenz des Integrals der $p$-ten Potenz folgt, dass die Menge der Punkte mit großer Abweichung klein sein muss.
        
83. **In einem Wahrscheinlichkeitsraum impliziert fast sichere Konvergenz die Konvergenz in Wahrscheinlichkeit (im Maß).**
    
    - **Antwort: Wahr.** Da ein Wahrscheinlichkeitsraum definitionsgemäß ein endliches Maß ($\mu(\Omega)=1$) besitzt , folgt aus fast sicherer Konvergenz auch die Konvergenz dem Maße nach (stochastische Konvergenz).
        
84. **$L^p$-Räume sind Vektorräume.**
    
    - **Antwort: Wahr.** Für $p \ge 1$ bildet die Menge $L^p(\mu)$ (genauer: die Äquivalenzklassen) mit punktweiser Addition und Skalarmultiplikation einen $\mathbb{R}$-Vektorraum.
        
85. **Die Ungleichung $|f+g|^p \le (|f|+|g|)^p$ wird genutzt, um die Vektorraumstruktur von $L^p$ zu zeigen.**
    
    - **Antwort: Falsch.** Um die Vektorraumstruktur und insbesondere die Dreiecksungleichung der Norm zu zeigen, wird die Minkowski-Ungleichung benötigt (im Text wird lediglich die Normeigenschaft für $p \ge 1$ konstatiert).
        
86. **Für $f \in L^p(\mu)$ ist $\|f\|_p = (\int |f|^p d\mu)^{1/p}$.**
    
    - **Antwort: Wahr.** Dies ist die Definition der $p$-Norm (bzw. für $f$ als Funktion die Definition der Bedingung für Zugehörigkeit zu $L^p$).
        
87. **Wenn $\|f\|_p = 0$, dann ist $f$ identisch 0.**
    
    - **Antwort: Falsch.** Wenn das Integral über $|f|^p$ null ist, folgt nur, dass $f = 0$ $\mu$-fast sicher gilt. Die Funktion kann auf einer Nullmenge von 0 verschiedene Werte annehmen.
        
88. **Elemente von $L^p(\mu)$ sind streng genommen Äquivalenzklassen von Funktionen.**
    
    - **Antwort: Wahr.** Um eine Norm zu erhalten (bei der $\|x\|=0 \implies x=0$), identifiziert man Funktionen, die fast überall gleich sind. Formal ist $L^p$ die Menge der Äquivalenzklassen $[f]$.
        
89. **$L^p$-Räume sind vollständig (Banachräume).**
    
    - **Antwort: Wahr.** Für $p \ge 1$ ist der Raum $(L^p(\mu), \|\cdot\|_p)$ vollständig, d.h. jede Cauchy-Folge konvergiert gegen ein Element im Raum.
        
90. **$(C[a,b], \|\cdot\|_1)$ ist ein vollständiger Raum.**
    
    - **Antwort: Falsch.** Der Raum der stetigen Funktionen mit der Integralnorm ist nicht vollständig. Eine Cauchy-Folge stetiger Funktionen kann gegen eine unstetige Funktion konvergieren, die nicht mehr in $C[a,b]$ liegt.
        
91. **Wenn $\sum \int |f_{n+1} - f_n| d\mu < \infty$, dann konvergiert die Reihe fast sicher.**
    
    - **Antwort: Wahr.** Wenn die Reihe der Differenzen integrierbar ist, existiert eine Grenzfunktion $f \in L^1$, gegen die die Folge $f_n$ fast sicher konvergiert. Dies ist ein wichtiges Konvergenzkriterium.
        
92. **$f \sim_\mu g$ ist eine Äquivalenzrelation.**
    
    - **Antwort: Wahr.** Die Relation "$f=g$ fast überall" erfüllt Reflexivität, Symmetrie und Transitivität. Sie partitioniert die Menge der messbaren Funktionen in disjunkte Klassen.
        
93. **Das Integral ist auf Äquivalenzklassen wohldefiniert.**
    
    - **Antwort: Wahr.** Funktionen, die sich nur auf einer Nullmenge unterscheiden, haben dasselbe Integral. Daher hängt der Wert des Integrals nicht vom gewählten Repräsentanten ab.
        
94. **$L^2(\mu)$ ist der einzige Hilbertraum unter den $L^p$-Räumen.**
    
    - **Antwort: Wahr.** Obwohl das Skript allgemein Banachräume für $p \ge 1$ definiert, ist $L^2$ der Spezialfall, in dem die Norm durch ein Skalarprodukt induziert wird (allgemeines mathematisches Wissen im Kontext von $L^p$, Skript spezifiziert nur Normeigenschaften).
        
95. **Für $p<1$ ist $\|\cdot\|_p$ keine Norm.**
    
    - **Antwort: Wahr.** Das Skript definiert die Norm und den Banachraum explizit für $p \ge 1$. Für $0 < p < 1$ ist die Dreiecksungleichung im Allgemeinen verletzt.
        
96. **Eine Cauchy-Folge in $L^p$ konvergiert gegen ein Element in $L^p$.**
    
    - **Antwort: Wahr.** Dies ist die Definition von Vollständigkeit, welche $L^p$-Räume erfüllen.
        
97. **Gleichmäßige Konvergenz ist stärker als punktweise Konvergenz.**
    
    - **Antwort: Wahr.** Aus gleichmäßiger Konvergenz folgt immer punktweise Konvergenz. Die Umkehrung gilt nicht.
        
98. **Punktweise Konvergenz ist stärker als Konvergenz im Maß (auf endlichen Räumen).**
    5
    - **Antwort: Wahr.** Auf Räumen mit endlichem Maß impliziert fast sichere (und damit auch punktweise) Konvergenz die Konvergenz dem Maß nach.
        
99. **Die Funktion $1/x$ auf $(0,1]$ ist in $L^1(\lambda)$.**
    
    - **Antwort: Falsch.** Das uneigentliche Integral $\int_0^1 \frac{1}{x} dx$ divergiert ($\ln(1) - \lim_{a\to 0} \ln(a) = \infty$). Daher ist die Funktion nicht integrierbar im Sinne von $L^1$.
        
100. **Die Indikatorfunktion der rationalen Zahlen $\chi_{\mathbb{Q}}$ ist in $L^1(\mathbb{R}, \lambda)$ gleich der Nullfunktion (in der Äquivalenzklasse).** * **Antwort: Wahr.** Da $\mathbb{Q}$ eine Nullmenge ist (abzählbar), ist $\chi_{\mathbb{Q}} = 0$ fast überall. In $L^1$ repräsentieren beide Funktionen dieselbe Äquivalenzklasse $[0]$.

Hier sind 3 Wahr/Falsch-Fragen basierend auf dem von Ihnen bereitgestellten Text:

**1. Wenn eine Eigenschaft mittels vollständiger Induktion für jede endliche Anzahl $n$ von Mengen bewiesen wurde, gilt sie automatisch auch für abzählbar unendliche Vereinigungen.**

- **Antwort: Falsch.**
    
    - **Erklärung:** Die Induktion beweist eine Aussage nur für jedes feste, endliche $n$. Sie erlaubt keinen direkten Schluss auf den Grenzwert $n \to \infty$ (abzählbar unendlich viele Schritte).
        

**2. Im Ring $\mathcal{R}$ der endlichen Vereinigungen halboffener Intervalle $(a,b]$ ist die Menge $(0,1)$ enthalten.**

- **Antwort: Falsch.**
    
    - **Erklärung:** Die Menge $(0,1)$ entsteht zwar als abzählbare Vereinigung von Elementen aus dem Ring ($\bigcup A_n$), liegt selbst aber nicht im Ring, da sie am rechten Rand offen ist und nicht als _endliche_ Vereinigung von Intervallen der Form $(a,b]$ dargestellt werden kann.
        

**3. Eine $\sigma$-Algebra unterscheidet sich von einem Ring dadurch, dass sie Abgeschlossenheit unter abzählbaren (und nicht nur endlichen) Vereinigungen fordert.**

- **Antwort: Wahr.**
    
    - **Erklärung:** Das Beispiel zeigt, dass der Ring $\mathcal{R}$ bei unendlichen Vereinigungen "ausbricht" (das Ergebnis liegt nicht mehr in $\mathcal{R}$), während die $\sigma$-Algebra genau diese Lücke schließt, indem sie per Definition auch abzählbar unendliche Vereinigungen enthält.
- 