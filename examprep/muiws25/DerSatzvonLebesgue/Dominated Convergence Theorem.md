Das ist eine hervorragende Zusammenfassung der wichtigsten Konzepte der Maßtheorie für eine Klausurvorbereitung. Ich habe die Inhalte strukturiert und übersichtlich aufbereitet, um die Logik hinter den Beweisen und die Anwendung der Sätze (insbesondere des **Dominated Convergence Theorem - DCT**) hervorzuheben.

---

# 📚 Klausurvorbereitung: Maßtheorie & Integration

## **Beispiel 1: Klassische DCT-Anwendung**

**Ziel:** Berechnung eines Grenzwerts unter dem Integralzeichen.

**Aufgabe:** Berechne $\lim_{n \to \infty} \int_0^\infty \frac{n \sin(x/n)}{x(1+x^2)} \, dx$.

### **Lösungsschritte:**

1. **Funktionenfolge:** $f_n(x) = \frac{n \sin(x/n)}{x(1+x^2)}$ für $x > 0$.
    
2. **Punktweiser Grenzwert:**
    
    Nutze die Standard-Limes-Beziehung $\lim_{u \to 0} \frac{\sin u}{u} = 1$.
    
    Setze $u = x/n$. Da $x$ fest ist, gilt für $n \to \infty$, dass $u \to 0$:
    
    $$\lim_{n \to \infty} f_n(x) = \lim_{n \to \infty} \underbrace{\frac{\sin(x/n)}{x/n}}_{\to 1} \cdot \frac{1}{1+x^2} = \frac{1}{1+x^2}$$
    
3. **Majorante finden:**
    
    Nutze die Abschätzung $|\sin u| \le |u|$.
    
    $$|f_n(x)| = \left| \frac{n \sin(x/n)}{x(1+x^2)} \right| \le \frac{n \cdot (x/n)}{x(1+x^2)} = \frac{1}{1+x^2} =: g(x)$$
    
4. **Integrierbarkeit prüfen:**
    
    $\int_0^\infty \frac{1}{1+x^2} \, dx = [\arctan x]_0^\infty = \frac{\pi}{2} < \infty$. Also $g \in L^1$.
    
5. **Anwendung DCT:**
    
    Da alle Bedingungen erfüllt sind, dürfen wir Limes und Integral vertauschen:
    
    $$\lim_{n \to \infty} \int_0^\infty f_n(x) \, dx = \int_0^\infty \frac{1}{1+x^2} \, dx = \frac{\pi}{2}$$
    

---

## **Beispiel 2: Gegenbeispiel (Warum die Majorante zwingend ist)**

**Ziel:** Verstehen, dass punktweise Konvergenz allein nicht ausreicht.

**Aufgabe:** Betrachte $f_n(x) = n \cdot \mathbb{1}_{(0,1/n)}(x)$ auf $[0,1]$.

### **Analyse:**

- **Integrale:** $\int_0^1 f_n(x) \, dx = n \cdot \frac{1}{n} = 1$ für alle $n$. Somit ist $\lim_{n \to \infty} \int f_n = 1$.
    
- **Punktweiser Limes:** Für jedes $x > 0$ gibt es ein $N$, sodass $1/n < x$ für alle $n > N$. Dann ist $f_n(x) = 0$. Also $f_n \to 0$ fast überall.
    
- **Widerspruch:** $\int \lim f_n = \int 0 = 0 \neq 1$.
    
- **Grund:** Es existiert keine integrierbare Majorante $g$. Jedes $g$, das alle $f_n$ beschränkt, müsste in der Nähe von $0$ gegen unendlich gehen, und zwar so steil, dass $\int g = \infty$.
    

---

## **Beispiel 3: Parameterabhängige Integrale**

**Ziel:** Konvergenzbereiche und Differenzierbarkeit bestimmen.

**Aufgabe:** $F(t) = \int_0^\infty \frac{\sin(tx)}{x^\alpha} \, dx$ für $t \in [a,b], 0 < a < b$.

### **Lösung & Analyse:**

|**Bereich**|**Verhalten des Integranden**|**Bedingung für Konvergenz**|
|---|---|---|
|**Bei $x \to 0$**|$\frac{\sin(tx)}{x^\alpha} \approx \frac{tx}{x^\alpha} = \frac{t}{x^{\alpha-1}}$|$\alpha-1 < 1 \implies \mathbf{\alpha < 2}$|
|**Bei $x \to \infty$**|$\left|\frac{\sin(tx)}{x^\alpha} \right|

**Resultat:** Das Integral konvergiert für $1 < \alpha < 2$.

### **Differenzierbarkeit:**

Um $F'(t)$ durch $\int \frac{\partial}{\partial t} f(x,t) \, dx$ zu berechnen, benötigen wir eine Majorante für die Ableitung:

$$\frac{\partial}{\partial t} \frac{\sin(tx)}{x^\alpha} = \frac{\cos(tx)}{x^{\alpha-1}}$$

- Damit diese Ableitung bei $x \to \infty$ integrierbar ist, müsste $\alpha-1 > 1$ gelten, also $\alpha > 2$.
    
- Dies steht im Widerspruch zum Konvergenzbereich des Originalintegrals ($1 < \alpha < 2$).
    
- **Fazit:** Im Bereich $1 < \alpha < 2$ ist die Standard-Regel zur Differentiation unter dem Integral nicht direkt anwendbar.
    

---

## **💡 Strategie-Checkliste für die Klausur**

### **1. Majoranten-Werkzeugkasten**

Achten Sie beim Suchen einer Majorante $g(x)$ auf diese Standard-Funktionen:

- **Auf $[1, \infty)$:** $1/x^p$ ist integrierbar für $p > 1$.
    
- **Auf $(0, 1]$:** $1/x^p$ ist integrierbar für $p < 1$.
    
- **Überall:** $e^{-ax}$ (für $a>0$) oder $\frac{1}{1+x^2}$.
    

### **2. Die drei großen Sätze**

1. **Monotone Konvergenz (Beppo Levi):** Wenn $f_n \ge 0$ und $f_n \nearrow f$. (Keine Majorante nötig!)
    
2. **Dominierte Konvergenz (Lebesgue/DCT):** Wenn $|f_n| \le g \in L^1$. (Der "Standardfall")
    
3. **Lemma von Fatou:** Wenn $f_n \ge 0$, dann gilt immer $\int \liminf f_n \le \liminf \int f_n$. (Nützlich für Untergrenzen)
    

### **3. Differentiation unter dem Integral**

Prüfen Sie drei Dinge:

1. $x \mapsto f(x,t)$ ist integrierbar für ein $t_0$.
    
2. $t \mapsto f(x,t)$ ist differenzierbar.
    
3. $|\frac{\partial}{\partial t} f(x,t)| \le g(x)$ mit $g \in L^1$ (**Wichtig:** Die Majorante muss für die Ableitung gelten!).
    

Soll ich für eines dieser Beispiele noch einmal einen detaillierteren Beweisschritt aufschreiben oder ein weiteres Beispiel (z.B. zum Satz von Fubini) hinzufügen?j