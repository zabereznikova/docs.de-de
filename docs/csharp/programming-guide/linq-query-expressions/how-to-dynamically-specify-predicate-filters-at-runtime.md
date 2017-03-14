---
redirect_url: /dotnet/articles/csharp/linq/dynamically-specify-predicate-filters-at-runtime
caps.handback.revision: 22
---
# Gewusst wie: Dynamisches Festlegen von Pr&#228;dikatfiltern zur Laufzeit (C#-Programmierhandbuch)
In einigen Fällen wissen Sie bis zur Laufzeit nicht, wie viele Prädikate Sie auf Quellelemente in der `where`\-Klausel anwenden müssen.  Sie können mehrere Prädikatfilter dynamisch festlegen, indem Sie beispielsweise die <xref:System.Linq.Enumerable.Contains%2A>\-Methode verwenden, wie im folgenden Beispiel gezeigt.  Das Beispiel wird auf zwei Weisen erstellt.  Zuerst wird das Projekt ausgeführt, indem Werte gefiltert werden, die im Programm bereitgestellt werden.  Dann wird das Projekt erneut ausgeführt, indem eine zur Laufzeit bereitgestellte Eingabe verwendet wird.  
  
### So filtern Sie mit der Contains\-Methode  
  
1.  Erstellen Sie in Visual Studio eine neue Konsolenanwendung.  Nennen Sie sie `PredicateFilters`.  
  
2.  Kopieren Sie die `StudentClass`\-Klasse aus [Gewusst wie: Abfragen einer Auflistung von Objekten](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md), und fügen Sie sie unter der `Program`\-Klasse in den `PredicateFilters`\-Namespace ein.  `StudentClass` stellt eine Liste von `Student`\-Objekten bereit.  
  
3.  Kommentieren Sie die `Main`\-Methode in `StudentClass`.  
  
4.  Ersetzen Sie die `Program`\-Klasse durch folgenden Code.  
  
     [!code-cs[csProgGuideLINQ#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]  
  
5.  Fügen Sie der `Main`\-Methode in der `DynamicPredicates`\-Klasse unter der Beschreibung von `ids` folgende Zeile hinzu.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
6.  Drücken Sie F5, um das Projekt auszuführen.  
  
7.  Im Eingabeaufforderungsfenster wird die die folgende Ausgabe angezeigt:  
  
     Garcia: 114  
  
     O'Donnell: 112  
  
     Omelchenko: 111  
  
8.  Als nächstes wird das Projekt erneut ausgeführt. Dieses Mal wird statt Array\-`ids` die Eingabe verwendet, die zur Laufzeit eingegeben wurde.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf **PredicateFilters**, und klicken Sie anschließend auf **Eigenschaften**.  
  
9. Klicken Sie auf die Registerkarte **Debuggen**.  
  
10. Geben Sie im Fenster **Befehlszeilenargumente** 122, 117, 120 und 115 ein, getrennt durch Leerzeichen: `122 117 120 115`.  Bei Ausführung des Projekts werden diese Werte zu Elementen von `args`, dem Parameter der `Main`\-Methode.  
  
11. Ändern Sie in der `Main`\-Methode `QueryByID(ids)` zu `QueryByID(args)`.  
  
12. Drücken Sie F5, um das Projekt auszuführen.  
  
13. Im Eingabeaufforderungsfenster wird die die folgende Ausgabe angezeigt:  
  
     Adams: 120  
  
     Feng: 117  
  
     Garcia: 115  
  
     Tucker: 122  
  
### So filtern Sie mit einer switch\-Anweisung  
  
1.  Sie können eine `switch`\-Anweisung zur Auswahl zuvor festgelegter Alternativabfragen verwenden.  Im folgenden Beispiel wird in Abhängigkeit von der während der Laufzeit angegebenen Klasstenstufe bzw. dem angegebenen Jahr von `studentQuery` eine andere `where`\-Klausel verwendet.  
  
2.  Kopieren Sie die folgende Methode, und fügen Sie sie in die `DynamicPredicates`\-Klasse ein.  
  
     [!code-cs[csProgGuideLINQ#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]  
  
3.  Ersetzen Sie im Fenster **Befehlszeilenargumente** die ID\-Nummern der vorherigen Prozedur durch einen ganzzahligen Wert zwischen 1 und 4.  
  
4.  Ersetzen Sie in der `Main`\-Methode den Aufruf von `QueryByID` mit dem folgenden Aufruf, der das erste Element des `args`\-Arrays als Argument sendet: `QueryByYear(args[0])`.  
  
5.  Drücken Sie F5, um das Projekt auszuführen.  
  
### So verwenden Sie diese Methode in eigenen Anwendungen  
  
-   Wenn Sie diese Methode an Ihre eigene Anwendung anpassen, beachten Sie, dass LINQ, Version 3.5 oder 4, von [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] erfordert, und dass das Projekt auf "System.Core.dll" verweisen und eine `using`\-Direktive für `System.Linq` enthalten muss.  LINQ\-to\-SQL\-, LINQ\-to\-XML\- und LINQ\-to\-DataSet\-Typen erfordern zusätzliche `using`\-Direktiven und \-Verweise.  Weitere Informationen hierzu finden Sie unter [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Siehe auch  
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [where\-Klausel](../../../csharp/language-reference/keywords/where-clause.md)