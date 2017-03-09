---
redirect_url: /dotnet/articles/csharp/linq/perform-custom-join-operations
caps.handback.revision: 13
---
# Gewusst wie: Ausf&#252;hren von benutzerdefinierten Verkn&#252;pfungsoperationen (C#-Programmierhandbuch)
In diesem Beispiel wird gezeigt, wie Sie Joinoperationen, die mit der `join`\-Klausel nicht möglich sind, ausführen können.  In einem Abfrageausdruck ist die `join`\-Klausel auf Equijoins beschränkt und wurde für sie optimiert. Equijoins sind der häufigste Typ an Joinoperationen.  Wenn Sie einen Equijoin ausführen, erhalten Sie mit der `join`\-Klausel wahrscheinlich immer die optimale Leistung.  
  
 Die `join`\-Klausel kann jedoch in den folgenden Fällen nicht verwendet werden:  
  
-   Wenn der Join auf einem Ausdruck der Ungleichheit \(ein Nicht\-Equijoin\) basiert wird.  
  
-   Wenn der Join auf mehr als einem Ausdruck der Gleichheit oder Ungleichheit basiert wird.  
  
-   Wenn Sie eine temporäre Bereichsvariable für die rechte \(innere\) Sequenz vor der Joinoperation verwenden müssen.  
  
 Um Joins auszuführen, bei denen es sich nicht um Equijoins handelt, können Sie mehrere `from`\-Klauseln verwenden, um jede Datenquelle einzeln einzuführen.  Sie wenden dann einen Prädikatsausdruck in einer `where`\-Klausel auf die Bereichsvariable für jede Quelle an.  Der Ausdruck kann auch die Form eines Methodenaufrufs annehmen.  
  
> [!NOTE]
>  Verwechseln Sie diese Art von benutzerdefinierten Joinoperationen nicht mit dem Einsatz von mehreren `from`\-Klauseln, um auf innere Sammlungen zuzugreifen.  Weitere Informationen finden Sie unter [join\-Klausel](../../../csharp/language-reference/keywords/join-clause.md).  
  
## Beispiel  
 Die erste Methode im folgenden Beispiel zeigt einen einfachen Cross Join.  Cross Joins müssen mit Vorsicht verwendet werden, da sie sehr große Ergebnissätze erzeugen können.  Sie können jedoch in einigen Szenarien zum Erstellen von Quellsequenzen, gegen die zusätzliche Abfragen ausgeführt werden, nützlich sein.  
  
 Die zweite Methode erzeugt eine Sequenz aller Produkte, deren Kategorie\-ID in der Kategorieliste links aufgeführt ist.  Beachten Sie die Verwendung der `let`\-Klausel und der `Contains`\-Methode, um ein temporäres Array zu erstellen.  Sie können das Array auch vor der Abfrage erstellen und die erste `from`\-Klausel ausschließen.  
  
 [!code-cs[csProgGuideLINQ#64](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csRef30LangFeatures_2.cs#64)]  
  
## Beispiel  
 Im folgenden Beispiel muss die Abfrage zwei Sequenzen anhand übereinstimmender Schlüssel verknüpfen, die im Fall der inneren \(rechten\) Sequenz nicht vor der join\-Klausel selbst abgerufen werden können.  Wenn dieser Join mit einer `join`\-Klausel ausgeführt wird, muss die `Split`\-Methode für jedes Element aufgerufen werden.  Der Einsatz von mehreren `from`\-Klauseln ermöglicht es der Abfrage, den Aufwand eines wiederholten Methodenaufrufs zu verhindern.  Da der `join` optimiert ist, ist dies in diesem speziellen Fall vermutlich dennoch schneller als die Verwendung mehrerer `from`\-Klauseln.  Die Ergebnisse ändern sich hauptsächlich in Abhängigkeit davon, wie teuer der Methodenaufruf ist.  
  
 [!code-cs[csProgGuideLINQ#13](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#13)]  
  
## Kompilieren des Codes  
  
-   Erstellen Sie ein [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)]\-Konsolenanwendungsprojekt für [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 3.5 oder höher.  Standardmäßig weist das Projekt einen Verweis auf System.Core.dll und eine `using`\-Direktive für den System.Linq\-Namespace auf.  
  
-   Ersetzen Sie die `Program`\-Klasse durch den Code im vorherigen Beispiel.  
  
-   Befolgen Sie die Anweisungen in [How to: Join Content from Dissimilar Files \(LINQ\)](../Topic/How%20to:%20Join%20Content%20from%20Dissimilar%20Files%20\(LINQ\).md), um die Datendateien scores.csv und names.csv einzurichten.  
  
-   Drücken Sie F5, um das Programm zu kompilieren und auszuführen.  
  
-   Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.  
  
## Siehe auch  
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [join\-Klausel](../../../csharp/language-reference/keywords/join-clause.md)   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [Gewusst wie: Sortieren der Ergebnisse einer Join\-Klausel](../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)