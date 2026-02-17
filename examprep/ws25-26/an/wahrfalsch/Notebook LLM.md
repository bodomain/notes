Hier sind die 100 Fragen für Anki-Karteikarten. Jede Antwort enthält nun eine kurze, nicht-formale Begründung sowie den Verweis auf den entsprechenden Abschnitt im Glossar.

### Reelle Zahlen & Konvergenz

1.  **Frage:** In einem Körper $(\mathbb{R}, +, \cdot)$ ist das neutrale Element der Addition eindeutig bestimmt.
    **Antwort:** **Wahr.** Es gibt nur genau eine Null (und eine Eins). (Abschnitt 1.1.1, Körpereigenschaften)

2.  **Frage:** Für reelle Zahlen $a, b$ gilt stets $|a + b| = |a| + |b|$.
    **Antwort:** **Falsch.** Das gilt nicht allgemein; die Dreiecksungleichung besagt $|a + b| \le |a| + |b|$. (Abschnitt 1.2.2, Dreiecksungleichung)

3.  **Frage:** Jede Cauchyfolge in einem normierten Raum ist konvergent.
    **Antwort:** **Falsch.** Das gilt nur, wenn der Raum vollständig ist (ein Banachraum). (Abschnitt 1.5.17, Vollständiger normierter Raum/Banachraum)

4.  **Frage:** Der Raum $(\mathbb{R}^n, \|\cdot\|)$ ist für jede beliebige Norm vollständig.
    **Antwort:** **Wahr.** Endlichdimensionale Vektorräume wie $\mathbb{R}^n$ sind immer vollständig. (Abschnitt 1.5.18, $\mathbb{R}^n$ als Banachraum)

5.  **Frage:** Eine reelle Folge ist genau dann konvergent, wenn sie eine Cauchyfolge ist.
    **Antwort:** **Wahr.** In den reellen Zahlen fallen Konvergenz und die Cauchy-Eigenschaft zusammen (Cauchykriterium). (Abschnitt 1.2.21, Cauchykriterium)

6.  **Frage:** Jede beschränkte reelle Folge ist konvergent.
    **Antwort:** **Falsch.** Sie muss nicht konvergieren (z.B. $(-1)^n$), besitzt aber eine konvergente Teilfolge. (Abschnitt 1.2.17, Satz von Bolzano–Weierstraß)

7.  **Frage:** Der Raum $C()$ versehen mit der Norm $\|f\|_1$ ist ein Banachraum.
    **Antwort:** **Falsch.** Eine Folge stetiger Funktionen kann bezüglich der Fläche (Integralnorm) gegen eine unstetige Funktion konvergieren, der Raum ist also unvollständig. (Abschnitt 1.5.19, Beispiel iii)

8.  **Frage:** In $\mathbb{R}^n$ sind alle Normen äquivalent.
    **Antwort:** **Wahr.** Konvergenz in einer Norm impliziert im Endlichdimensionalen Konvergenz in jeder anderen Norm. (Abschnitt 1.5.11, Äquivalenz der Normen auf $\mathbb{R}^n$)

9.  **Frage:** Ist eine Folge $(a_k)$ konvergent gegen $a$, so ist sie auch beschränkt.
    **Antwort:** **Wahr.** Da sie sich dem Grenzwert nähert, kann sie nicht unendlich groß werden. (Abschnitt 1.2.9, $c \subseteq \ell^\infty$)

10. **Frage:** Für das Supremum $S$ einer Menge $M$ muss gelten, dass $S \in M$.
    **Antwort:** **Falsch.** Das Supremum ist die kleinste obere Schranke, muss aber nicht zur Menge gehören (z.B. bei offenen Intervallen). (Abschnitt 1.1.10, Supremum/Infimum)

### Topologie & Stetigkeit

11. **Frage:** Eine Menge $M \subseteq \mathbb{R}^n$ ist genau dann offen, wenn ihr Komplement abgeschlossen ist.
    **Antwort:** **Wahr.** Dies ist die duale Definition von offenen und abgeschlossenen Mengen. (Abschnitt 2.4.6, Offene und abgeschlossene Mengen)

