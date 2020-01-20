---
title: Einführung in LINQ-Abfragen (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- deferred execution [LINQ]
- LINQ, queries
- LINQ, deferred execution
- queries [LINQ], about LINQ queries
ms.assetid: 37895c02-268c-41d5-be39-f7d936fa88a8
ms.openlocfilehash: 74a6f2e1e9296551f4faf73a905b49d3e2e3687e
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635716"
---
# <a name="introduction-to-linq-queries-c"></a>Einführung in LINQ-Abfragen (C#)
Eine *Abfrage* ist ein Ausdruck, der Daten von einer Datenquelle abruft. Abfragen werden normalerweise in einer spezialisierten Abfragesprache ausgedrückt. Im Laufe der Zeit wurden verschiedene Sprachen für die verschiedenen Datenquellen entwickelt, beispielsweise SQL für relationale Datenbanken und XQuery für XML. Aus diesem Grund mussten Entwickler für jeden Typ von Datenquelle oder Datenformat, den sie unterstützen müssen, eine neue Abfragesprache erlernen. LINQ vereinfacht diese Situation durch die Bereitstellung eines konsistenten Modells zum Arbeiten mit Daten in verschiedenen Arten von Datenquellen und Formaten. In einer LINQ-Abfrage arbeiten Sie immer mit Objekten. Sie verwenden dieselben grundlegenden Codierungsmuster für die Abfrage und Transformation von Daten in XML-Dokumenten, SQL-Datenbanken, ADO.NET-Datasets, .NET-Auflistungen sowie allen anderen Quellen und Formaten, für die ein LINQ-Anbieter verfügbar ist.  
  
## <a name="three-parts-of-a-query-operation"></a>Drei Teile einer Abfrageoperation  
 Alle LINQ-Abfrageoperationen bestehen aus drei unterschiedlichen Aktionen:  
  
1. Abrufen der Datenquelle  
  
2. Erstellen der Abfrage  
  
3. Ausführen der Abfrage  
  
 Im folgenden Beispiel wird gezeigt, wie die drei Teile einer Abfrageoperation in Quellcode ausgedrückt werden. Das Beispiel verwendet aus praktischen Gründen ein Array von Ganzzahlen als Datenquelle. Dieselben Konzepte gelten jedoch auch für andere Datenquellen. Auf dieses Beispiel wird im Rest dieses Themas Bezug genommen.  
  
 [!code-csharp[CsLINQGettingStarted#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#1)]  
  
 Die folgende Abbildung zeigt die vollständige Abfrageoperation. In LINQ unterscheidet sich die Ausführung der Abfrage von der Abfrage selbst. Anders ausgedrückt: Sie haben keine Daten abgerufen, indem Sie nur eine Abfragevariable erstellen.  
  
 ![Diagramm des vollständigen LINQ-Abfragevorgangs](./media/introduction-to-linq-queries/linq-query-complete-operation.png)  
  
## <a name="the-data-source"></a>Die Datenquelle  
 Da es sich bei der Datenquelle im vorherigen Beispiel um ein Array handelt, unterstützt sie implizit die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle. Das bedeutet, dass sie mit L abgefragt werden kann. Eine Abfrage wird in einer `foreach`-Anweisung ausgeführt, und `foreach` erfordert <xref:System.Collections.IEnumerable> oder <xref:System.Collections.Generic.IEnumerable%601>. Typen, die <xref:System.Collections.Generic.IEnumerable%601> unterstützen oder eine abgeleitete Schnittstelle, wie z.B. der generische Typ <xref:System.Linq.IQueryable%601>, werden als *abfragbare Typen* bezeichnet.  
  
 Für abfragbare Typen ist keine Änderung oder besondere Behandlung notwendig, um sie als LINQ-Datenquelle zu verwenden. Wenn die Quelldaten nicht bereits als abfragbarer Typ im Arbeitsspeicher vorhanden sind, muss der LINQ-Anbieter diese als solcher darstellen. Zum Beispiel lädt [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ein XML-Dokument in einen abfragbaren <xref:System.Xml.Linq.XElement>-Typ:  
  
 [!code-csharp[CsLINQGettingStarted#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#2)]  
  
 Mit [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] erstellen Sie zuerst eine objektrelationale Zuordnung zur Entwurfszeit, entweder manuell oder mit den [LING in SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2). Sie schreiben die Abfragen anhand der Objekte, und zur Laufzeit übernimmt [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] die Kommunikation mit der Datenbank. Im folgenden Beispiel stellt `Customers` eine bestimmte Tabelle in der Datenbank dar, und der Typ des Abfrageergebnisses, <xref:System.Linq.IQueryable%601>, wird von <xref:System.Collections.Generic.IEnumerable%601> abgeleitet.  
  
```csharp  
Northwnd db = new Northwnd(@"c:\northwnd.mdf");  
  
// Query for customers in London.  
IQueryable<Customer> custQuery =  
    from cust in db.Customers  
    where cust.City == "London"  
    select cust;  
```  
  
 Weitere Informationen zum Erstellen bestimmter Typen von Datenquellen finden Sie in der Dokumentation der verschiedenen LINQ-Anbieter. Die Grundregel ist jedoch sehr einfach: Eine LINQ-Datenquelle ist jedes Objekt, das die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle oder eine Schnittstelle unterstützt, die davon erbt.  
  
> [!NOTE]
> Typen wie <xref:System.Collections.ArrayList>, die die nicht generische <xref:System.Collections.IEnumerable>-Schnittstelle unterstützen, können ebenso als LINQ-Datenquelle verwendet werden. Weitere Informationen finden Sie unter [Vorgehensweise: Abfragen von ArrayList mit LINQ (C#)](./how-to-query-an-arraylist-with-linq.md).  
  
## <a name="query"></a> Die Abfrage  
 Die Abfrage gibt an, welche Informationen aus der Datenquelle oder den Datenquellen abgerufen werden sollen. Optional kann eine Abfrage auch angeben, wie diese Informationen vor der Rückgabe sortiert, gruppiert und strukturiert werden sollen. Eine Abfrage wird in einer Abfragevariablen gespeichert und mit einem Abfrageausdruck initialisiert. Um das Schreiben von Abfragen zu erleichtern, hat C# eine neue Abfragesyntax eingeführt.  
  
 Die Abfrage im vorherigen Beispiel gibt alle geraden Zahlen aus einem Ganzzahlen-Array zurück. Der Abfrageausdruck enthält drei Klauseln: `from`, `where` und `select`. (Wenn Sie mit SQL vertraut sind, ist Ihnen wahrscheinlich aufgefallen, dass die Klauseln umgekehrt wie in SQL angeordnet sind.) Die `from`-Klausel gibt die Datenquelle an, die `where`-Klausel wendet den Filter an, und die `select`-Klausel gibt den Typ der zurückgegebenen Elemente an. Diese und weitere Abfrageklauseln werden ausführlich im Abschnitt [LINQ-Abfrageausdrücke](../../../linq/index.md) erläutert. Wichtig ist hier, dass die Abfragevariable selbst in LINQ keine Aktion ausführt und keine Daten zurückgibt. Sie speichert nur die Informationen, die erforderlich sind, um Ergebnisse zu erzeugen, wenn die Abfrage zu einem späteren Zeitpunkt ausgeführt wird. Weitere Informationen zum Erstellen von Abfragen hinter den Kulissen finden Sie unter [Übersicht über Standardabfrageoperatoren (C#)](./standard-query-operators-overview.md).  
  
> [!NOTE]
> Abfragen können auch unter Verwendung der Methodensyntax ausgedrückt werden. Weitere Informationen finden Sie unter [Abfragesyntax und Methodensyntax in LINQ](./query-syntax-and-method-syntax-in-linq.md).  
  
## <a name="query-execution"></a>Abfrageausführung  
  
### <a name="deferred-execution"></a>Verzögerte Ausführung  
 Wie bereits erwähnt, speichert die Abfragevariable selbst nur die Abfragebefehle. Die tatsächliche Ausführung der Abfrage wird so lange verzögert, bis Sie die Abfragevariable in einer `foreach`-Anweisung durchlaufen. Dieses Konzept wird als *verzögerte Ausführung* bezeichnet und wird im folgenden Beispiel veranschaulicht:  
  
 [!code-csharp[csLinqGettingStarted#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#4)]  
  
 In der `foreach`-Anweisung werden auch die Abfrageergebnisse abgerufen. So ist beispielsweise in der vorherigen Abfrage in der Iterationsvariablen `num` jeder Wert (jeweils einzeln) der zurückgegebenen Sequenz enthalten.  
  
 Da die Abfragevariable selbst nie die Abfrageergebnisse enthält, können Sie sie beliebig oft ausführen. Sie könnten beispielsweise über eine Datenbank verfügen, die ständig durch eine separate Anwendung aktualisiert wird. Sie könnten in Ihrer Anwendung eine Abfrage erstellen, die die neuesten Daten abruft, und Sie könnten diese Abfrage in bestimmten Abständen wiederholt ausführen, um bei jeder Ausführung andere Ergebnisse abzurufen.  
  
### <a name="forcing-immediate-execution"></a>Erzwingen der unmittelbaren Ausführung  
 Abfragen, die Aggregationsfunktionen für einen Bereich von Quellelementen ausführen, müssen zuerst diese Elemente durchlaufen. Beispiele für solche Abfragen sind `Count`, `Max`, `Average` und `First`. Diese Abfragen werden ohne explizite `foreach`-Anweisung ausgeführt, da die Abfrage selbst `foreach` verwenden muss, um ein Ergebnis auszugeben. Beachten Sie auch, dass diese Typen von Abfragen einen einzelnen Wert und keine `IEnumerable`-Auflistung zurückgeben. Die folgende Abfrage gibt eine Anzahl der geraden Zahlen im Quellarray zurück:  
  
 [!code-csharp[csLinqGettingStarted#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#5)]  
  
 Um die unmittelbare Ausführung einer Abfrage zu erzwingen und ihre Ergebnisse zwischenzuspeichern, können Sie die <xref:System.Linq.Enumerable.ToList%2A>-Methode oder die <xref:System.Linq.Enumerable.ToArray%2A>-Methode aufrufen.  
  
 [!code-csharp[csLinqGettingStarted#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#6)]  
  
 Sie können die Ausführung auch erzwingen, indem Sie die `foreach`-Schleife unmittelbar nach dem Abfrageausdruck setzen. Durch Aufrufen von `ToList` oder `ToArray` speichern Sie jedoch auch alle Daten in einem einzelnen Auflistungsobjekt zwischen.  
  
## <a name="see-also"></a>Siehe auch

- [Erste Schritte mit LINQ in C#](/dotnet/csharp/programming-guide/concepts/linq/)
- [Exemplarische Vorgehensweise: Schreiben von Abfragen in C#](./walkthrough-writing-queries-linq.md)
- [LINQ-Abfrageausdrücke](../../../linq/index.md)
- [foreach, in](../../../language-reference/keywords/foreach-in.md)
- [Abfrageschlüsselwörter (LINQ)](../../../language-reference/keywords/query-keywords.md)
