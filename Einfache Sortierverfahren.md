![[Pasted image 20250723185027.png]]

Die Zahlenfolge 35,62,28,50,11,45 wird mittels **Insertion Sort** sortiert. Für jeden Wert der Laufvariable i wird das Array nach jedem Schleifendurchlauf dargestellt, wobei das sortierte Teil-Array unterstrichen ist.

---

## **Initiales Array**

[35,62,28,50,11,45]

---

## **Schleifendurchläufe**

### **i=1 (erstes Element ist immer sortiert)**

Das erste Element 35 wird als bereits sortiert betrachtet.

[35]​,62,28,50,11,45

### **i=2 (Element 62)**

62 wird mit 35 verglichen. Da 62>35, bleibt die Reihenfolge unverändert.

[35,62]​,28,50,11,45

### **i=3 (Element 28)**

28 wird mit 62 verglichen. 28<62, also wird 62 nach rechts verschoben.

[35,_,62,50,11,45]

28 wird mit 35 verglichen. 28<35, also wird 35 nach rechts verschoben.

[_,35,62,50,11,45]

28 wird an die erste Position eingefügt.

[28,35,62]​,50,11,45

### **i=4 (Element 50)**

50 wird mit 62 verglichen. 50<62, also wird 62 nach rechts verschoben.

[28,35,_,62,11,45]

50 wird mit 35 verglichen. 50>35, also wird 50 an diese Position eingefügt.

[28,35,50,62]​,11,45

### **i=5 (Element 11)**

11 wird mit 62 verglichen. 11<62, also wird 62 nach rechts verschoben.

[28,35,50,_,62,45]

11 wird mit 50 verglichen. 11<50, also wird 50 nach rechts verschoben.

[28,35,_,50,62,45]

11 wird mit 35 verglichen. 11<35, also wird 35 nach rechts verschoben.

[28,_,35,50,62,45]

11 wird mit 28 verglichen. 11<28, also wird 28 nach rechts verschoben.

[_,28,35,50,62,45]

11 wird an die erste Position eingefügt.

[11,28,35,50,62]​,45

### **i=6 (Element 45)**

45 wird mit 62 verglichen. 45<62, also wird 62 nach rechts verschoben.

[11,28,35,50,_,62]

45 wird mit 50 verglichen. 45<50, also wird 50 nach rechts verschoben.

[11,28,35,_,50,62]

45 wird mit 35 verglichen. 45>35, also wird 45 an diese Position eingefügt.

[11,28,35,45,50,62]​

---

## **Endgültig sortiertes Array**

[11,28,35,45,50,62]