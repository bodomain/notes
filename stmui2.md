![[Pasted image 20260121204920.png]]

Diese Rechnung zeigt den klassischen „Trick“, wie man das Gaußsche Integral berechnet. Da man für die Funktion $e^{-x^2/2}$ keine elementare Stammfunktion finden kann, berechnet man stattdessen das Quadrat des Integrals in zwei Dimensionen und nutzt Polarkoordinaten.

Hier ist die schrittweise Erläuterung der Zeilen aus deinem Screenshot:

### 1. Übergang zum Doppelintegral

$$\left(\int_{-\infty}^{\infty}e^{-\frac{x^{2}}{2}}dx\right)^{2}=\int_{-\infty}^{\infty}\int_{-\infty}^{\infty}e^{-\frac{x^{2}}{2}}e^{-\frac{y^{2}}{2}}dx~dy$$

- **Erklärung:** Du nimmst das Integral zweimal und benennst die Integrationsvariable beim zweiten Mal in $y$ um. Da die Variablen unabhängig voneinander sind, kannst du sie nach dem Satz von Fubini in ein Doppelintegral über die gesamte Ebene $\mathbb{R}^2$ zusammenschreiben.
    

### 2. Zusammenfassen der Exponenten

$$=\int_{\mathbb{R}^{2}}e^{\frac{-(x^{2}+y^{2})}{2}}d\lambda_{2}(x,y)$$

- **Erklärung:** Mit dem Potenzgesetz $e^a \cdot e^b = e^{a+b}$ werden die beiden Funktionen kombiniert. Der Ausdruck $x^2 + y^2$ im Exponenten ist der entscheidende Hinweis darauf, dass ein Wechsel in Polarkoordinaten sinnvoll ist, da dies genau dem Quadrat des Radius ($r^2$) entspricht.
    

### 3. Definition des Integrationsbereichs in Polarkoordinaten

$$=\int_{\Phi([0,\infty)\times[0,2\pi])}e^{\frac{-(x^{2}+y^{2})}{2}}d\lambda_{2}(x,y)$$

- **Erklärung:** Hier wird die Transformation vorbereitet. $\Phi$ ist die Abbildung, die Polarkoordinaten $(r, \vartheta)$ in kartesische Koordinaten $(x, y)$ umrechnet. Der Bereich $[0,\infty) \times [0,2\pi]$ deckt dabei den Radius von Null bis Unendlich und den Winkel einmal komplett um den Ursprung ab, was genau dem gesamten $\mathbb{R}^2$ entspricht.
    

### 4. Anwendung der Transformationsformel (Substitutionsregel)

$$=\int_{[0,\infty)\times[0,2\pi]}e^{\frac{-r^{2}}{2}}r~d\lambda_{2}(r,\vartheta)$$

- **Erklärung:** Dies ist der wichtigste Schritt. Beim Variablenwechsel im Mehrdimensionalen musst du die Determinante der Jacobi-Matrix (den Verzerrungsfaktor) berücksichtigen. Bei Polarkoordinaten ist dieser Faktor $r$. Aus $x^2 + y^2$ wird $r^2$.
    

### 5. Trennung der Integrale (Fubini)

$$=\int_{0}^{\infty}\int_{0}^{2\pi}e^{\frac{-r^{2}}{2}}r~d\vartheta~dr$$

- **Erklärung:** Da die Grenzen nun konstant sind und der Integrand als Produkt von Funktionen dargestellt werden kann, die nur von $r$ bzw. nur von $\vartheta$ abhängen (hier ist der $\vartheta$-Teil einfach $1$), kann man das Doppelintegral wieder als hintereinander ausgeführte Einzelintegrale schreiben.
    

### 6. Integration über den Winkel $\vartheta$

$$=2\pi\int_{0}^{\infty}e^{\frac{-r^{2}}{2}}r~dr$$

- **Erklärung:** Das innere Integral $\int_{0}^{2\pi} d\vartheta$ ergibt einfach $2\pi$. Dieses Ergebnis wird vor das verbleibende Integral über $r$ gezogen.
    

### Das fertige Ergebnis (Ergänzung zur Rechnung)

Um die Rechnung abzuschließen, berechnet man das verbleibende Integral mit der Substitution $u = \frac{r^2}{2}$ (woraus $du = r \, dr$ folgt):

$$\int_{0}^{\infty} e^{-\frac{r^{2}}{2}} r \, dr = \int_{0}^{\infty} e^{-u} du = [-e^{-u}]_0^\infty = 0 - (-1) = 1$$

Das gesamte Quadrat des Integrals ist also:

$$2\pi \cdot 1 = 2\pi$$

Zieht man daraus die Wurzel, erhält man den Wert des ursprünglichen Integrals:

$$\int_{-\infty}^{\infty} e^{-\frac{x^{2}}{2}} dx = \sqrt{2\pi}$$