12. **Frage:** Die Vereinigung beliebig vieler abgeschlossener Mengen ist stets abgeschlossen.
    **Antwort:** **Falsch.** Unendliche Vereinigungen können offen sein; nur endliche Vereinigungen bleiben sicher abgeschlossen. (Abschnitt 2.4.4, Eigenschaften offener Mengen – dual betrachtet)

13. **Frage:** Eine Teilmenge $M \subseteq \mathbb{R}^n$ ist genau dann kompakt, wenn sie abgeschlossen und beschränkt ist.
    **Antwort:** **Wahr.** Dies ist die zentrale Aussage des Satzes von Heine-Borel für den $\mathbb{R}^n$. (Abschnitt 2.5.6, Satz von Heine–Borel)

14. **Frage:** Das stetige Bild einer kompakten Menge ist wieder kompakt.
    **Antwort:** **Wahr.** Stetige Funktionen erhalten die Kompaktheitseigenschaft. (Abschnitt 2.1.22 / 2.5.7, Stetiges Bild einer kompakten Menge)

15. **Frage:** Eine Funktion $f: \mathbb{R}^n \to \mathbb{R}^m$ ist genau dann stetig, wenn das Urbild jeder offenen Menge offen ist.
    **Antwort:** **Wahr.** Das ist die topologische Definition von Stetigkeit. (Abschnitt 2.4.7, Stetigkeit und offene Mengen)

16. **Frage:** Jede stetige Funktion auf einem offenen Intervall ist gleichmäßig stetig.
    **Antwort:** **Falsch.** Auf offenen Mengen kann die Steigung unbeschränkt sein (z.B. $1/x$ nahe 0), was gleichmäßige Stetigkeit verhindert. (Abschnitt 2.1.27 / 2.5.9, Gleichmäßige Stetigkeit auf kompakten Mengen)

17. **Frage:** Ist $f: M \to \mathbb{R}$ stetig auf einer kompakten Menge $M$, so nimmt $f$ Maximum und Minimum an.
    **Antwort:** **Wahr.** Auf kompakten Mengen werden die Extremwerte tatsächlich erreicht. (Abschnitt 2.1.23 / 2.5.8, Satz von Weierstraß / Satz vom Maximum)

18. **Frage:** Jede lineare Abbildung $f: \mathbb{R}^n \to \mathbb{R}^m$ ist stetig.
    **Antwort:** **Wahr.** Lineare Abbildungen in endlichen Dimensionen sind immer beschränkt und damit stetig. (Abschnitt 2.3.11, Beispiel ii)

19. **Frage:** Eine Menge $M \subseteq \mathbb{R}$ ist genau dann zusammenhängend, wenn sie ein Intervall ist.
    **Antwort:** **Wahr.** In $\mathbb{R}$ gibt es keine anderen zusammenhängenden Formen. (Abschnitt 2.4.11, Zusammenhängende Mengen in $\mathbb{R}$)

20. **Frage:** Der Zwischenwertsatz besagt, dass das stetige Bild eines Intervalls wieder ein Intervall ist.
    **Antwort:** **Wahr.** Die Funktion nimmt alle Werte zwischen Minimum und Maximum an, es entstehen keine Lücken. (Abschnitt 2.1.15 / 2.4.13, Stetiges Bild eines Intervalls)

### Differenzierbarkeit in $\mathbb{R}$

21. **Frage:** Ist eine Funktion $f: \mathbb{R} \to \mathbb{R}$ differenzierbar in $a$, so ist sie dort auch stetig.
    **Antwort:** **Wahr.** Differenzierbarkeit ist eine stärkere Eigenschaft als Stetigkeit. (Abschnitt 3.3.3, Differenzierbarkeit und Stetigkeit)

22. **Frage:** Ist eine Funktion $f: \mathbb{R} \to \mathbb{R}$ stetig in $a$, so ist sie dort auch differenzierbar.
    **Antwort:** **Falsch.** Stetige Funktionen können Ecken haben (z.B. Betragsfunktion), wo sie nicht differenzierbar sind. (Abschnitt 3.3.3, Differenzierbarkeit und Stetigkeit)

23. **Frage:** Wenn $f: I \to \mathbb{R}$ auf dem Inneren eines Intervalls differenzierbar ist und $f'(x) = 0$ für alle $x$, dann ist $f$ konstant.
    **Antwort:** **Wahr.** Ohne Steigung ändert sich der Funktionswert nicht. (Abschnitt 3.3.12, Charakterisierung der konstanten Funktionen)

