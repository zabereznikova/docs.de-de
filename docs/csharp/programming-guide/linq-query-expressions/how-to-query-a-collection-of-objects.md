---
redirect_url: /dotnet/articles/csharp/linq/query-a-collection-of-objects
caps.handback.revision: 8
---
# Gewusst wie: Abfragen einer Auflistung von Objekten (C#-Programmierhandbuch)
In diesem Beispiel wird gezeigt, wie eine einfache Abfrage für eine Liste von `Student`\-Objekten ausgeführt wird.  Jedes `Student`\-Objekt enthält einige grundlegende Informationen zum Studenten sowie eine Liste mit Bewertungen aus vier Prüfungen des Studenten.  
  
 Diese Anwendung dient als Grundlage für viele andere Beispiele in diesem Abschnitt, in denen die gleiche `students` \-Datenquelle verwendet wird.  
  
## Beispiel  
 Die folgende Abfrage gibt die Studenten zurück, die in der ersten Prüfung ein Testergebnis von 90 oder mehr erzielt haben.  
  
 [!code-cs[csProgGuideLINQ#15](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#15)]  
  
 Diese Abfrage wurde absichtlich einfach gehalten, damit Sie damit etwas üben können.  Sie können beispielsweise mehr Prädikate in der `where`\-Klausel angeben oder eine `orderby`\-Klausel zum Sortieren der Ergebnisse verwenden.  
  
## Kompilieren des Codes  
  
-   Erstellen Sie ein [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)]\-Projekt für .NET Framework, Version 3.5.  Standardmäßig weist das Projekt einen Verweis auf System.Core.dll und eine `using`\-Direktive für den System.Linq\-Namespace auf.  
  
-   Kopieren Sie den Code in Ihr Projekt.  
  
-   Drücken Sie F5, um das Programm zu kompilieren und auszuführen.  
  
-   Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.  
  
## Siehe auch  
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)