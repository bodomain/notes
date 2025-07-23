Klar, hier ist der schrittweise Aufbau des Minimum-Heaps. Bei jeder Einfügung wird die neue Zahl an die nächste freie Position im Baum gesetzt und dann bei Bedarf nach oben verschoben („heapify-up“), um die Heap-Bedingung (Elternknoten ist kleiner als seine Kinder) wiederherzustellen.

-----

### **1. Füge 4 hinzu**

Der Baum ist leer, also wird 4 zur Wurzel.

```mermaid
graph TD;
    A(4);
```

### **2. Füge 11 hinzu**

11 wird als linkes Kind von 4 eingefügt. Da `11 > 4` ist, bleibt die Heap-Bedingung erfüllt.

```mermaid
graph TD;
    A(4) --> B(11);
```

### **3. Füge 1 hinzu**

1 wird als rechtes Kind von 4 eingefügt. Da `1 < 4` ist, wird die Heap-Bedingung verletzt. Die beiden werden vertauscht.

```mermaid
graph TD;
    subgraph Vorher
        A(4) --> B(11);
        A --> C(1);
        style C fill:#f99,stroke:#333,stroke-width:2px
    end
    subgraph Nachher
        D(1) --> E(11);
        D --> F(4);
    end
```

### **4. Füge 42 hinzu**

42 wird als linkes Kind von 11 eingefügt. Da `42 > 11` ist, ist alles in Ordnung.

```mermaid
graph TD;
    A(1) --> B(11);
    A --> C(4);
    B --> D(42);
```

### **5. Füge 17 hinzu**

17 wird als rechtes Kind von 11 eingefügt. Da `17 > 11` ist, ist die Heap-Bedingung erfüllt.

```mermaid
graph TD;
    A(1) --> B(11);
    A --> C(4);
    B --> D(42);
    B --> E(17);
```

### **6. Füge 7 hinzu**

7 wird als linkes Kind von 4 eingefügt. Da `7 > 4` ist, ist alles in Ordnung.

```mermaid
graph TD;
    A(1) --> B(11);
    A --> C(4);
    B --> D(42);
    B --> E(17);
    C --> F(7);
```

### **7. Füge 6 hinzu**

6 wird als rechtes Kind von 4 eingefügt. Da `6 > 4` ist, bleibt die Heap-Bedingung erfüllt.

```mermaid
graph TD;
    A(1) --> B(11);
    A --> C(4);
    B --> D(42);
    B --> E(17);
    C --> F(7);
    C --> G(6);
```

### **8. Füge 3 hinzu**

3 wird als linkes Kind von 42 eingefügt.

1.  `3 < 42` → Tausch.
2.  `3 < 11` → Tausch.
3.  `3 > 1` → Stopp.

<!-- end list -->

```mermaid
graph TD;
    subgraph Vorher
        A(1) --> B(11);
        A --> C(4);
        B --> D(42);
        B --> E(17);
        C --> F(7);
        C --> G(6);
        D --> H(3);
        style H fill:#f99,stroke:#333,stroke-width:2px
    end
    subgraph Nachher
        I(1) --> J(3);
        I --> K(4);
        J --> L(11);
        J --> M(17);
        K --> N(7);
        K --> O(6);
        L --> P(42);
    end
```

### **9. Füge 2 hinzu**

2 wird als rechtes Kind von 11 eingefügt.

1.  `2 < 11` → Tausch.
2.  `2 < 3` → Tausch.
3.  `2 > 1` → Stopp.

<!-- end list -->

```mermaid
graph TD;
    subgraph Vorher
        I(1) --> J(3);
        I --> K(4);
        J --> L(11);
        J --> M(17);
        K --> N(7);
        K --> O(6);
        L --> P(42);
        L --> Q(2)
        style Q fill:#f99,stroke:#333,stroke-width:2px
    end
    subgraph Nachher
        R(1) --> S(2);
        R --> T(4);
        S --> U(3);
        S --> V(17);
        T --> W(7);
        T --> X(6);
        U --> Y(42);
        U --> Z(11);
    end
```

### **10. Füge 5 hinzu (Finaler Baum)**

5 wird als linkes Kind von 7 eingefügt.

1.  `5 < 7` → Tausch.
2.  `5 > 4` → Stopp.

<!-- end list -->


```mermaid
graph TD;
    subgraph Vorher
        R(1) --> S(2);
        R --> T(4);
        S --> U(3);
        S --> V(11);
        T --> W(7);
        T --> X(6);
        U --> Y(42);
        U --> Z(17);
        V --> AA(5);
        style AA fill:#f99,stroke:#333,stroke-width:2px
    end
    subgraph Nachher
        A(1) --> B(2);
        A --> C(4);
        B --> D(3);
        B --> E(5);
        C --> F(7);
        C --> G(6);
        D --> H(42);
        D --> I(17);
        E --> J(11);
    end
```










