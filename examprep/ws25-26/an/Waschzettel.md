- Voraussetzungen Lagrange

# Elementare Ungleichungen

Ja, absolut. Der „Trick“ mit $(x-y)^2 \ge 0$ (was äquivalent zu $x^2 + y^2 \ge 2xy$ ist) gehört zu den sogenannten **elementaren Ungleichungen**. Solche Abschätzungen sind das „Handwerkszeug“ in der Analysis, um Grenzwerte zu beweisen, Fehler abzuschätzen oder wie in deiner Aufgabe Minima zu finden.

Das `glossar.pdf` enthält mehrere solcher fundamentalen Werkzeuge und Ungleichungen, die in Klausuraufgaben oft als entscheidende Zwischenschritte dienen. Hier sind die nützlichsten „Tricks“ aus deinem Dokument:

### 1. Die Cauchy-Schwarzsche Ungleichung (CSU)

Das ist der „große Bruder“ deines Tricks. Während dein Trick für zwei Zahlen gilt, gilt die CSU für ganze Summen (Vektoren).

Sie besagt, dass das Quadrat des Skalarprodukts immer kleiner oder gleich dem Produkt der Längen ist.

- **Formel:** $|\sum_{k=1}^{n}x_{k}y_{k}| \le \sqrt{\sum_{k=1}^{n}x_{k}^{2}} \cdot \sqrt{\sum_{k=1}^{n}y_{k}^{2}}$ .
    
- **Wann man sie nutzt:** Wenn man Produkte von Termen ($x_k y_k$) nach oben durch Quadrate abschätzen will. Das ist extrem nützlich, um Konvergenz zu zeigen oder Normen abzuschätzen.
    

### 2. Die Dreiecksungleichung(en)

Das ist wahrscheinlich das am häufigsten genutzte Werkzeug in der gesamten Analysis, um Abstände abzuschätzen.

- **Formel:** $|x+y| \le |x| + |y|$ .
    
- **Der „böse“ Zwilling (Ungleichung nach unten):** $||x| - |y|| \le |x+y|$ .
    
- **Wann man sie nutzt:**
    
    - Wenn man zeigen will, dass eine Folge konvergiert ($|a_n - a| < \epsilon$).
        
    - Wenn man einen komplexen Term wie $|(x+1)^2 - 4|$ zerlegen muss.
        
    - Die zweite Version ist oft der „Trick“, wenn man zeigen muss, dass ein Nenner _nicht_ Null wird oder eine Funktion nach unten beschränkt ist.
        

### 3. Das Sandwich-Theorem (Einschließungskriterium)

Ein logischer „Trick“ für Grenzwerte. Wenn man einen komplizierten Grenzwert nicht direkt berechnen kann, sucht man sich eine kleinere und eine größere Folge, die beide gegen denselben Wert streben.

- **Formel:** Wenn $a_k \le c_k \le b_k$ und $\lim a_k = \lim b_k = a$, dann ist auch $\lim c_k = a$ .
    
- **Wann man es nutzt:** Typischerweise bei Termen wie $\frac{\sin(n)}{n}$. Da $-1 \le \sin(n) \le 1$, folgt $-\frac{1}{n} \le \frac{\sin(n)}{n} \le \frac{1}{n}$. Da beide äußeren Seiten gegen 0 gehen, muss auch der innere Term gegen 0 gehen.
    

### 4. Der Mittelwertsatz (MWS) als Abschätzung

Oft wird der MWS nicht genutzt, um eine Stelle $\xi$ zu finden, sondern um eine Funktion durch ihre Ableitung abzuschätzen (Schrankensatz).

- **Formel:** $\frac{f(b)-f(a)}{b-a} = f'(\xi)$ bzw. umgeformt $|f(b) - f(a)| = |f'(\xi)| \cdot |b-a|$ .
    
- **Der Trick:** Wenn du weißt, dass die Ableitung beschränkt ist (z. B. $|f'(x)| \le L$), kannst du sofort folgern: $|f(b) - f(a)| \le L \cdot |b-a|$.
    
- **Wann man es nutzt:** Um Lipschitz-Stetigkeit zu zeigen (siehe Aufgabe 1c aus deinem Upload) oder um zu beweisen, dass eine Funktion sehr wenig schwankt (Kontraktion).
    

### 5. Die Standard-Integralabschätzung

Ein sehr simpler, aber oft übersehener Schritt bei Integralen.

- **Formel:** $|\int_{a}^{b} f(x) dx| \le \int_{a}^{b} |f(x)| dx \le (b-a) \cdot \|f\|_\infty$ .
    
- **Der Trick:** Man zieht den Betrag _in_ das Integral. Wenn man dann das Maximum der Funktion ($\|f\|_\infty$) kennt, kann man das Integral ganz einfach durch "Länge des Intervalls mal Maximum" abschätzen, ohne das Integral wirklich lösen zu müssen.
    

### 6. Besselsche Ungleichung (für Fourierreihen)

Spezifisch für Fourierreihen, aber sehr mächtig. Sie besagt, dass die Summe der Quadrate der Fourierkoeffizienten immer kleiner ist als das Integral über das Quadrat der Funktion.

- **Formel:** $\frac{1}{2}a_0^2 + \sum (a_k^2 + b_k^2) \le \frac{1}{\pi} \int f^2(x) dx$ .
    
- **Der Trick:** Daraus folgt sofort, dass die Koeffizienten $a_k$ und $b_k$ gegen 0 gehen müssen ($ \lim a_k = \lim b_k = 0$) . Das ist oft eine schnelle Antwort auf Fragen zur Konvergenz von Fourierreihen.
    

### Zusammenfassung für die Prüfung

Wenn du in einer Aufgabe steckst und eine Abschätzung brauchst:

1. Sind Quadrate im Spiel? $\to$ Versuch es mit $(x-y)^2 \ge 0$ oder **Cauchy-Schwarz**.
    
2. Sind Beträge im Spiel? $\to$ **Dreiecksungleichung**.
    
3. Geht es um Differenzen von Funktionswerten? $\to$ **Mittelwertsatz**.
    
4. Geht es um Grenzwerte, die "wackeln" (wie Sinus)? $\to$ **Sandwich-Theorem**.