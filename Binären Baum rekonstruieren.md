Preorder- und Inorder-Folgen, oder die Postorder- und Inorder-Folgen, reichen aus, um einen binären Baum eindeutig zu rekonstruieren.  Die Preorder- und Postorder-Folgen allein reichen jedoch nicht aus, da sie die Struktur des Baums nicht vollständig festlegen.

**Warum Preorder + Inorder funktioniert:**

*   **Preorder:** Die erste Node in der Preorder-Sequenz ist immer die Wurzel des Baums (oder des aktuellen Subbaums).
*   **Inorder:**  In der Inorder-Sequenz sind alle Nodes links von der Wurzel im linken Subbaum und alle Nodes rechts von der Wurzel im rechten Subbaum.

**Der Algorithmus (Preorder + Inorder):**

1.  **Wurzel finden:** Nimm die erste Node aus der Preorder-Sequenz. Das ist die Wurzel des aktuellen (Sub-)Baums.
2.  **Wurzel in Inorder suchen:** Finde die Position der Wurzel in der Inorder-Sequenz.
3.  **Subbäume aufteilen:** Die Nodes links von der Wurzel in der Inorder-Sequenz bilden den linken Subbaum. Die Nodes rechts von der Wurzel bilden den rechten Subbaum.
4.  **Rekursion:**  Rekursiv die Schritte 1-3 für den linken und rechten Subbaum ausführen.  Dabei musst du in der Preorder-Sequenz voranschreiten, um die Wurzeln der Subbäume zu finden.

**Warum Postorder + Inorder funktioniert:**

*   **Postorder:** Die letzte Node in der Postorder-Sequenz ist immer die Wurzel des Baums (oder des aktuellen Subbaums).
*   **Inorder:** Wie oben.

**Der Algorithmus (Postorder + Inorder):**

1.  **Wurzel finden:** Nimm die letzte Node aus der Postorder-Sequenz. Das ist die Wurzel des aktuellen (Sub-)Baums.
2.  **Wurzel in Inorder suchen:** Finde die Position der Wurzel in der Inorder-Sequenz.
3.  **Subbäume aufteilen:** Die Nodes links von der Wurzel in der Inorder-Sequenz bilden den linken Subbaum. Die Nodes rechts von der Wurzel bilden den rechten Subbaum.
4.  **Rekursion:** Rekursiv die Schritte 1-3 für den linken und rechten Subbaum ausführen. Dabei musst du in der Postorder-Sequenz zurückgehen, um die Wurzeln der Subbäume zu finden.

**Warum Preorder + Postorder nicht funktioniert:**

Betrachten wir folgendes Beispiel:

*   Preorder: A B C
*   Postorder: B C A

Es gibt zwei mögliche binäre Bäume, die diese Traversierungen erzeugen können:

*   Baum 1:
    
       A
      /
     B
      \
       C
    ```
*   Baum 2:
    
       A
        \
         C
        /
       B
    ```

Weil du nicht weißt, welche Nodes zum linken oder rechten Subbaum gehören, kannst du den Baum nicht eindeutig rekonstruieren.  Wenn jede Node nur einen Kind-Knoten haben kann, könnte es trotzdem funktionieren.

**Beispiel (Preorder + Inorder):**

*   Preorder: A B D E C F G
*   Inorder:  D B E A F C G

1.  **Wurzel:** A (erste Node in Preorder)
2.  **Wurzel in Inorder:** D B E A F C G  (Index von A ist 3)
3.  **Linker Subbaum (Inorder):** D B E
    **Rechter Subbaum (Inorder):** F C G
4.  **Linker Subbaum (Preorder):** B D E (Die nächsten 3 Nodes in der Preorder Sequenz nach A)
    **Rechter Subbaum (Preorder):** C F G (Die verbleibenden Nodes in der Preorder Sequenz)
5.  **Rekursion:**

    *   **Linker Subbaum:**
        *   Preorder: B D E
        *   Inorder: D B E
        *   Wurzel: B
        *   Linker Subbaum: D
        *   Rechter Subbaum: E
    *   **Rechter Subbaum:**
        *   Preorder: C F G
        *   Inorder: F C G
        *   Wurzel: C
        *   Linker Subbaum: F
        *   Rechter Subbaum: G

Der resultierende Baum ist:


      A
     / \
    B   C
   / \ / \
  D   E F   G


**Zusammenfassung:**

*   Preorder + Inorder:  Eindeutige Rekonstruktion möglich.
*   Postorder + Inorder: Eindeutige Rekonstruktion möglich.
*   Preorder + Postorder:  Rekonstruktion im Allgemeinen *nicht* eindeutig möglich (Ausnahmen sind möglich, z.B. wenn jede Node maximal ein Kind hat).
