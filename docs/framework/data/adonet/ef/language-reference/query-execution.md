---
title: Abfrageausführung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c0e6cf23-63ac-47dd-bfe9-d5bdca826fac
ms.openlocfilehash: e372744eea3eed7fc3f7ee9c8bbdd711c95b586e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149972"
---
# <a name="query-execution"></a>Abfrageausführung
Nachdem eine LINQ-Abfrage von einem Benutzer erstellt wurde, wird sie in eine Befehlsstruktur konvertiert. Eine Befehlsstruktur ist eine Darstellung einer Abfrage, die mit dem Entity Framework kompatibel ist. Die Befehlsstruktur wird dann für die Datenquelle ausgeführt. Während der Ausführung der Abfrage werden alle Abfrageausdrücke (d. h. alle Komponenten der Abfrage) ausgewertet, einschließlich der Ausdrücke, die für die Materialisierung der Ergebnisse verwendet werden.  
  
 An welchem Punkt Abfrageausdrücke ausgeführt werden ist unterschiedlich. LINQ-Abfragen werden nicht bei der Erstellung der Abfragevariablen, sondern beim Durchlaufen der Abfragevariablen ausgeführt. Dies wird als *verzögerte Ausführung*bezeichnet. Eine sofortige Ausführung der Abfrage kann auch erzwungen werden. Dies ist für die Zwischenspeicherung von Abfrageergebnissen sinnvoll. Dies wird weiter unten in diesem Thema beschrieben.  
  
 Beim Ausführen einer LINQ to Entities-Abfrage werden möglicherweise einige Ausdrücke auf dem Server und andere lokal auf dem Client ausgeführt. Ein Ausdruck wird auf dem Client ausgewertet, bevor die Abfrage auf dem Server ausgeführt wird. Wenn ein Ausdruck auf dem Client ausgewertet wird, wird dieser Ausdruck in der Abfrage durch das Ergebnis der Auswertung ersetzt. Anschließend wird die Abfrage auf dem Server ausgeführt. Da Abfragen für die Datenquelle ausgeführt werden, wird das auf dem Client festgelegte Verhalten von der Konfiguration der Datenquelle überschrieben. Zum Beispiel hängen die Behandlung von NULL-Werten und die numerische Genauigkeit von den Servereinstellungen ab. Alle Ausnahmen, die bei der Abfrageausführung auf dem Server ausgelöst wurden, werden direkt an den Client weitergegeben.  

> [!TIP]
> Eine praktische Zusammenfassung der Abfrageoperatoren im Tabellenformat, mit der Sie das Ausführungsverhalten eines Operators schnell identifizieren können, finden Sie unter [Klassifizierung von Standardabfrageoperatoren nach Ausführungsweisen (C)](../../../../../csharp/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md).

