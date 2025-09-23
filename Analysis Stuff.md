# Walter II, 2.1

Ja — das kann man so machen, **wenn** man $f_n$ an der Stelle $t=0$ passend definiert. Deine Idee

$$
f_n(t)=\min\!\big(n,\;t^{-1/2}\big)
$$

ist für $t>0$ sinnvoll; man muss zusätzlich $f_n(0)=n$ setzen, damit $f_n$ auf ganz $[0,1]$ stetig ist (für $t\to0^+$ gilt $t^{-1/2}\to\infty$, also ist $\min(n,t^{-1/2})\to n$). Mit dieser Ergänzung ist $f_n\in C([0,1])$.

Ich zeige kurz, dass die so definierten Funktionen genau das gewünschte Gegenbeispiel liefern:

1. Definition (stetig): Für $n\in\mathbb N$ setze

$$
f_n(t)=\begin{cases}
n, & t=0,\\[4pt]
\min\!\big(n,\,t^{-1/2}\big), & t\in(0,1].
\end{cases}
$$

Bei $t=\tfrac{1}{n^2}$ gilt $t^{-1/2}=n$, also sind die Stücke glatt verbunden. Daher ist $f_n$ stetig auf $[0,1]$.

2. Betrachte $g_n(t):=t\,f_n(t)$. Für alle $t\in[0,1]$ gilt

$$
g_n(t)=t\min(n,t^{-1/2})=\min(n t,\;t^{1/2}).
$$

Somit ist $g_n$ stetig (und $g_n\in\operatorname{Im}T$ mit $T(f)=t f$, denn $g_n=T(f_n)$).

3. Grenzwertfunktion: Für festes $t>0$ gilt $\min(n,t^{-1/2})\xrightarrow[n\to\infty]{}t^{-1/2}$, also

$$
g_n(t)\xrightarrow[n\to\infty]{}t\cdot t^{-1/2}=t^{1/2}.
$$

Für $t=0$ ist $g_n(0)=0$ und $t^{1/2}=0$, also die Punktweise-Grenzfunktion ist

$$
g(t)=\sqrt{t}\quad (t\in[0,1]).
$$

4. Gleichmäßige Konvergenz: Für $t\ge 1/n^2$ gilt $g_n(t)=t^{1/2}$. Für $0\le t\le 1/n^2$ gilt

$$
|g_n(t)-\sqrt t|=|n t-\sqrt t|=\sqrt t\,(1-n\sqrt t).
$$

Setze $s=\sqrt t\in[0,1/n]$. Die Funktion $\phi(s)=s(1-ns)$ auf $[0,1/n]$ hat ihr Maximum bei $s=\tfrac{1}{2n}$ und erreicht dort den Wert $\tfrac{1}{4n}$. Also

$$
\|g_n-g\|_\infty \le \frac{1}{4n}\xrightarrow[n\to\infty]{}0.
$$

Damit konvergiert $g_n$ gleichmäßig gegen $g(t)=\sqrt t$.

5. Warum das einen Widerspruch zur Abgeschlossenheit von $\operatorname{Im}T$ liefert: Der Grenzwert $g$ ist zwar stetig (also $g\in C([0,1])$), aber **nicht** in $\operatorname{Im}T$. Denn wäre $g=t h$ mit $h\in C([0,1])$, so müsste für $t>0$ gelten $h(t)=g(t)/t=t^{-1/2}$ und damit $\lim_{t\to0^+}h(t)=\infty$, was einer stetigen Fortsetzung von $h$ in $0$ widerspricht. Also $g\notin\operatorname{Im}T$, obwohl $g_n\in\operatorname{Im}T$ und $g_n\to g$ gleichmäßig. Das zeigt, dass $\operatorname{Im}T$ nicht abgeschlossen ist.

6. Schluss: $\operatorname{Im}T$ ist nicht abgeschlossen in $(C([0,1]),\|\cdot\|_\infty)$. Wegen

$$
\|f\|_*=\sup_{t\in[0,1]}|t f(t)|=\|T f\|_\infty
$$

ist $(C([0,1]),\|\cdot\|_*)$ isometrisch zu $\operatorname{Im}T$ mit der Supremumsnorm. Da $\operatorname{Im}T$ nicht abgeschlossen ist, ist $(C([0,1]),\|\cdot\|_*)$ **nicht vollständig**, also **kein Banachraum**.

---

Fazit: Deine Idee $f_n(t)=\min(n,t^{-1/2})$ funktioniert — **unter** der sinnvollen Ergänzung $f_n(0)=n$. Die so erhaltene Folge liefert genau das Gegenbeispiel: $g_n=t f_n$ liegt in $\operatorname{Im}T$, konvergiert gleichmäßig gegen $\sqrt t$, aber $\sqrt t\not\in\operatorname{Im}T$.

Willst du, dass ich die obige Rechnung in noch kompakter Form als eine komplette, formale Beweisnotiz aufschreibe?


