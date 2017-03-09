---
redirect_url: /dotnet/articles/csharp/linq/index
caps.handback.revision: 21
---
# LINQ-Abfrageausdr&#252;cke (C#-Programmierhandbuch)
[!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext-md.md)] ist der Name für einen Satz an Technologien, die auf der direkten Integration von Abfragefunktionen in die C\#\-Programmiersprache \(sowie in Visual Basic und potenziell auch in andere .NET\-Sprachen\) basieren.  In [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] entspricht eine Abfrage nun einem erstklassigen Sprachkonstrukt, ebenso wie Klassen, Methoden, Ereignisse usw.  
  
 Für Entwickler, die Abfragen schreiben, ist der sichtbarste "sprachintegrierte" Teil von [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] der Abfrageausdruck.  Abfrageausdrücke werden in einer deklarativen *Abfragesyntax* geschrieben, die in C\# 3.0 eingeführt wurde.  Die Abfragesyntax ermöglicht die Ausführung komplexer Filter\-, Sortier\- und Gruppiervorgänge mit minimalem Codeeinsatz.  Sie verwenden dieselben grundlegenden Abfrageausdrucksmuster zum Abfragen und Transformieren von Daten SQL\-Datenbanken, [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado-md.md)]\-Datasets, XML\-Dokumenten und \-Streams sowie .NET\-Auflistungen.  
  
 Das folgende Beispiel zeigt die vollständige Abfrageoperation.  Der vollständige Vorgang umfasst die Erstellung einer Datenquelle, die Definition des Abfrageausdrucks und die Ausführung der Abfrage in einer `foreach`\-Anweisung.  
  
 [!code-cs[csProgGuideLINQ#11](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#11)]  
  
 Weitere Informationen über die Grundlagen von [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] in C\# finden Sie unter [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md).  
  
## Übersicht über Abfrageausdrücke  
  
-   Abfrageausdrücke können verwendet werden, um Daten von einer [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]\-aktivierten Datenquelle abzufragen und zu transformieren.  Eine einzelne Abfrage kann beispielsweise Daten aus einer SQL\-Datenbank abrufen und als Ausgabe einen XML\-Stream erzeugen.  
  
-   Der Umgang mit Abfrageausdrücken ist nicht schwer zu erlernen, da sie viele vertraute C\#\-Sprachkonstrukte verwenden.  Weitere Informationen finden Sie unter [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md).  
  
-   Die Variablen in einem Abfrageausdruck sind alle stark typisiert, obwohl Sie in vielen Fällen den Typ nicht explizit angeben müssen, da der Compiler ihn ableiten kann.  Weitere Informationen finden Sie unter [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
-   Die Abfrage wird so lange nicht ausgeführt, bis Sie die Abfragevariable in einer `foreach`\-Anweisung durchlaufen.  Weitere Informationen hierzu finden Sie unter [Introduction to LINQ Queries \(C\#\)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
-   Abfrageausdrücke werden bei der Kompilierung gemäß den Regeln der C\#\-Spezifikation in Standardabfrageoperator\-Methodenaufrufe konvertiert.  Abfragen, die durch eine Abfragesyntax ausgedrückt werden können, können auch mit der Methodensyntax ausgedrückt werden.  In den meisten Fällen ist die Abfragesyntax jedoch leichter lesbar und präziser.  Weitere Informationen finden Sie unter [C\#\-Sprachspezifikation](../../../csharp/language-reference/language-specification.md) und unter [Standard Query Operators Overview](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
-   Als Regel gilt: Wenn Sie [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]\-Abfragen schreiben, ist es empfehlenswert, dass Sie wenn immer möglich die Abfragesyntax und wenn immer notwendig die Methodensyntax verwenden.  Es gibt keinen Semantik\- oder Leistungsunterschied zwischen den beiden.  Abfrageausdrücke sind oft leichter lesbar als entsprechende in Methodensyntax geschriebene Ausdrücke.  
  
-   Einige Abfrageoperationen, z. B. <xref:System.Linq.Enumerable.Count%2A> oder <xref:System.Linq.Enumerable.Max%2A>, haben keine entsprechende Abfrageausdruckklausel und müssen daher als Methodenaufruf ausgedrückt werden.  Die Methodensyntax kann auf verschiedene Weisen mit der Abfragesyntax kombiniert werden.  Weitere Informationen finden Sie unter [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
-   Abfrageausdrücke können je nach dem Typ, auf den die Abfrage angewendet wird, zu Ausdrucksbaumstrukturen oder zu Delegaten kompiliert werden.  <xref:System.Collections.Generic.IEnumerable%601>\-Abfragen werden zu Delegaten kompiliert.  <xref:System.Linq.IQueryable>\-Abfragen und <xref:System.Linq.IQueryable%601>\-Abfragen werden zu Ausdrucksbaumstrukturen kompiliert.  Weitere Informationen finden Sie unter [Ausdrucksbaumstrukturen](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md).  
  
 In der folgenden Tabelle werden Themen, die weitere Informationen über Abfragen und Codebeispiele für häufige Aufgaben enthalten, aufgeführt.  
  
|Thema|Beschreibung|  
|-----------|------------------|  
|[Grundlagen zu Abfrageausdrücken](../../../csharp/programming-guide/linq-query-expressions/query-expression-basics.md)|Führt wesentliche Abfragebegriffe ein, und stellt Beispiele für die C\#\-Abfragesyntax bereit.|  
|[Gewusst wie: Schreiben von LINQ\-Abfragen in C\#](../../../csharp/programming-guide/linq-query-expressions/how-to-write-linq-queries.md)|Stellt Beispiele für mehrere grundlegende Typen von Abfrageausdrücken bereit.|  
|[Gewusst wie: Behandeln von Ausnahmen in Abfrageausdrücken](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)|Gibt an, wie und wann Code, der potenziell zu Ausnahmen führen kann, aus einem Abfrageausdruck heraus verschoben werden sollte.|  
|[How to: Populate Object Collections from Multiple Sources \(LINQ\)](../Topic/How%20to:%20Populate%20Object%20Collections%20from%20Multiple%20Sources%20\(LINQ\).md)|Gibt an, wie die `select`\-Anweisung zum Zusammenführen von Daten aus unterschiedlichen Quellen zu einem neuen Typ verwendet wird.|  
|[Gewusst wie: Gruppieren von Abfrageergebnissen](../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md)|Zeigt andere Möglichkeiten auf, die `group`\-Klausel zu verwenden.|  
|[Gewusst wie: Erstellen einer geschachtelten Gruppe](../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)|Zeigt, wie geschachtelte Gruppen erstellt werden.|  
|[Gewusst wie: Ausführen einer Unterabfrage für eine Gruppierungsoperation](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)|Zeigt, wie ein Unterausdruck in einer Abfrage als Datenquelle für eine neue Abfrage verwendet wird.|  
|[Gewusst wie: Gruppieren von Ergebnissen nach zusammenhängenden Schlüsseln](../../../csharp/programming-guide/linq-query-expressions/how-to-group-results-by-contiguous-keys.md)|Veranschaulicht die Implementierung eines threadsicheren Standardabfrageoperators, der Gruppierungsvorgänge für Quellen von Streamingdaten ausführen kann.|  
|[Gewusst wie: Dynamisches Festlegen von Prädikatfiltern zur Laufzeit](../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)|Zeigt, wie eine beliebige Anzahl von Werten bereitgestellt wird, um sie in Vergleichen auf Gleichheit in einer `where`\-Klausel zu verwenden.|  
|[Gewusst wie: Speichern der Ergebnisse einer Abfrage im Speicher](../../../csharp/programming-guide/linq-query-expressions/how-to-store-the-results-of-a-query-in-memory.md)|Illustriert, wie Abfrageergebnisse materialisiert und gespeichert werden, ohne unbedingt eine `foreach`\-Schleife zu verwenden.|  
|[Gewusst wie: Zurückgeben einer Abfrage aus einer Methode](../../../csharp/programming-guide/linq-query-expressions/how-to-return-a-query-from-a-method.md)|Zeigt, wie Abfragevariablen aus Methoden zurückgegeben und als Eingabeparameter an Methoden übergeben werden.|  
|[Gewusst wie: Ausführen von benutzerdefinierten Verknüpfungsoperationen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md)|Zeigt, wie Joinoperationen auf Grundlage einer Prädikatfunktion ausgeführt werden.|  
|[Gewusst wie: Verknüpfen mithilfe eines zusammengesetzten Schlüssels](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md)|Zeigt, wie zwei Quellen auf Grundlage von mehr als einem übereinstimmenden Schlüssel verknüpft werden.|  
|[Gewusst wie: Sortieren der Ergebnisse einer Join\-Klausel](../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)|Zeigt, wie eine Sequenz, die von einer Joinoperation erzeugt wird, sortiert wird.|  
|[Gewusst wie: Ausführen innerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)|Zeigt, wie ein innerer Join in [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] ausgeführt wird.|  
|[Gewusst wie: Ausführen von Gruppenverknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)|Zeigt, wie ein Group Join in [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] erzeugt wird.|  
|[Gewusst wie: Ausführen linker äußerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)|Zeigt, wie ein linker äußerer Join in [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] erzeugt wird.|  
|[Gewusst wie: Behandeln von NULL\-Werten in Abfrageausdrücken](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-null-values-in-query-expressions.md)|Zeigt, wie NULL\-Werte in [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]\-Abfragen behandelt werden.|  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Walkthrough: Writing Queries in C\#](../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)   
 [Basic LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)   
 [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)   
 [Standard Query Operators Overview](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Abfrageschlüsselwörter \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Funktionsweise von Linq to Objects\-Abfragen](http://go.microsoft.com/fwlink/?LinkId=112389)   
 [Lesen und Schreiben von Abfragen](http://go.microsoft.com/fwlink/?LinkId=112391)   
 [Was ist eine Auflistung?](http://go.microsoft.com/fwlink/?LinkId=112394)   
 [Link für alle Elemente: Eine Liste mit LINQ\-Anbietern](http://go.microsoft.com/fwlink/?LinkId=112411)