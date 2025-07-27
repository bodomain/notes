![[Pasted image 20250727152017.png]]

![[Pasted image 20250727151842.png]]


![[Pasted image 20250727152023.png]]



Hier ist eine strukturierte Lösung zur **Aufgabe 3: Algebra für Datumsangaben** (insgesamt 20 Punkte):

---

### (a) **Signaturen definieren** (5 Punkte)

#### Gegeben sind folgende Operationen:

**Sorten:**

* `Date` – für Datumsangaben (Tag, Monat, Jahr)
* `Duration` – für Zeitdauern (in Tagen)
* `Bool` – für Wahrheitswerte

#### Signaturen:

```plaintext
create       : int × int × int → Date?
valid        : int × int × int → Bool
weekdayOf    : Date → int         // z. B. 0=Sonntag, ..., 6=Samstag
+            : Duration × Duration → Duration
+            : Duration × Date → Date
-            : Duration × Duration → DurationHier ist eine strukturierte Lösung zur **Aufgabe 3: Algebra für Datumsangaben** (insgesamt 20 Punkte):

---

### (a) **Signaturen definieren** (5 Punkte)

#### Gegeben sind folgende Operationen:

**Sorten:**

* `Date` – für Datumsangaben (Tag, Monat, Jahr)
* `Duration` – für Zeitdauern (in Tagen)
* `Bool` – für Wahrheitswerte

#### Signaturen:

```plaintext
create       : int × int × int → Date?
valid        : int × int × int → Bool
weekdayOf    : Date → int         // z. B. 0=Sonntag, ..., 6=Samstag
+            : Duration × Duration → Duration
+            : Duration × Date → Date
-            : Duration × Duration → Duration
-            : Date × Date → Duration
=            : Date × Date → Bool
=            : Duration × Duration → Bool
<            : Date × Date → Bool
<            : Duration × Duration → Bool
leapyear     : Date → Bool
```

> **Hinweise**:

* `Date?` bedeutet: **undefiniert möglich**, z. B. bei ungültigem Datum.
* Überladen erlaubt, daher `+` und `-` mit mehreren Signaturen.

---

### (b) **Trägermengen angeben** (5 Punkte)

**Sorten und ihre Wertebereiche:**

```plaintext
Date:
  Menge aller gültigen Tripel (Tag, Monat, Jahr), z. B. (24, 7, 2025)
  ⊥ (undefiniert), falls ungültig (z. B. 31.02.2024)

Duration:
  Ganze Zahlen ℤ (auch negativ möglich)

Bool:
  {true, false}
```

---

### (c) **Funktionen implementieren** (10 Punkte)

Es sind zwei Hilfsfunktionen gegeben:

```plaintext
toJulian   : int × int × int → int
fromJulian : int → (int × int × int)
```

#### Implementierungen:

```plaintext
create(t, m, j):
  if valid(t, m, j) then return fromJulian(toJulian(t, m, j)) else ⊥

valid(t, m, j):
  // Prüfe, ob das Datum gültig ist (z. B. 30.2. ist ungültig)
  try:
    d = toJulian(t, m, j)
    return true
  catch error:
    return false

weekdayOf(d):
  (t, m, j) = d
  jul = toJulian(t, m, j)
  return jul mod 7

+(d1, d2):        // Duration + Duration
  return d1 + d2

+(dur, date):     // Duration + Date
  (t, m, j) = date
  jul = toJulian(t, m, j)
  return fromJulian(jul + dur)

-(d1, d2):        // Duration - Duration
  return d1 - d2

-(date1, date2):  // Date - Date → Duration
  return toJulian(date1) - toJulian(date2)

=(d1, d2):        // Duration = Duration
  return d1 = d2

=(date1, date2):  // Date = Date
  return toJulian(date1) = toJulian(date2)

<(d1, d2):        // Duration < Duration
  return d1 < d2

<(date1, date2):  // Date < Date
  return toJulian(date1) < toJulian(date2)

leapyear(date):
  (_, _, j) = date
  return (j mod 4 = 0 and j mod 100 ≠ 0) or (j mod 400 = 0)
```

> Hinweis: In den Funktionen wie `toJulian(date)` ist gemeint:

```plaintext
toJulian(t, m, j), wobei (t, m, j) = date
```

---

Wenn du möchtest, kann ich die Lösung auch in LaTeX-Format bringen oder in Tabellenform.

-            : Date × Date → Duration
=            : Date × Date → Bool
=            : Duration × Duration → Bool
<            : Date × Date → Bool
<            : Duration × Duration → Bool
leapyear     : Date → Bool
```

> **Hinweise**:

* `Date?` bedeutet: **undefiniert möglich**, z. B. bei ungültigem Datum.
* Überladen erlaubt, daher `+` und `-` mit mehreren Signaturen.

---

### (b) **Trägermengen angeben** (5 Punkte)

**Sorten und ihre Wertebereiche:**

```plaintext
Date:
  Menge aller gültigen Tripel (Tag, Monat, Jahr), z. B. (24, 7, 2025)
  ⊥ (undefiniert), falls ungültig (z. B. 31.02.2024)

Duration:
  Ganze Zahlen ℤ (auch negativ möglich)

Bool:
  {true, false}
```

---

### (c) **Funktionen implementieren** (10 Punkte)

Es sind zwei Hilfsfunktionen gegeben:

```plaintext
toJulian   : int × int × int → int
fromJulian : int → (int × int × int)
```

#### Implementierungen:

```plaintext
create(t, m, j):
  if valid(t, m, j) then return fromJulian(toJulian(t, m, j)) else ⊥

valid(t, m, j):
  // Prüfe, ob das Datum gültig ist (z. B. 30.2. ist ungültig)
  try:
    d = toJulian(t, m, j)
    return true
  catch error:
    return false

weekdayOf(d):
  (t, m, j) = d
  jul = toJulian(t, m, j)
  return jul mod 7

+(d1, d2):        // Duration + Duration
  return d1 + d2

+(dur, date):     // Duration + Date
  (t, m, j) = date
  jul = toJulian(t, m, j)
  return fromJulian(jul + dur)

-(d1, d2):        // Duration - Duration
  return d1 - d2

-(date1, date2):  // Date - Date → Duration
  return toJulian(date1) - toJulian(date2)

=(d1, d2):        // Duration = Duration
  return d1 = d2

=(date1, date2):  // Date = Date
  return toJulian(date1) = toJulian(date2)

<(d1, d2):        // Duration < Duration
  return d1 < d2

<(date1, date2):  // Date < Date
  return toJulian(date1) < toJulian(date2)

leapyear(date):
  (_, _, j) = date
  return (j mod 4 = 0 and j mod 100 ≠ 0) or (j mod 400 = 0)
```

> Hinweis: In den Funktionen wie `toJulian(date)` ist gemeint:

```plaintext
toJulian(t, m, j), wobei (t, m, j) = date
```

---

Wenn du möchtest, kann ich die Lösung auch in LaTeX-Format bringen oder in Tabellenform.
