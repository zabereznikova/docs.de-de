---
redirect_url: /dotnet/articles/csharp/linq/perform-left-outer-joins
caps.handback.revision: 23
---
# Gewusst wie: Ausf&#252;hren linker &#228;u&#223;erer Verkn&#252;pfungen (C#-Programmierhandbuch)
Ein linker äußerer Join ist ein Join, in dem jedes Element aus der ersten Auflistung zurückgegeben wird, unabhängig davon, ob korrelierte Elemente in der zweiten Auflistung dafür zur Verfügung stehen.  Sie können [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] verwenden, um einen linken äußeren Join ausführen, indem Sie die <xref:System.Linq.Enumerable.DefaultIfEmpty%2A>\-Methode für die Ergebnisse eines Group Joins aufrufen.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht, wie die <xref:System.Linq.Enumerable.DefaultIfEmpty%2A>\-Methode auf die Ergebnisse des Group Joins angewendet wird, um einen linken äußeren Join auszuführen.  
  
 Der erste Schritt beim Erstellen eines linken äußeren Joins zweier Auflistungen besteht darin, einen inneren Join mithilfe eines Group Joins auszuführen.  \(Eine Erläuterung dieses Vorgangs finden Sie unter [Gewusst wie: Ausführen innerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md).\) In diesem Beispiel ist die Liste der `Person`\-Objekten zur Liste der `Pet`\-Objekte auf Grundlage eines `Person`\-Objekt die mit `Pet.Owner` einen.  
  
 Als Nächstes muss jedes Element der ersten \(linken\) Auflistung in den Ergebnissatz eingeschlossen werden, selbst wenn dieses Element keine Entsprechung in der rechten Auflistung hat.  Dazu rufen Sie <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> für jede Sequenz von übereinstimmenden Elementen aus dem Group Join auf.  In diesem Beispiel wird <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> um jeder Sequenz für passende `Pet`\-Objekten aufgerufen.  Die \- Methode eine Auflistung, die einen einzelnen Standardwert enthält, zurückgibt, wenn die Sequenz für passende `Pet`\-Objekten für jedes beliebige `Person`\-Objekt leer ist, somit wird sichergestellt, dass jedes Objekt `Person` in der Ergebnisauflistung dargestellt wird.  
  
> [!NOTE]
>  Der Standardwert für einen Referenztyp ist `null`; daher nach als ein NULL\-Verweis, bevor auf jedes Element in jeder `Pet`\-Auflistung zugegriffen wird.  
  
 [!code-cs[CsLINQProgJoining#7](../../../csharp/programming-guide/linq-query-expressions/codesnippet/csharp/Joins/joins.cs#7)]  
  
## Kompilieren des Codes  
  
-   Erstellen Sie ein neues Konsolenanwendungsprojekt in [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)].  
  
-   Fügen Sie einen Verweis auf System.Core.dll hinzu, wenn er noch nicht vorhanden ist.  
  
-   Schließen Sie den <xref:System.Linq>\-Namespace ein.  
  
-   Kopieren Sie den Code aus dem Beispiel in die program.cs\-Datei, unter der `Main`\-Methode in der Klasse `Program`.  Fügen Sie eine Codezeile der `Main`\-Methode hinzu, die `LeftOuterJoinExample`\-Methode aufzurufen.  
  
-   Führen Sie das Programm aus.  
  
## Siehe auch  
 <xref:System.Linq.Enumerable.Join%2A>   
 <xref:System.Linq.Enumerable.GroupJoin%2A>   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [Gewusst wie: Ausführen innerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)   
 [Gewusst wie: Ausführen von Gruppenverknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)   
 [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)