---
redirect_url: /dotnet/articles/csharp/linq/group-query-results
caps.handback.revision: 19
---
# Gewusst wie: Gruppieren von Abfrageergebnissen (C#-Programmierhandbuch)
Das Gruppieren ist eine der leistungsstärksten Funktionen von [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)].  In den folgenden Beispielen wird gezeigt, wie Daten auf verschiedene Weisen gruppiert werden:  
  
-   Anhand einer einzelnen Eigenschaft.  
  
-   Anhand des ersten Buchstabens einer Zeichenfolgeneigenschaft.  
  
-   Anhand eines berechneten numerischen Bereichs.  
  
-   Anhand eines booleschen Prädikats oder anderen Ausdrucks.  
  
-   Anhand eines zusammengesetzten Schlüssels.  
  
 Darüber hinaus projizieren die letzten beiden Abfragen die Ergebnisse in einen neuen anonymen Typ, der nur den Vor\- und Nachnamen des Studenten enthält.  Weitere Informationen finden Sie unter [group\-Klausel](../../../csharp/language-reference/keywords/group-clause.md).  
  
## Beispiel  
 Alle Beispiele in diesem Thema nutzen die folgenden Hilfsklassen und Datenquellen.  
  
 [!code-cs[csProgGuideLINQ#15](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#15)]  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Sie Quellelemente gruppieren können, indem Sie eine einzelne Eigenschaft des Elements als Gruppenschlüssel verwenden.  In diesem Fall ist der Schlüssel ein `string`, der Nachname des Studenten.  Es ist auch möglich, eine Teilzeichenfolge für den Schlüssel zu verwenden.  Der Gruppierungsvorgang verwendet den Standardgleichheitsvergleich für den Typ.  
  
 Fügen Sie die folgende Methode in die `StudentClass`\-Klasse ein.  Ändern Sie die Aufrufanweisung in der `Main`\-Methode in `sc.GroupBySingleProperty()`.  
  
 [!code-cs[csProgGuideLINQ#17](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#17)]  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Sie Quellelemente gruppieren können, indem Sie einen anderen Gruppenschlüssel als die Objekteigenschaft verwenden.  In diesem Beispiel ist der Schlüssel der erste Buchstabe des Nachnamens des Studenten.  
  
 Fügen Sie die folgende Methode in die `StudentClass`\-Klasse ein.  Ändern Sie die Aufrufanweisung in der `Main`\-Methode in `sc.GroupBySubstring()`.  
  
 [!code-cs[csProgGuideLINQ#18](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#18)]  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Sie Quellelemente gruppieren können, indem Sie einen numerischen Bereich als Gruppenschlüssel verwenden.  Die Abfrage projiziert dann die Ergebnisse in einen anonymen Typ, der nur den Vor\- und Nachnamen sowie den prozentualen Bereich des Studenten enthält.  Der anonyme Typ wird verwendet, da nicht das gesamte `Student`\-Objekt zur Anzeige der Ergebnisse verwendet werden muss.  `GetPercentile` ist eine Hilfsfunktion, mit der ein prozentualer Bereich anhand der Durchschnittsbewertung des Studenten berechnet wird.  Die Methode gibt einen ganzzahligen Wert zwischen 0 und 10 zurück.  
  
 [!code-cs[csProgGuideLINQ#50](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#50)]  
  
 Fügen Sie die folgende Methode in die `StudentClass`\-Klasse ein.  Ändern Sie die Aufrufanweisung in der `Main`\-Methode in `sc.GroupByRange()`.  
  
 [!code-cs[csProgGuideLINQ#19](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#19)]  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Sie Quellelemente gruppieren können, indem Sie einen booleschen Vergleichsausdruck verwenden.  In diesem Beispiel überprüft der boolesche Ausdruck, ob die Prüfungsdurchschnittsbewertung eines Studenten größer als 75 ist.  Wie in vorherigen Beispielen werden die Ergebnisse in einen anonymen Typ projiziert, da nicht das gesamte Quellelement benötigt wird.  Beachten Sie, dass die Eigenschaften im anonymen Typ zu Eigenschaften auf dem `Key`\-Member werden und beim Ausführen der Abfrage der Zugriff auf sie anhand des Namens möglich ist.  
  
 Fügen Sie die folgende Methode in die `StudentClass`\-Klasse ein.  Ändern Sie die Aufrufanweisung in der `Main`\-Methode in `sc.GroupByBoolean()`.  
  
 [!code-cs[csProgGuideLINQ#20](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#20)]  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Sie einen anonymen Typ zum Kapseln eines Schlüssels mit mehreren Werten verwenden können.  In diesem Beispiel ist der erste Schlüsselwert der erste Buchstabe des Nachnamens des Studenten.  Der zweite Schlüsselwert ist ein boolescher Wert, der angibt, ob der Student in der ersten Prüfung einen Wert über 85 erzielt hat.  Sie können die Gruppen anhand jeder Eigenschaft im Schlüssel sortieren.  
  
 Fügen Sie die folgende Methode in die `StudentClass`\-Klasse ein.  Ändern Sie die Aufrufanweisung in der `Main`\-Methode in `sc.GroupByCompositeKey()`.  
  
 [!code-cs[csProgGuideLINQ#21](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#21)]  
  
## Kompilieren des Codes  
 Kopieren Sie jede Methode, die Sie testen möchten, in die `StudentClass`\-Klasse.  Fügen Sie der `Main`\-Methode eine Aufrufanweisung für die Methode hinzu, und drücken Sie F5.  
  
 Wenn Sie diese Methoden an die eigene Anwendung anpassen, beachten Sie, dass LINQ [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] Version 3.5 oder 4 erfordert und dass das Projekt einen Verweis auf System.Core.dll enthalten und eine Direktive für System.Linq verwenden muss.  LINQ to SQL\-, LINQ to XML\- und LINQ to DataSet\-Typen erfordern zusätzliche using\-Direktiven und \-Verweise.  Weitere Informationen hierzu finden Sie unter [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Siehe auch  
 <xref:System.Linq.Enumerable.GroupBy%2A>   
 <xref:System.Linq.IGrouping%602>   
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [group\-Klausel](../../../csharp/language-reference/keywords/group-clause.md)   
 [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Gewusst wie: Ausführen einer Unterabfrage für eine Gruppierungsoperation](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)   
 [Gewusst wie: Erstellen einer geschachtelten Gruppe](../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)   
 [Grouping Data](../../../visual-basic/programming-guide/concepts/linq/grouping-data.md)