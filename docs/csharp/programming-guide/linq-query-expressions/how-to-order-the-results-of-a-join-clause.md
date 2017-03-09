---
redirect_url: /dotnet/articles/csharp/linq/order-the-results-of-a-join-clause
caps.handback.revision: 6
---
# Gewusst wie: Sortieren der Ergebnisse einer Join-Klausel (C#-Programmierhandbuch)
In diesem Beispiel wird gezeigt, wie die Ergebnisse einer Joinoperation sortiert werden.  Beachten Sie, dass die Sortierung nach dem Join ausgeführt wird.  Zwar ist es möglich, eine `orderby`\-Klausel mit einer oder mehreren Quellsequenzen vor dem Join zu verwenden, diese Vorgehensweise wird aber nicht empfohlen.  Diese Sortierung wird nach dem Join möglicherweise nicht bei allen [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]\-Anbietern beibehalten.  
  
## Beispiel  
 Diese Abfrage erstellt einen Group Join und sortiert die Gruppen dann auf Basis des Kategorieelements, das sich noch im Gültigkeitsbereich befindet.  Im anonymen Typinitialisierer werden alle übereinstimmenden Elemente aus der Produktsequenz durch eine Unterabfrage sortiert.  
  
 [!code-cs[csProgGuideLINQ#81](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csRef30LangFeatures_2.cs#81)]  
  
## Kompilieren des Codes  
  
-   Erstellen Sie ein [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)]\-Projekt für .NET Framework, Version 3.5.  Standardmäßig weist das Projekt einen Verweis auf System.Core.dll und eine `using`\-Direktive für den System.Linq\-Namespace auf.  
  
-   Kopieren Sie den Code in Ihr Projekt.  
  
-   Drücken Sie F5, um das Programm zu kompilieren und auszuführen.  
  
-   Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.  
  
## Siehe auch  
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [orderby\-Klausel](../../../csharp/language-reference/keywords/orderby-clause.md)   
 [join\-Klausel](../../../csharp/language-reference/keywords/join-clause.md)   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)