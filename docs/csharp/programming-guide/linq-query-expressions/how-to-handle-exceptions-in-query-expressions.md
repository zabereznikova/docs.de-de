---
redirect_url: /dotnet/articles/csharp/linq/handle-exceptions-in-query-expressions
caps.handback.revision: 15
---
# Gewusst wie: Behandeln von Ausnahmen in Abfrageausdr&#252;cken (C#-Programmierhandbuch)
Es ist möglich, eine Methode im Kontext eines Abfrageausdrucks aufzurufen.  Sie sollten es jedoch vermeiden, eine Methode in einem Abfrageausdruck aufzurufen, wenn dies zu unerwünschten Nebeneffekten führt, z. B. zum Ändern des Inhalts der Datenquelle oder zum Auslösen einer Ausnahme.  Dieses Beispiel zeigt, wie Sie verhindern können, dass Ausnahmen ausgelöst werden, wenn Sie Methoden in einem Abfrageausdruck aufrufen, ohne gegen die allgemeinen [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Richtlinien zur Ausnahmebehandlung zu verstoßen.  Diese Richtlinien besagen, dass spezielle Ausnahmen abgefangen werden können, wenn Sie wissen, warum sie in einem bestimmten Kontext ausgelöst werden.  Weitere Informationen finden Sie unter [Best Practices für Ausnahmen](../Topic/Best%20Practices%20for%20Exceptions.md).  
  
 Im letzten Beispiel wird gezeigt, wie Sie Fälle, in denen die Ausgabe einer Ausnahme während der Ausführung einer Abfrage erforderlich ist, behandeln können.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Ausnahmebehandlungscode außerhalb eines Abfrageausdrucks verschoben wird.  Dies ist nur möglich, wenn die Methode von keiner für die Abfrage lokalen Variablen abhängig ist.  
  
 [!code-cs[csProgGuideLINQ#10](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#10)]  
  
## Beispiel  
 In einigen Fällen ist die beste Antwort auf eine Ausnahme, die in einer Abfrage ausgelöst wird, das unmittelbare Anhalten des Abfragevorgangs.  Im folgenden Beispiel wird gezeigt, wie Ausnahmen, die in einem Abfragetext ausgelöst werden könnten, behandelt werden.  Annahme: `SomeMethodThatMightThrow` kann potenziell eine Ausnahme auslösen, woraufhin die Ausführung der Abfrage beendet werden muss.  
  
 Beachten Sie, dass der `try`\-Block die `foreach`\-Schleife einschließt, und nicht die Abfrage selbst.  Das liegt daran, dass die `foreach`\-Schleife der Punkt ist, an dem die Abfrage eigentlich ausgeführt wird.  Weitere Informationen hierzu finden Sie unter [Introduction to LINQ Queries \(C\#\)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 [!code-cs[csProgGuideLINQ#12](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#12)]  
  
## Kompilieren des Codes  
  
-   Erstellen Sie ein [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)]\-Projekt für .NET Framework, Version 3.5.  Standardmäßig weist das Projekt einen Verweis auf System.Core.dll und eine `using`\-Direktive für den System.Linq\-Namespace auf.  
  
-   Kopieren Sie den Code in Ihr Projekt.  
  
-   Drücken Sie F5, um das Programm zu kompilieren und auszuführen.  
  
 Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.  
  
## Siehe auch  
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)