---
redirect_url: /dotnet/articles/csharp/linq/return-a-query-from-a-method
caps.handback.revision: 11
---
# Gewusst wie: Zur&#252;ckgeben einer Abfrage aus einer Methode (C#-Programmierhandbuch)
Dieses Beispiel zeigt, wie eine Abfrage von einer Methode als Rückgabewert und als `out`\-Parameter zurückgegeben wird.  
  
 Alle Abfragen müssen vom Typ <xref:System.Collections.IEnumerable> oder <xref:System.Collections.Generic.IEnumerable%601> oder von einem abgeleiteten Typ wie <xref:System.Linq.IQueryable%601> sein.  Daher müssen alle Rückgabewerte oder `out`\-Parameter einer Methode, die eine Abfrage zurückgibt, ebenfalls diesen Typ haben.  Wenn eine Methode eine Abfrage in einen konkreten <xref:System.Collections.Generic.List%601>\- oder <xref:System.Array>\-Typ materialisiert, wird sie so betrachtet, als würde sie die Abfrageergebnisse zurückgeben, und nicht die Abfrage selbst.  Eine von einer Methode zurückgegebene Abfragevariable kann immer noch zusammengesetzt oder geändert werden.  
  
## Beispiel  
 Im folgenden Beispiel gibt die erste Methode eine Abfrage als Rückgabewert zurück, und die zweite Methode gibt eine Abfrage als `out`\-Parameter zurück.  Beachten Sie, dass in beiden Fällen keine Abfrageergebnisse zurückgegeben werden, sondern eine Abfrage zurückgegeben wird.  
  
 [!code-cs[csProgGuideLINQ#80](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-return-a-query-from-a-method_1.cs)]  
  
## Kompilieren des Codes  
  
-   Erstellen Sie ein [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)]\-Projekt für .NET Framework, Version 3.5 oder höher.  Standardmäßig weist das Projekt einen Verweis auf System.Core.dll und eine `using`\-Direktive für den System.Linq\-Namespace auf.  
  
-   Ersetzen Sie die Klasse durch den Code im Beispiel.  
  
-   Drücken Sie F5, um das Programm zu kompilieren und auszuführen.  
  
-   Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.  
  
## Siehe auch  
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)