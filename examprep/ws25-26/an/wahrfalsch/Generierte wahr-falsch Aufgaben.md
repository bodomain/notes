Hier sind die 10 Wahr/Falsch-Fragen im Obsidian-kompatiblen Markdown-Format:

---

## Frage 1

Ist $f: \mathbb{R}^n \to \mathbb{R}^m$ linear, so ist $f$ auf ganz $\mathbb{R}^n$ differenzierbar mit $f'(a) = A$ für alle $a \in \mathbb{R}^n$, wobei $A$ die zugehörige Matrix ist.

**Lösung:** **Wahr**

**Begründung:** Gemäß Definition 3.5.4 ist jede lineare Abbildung $f(x) = Ax$ auf $\mathbb{R}^n$ differenzierbar mit konstanter Ableitung $f'(a) = A$ für alle $a \in \mathbb{R}^n$.

---

## Frage 2

Ist $f: [a,b] \to \mathbb{R}$ Riemann-integrierbar und $F(x) = \int_a^x f(t)\,dt$, so ist $F$ auf $[a,b]$ stetig differenzierbar.

**Lösung:** **Falsch**

**Begründung:** Nach dem Hauptsatz 5.1.10(i) ist $F$ nur in Punkten differenzierbar, wo $f$ stetig ist. Ist $f$ unstetig, ist $F$ dort nicht differenzierbar. $F$ ist zwar stetig (Satz 5.1.8), aber nicht notwendig stetig differenzierbar.

---

## Frage 3

Ist $f: \mathbb{R} \to \mathbb{R}$ eine Cauchy-Folge im Raum $(C(\mathbb{R}), \|\cdot\|_\infty)$, so konvergiert $f$ gleichmäßig gegen eine stetige Funktion.

**Lösung:** **Falsch**

**Begründung:** $(C(\mathbb{R}), \|\cdot\|_\infty)$ ist **kein** Banachraum, da $\mathbb{R}$ nicht kompakt ist. Die Supremumnorm kann unendlich sein oder die Grenzfunktion nicht stetig sein. Kompaktes Intervall wäre nötig (Satz 1.5.19(ii)).

---

## Frage 4

Ist $f: \mathbb{R}^2 \to \mathbb{R}$ in $(0,0)$ partiell differenzierbar, so ist $f$ in $(0,0)$ stetig.

**Lösung:** **Falsch**

**Begründung:** Partielle Differenzierbarkeit impliziert nicht Stetigkeit (nur totale Differenzierbarkeit tut das, siehe 3.5.5). Gegenbeispiel: 
$$f(x,y) = \begin{cases} \frac{xy}{x^2+y^2} & (x,y) \neq (0,0) \\ 0 & (x,y) = (0,0) \end{cases}$$
ist partiell differenzierbar, aber nicht stetig in $(0,0)$.

---

## Frage 5

Ist $M \subset \mathbb{R}^n$ kompakt und $f: M \to \mathbb{R}^m$ stetig, so ist $f(M)$ kompakt.

**Lösung:** **Wahr**

**Begründung:** Satz 2.5.7 (stetiges Bild kompakter Mengen): Ist $M$ kompakt und $f$ stetig, so ist $f(M)$ kompakt.

---

## Frage 6

Ist $f: \mathbb{R} \to \mathbb{R}$ monoton wachsend und beschränkt, so existiert $\lim_{x \to \infty} f(x)$.

**Lösung:** **Wahr**

**Begründung:** Nach dem Monotoniekriterium 1.2.16 ist eine monotone, beschränkte Folge konvergent. Für Funktionen folgt analog: Eine monoton wachsende, nach oben beschränkte Funktion hat einen Grenzwert in $\infty$ (vgl. auch 3.1.13 und Übung 3.1.4).

---

## Frage 7

Ist $f: ]a,b[ \to \mathbb{R}$ stetig und gleichmäßig stetig, so lässt sich $f$ stetig auf $[a,b]$ fortsetzen.

**Lösung:** **Wahr**

**Begründung:** Gleichmäßig stetige Funktionen auf beschränkten Intervallen lassen sich stetig auf den Abschluss fortsetzen. Die Grenzwerte $\lim_{x \to a^+} f(x)$ und $\lim_{x \to b^-} f(x)$ existieren (Cauchy-Kriterium für Funktionsgrenzwerte).

---

## Frage 8

Ist $f: \mathbb{R}^n \to \mathbb{R}$ zweimal stetig differenzierbar, so gilt $D_{ij}f(a) = D_{ji}f(a)$ für alle $a \in \mathbb{R}^n$ und alle $i,j$.

**Lösung:** **Wahr**

**Begründung:** Satz von Schwarz 4.4.3: Bei zweimal stetig differenzierbaren Funktionen kommt es auf die Reihenfolge der partiellen Differentiationen nicht an.

---

## Frage 9

Ist $\sum_{k=0}^\infty a_k x^k$ eine Potenzreihe mit Konvergenzradius $R > 0$, so konvergiert sie auf $[-R,R]$ gleichmäßig.

**Lösung:** **Falsch*-*

**Begründung:** Nach 2.6.9 konvergiert die Potenzreihe nur auf jedem **kompakten Teilintervall** $[\alpha,\beta] \subset ]a-R, a+R[$ gleichmäßig. Am Rand $x = \pm R$ kann die Konvergenz nicht gleichmäßig sein (Beispiel: $\sum x^k$ bei $x=1$).

---

## Frage 10

Ist $f: G \to \mathbb{R}^n$ ein stetig differenzierbares Vektorfeld auf einem Gebiet $G \subset \mathbb{R}^n$, das die Integrabilitätsbedingungen $D_i f_j = D_j f_i$ erfüllt, so besitzt $f$ eine Stammfunktion.

**Lösung:** **Falsch**

**Begründung:** Die Integrabilitätsbedingungen sind nur **notwendig**, nicht hinreichend auf beliebigen Gebieten. Nach 6.4.6 benötigt man zusätzlich, dass $G$ **sternförmig** ist (oder einfach zusammenhängend). Auf $\mathbb{R}^2 \setminus \{0\}$ mit 
$$f(x,y) = \frac{(-y,x)}{x^2+y^2}$$ 
sind die Bedingungen erfüllt, aber keine Stammfunktion existiert.