## <a name="deferred-query-execution"></a>Verzögerte Abfrageausführung  
 In einer Abfrage, die eine Sequenz von Werten zurückgibt, enthält die Abfragevariable selbst niemals die Abfrageergebnisse, sondern immer nur die Abfragebefehle. Die Ausführung der Abfrage wird verzögert, bis die Abfragevariable in einer `foreach`- oder `For Each`-Schleife durchlaufen wird. Dies wird als *verzögerte Ausführung*bezeichnet; Das heißt, die Abfrageausführung erfolgt einige Zeit nach dem Erstellen der Abfrage. Auf diese Weise können Sie die Abfrage so häufig ausführen, wie Sie dies wünschen. Dies bietet sich z. B. dann an, wenn Sie eine Datenbank haben, die von anderen Anwendungen aktualisiert wird. Sie können in Ihrer Anwendung eine Abfrage erstellen, mit der die neuesten Informationen abgerufen werden, und diese Abfrage wiederholt ausführen, wobei jedes Mal die aktualisierten Informationen zurückgegeben werden.  
  
 Die verzögerte Ausführung ermöglicht die Kombination mehrerer Abfragen oder die Erweiterung einer bestehenden Abfrage. durch das Hinzufügen neuer Operationen. Die Änderungen werden dann bei der Ausführung der Abfrage berücksichtigt. Im folgenden Beispiel gibt die erste Abfrage alle Produkte zurück. Die zweite Abfrage erweitert die erste, indem sie `Where` verwendet, um alle Produkte der Größe "L" zurückzugeben:  
  
 [!code-csharp[DP L2E Conceptual Examples#Composing1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#composing1)]
 [!code-vb[DP L2E Conceptual Examples#Composing1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#composing1)]  
  
 Nachdem eine Abfrage ausgeführt wurde, verwenden alle folgenden Abfragen die LINQ-Operatoren im Arbeitsspeicher. Durch das Durchlaufen der Abfragevariable durch die Verwendung einer `foreach`- oder `For Each`-Anweisung oder das Aufrufen eines der LINQ-Konvertierungsoperatoren wird die sofortige Ausführung verursacht. Dabei kann es sich um folgende Konvertierungsoperatoren handeln: <xref:System.Linq.Enumerable.ToList%2A>, <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToLookup%2A> und <xref:System.Linq.Enumerable.ToDictionary%2A>.  
  
## <a name="immediate-query-execution"></a>Unmittelbare Abfrageausführung  
 Im Gegensatz zur verzögerten Ausführung von Abfragen, die eine Sequenz von Werten zurückgeben, werden Abfragen, die einen Singleton-Wert zurückgeben, sofort ausgeführt. Einige Beispiele für SINGLETON-Abfragen sind <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.First%2A> und <xref:System.Linq.Enumerable.Max%2A>. Diese werden sofort ausgeführt, da die Abfrage eine Sequenz für die Berechnung des Singleton-Ergebnisses erzeugen muss. Eine unmittelbare Ausführung kann auch erzwungen werden. Dies ist nützlich, wenn die Ergebnisse einer Abfrage zwischengespeichert werden sollen. Zur Erzwingung der sofortigen Ausführung einer Abfrage, die keinen Singleton-Wert zurückgibt, kann die <xref:System.Linq.Enumerable.ToList%2A>-Methode, die <xref:System.Linq.Enumerable.ToDictionary%2A>-Methode oder die <xref:System.Linq.Enumerable.ToArray%2A>-Methode für eine Abfrage oder eine Abfragevariable aufgerufen werden. Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.ToArray%2A>-Methode verwendet, um eine Sequenz unmittelbar in ein Array auszuwerten.  
  
 [!code-csharp[DP L2E Examples#ToArray](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#toarray)]
 [!code-vb[DP L2E Examples#ToArray](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#toarray)]  
  
 Die Ausführung kann auch erzwungen werden, indem die `foreach`-Schleife oder die `For Each`-Schleife unmittelbar hinter den Abfrageausdruck gestellt wird. Mit einem Aufruf von <xref:System.Linq.Enumerable.ToList%2A> oder <xref:System.Linq.Enumerable.ToArray%2A> werden jedoch alle Daten in einem einzelnen Auflistungsobjekt zwischengespeichert.  
  
## <a name="store-execution"></a>Speicherausführung  
 Im Allgemeinen werden Ausdrücke in LINQ to Entities auf dem Server ausgewertet, und das Verhalten der Ausdrücke richtet sich nicht nach der CLR-Semantik, sondern nach der Semantik der Datenquelle. Dies gilt jedoch nicht, wenn der Ausdruck z. B. auf dem Client ausgeführt wird. Dies kann zu unerwarteten Ergebnissen führen, wenn sich beispielsweise Server und Client in unterschiedlichen Zeitzonen befinden.  
  
 Einige Ausdrücke in der Abfrage werden möglicherweise auf dem Client ausgeführt. Im Allgemeinen findet der größte Teil der Abfrageausführung auf dem Server statt. Neben Methoden, die für der Datenquelle zugeordnete Abfrageelemente ausgeführt werden, gibt es häufig Ausdrücke in der Abfrage, die lokal ausgeführt werden können. Bei der lokalen Ausführung eines Abfrageausdrucks wird ein Wert zurückgegeben, der für die Ausführung der Abfrage oder die Konstruktion des Ergebnisses verwendet werden kann.  
  
 Bestimmte Operationen werden stets auf dem Client ausgeführt. Dazu gehören die Bindung von Werten, Unterausdrücken und Unterabfragen von Abschlüssen sowie die Materialisierung von Objekten in Abfrageergebnisse. Das bedeutet, dass diese Elemente (beispielsweise Parameterwerte) während der Ausführung nicht aktualisiert werden können. Anonyme Typen können inline in der Datenquelle erstellt werden. Davon sollte jedoch nicht ausgegangen werden. Inlinegruppierungen können ebenfalls in der Datenquelle erstellt werden. Davon sollte jedoch ebenfalls nicht in jedem Fall ausgegangen werden. Im Allgemeinen sollten keine Annahmen darüber gemacht werden, was auf dem Server erstellt wird.  
  
 In diesem Abschnitt werden die Szenarios, in denen Code lokal auf dem Client ausgeführt wird, beschrieben. Weitere Informationen darüber, welche Arten von Ausdrücken lokal ausgeführt werden, finden Sie unter [Ausdrücke in LINQ to Entities Queries](expressions-in-linq-to-entities-queries.md).  
  
### <a name="literals-and-parameters"></a>Literale und Parameter  
 Lokale Variablen, wie die `orderID`-Variable im folgenden Beispiel, werden auf dem Client ausgewertet.  
  
 [!code-csharp[DP L2E Conceptual Examples#LiteralParameter1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#literalparameter1)]
 [!code-vb[DP L2E Conceptual Examples#LiteralParameter1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#literalparameter1)]  
  
 Methodenparameter werden ebenfalls auf dem Client ausgewertet. Der unten der `orderID`-Methode übergebene `MethodParameterExample`-Parameter ist ein Beispiel dafür.  
  
 [!code-csharp[DP L2E Conceptual Examples#MethodParameterExample](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#methodparameterexample)]
 [!code-vb[DP L2E Conceptual Examples#MethodParameterExample](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#methodparameterexample)]  
  
### <a name="casting-literals-on-the-client"></a>Umwandeln von Literalen auf dem Client  
 Umwandlungen von `null` in einen CLR-Typ werden auf dem Client ausgeführt:  
  
 [!code-csharp[DP L2E Conceptual Examples#NullCastToString](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#nullcasttostring)]
 [!code-vb[DP L2E Conceptual Examples#NullCastToString](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#nullcasttostring)]  
  
 Umwandlungen in einen Typ, wie ein <xref:System.Decimal>, das NULL-Werte zulässt, werden auf dem Client ausgeführt:  
  
 [!code-csharp[DP L2E Conceptual Examples#CastToNullable](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#casttonullable)]
 [!code-vb[DP L2E Conceptual Examples#CastToNullable](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#casttonullable)]  
  
### <a name="constructors-for-literals"></a>Konstruktoren für Literale  
 Neue CLR-Typen, die konzeptionellen Modelltypen zugeordnet werden können, werden auf dem Client ausgeführt:  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstructorForLiteral](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constructorforliteral)]
 [!code-vb[DP L2E Conceptual Examples#ConstructorForLiteral](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constructorforliteral)]  
  
 Neue Arrays werden ebenfalls auf dem Client ausgeführt.  
  
## <a name="store-exceptions"></a>Speicherausnahmen  
 Während der Abfrageausführung auftretende Speicherfehler werden an den Client übergeben und nicht zugeordnet oder behandelt.  
  
## <a name="store-configuration"></a>Speicherkonfiguration  
 Bei der Abfrageausführung im Speicher überschreibt die Speicherkonfiguration das Clientverhalten, und für alle Operationen und Ausdrücke wird Speichersemantik verwendet. Das kann zu unterschiedlichem Verhalten von CLR- und Speicherausführung in Bereichen wie NULL-Vergleichen, GUID-Sortierung, Genauigkeit von Operationen mit nicht-präzisen Datentypen (wie Gleitkommatypen oder <xref:System.DateTime>) sowie Zeichenfolgenoperationen führen. Bei der Beurteilung von Abfrageergebnissen sollten diese Punkte beachtet werden.  
  
 Folgende Beispiele zeigen einige Unterschiede im Verhalten zwischen der CLR und SQL Server:  
  
- SQL Server sortiert GUIDs anders als die CLR.  
  
- Es können auch Unterschiede in der Ergebnisgenauigkeit beim Arbeiten mit dem Decimal-Typ auf SQL Server auftreten. Der Grund dafür sind die Anforderungen fester Präzision des Dezimaltyps von SQL Server. Beispielsweise ist der Durchschnitt der <xref:System.Decimal>-Werte 0,0 und 0,0 und 1,0 im Arbeitsspeicher des Clients 0,3333333333333333333333333333 und im Speicher 0,333333 (für die Standardpräzision des Dezimaltyps von SQL Server).  
  
- Einige Zeichenfolgenvergleichsvorgänge werden in SQL Server ebenfalls anders behandelt als in der CLR. Das Verhalten bei Zeichenfolgenvergleichen hängt von den Sortiereinstellungen auf dem Server ab.  
  
- Funktions- oder Methodenaufrufe, die in einer LINQ to Entities-Abfrage enthalten sind, werden kanonischen Funktionen im Entity Framework zugeordnet, die wiederum in Transact-SQL übersetzt und in der SQL Server-Datenbank ausgeführt werden. Es gibt Fälle, in denen sich das Verhalten dieser zugeordneten Funktionen von dem der Implementierung in den Basisklassenbibliotheken unterscheidet. Ein Aufruf der <xref:System.String.Contains%2A>, <xref:System.String.StartsWith%2A>-Methode und der <xref:System.String.EndsWith%2A>-Methode mit einer leeren Zeichenfolge als Parameter gibt bei der Ausführung in der CLR `true` zurück und bei der Ausführung in SQL Server `false`. Die <xref:System.String.EndsWith%2A>-Methode kann ebenfalls unterschiedliche Ergebnisse zurückgeben, da zwei Zeichenfolgen, die sich nur in nachfolgenden Leerzeichen unterscheiden, in SQL Server als gleich aufgefasst werden, in der CLR jedoch nicht. Dies wird im folgenden Beispiel illustriert:  
  
 [!code-csharp[DP L2E Conceptual Examples#CanonicalFuncVsCLRBaseType](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#canonicalfuncvsclrbasetype)]
 [!code-vb[DP L2E Conceptual Examples#CanonicalFuncVsCLRBaseType](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#canonicalfuncvsclrbasetype)]
