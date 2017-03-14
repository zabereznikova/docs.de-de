---
redirect_url: /dotnet/articles/csharp/linq/create-a-nested-group
caps.handback.revision: 12
---
# Gewusst wie: Erstellen einer geschachtelten Gruppe (C#-Programmierhandbuch)
Im folgenden Beispiel wird gezeigt, wie geschachtelte Gruppen in einem [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]\-Abfrageausdruck erstellt werden.  Jede Gruppe, die in Abhängigkeit vom Studienjahr oder Notenniveau erstellt wird, wird anschließend anhand der Namen der einzelnen Personen weiter in Gruppen unterteilt.  
  
## Beispiel  
 [!code-cs[csProgGuideLINQ#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-create-a-nested-group_1.cs)]  
  
 Beachten Sie, dass zum Durchlaufen der inneren Elemente einer geschachtelten Gruppe drei geschachtelte `foreach`\-Schleifen erforderlich sind.  
  
## Kompilieren des Codes  
 Dieses Beispiel enthält Verweise auf Objekte, die in der Beispielanwendung in [Gewusst wie: Abfragen einer Auflistung von Objekten](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md) definiert werden.  Um diese Methode zu kompilieren und auszuführen, fügen Sie sie in die `StudentClass`\-Klasse dieser Anwendung ein, und fügen Sie ihr von der `Main`\-Methode einen Aufruf hinzu.  
  
 Wenn Sie diese Methode an Ihre eigene Anwendung anpassen, beachten Sie, dass LINQ [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Version 3.5 benötigt und dass das Projekt einen Verweis auf System.Core.dll enthalten und eine Direktive für System.Linq verwenden muss.  LINQ\-to\-SQL\-, LINQ\-to\-XML\- und LINQ\-to\-DataSet\-Typen erfordern zusätzliche Usings und Verweise.  Weitere Informationen hierzu finden Sie unter [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Siehe auch  
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)