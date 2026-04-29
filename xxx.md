Gut — ich gehe die Aufgabe jetzt **strukturiert und im Stil des Skripts (nmtext)** durch. Der Kern ist: Das inexakte Newton-Verfahren ist eine **gestörte Fixpunktiteration**, und man zeigt wieder eine Abschätzung wie in (a).

---

# 🔹 1. Setup

Gegeben:

* (f: \mathbb{R}^n \to \mathbb{R}^n)
* (f(x^*) = 0)
* (f'(x^*)) regulär (invertierbar)
* (f') ist lokal Lipschitz-stetig

Iteration:

[
x^{k+1} = x^k + d^k
]

mit

[
| f'(x^k)d^k + f(x^k) |*\infty \le |f(x^k)|*\infty^\tau, \quad \tau \in (1,2].
]

---

# 🔹 2. Ziel

Zeige:

* lokale Konvergenz
* Q-Ordnung (\tau)

---

# 🔹 3. Fehlernotation

Setze:

[
e_k := x^k - x^*
]

---

# 🔹 4. Zentrale Umformung (wie Newton)

Schreibe:

[
f'(x^k)d^k = -f(x^k) + r_k
]

mit

[
|r_k| \le |f(x^k)|^\tau.
]

👉 Das ist der **Fehler in der Newton-Gleichung**

---

# 🔹 5. Taylor-Entwicklung von (f(x^k))

Da (f') Lipschitz ist:

[
f(x^k)
======

# f'(x^*)(x^k - x^*) + R_k

f'(x^*) e_k + R_k
]

mit

[
|R_k| \le C |e_k|^2.
]

---

# 🔹 6. Vergleich der Ableitungen

Da (f') stetig ist:

[
f'(x^k) = f'(x^*) + O(|e_k|).
]

---

# 🔹 7. Fehlergleichung für (d^k)

Einsetzen:

[
f'(x^k)d^k
==========

* f'(x^*) e_k - R_k + r_k
  ]

---

# 🔹 8. Ziel: Ausdruck für (e_{k+1})

[
e_{k+1}
=======

# x^{k+1} - x^*

# x^k + d^k - x^*

e_k + d^k
]

---

# 🔹 9. Löse nach (d^k) auf

Multipliziere mit ((f'(x^k))^{-1}):

[
d^k
===

-(f'(x^k))^{-1} f'(x^*) e_k

* (f'(x^k))^{-1} R_k

- (f'(x^k))^{-1} r_k
  ]

---

# 🔹 10. Einsetzen in (e_{k+1})

[
e_{k+1}
=======

## e_k

## (f'(x^k))^{-1} f'(x^*) e_k

(f'(x^k))^{-1} R_k
+
(f'(x^k))^{-1} r_k
]

---

# 🔹 11. Schlüsselbeobachtung

Der Ausdruck

[
I - (f'(x^k))^{-1} f'(x^*)
]

ist klein:

[
= O(|e_k|)
]

👉 wegen Stetigkeit von (f')

---

# 🔹 12. Abschätzung der Terme

### (1) Linearer Term:

[
\left| e_k - (f'(x^k))^{-1} f'(x^*) e_k \right|
\le C |e_k|^2
]

---

### (2) Restterm:

[
|(f'(x^k))^{-1} R_k| \le C |e_k|^2
]

---

### (3) Inexaktheit:

[
|(f'(x^k))^{-1} r_k| \le C |f(x^k)|^\tau
]

Und:

[
|f(x^k)| \le C |e_k|
]

⇒

[
|(f'(x^k))^{-1} r_k| \le C |e_k|^\tau
]

---

# 🔹 13. Gesamtschätzung

[
|e_{k+1}|
\le
C |e_k|^2 + C |e_k|^\tau
]

---

# 🔹 14. Dominanter Term

Da (\tau \in (1,2]):

👉 Für kleine (e_k):

[
|e_k|^\tau \gg |e_k|^2
\quad (\text{falls } \tau < 2)
]

⇒

[
|e_{k+1}| \le C |e_k|^\tau
]

---

# 🔹 15. Anwendung von (a)

Das ist genau die Situation aus Teil (a):

[
|x_{k+1} - x^*| \le M |x_k - x^*|^\tau
]

⇒

[
\text{Q-Ordnung mindestens } \tau
]

---

# 🔹 16. Lokale Konvergenz

Wie in (a)(i):

* rechte Seite klein ⇒ Kontraktion
* ⇒ Fixpunktsatz (lokal)
* ⇒ Konvergenz

---

# 🔹 17. Fazit

* Verfahren ist lokal wohldefiniert
* Folge konvergiert gegen (x^*)
* Konvergenzordnung:

[
\boxed{\text{Q-Ordnung } \ge \tau}
]

---

# 🔹 🔥 Intuition (wichtig)

* Exaktes Newton: Fehler (O(e_k^2))
* Inexaktes Newton: Fehlerterm (O(e_k^\tau))

👉 Der „schlechtere“ Term dominiert
⇒ Ordnung sinkt auf (\tau)

---

Wenn du willst, kann ich dir das Ganze noch in eine **klausurtaugliche Kurzlösung (1 Seite)** komprimieren.
Gut — ich gehe die Aufgabe jetzt **strukturiert und im Stil des Skripts (nmtext)** durch. Der Kern ist: Das inexakte Newton-Verfahren ist eine **gestörte Fixpunktiteration**, und man zeigt wieder eine Abschätzung wie in (a).

---

# 🔹 1. Setup

Gegeben:

* (f: \mathbb{R}^n \to \mathbb{R}^n)
* (f(x^*) = 0)
* (f'(x^*)) regulär (invertierbar)
* (f') ist lokal Lipschitz-stetig

Iteration:

[
x^{k+1} = x^k + d^k
]

mit

[
| f'(x^k)d^k + f(x^k) |*\infty \le |f(x^k)|*\infty^\tau, \quad \tau \in (1,2].
]

---

# 🔹 2. Ziel

Zeige:

* lokale Konvergenz
* Q-Ordnung (\tau)

---

# 🔹 3. Fehlernotation

Setze:

[
e_k := x^k - x^*
]

---

# 🔹 4. Zentrale Umformung (wie Newton)

Schreibe:

[
f'(x^k)d^k = -f(x^k) + r_k
]

mit

[
|r_k| \le |f(x^k)|^\tau.
]

👉 Das ist der **Fehler in der Newton-Gleichung**

---

# 🔹 5. Taylor-Entwicklung von (f(x^k))

Da (f') Lipschitz ist:

[
$$f(x^k)$$
======

$$ f'(x^*)(x^k - x^*) + R_k$$j

$$f'(x^*) e_k + R_k$$
]

mit

[
|R_k| \le C |e_k|^2.
]

---

# 🔹 6. Vergleich der Ableitungen

Da (f') stetig ist:

[
f'(x^k) = f'(x^*) + O(|e_k|).
]

---

# 🔹 7. Fehlergleichung für (d^k)

Einsetzen:

[
f'(x^k)d^k
==========

* f'(x^*) e_k - R_k + r_k
  ]

---

# 🔹 8. Ziel: Ausdruck für (e_{k+1})

[
e_{k+1}
=======

# x^{k+1} - x^*

# x^k + d^k - x^*

e_k + d^k
]

---

# 🔹 9. Löse nach (d^k) auf

Multipliziere mit ((f'(x^k))^{-1}):

[
d^k
===

-(f'(x^k))^{-1} f'(x^*) e_k

* (f'(x^k))^{-1} R_k

- (f'(x^k))^{-1} r_k
  ]

---

# 🔹 10. Einsetzen in (e_{k+1})

[
e_{k+1}
=======

## e_k

## (f'(x^k))^{-1} f'(x^*) e_k

(f'(x^k))^{-1} R_k
+
(f'(x^k))^{-1} r_k
]

---

# 🔹 11. Schlüsselbeobachtung

Der Ausdruck

[
I - (f'(x^k))^{-1} f'(x^*)
]

ist klein:

[
= O(|e_k|)
]

👉 wegen Stetigkeit von (f')

---

# 🔹 12. Abschätzung der Terme

### (1) Linearer Term:

[
\left| e_k - (f'(x^k))^{-1} f'(x^*) e_k \right|
\le C |e_k|^2
]

---

### (2) Restterm:

[
|(f'(x^k))^{-1} R_k| \le C |e_k|^2
]

---

### (3) Inexaktheit:

[
|(f'(x^k))^{-1} r_k| \le C |f(x^k)|^\tau
]

Und:

[
|f(x^k)| \le C |e_k|
]

⇒

[
|(f'(x^k))^{-1} r_k| \le C |e_k|^\tau
]

---

# 🔹 13. Gesamtschätzung

[
|e_{k+1}|
\le
C |e_k|^2 + C |e_k|^\tau
]

---

# 🔹 14. Dominanter Term

Da (\tau \in (1,2]):

👉 Für kleine (e_k):

[
|e_k|^\tau \gg |e_k|^2
\quad (\text{falls } \tau < 2)
]

⇒

[
|e_{k+1}| \le C |e_k|^\tau
]

---

# 🔹 15. Anwendung von (a)

Das ist genau die Situation aus Teil (a):

[
|x_{k+1} - x^*| \le M |x_k - x^*|^\tau
]

⇒

[
\text{Q-Ordnung mindestens } \tau
]

---

# 🔹 16. Lokale Konvergenz

Wie in (a)(i):

* rechte Seite klein ⇒ Kontraktion
* ⇒ Fixpunktsatz (lokal)
* ⇒ Konvergenz

---

# 🔹 17. Fazit

* Verfahren ist lokal wohldefiniert
* Folge konvergiert gegen (x^*)
* Konvergenzordnung:

[
\boxed{\text{Q-Ordnung } \ge \tau}
]

---

# 🔹 🔥 Intuition (wichtig)

* Exaktes Newton: Fehler (O(e_k^2))
* Inexaktes Newton: Fehlerterm (O(e_k^\tau))

👉 Der „schlechtere“ Term dominiert
⇒ Ordnung sinkt auf (\tau)

---

Wenn du willst, kann ich dir das Ganze noch in eine **klausurtaugliche Kurzlösung (1 Seite)** komprimieren.