24. **Frage:** Der Mittelwertsatz besagt, dass ein $\xi \in ]a,b[$ existiert mit $f(b)-f(a) = f'(\xi)(b-a)$.
    **Antwort:** **Wahr.** Die Sekantensteigung wird an mindestens einer Stelle als Tangentensteigung angenommen. (Abschnitt 3.3.10, Mittelwertsatz der Differenzialrechnung)

25. **Frage:** Jede Polynomfunktion ist auf ganz $\mathbb{R}$ differenzierbar.
    **Antwort:** **Wahr.** Polynome sind glatte Funktionen ohne Ecken oder Sprünge. (Abschnitt 3.3.6, Polynomfunktion)

26. **Frage:** Die Ableitung der Funktion $f(x) = \ln(x)$ ist $f'(x) = \frac{1}{x}$.
    **Antwort:** **Wahr.** Das ist eine Standardableitung. (Tabelle 3.3-1, Elementare Funktionen und ihre Ableitungen)

27. **Frage:** Die Funktion $f(x) = |x|$ ist im Punkt $0$ differenzierbar.
    **Antwort:** **Falsch.** Sie hat dort einen Knick; die links- und rechtsseitigen Ableitungen sind verschieden. (Implizit in Abschnitt 3.3.1)

28. **Frage:** Satz von Rolle: Wenn $f(a)=f(b)$, dann gibt es ein $\xi \in ]a, b[$ mit $f'(\xi) = 0$.
    **Antwort:** **Wahr.** Dies ist der Spezialfall des Mittelwertsatzes für gleiche Randwerte (waagrechte Tangente). (Abschnitt 3.3.10, Folgerung aus dem Mittelwertsatz)

29. **Frage:** Die Regel von de l'Hospital gilt für Grenzwerte vom Typ $0/0$ oder $\infty/\infty$.
    **Antwort:** **Wahr.** Sie hilft, unbestimmte Ausdrücke durch Ableiten von Zähler und Nenner zu bestimmen. (Abschnitt 3.3.14 / 3.3.16, Regel von de l’Hospital)

### Differenzierbarkeit in $\mathbb{R}^n$

30. **Frage:** Eine Funktion $f: \mathbb{R}^n \to \mathbb{R}^m$ ist genau dann total differenzierbar, wenn alle partiellen Ableitungen existieren.
    **Antwort:** **Falsch.** Existenz reicht nicht, die partiellen Ableitungen müssen (hinreichend) auch stetig sein. (Abschnitt 3.6.4, Partielle und totale Differenzierbarkeit)

31. **Frage:** Wenn $f: \mathbb{R}^n \to \mathbb{R}$ in $a$ total differenzierbar ist, dann existieren dort alle partiellen Ableitungen.
    **Antwort:** **Wahr.** Totale Differenzierbarkeit impliziert Differenzierbarkeit in jede Richtung. (Abschnitt 3.6.3, Totale und partielle Differenzierbarkeit)

32. **Frage:** Der Gradient zeigt in die Richtung des steilsten Anstiegs.
    **Antwort:** **Wahr.** Die Richtungsableitung ist maximal in Richtung des Gradienten. (Abschnitt 3.6.7, Ableitung und Richtungsableitung)

33. **Frage:** Die Funktionalmatrix einer Abbildung $f: \mathbb{R}^n \to \mathbb{R}^m$ hat das Format $(n, m)$.
    **Antwort:** **Falsch.** Sie hat das Format $(m, n)$ ($m$ Zeilen für die Funktionen, $n$ Spalten für die Variablen). (Abschnitt 3.6.8, Funktionalmatrix)

34. **Frage:** Ist $f$ zweimal stetig partiell differenzierbar, so gilt $D_{ij}f = D_{ji}f$.
    **Antwort:** **Wahr.** Bei stetigen zweiten Ableitungen darf die Reihenfolge vertauscht werden (Satz von Schwarz). (Abschnitt 4.4.3, Satz von Schwarz)

35. **Frage:** Wenn $f: \mathbb{R}^n \to \mathbb{R}$ in $a$ differenzierbar ist und ein lokales Extremum hat, gilt $\operatorname{grad} f(a) = 0$.
    **Antwort:** **Wahr.** In einem Extremum muss die Tangentialebene waagrecht sein (notwendige Bedingung). (Abschnitt 4.5.3, Notwendige Bedingung)

36. **Frage:** Wenn $\operatorname{grad} f(a) = 0$ und die Hesse-Matrix $H(a)$ positiv definit ist, liegt ein lokales Maximum vor.
    **Antwort:** **Falsch.** Positiv definit (Krümmung nach oben) bedeutet ein Minimum. (Abschnitt 4.5.6, Lokales Extremum)

37. **Frage:** Ist die Hesse-Matrix indefinit an einer Stelle mit verschwindendem Gradienten, so liegt kein Extremum vor.
    **Antwort:** **Wahr.** Es handelt sich um einen Sattelpunkt. (Abschnitt 4.5.6, Lokales Extremum)

38. **Frage:** Der Satz über implizite Funktionen garantiert die lokale Auflösbarkeit einer Gleichung $F(x,y)=0$.
    **Antwort:** **Wahr.** Unter der Bedingung, dass die Funktionalmatrix invertierbar ist, kann man lokal nach Variablen auflösen. (Abschnitt 4.2.3, Satz über implizite Funktionen)

39. **Frage:** Eine Funktion $f: \mathbb{R}^n \to \mathbb{R}^m$ heißt stetig differenzierbar, wenn sie differenzierbar ist und ihre Ableitung stetig ist.
    **Antwort:** **Wahr.** Das ist die Definition der Klasse $C^1$. (Abschnitt 4.4.4, Differenzierbarkeit höherer Ordnung)

### Funktionenfolgen und Reihen

40. **Frage:** Konvergiert eine Folge stetiger Funktionen gleichmäßig gegen $f$, so ist $f$ stetig.
    **Antwort:** **Wahr.** Gleichmäßige Konvergenz erhält die Stetigkeitseigenschaft. (Abschnitt 2.6.5, Satz von Weierstraß)

41. **Frage:** Punktweise Konvergenz einer Funktionenfolge impliziert gleichmäßige Konvergenz.
    **Antwort:** **Falsch.** Punktweise Konvergenz ist schwächer und erlaubt z.B., dass "Buckel" immer schmaler werden und wandern. (Abschnitt 2.6.2, Gleichmäßige Konvergenz)

42. **Frage:** Eine Potenzreihe konvergiert innerhalb ihres Konvergenzradius auf jedem kompakten Teilintervall gleichmäßig.
    **Antwort:** **Wahr.** Im Inneren des Konvergenzbereichs ist die Konvergenz "gut" (gleichmäßig). (Abschnitt 2.6.9, Potenzreihenfunktion)

43. **Frage:** Eine Potenzreihe darf innerhalb ihres Konvergenzradius gliedweise differenziert werden.
    **Antwort:** **Wahr.** Potenzreihen verhalten sich im Inneren wie Polynome. (Abschnitt 3.3.19, Potenzreihenfunktion)

44. **Frage:** Das Majorantenkriterium von Weierstraß dient dem Nachweis der punktweisen Konvergenz.
    **Antwort:** **Falsch.** Es ist ein starkes Kriterium für die *gleichmäßige* Konvergenz. (Abschnitt 2.6.8, Majorantenkriterium)

45. **Frage:** Die Fourierreihe einer $2\pi$-periodischen differenzierbaren Funktion konvergiert punktweise gegen die Funktion.
    **Antwort:** **Wahr.** Unter Glattheitsvoraussetzungen stellt die Fourierreihe die Funktion dar. (Abschnitt 5.4.9, Darstellungssatz)

46. **Frage:** Die Fourierkoeffizienten einer integrierbaren Funktion streben gegen Null für $k \to \infty$.
    **Antwort:** **Wahr.** Hohe Frequenzen haben immer kleinere Amplituden (Lemma von Riemann-Lebesgue). (Abschnitt 5.4.7, Besselsche Ungleichung)

47. **Frage:** Nach dem Satz von Fejér konvergiert die Fourierreihe jeder stetigen Funktion gleichmäßig gegen die Funktion.
    **Antwort:** **Falsch.** Die Reihe selbst konvergiert nicht zwingend, aber ihre Mittelwerte (Fejér-Summen) tun es. (Abschnitt 5.5.3, Satz von Fejér)

48. **Frage:** Jede stetige Funktion auf einem kompakten Intervall kann gleichmäßig durch Polynome approximiert werden.
    **Antwort:** **Wahr.** Polynome liegen "dicht" im Raum der stetigen Funktionen. (Abschnitt 5.5.4, Weierstraßscher Approximationssatz)

### Integration

49. **Frage:** Jede monotone Funktion auf einem kompakten Intervall ist Riemann-integrierbar.
    **Antwort:** **Wahr.** Monotone Funktionen haben nur abzählbar viele Sprungstellen und sind daher integrierbar. (Abschnitt 5.1.6, Riemannintegral)

50. **Frage:** $F(x) = \int_a^x f(t) dt$ ist eine Stammfunktion für stetiges $f$.
    **Antwort:** **Wahr.** Das Integral als Funktion der oberen Grenze leitet sich zur Funktion ab. (Abschnitt 5.1.10, Hauptsatz der Differenzial- und Integralrechnung)

51. **Frage:** Für das Riemann-Integral gilt stets $\int f \cdot g = \int f \cdot \int g$.
    **Antwort:** **Falsch.** Das Integral ist linear, aber nicht multiplikativ (Produktregel beachten). (Abschnitt 5.1.7, Eigenschaften des Integrals)

52. **Frage:** Ist $f$ auf $[a,b]$ integrierbar, so ist auch $|f|$ integrierbar.
    **Antwort:** **Wahr.** Die Betragsbildung erhält die Integrierbarkeit. (Abschnitt 5.1.7, Eigenschaften des Integrals)

53. **Frage:** Wenn $\int_a^b |f(x)| dx = 0$ für eine stetige Funktion $f$, dann ist $f(x) = 0$ für alle $x$.
    **Antwort:** **Wahr.** Eine stetige Funktion, die nicht überall Null ist, würde eine positive Fläche erzeugen. (Abschnitt 1.1.19 / 5.1.7, Normeigenschaften)

54. **Frage:** Ein uneigentliches Integral konvergiert genau dann, wenn die Folge der Integrale bis $n$ konvergiert.
    **Antwort:** **Falsch.** Der Grenzwert muss für jede beliebige Annäherung existieren, nicht nur für ganzzahlige Schritte. (Abschnitt 5.2.1, Uneigentliches Integral)

55. **Frage:** Die Gammafunktion ist definiert als $\Gamma(x) = \int_0^\infty t^{x-1}e^{-t} dt$.
    **Antwort:** **Wahr.** Dies ist die Standard-Integraldarstellung der Gammafunktion. (Abschnitt 5.2.5 / 5.3.3, Gammafunktion)

56. **Frage:** Es gilt $\Gamma(n+1) = n!$ für $n \in \mathbb{N}_0$.
    **Antwort:** **Wahr.** Die Gammafunktion interpoliert die Fakultät. (Abschnitt 5.2.5, Eigenschaften der Gammafunktion)

57. **Frage:** Die Leibniz-Regel erlaubt unter Voraussetzungen das Vertauschen von Differentiation und Integration.
    **Antwort:** **Wahr.** Man darf "unter dem Integralzeichen" ableiten, wenn der Integrand glatt genug ist. (Abschnitt 5.3.4, Leibnizsche Regel)

### Kurven & Vektorfelder

58. **Frage:** Eine Kurve heißt rektifizierbar, wenn ihre Länge endlich ist.
    **Antwort:** **Wahr.** Rektifizierbarkeit ist gleichbedeutend mit messbarer, endlicher Länge. (Abschnitt 6.2.2, Länge einer Kurve)

59. **Frage:** Die Länge einer stetig differenzierbaren Kurve ist $\int_\alpha^\beta \|\dot{\phi}(t)\|_2 dt$.
    **Antwort:** **Wahr.** Man integriert den Betrag der Geschwindigkeit über die Zeit. (Abschnitt 6.2.5, Stetig differenzierbare Kurve)

60. **Frage:** Ein Vektorfeld besitzt genau dann eine Stammfunktion, wenn das Wegintegral wegunabhängig ist.
    **Antwort:** **Wahr.** Das ist der Hauptsatz für Kurvenintegrale (Gradientenfelder sind konservativ). (Abschnitt 6.4.4, Wegunabhängigkeit)

61. **Frage:** Auf einem sternförmigen Gebiet ist die Integrabilitätsbedingung hinreichend für eine Stammfunktion.
    **Antwort:** **Wahr.** Auf einfach zusammenhängenden (hier sternförmigen) Gebieten reicht die Rotationsfreiheit. (Abschnitt 6.4.6, Existenz einer Stammfunktion)

62. **Frage:** Das Kurvenintegral 1. Art ist für vektorwertige Funktionen definiert.
    **Antwort:** **Falsch.** Das Integral 1. Art ($\int f ds$) ist für skalare Funktionen; für Vektorfelder nimmt man das 2. Art. (Abschnitt 6.3.1 / 6.3.4)

63. **Frage:** Die Länge einer Kurve ändert sich nicht bei einer Umparametrisierung.
    **Antwort:** **Wahr.** Die geometrische Länge hängt nicht davon ab, wie schnell man die Kurve durchläuft. (Abschnitt 6.2.8, Bogenlänge / Invarianz der Spur und Länge)

### Gemischte Themen

64. **Frage:** Für $x,y \in \mathbb{R}^n$ gilt die Cauchy-Schwarzsche Ungleichung $|\sum x_k y_k| \le \sqrt{\sum x_k^2} \sqrt{\sum y_k^2}$.
    **Antwort:** **Wahr.** Der Betrag des Skalarprodukts ist kleiner gleich dem Produkt der Normen. (Abschnitt 1.1.8, Cauchy–Schwarzsche Ungleichung)

65. **Frage:** Jede beschränkte Teilmenge von $\mathbb{R}$ hat ein Supremum in $\mathbb{R}$.
    **Antwort:** **Falsch.** Die Menge muss zusätzlich *nichtleer* sein. (Abschnitt 1.1.12, Existenz des Supremums)

66. **Frage:** Das Intervall $]0, 1[$ ist kompakt.
    **Antwort:** **Falsch.** Es ist beschränkt, aber nicht abgeschlossen (Rand fehlt). (Abschnitt 1.1.14 / 2.5.2, Kompaktheit)

67. **Frage:** Jede Cauchyfolge in $\mathbb{Q}$ konvergiert gegen ein Element in $\mathbb{Q}$.
    **Antwort:** **Falsch.** $\mathbb{Q}$ hat "Lücken" (z.B. $\sqrt{2}$), ist also nicht vollständig. (Implizit in Abschnitt 1.1.5)

68. **Frage:** Eine Funktion $f: [a, b] \to \mathbb{R}$ ist Riemann-integrierbar, wenn sie stetig ist.
    **Antwort:** **Wahr.** Stetigkeit ist eine hinreichende Bedingung für Integrierbarkeit. (Abschnitt 5.1.5, $C(I) \subseteq R(I)$)

69. **Frage:** Die Funktion $f(x) = 1/x$ ist über $]0, 1]$ uneigentlich integrierbar.
    **Antwort:** **Falsch.** Die Fläche unter der Hyperbel wird unendlich groß (divergiert). (Abschnitt 5.2.3, Tabelle 5.1-1 Stammfunktion ln|x|)

