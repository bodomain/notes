Kl 8/23 Hashing Div./QS

k![[Pasted image 20250722152554.png]]



Um dieses Problem zu lösen, verwenden wir die Divisionsmethode als Hashfunktion und quadratisches Sondieren als Kollisionsstrategie für eine Hashtabelle der Größe 5. Die Eingabewerte sind "Alex", "Carl", "Emil", "Finn" und "Luca", und wir berechnen den initialen Hashwert, indem wir die Werte der ersten drei Buchstaben nach dem durchnummerierten Alphabet (A/a = 1, B/b = 2, ...) summieren und modulo 5 rechnen. Lassen Sie uns Schritt für Schritt vorgehen.

### Hashfunktion und initiale Hashwerte
Die Hashfunktion ist \( h(k) = \text{Summe der Werte der ersten drei Buchstaben} \mod 5 \).

- **Alex**: 
  - A = 1, l = 12, e = 5
  - Summe = 1 + 12 + 5 = 18
  - \( h(\text{Alex}) = 18 \mod 5 = 3 \)

- **Carl**: 
  - C = 3, a = 1, r = 18
  - Summe = 3 + 1 + 18 = 22
  - \( h(\text{Carl}) = 22 \mod 5 = 2 \)

- **Emil**: 
  - E = 5, m = 13, i = 9
  - Summe = 5 + 13 + 9 = 27
  - \( h(\text{Emil}) = 27 \mod 5 = 2 \)

- **Finn**: 
  - F = 6, i = 9, n = 14
  - Summe = 6 + 9 + 14 = 29
  - \( h(\text{Finn}) = 29 \mod 5 = 4 \)

- **Luca**: 
  - L = 12, u = 21, c = 3
  - Summe = 12 + 21 + 3 = 36
  - \( h(\text{Luca}) = 36 \mod 5 = 1 \)

### Quadratisches Sondieren und finale Hashtabelle
Wir verwenden quadratisches Sondieren (\( h_i = (h(k) + i^2) \mod 5 \)) zur Kollisionsauflösung. Lassen Sie uns die Werte in der gegebenen Reihenfolge einfügen:

1. **Finn**: \( h = 4 \)
   - Einfügen an Index 4. Hashtabelle: [-, -, -, -, Finn]

2. **Alex**: \( h = 3 \)
   - Einfügen an Index 3. Hashtabelle: [-, -, -, Alex, Finn]

3. **Carl**: \( h = 2 \)
   - Einfügen an Index 2. Hashtabelle: [-, -, Carl, Alex, Finn]

4. **Emil**: \( h = 2 \) (Kollision mit Carl)
   - Probe 1: \( (2 + 1^2) \mod 5 = 3 \) (Kollision mit Alex)
   - Probe 2: \( (2 + 2^2) \mod 5 = (2 + 4) \mod 5 = 1 \)
   - Insert at index 1. Hashtabelle: [-, Emil, Carl, Alex, Finn]

5. **Luca**: \( h = 1 \) (Kollision mit Emil)
   - Probe 1: \( (1 + 1^2) \mod 5 = 2 \) (Kollision mit Carl)
   - Probe 2: \( (1 + 2^2) \mod 5 = (1 + 4) \mod 5 = 0 \)
   - Insert at index 0. Hashtabelle: [Luca, Emil, Carl, Alex, Finn]

### Finale Hashtabelle
- Index 0: Luca (initial h = 1, geprüft bis 0)
- Index 1: Emil (initial h = 2, geprüft bis 1)
- Index 2: Carl (initial h = 2)
- Ind
x (initial h = 3)
- Index 4: Finn (initial h = 4)

### Zusammenfassung
- Finn: Initial h = 4, geprüft: 4
- Alex: Initial h = 3, geprüft: 3
- Carl: Initial h = 2, geprüft: 2
- Emil: Initial h = 2, geprüft: 2, 3, 1
- Luca: Initial h = 1, geprüft: 1, 2, 0

Finaler Inhalt der Hashtabelle: [Luca, Emil, Carl, Alex, Finn]