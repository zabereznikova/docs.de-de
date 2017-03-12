---
redirect_url: /dotnet/articles/csharp/linq/handle-null-values-in-query-expressions
caps.handback.revision: 6
---
# Gewusst wie: Behandeln von NULL-Werten in Abfrageausdr&#252;cken (C#-Programmierhandbuch)
In diesem Beispiel wird gezeigt, wie mögliche NULL\-Werte in Quellauflistungen behandelt werden.  Eine Objektauflistung wie <xref:System.Collections.Generic.IEnumerable%601> kann Elemente enthalten, deren Wert [NULL](../../../csharp/language-reference/keywords/null.md) ist.  Wenn eine Quellauflistung NULL ist oder ein Element enthält, dessen Wert NULL ist, und die Abfrage keine NULL\-Werte behandelt, wird beim Ausführen der Abfrage <xref:System.NullReferenceException> ausgelöst.  
  
## Beispiel  
 Sie können defensiv codieren, um eine NULL\-Verweisausnahme zu vermeiden, wie im folgenden Beispiel gezeigt:  
  
 [!code-cs[csProgGuideLINQ#82](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csRef30LangFeatures_2.cs#82)]  
  
 Im vorherigen Beispiel filtert die `where`\-Klausel alle NULL\-Elemente in der Kategoriesequenz aus.  Diese Technik ist unabhängig von der NULL\-Prüfung in der join\-Klausel.  Der bedingte Ausdruck mit NULL in diesem Beispiel funktioniert, da `Products.CategoryID` vom Typ `int?` ist, was die Kurzform für `Nullable<int>` ist.  
  
## Beispiel  
 Ist in einer join\-Klausel nur einer der beiden Vergleichsschlüssel ein Werttyp, der NULL\-Werte zulässt, können Sie den anderen im Abfrageausdruck in einen Typ umwandeln, der auf NULL festgelegt werden kann.  Im folgenden Beispiel wird angenommen, dass `EmployeeID` eine Spalte ist, die Werte vom Typ `int?` enthält:  
  
 [!code-cs[csProgGuideLINQ#83](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csRef30LangFeatures_2.cs#83)]  
  
## Siehe auch  
 <xref:System.Nullable%601>   
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Typen, die NULL\-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md)