70. **Frage:** Die Ableitung von $\arctan(x)$ ist $1/(1+x^2)$.
    **Antwort:** **Wahr.** Das ist die Standardableitung des Arkustangens. (Tabelle 3.3-1, Elementare Funktionen und ihre Ableitungen)

71. **Frage:** Ist $f$ differenzierbar in $a$, so existiert der Grenzwert des Differenzenquotienten.
    **Antwort:** **Wahr.** Genau das ist die Definition der Differenzierbarkeit. (Abschnitt 3.3.1, Differenzierbarkeit)

72. **Frage:** Wenn $f'(x) > 0$ auf einem Intervall, dann ist $f$ dort streng monoton wachsend.
    **Antwort:** **Wahr.** Positive Steigung bedeutet Anstieg der Funktionswerte. (Abschnitt 3.3.13, Charakterisierung der differenzierbaren, monotonen Funktionen)

73. **Frage:** Der Banachsche Fixpunktsatz gilt für jede stetige Selbstabbildung auf einer abgeschlossenen Menge.
    **Antwort:** **Falsch.** Die Abbildung muss eine *Kontraktion* sein (Abstände verringern). (Abschnitt 4.1.6, Banachscher Fixpunktsatz)

74. **Frage:** Ein lokales Maximum einer Funktion $f$ ist immer auch ein globales Maximum.
    **Antwort:** **Falsch.** Lokal bedeutet nur "in der Nähe" am größten, woanders kann es höhere Werte geben. (Abschnitt 4.5.1, Lokales Extremum)

