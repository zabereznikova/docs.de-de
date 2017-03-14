---
redirect_url: /dotnet/articles/csharp/linq/perform-a-subquery-on-a-grouping-operation
caps.handback.revision: 15
---
# Gewusst wie: Ausf&#252;hren einer Unterabfrage f&#252;r eine Gruppierungsoperation (C#-Programmierhandbuch)
Dieses Thema zeigt zwei verschiedene Wege, wie Sie eine Abfrage erstellen können, die die Quelldaten in Gruppen sortiert und dann eine Unterabfrage für jede einzelne Gruppe durchführt.  Die zugrunde liegende Technik in jedem Beispiel besteht darin, die Quellelemente zu gruppieren, indem Sie eine *Fortsetzung* mit dem Namen `newGroup` verwenden und dann eine neue Unterabfrage für `newGroup` erstellen.  Diese Unterabfrage wird für jede neue Gruppe ausgeführt, die von der äußeren Abfrage erstellt wird.  Beachten Sie, dass in diesem speziellen Beispiel die Endausgabe keine Gruppe ist, sondern eine flache Sequenz mit anonymen Typen.  
  
 Weitere Informationen zum Gruppieren finden Sie unter [group\-Klausel](../../../csharp/language-reference/keywords/group-clause.md).  
  
 Weitere Informationen zu Fortsetzungen finden Sie unter [into](../../../csharp/language-reference/keywords/into.md).  Im folgenden Beispiel wird eine speicherinterne Datenstruktur als Datenquelle verwendet, die gleichen Prinzipien gelten jedoch auch für andere [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]\-Datenquellen.  
  
## Beispiel  
 [!code-cs[csProgGuideLINQ#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]  
  
## Kompilieren des Codes  
 Dieses Beispiel enthält Verweise auf Objekte, die in der Beispielanwendung in [Gewusst wie: Abfragen einer Auflistung von Objekten](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md) definiert werden.  Um diese Methode zu kompilieren und auszuführen, fügen Sie sie in die `StudentClass`\-Klasse dieser Anwendung ein, und fügen Sie ihr von der `Main`\-Methode einen Aufruf hinzu.  
  
 Wenn Sie diese Methode an Ihre eigene Anwendung anpassen, beachten Sie, dass LINQ [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Version 3.5 benötigt und dass das Projekt einen Verweis auf System.Core.dll enthalten und eine Direktive für System.Linq verwenden muss.  LINQ\-to\-SQL\-, LINQ\-to\-XML\- und LINQ\-to\-DataSet\-Typen erfordern zusätzliche Usings und Verweise.  Weitere Informationen hierzu finden Sie unter [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Siehe auch  
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)