Das Konvergieren einer Folge $(\mathbf{z}_n)_{n \in \mathbb{N}}$ gegen einen Punkt $\mathbf{a}$ im $\mathbb{R}^2$ wird mathematisch auf verschiedene Weisen ausgedrückt.

Da die Folge mit den Komponenten **$\left(\left(x_{1n}, x_{2n}\right)\right)_{n \in \mathbb{N}}$** notiert wurde und der Grenzwert $\mathbf{a}$ selbst ein Punkt im $\mathbb{R}^2$ ist, den wir als $\mathbf{a} = (a_1, a_2)$ schreiben können, sind die gängigsten Notationen:

***

## 1. Limes-Schreibweise (Standard)

Dies ist die formellste und am häufigsten verwendete Schreibweise:

$$\mathbf{\lim_{n \to \infty} \left(x_{1n}, x_{2n}\right) = (a_1, a_2)}$$

*oder allgemeiner formuliert:*

$$\mathbf{\lim_{n \to \infty} \mathbf{z}_n = \mathbf{a}}$$

***

## 2. Pfeil-Schreibweise (Kurzform)

Die Konvergenz wird oft mit einem Pfeil (über dem oder unter dem ein $n \to \infty$ steht) abgekürzt:

$$\mathbf{\left(x_{1n}, x_{2n}\right) \xrightarrow{n \to \infty} (a_1, a_2)}$$

***

## 3. Komponentenschreibweise

Da eine Folge im $\mathbb{R}^2$ genau dann konvergiert, wenn **jede ihrer Komponenten konvergiert**, kann die Konvergenz auch über die einzelnen Komponenten ausgedrückt werden:

$$\mathbf{\left(x_{1n}, x_{2n}\right) \text{ konvergiert gegen } (a_1, a_2) \iff \begin{cases} \lim_{n \to \infty} x_{1n} = a_1 \\ \lim_{n \to \infty} x_{2n} = a_2 \end{cases}}$$

Diese Darstellung ist besonders nützlich, wenn man die Konvergenz beweisen oder berechnen möchte.



Es scheint, Sie möchten eine mathematische Zeile formatieren, um zu zeigen, dass der Ausdruck gegen Null konvergiert, wenn der Vektor $\begin{pmatrix} x_1 \\ x_2 \end{pmatrix}$ gegen $\begin{pmatrix} 0 \\ 0 \end{pmatrix}$ konvergiert.

Die Konvergenz wird in diesem Fall gegen den Skalarwert $0$ gezeigt, da der Ausdruck auf der linken Seite einen **Skalar**-Betrag $\left| \frac{(x_1 + x_2)^2}{\sqrt{x_1^2 + x_2^2}} \right|$ darstellt. Der Grenzwert muss daher der Skalar $0$ sein, nicht der Vektor $\begin{pmatrix} 0 \\ 0 \end{pmatrix}$.

Hier ist die korrigierte und wunschgemäß formatierte Darstellung:

$$\mathbf{ \left| \frac{(x_1 + x_2)^2}{\sqrt{x_1^2 + x_2^2}} \right| \leq \frac{2(x_1^2 + x_2^2)}{\sqrt{x_1^2+x_2^2}} = 2\sqrt{x_1^2+x_2^2} \xrightarrow{\quad \begin{pmatrix} x_1 \\ x_2 \end{pmatrix} \to \begin{pmatrix} 0 \\ 0 \end{pmatrix} \quad} 0 }$$

---

### Erläuterung der Korrekturen

1. **Zielwert:** Der Grenzwert des Ausdrucks ist der **Skalarwert 0**, da die gesamte Ungleichung einen Betrag (einen Skalar) begrenzt. Die Notation $\begin{pmatrix} 0 \\ 0 \end{pmatrix}$ als Grenzwert wurde korrigiert zu $\mathbf{0}$.
    
2. **Pfeil-Notation:** Die gewünschte Konvergenz $\begin{pmatrix} x_1 \\ x_2 \end{pmatrix} \to \begin{pmatrix} 0 \\ 0 \end{pmatrix}$ wurde über dem Pfeil platziert.
    
3. **Vereinfachung:** $\frac{2(x_1^2 + x_2^2)}{\sqrt{x_1^2+x_2^2}}$ wurde korrekt zu $\mathbf{2\sqrt{x_1^2+x_2^2}}$ vereinfacht (da $\frac{a}{\sqrt{a}} = \sqrt{a}$ für $a>0$).
    

Die gesamte Aussage beweist, dass der Grenzwert des Ausdrucks $\mathbf{0}$ ist, da $\sqrt{x_1^2+x_2^2}$ die euklidische Norm (Abstand zum Ursprung) ist, die gegen Null konvergiert, und somit auch der gesamte Ausdruck gegen Null geht (Sandwich-Theorem, da der ursprüngliche Ausdruck $\geq 0$ ist).