75. **Frage:** Ist $A$ eine invertierbare Matrix, so ist $Rang(A) = n$.
    **Antwort:** **Wahr.** Voller Rang ist äquivalent zur Invertierbarkeit. (Abschnitt 4.1.1, Umkehrsatz für lineare Abbildungen)

76. **Frage:** Das Skalarprodukt zweier Vektoren ist 0, wenn sie orthogonal sind.
    **Antwort:** **Wahr.** Das ist die Definition von Orthogonalität. (Abschnitt 1.4.5, Skalarprodukt)

77. **Frage:** Orthogonale Vektoren erfüllen den Satz des Pythagoras $\|x-y\|^2 = \|x\|^2 + \|y\|^2$.
    **Antwort:** **Wahr.** Wenn der Mischterm (Skalarprodukt) wegfällt, gilt Pythagoras. (Abschnitt 1.4.7, Satz des Pythagoras)

78. **Frage:** Ist $f$ stetig, so ist $\int_a^b f(x) dx = F(b) - F(a)$ für jede Stammfunktion $F$.
    **Antwort:** **Wahr.** Man berechnet bestimmte Integrale durch Einsetzen der Grenzen in die Stammfunktion. (Abschnitt 5.1.10, Hauptsatz der Differenzial- und Integralrechnung)

