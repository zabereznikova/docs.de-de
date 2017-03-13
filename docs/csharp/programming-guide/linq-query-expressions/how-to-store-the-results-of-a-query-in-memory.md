---
redirect_url: /dotnet/articles/csharp/linq/store-the-results-of-a-query-in-memory
caps.handback.revision: 13
---
# Gewusst wie: Speichern der Ergebnisse einer Abfrage im Speicher (C#-Programmierhandbuch)
Eine Abfrage ist im Grunde ein Satz von Anweisungen, wie Daten abgerufen und organisiert werden.  Um die Abfrage auszuführen, muss die <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>\-Methode aufgerufen werden.  Dieser Aufruf wird durchgeführt, wenn Sie eine `foreach`\-Schleife zum Durchlaufen der Elemente verwenden.  Um eine Abfrage auszuwerten und ihre Ergebnisse ohne eine `foreach`\-Schleife ausführen zu speichern auf, indem Sie eine der folgenden Methoden für die Abfragevariable:  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 Es wird empfohlen, das zurückgegebene Auflistungsobjekt beim Speichern der Abfrageergebnisse einer neuen Variable zuzuweisen, wie es im folgenden Beispiel dargestellt wird:  
  
## Beispiel  
 [!code-cs[csProgGuideLINQ#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-store-the-results-of-a-query-in-memory_1.cs)]  
  
## Kompilieren des Codes  
  
-   Erstellen Sie ein [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)]\-Projekt für .NET Framework, Version 3.5.  Standardmäßig weist das Projekt einen Verweis auf System.Core.dll und eine `using`\-Direktive für den System.Linq\-Namespace auf.  
  
-   Kopieren Sie den Code in Ihr Projekt.  
  
-   Drücken Sie F5, um das Programm zu kompilieren und auszuführen.  
  
-   Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.  
  
## Siehe auch  
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)