79. **Frage:** Die Funktion $f(x) = e^x$ ist ihre eigene Ableitung.
    **Antwort:** **Wahr.** Das ist die charakteristische Eigenschaft der e-Funktion. (Tabelle 3.3-1, Elementare Funktionen)

80. **Frage:** Es gilt $\cos^2(x) = 1 + \tan^2(x)$.
    **Antwort:** **Falsch.** Es gilt $1/\cos^2(x) = 1 + \tan^2(x)$ (Ableitung des Tangens). (Tabelle 3.3-1)

81. **Frage:** Eine Funktion heißt Lipschitz-stetig, wenn $|f(x)-f(y)| \le L|x-y|$.
    **Antwort:** **Wahr.** Die Steigung ist durch $L$ beschränkt (Dehnungsbeschränktheit). (Abschnitt 2.3.9, Beispiel ii)

82. **Frage:** Jede Lipschitz-stetige Funktion ist gleichmäßig stetig.
    **Antwort:** **Wahr.** Da die Steigung beschränkt ist, kann die Funktion nicht beliebig steil werden. (Abschnitt 2.5.9, Übung 2.5.3)

83. **Frage:** Der Durchschnitt endlich vieler offener Mengen ist offen.
    **Antwort:** **Wahr.** Schneidet man endlich viele offene Mengen, bleibt die Schnittmenge offen. (Abschnitt 2.4.4, Eigenschaften offener Mengen)

84. **Frage:** Jede Teilfolge einer konvergenten Folge konvergiert gegen denselben Grenzwert.
    **Antwort:** **Wahr.** Man kann dem Ziel nicht entkommen, egal welche Elemente man auswählt. (Abschnitt 1.2.12, Teilfolge)

85. **Frage:** Eine Reihe $\sum a_k$ konvergiert, wenn die Folge $(a_k)$ eine Nullfolge ist.
    **Antwort:** **Falsch.** Das ist notwendig, aber nicht hinreichend (siehe harmonische Reihe). (Abschnitt 1.2.10, Raum c)

86. **Frage:** In einem Banachraum impliziert absolute Konvergenz einer Reihe die Konvergenz.
    **Antwort:** **Wahr.** In vollständigen Räumen konvergieren absolut konvergente Reihen. (Abschnitt 2.6.8, Majorantenkriterium)

87. **Frage:** Der Konvergenzradius einer Potenzreihe bestimmt den Bereich der punktweisen Konvergenz.
    **Antwort:** **Wahr.** Innerhalb konvergiert sie, außerhalb divergiert sie. (Abschnitt 2.6.9, Potenzreihenfunktion)

88. **Frage:** Das Taylorpolynom approximiert $f(x)$ so, dass der Restterm schneller als $(x-a)^k$ gegen 0 geht.
    **Antwort:** **Wahr.** Das ist die definierende Eigenschaft der Taylor-Approximation ("little-o"). (Abschnitt 4.4.9, Approximationsgeschwindigkeit)

89. **Frage:** Die Lagrange-Restgliedformel gibt eine Darstellung für den Fehler der Taylorapproximation.
    **Antwort:** **Wahr.** Sie drückt den Fehler durch die $(k+1)$-te Ableitung an einer Zwischenstelle aus. (Abschnitt 4.3.9, Satz von Taylor)

90. **Frage:** Ein Gebiet $G \subset \mathbb{R}^n$ ist eine offene und zusammenhängende Menge.
    **Antwort:** **Wahr.** Das ist die topologische Definition eines Gebiets. (Abschnitt 6.4.1, Stammfunktion – Definition Gebiet)

91. **Frage:** Ist $\nabla f = 0$ auf einem zusammenhängenden Gebiet, so ist $f$ konstant.
    **Antwort:** **Wahr.** Wenn die Änderung überall null ist und das Gebiet "am Stück" ist, ändert sich der Wert nie. (Abschnitt 3.5.10, Konstante Funktionen)

92. **Frage:** Das Volumen eines Rotationskörpers ist $V = \pi \int_a^b (f(x))^2 dx$.
    **Antwort:** **Wahr.** Man integriert die Kreisflächen $\pi r^2$ entlang der Achse. (Abschnitt 6.5.5, Rotationskörper)

93. **Frage:** Die Fläche zwischen zwei Graphen $f$ und $g$ (mit $g \le f$) ist $\int_a^b (g(x)-f(x)) dx$.
    **Antwort:** **Falsch.** Für eine positive Fläche muss man "oben minus unten" rechnen, also $f-g$. (Abschnitt 6.5.2, Flächen zwischen zwei Graphen)

94. **Frage:** $f(x,y) = x^2 + y^2$ hat im Ursprung ein lokales Minimum.
    **Antwort:** **Wahr.** Es ist ein Paraboloid, der nach oben geöffnet ist; Hesse-Matrix ist positiv definit. (Abschnitt 4.5.6, Lokales Extremum)

95. **Frage:** Die partielle Integration leitet sich aus der Produktregel ab.
    **Antwort:** **Wahr.** Sie ist die Umkehrung der Produktregel der Differentiation. (Abschnitt 5.1.11, Partielle Integration)

96. **Frage:** Die Substitutionsregel entspricht der Kettenregel der Differentiation.
    **Antwort:** **Wahr.** Sie ist die Umkehrung der Kettenregel für Integrale. (Abschnitt 5.1.12, Substitutionsregel)

97. **Frage:** Vertauschung der Integrationsgrenzen kehrt das Vorzeichen um.
    **Antwort:** **Wahr.** Das ist Teil der Definition des orientierten Integrals. (Abschnitt 5.1.9, Vertauschung der Integrationsgrenzen)

98. **Frage:** Jede stetige Funktion auf einem kompakten Intervall ist beschränkt.
    **Antwort:** **Wahr.** Stetige Bilder kompakter Mengen sind kompakt (also auch beschränkt). (Abschnitt 2.5.8, Satz vom Maximum)

99. **Frage:** Eine Menge ist abgeschlossen, wenn sie alle ihre Häufungspunkte enthält.
    **Antwort:** **Wahr.** Das ist eine Standardcharakterisierung abgeschlossener Mengen. (Abschnitt 2.4.5, Häufungspunkt, abgeschlossene Menge)

100. **Frage:** Der Grenzwert $\lim_{x \to \infty} \ln(x)/x$ ist $0$.
     **Antwort:** **Wahr.** Der Logarithmus wächst langsamer als jede lineare Funktion (l'Hospital). (Abschnitt 3.1.12, Randverhalten einiger elementarer Funktionen)