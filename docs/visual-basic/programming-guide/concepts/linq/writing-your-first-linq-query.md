---
title: Schreiben der ersten LINQ-Abfrage
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ queries [Visual Basic]
- LINQ [Visual Basic], writing queries
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
ms.openlocfilehash: a9fe4241972815a04ec9c6a51a45760d72a8bbb2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349344"
---
# <a name="writing-your-first-linq-query-visual-basic"></a>Schreiben der ersten LINQ-Abfrage (Visual Basic)
Eine *Abfrage* ist ein Ausdruck, der Daten von einer Datenquelle abruft. Abfragen werden in einer dedizierten Abfragesprache ausgedrückt. Im Laufe der Zeit wurden verschiedene Sprachen für verschiedene Arten von Datenquellen entwickelt, beispielsweise SQL für relationale Datenbanken und XQuery für XML. Dadurch muss der Anwendungsentwickler für jeden unterstützten Typ von Datenquelle oder Datenformat eine neue Abfragesprache erlernen.  
  
 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] vereinfacht die Situation, indem ein konsistentes Modell zum Arbeiten mit Daten über verschiedene Arten von Datenquellen und-Formaten angeboten wird. In einer [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrage arbeiten Sie immer mit Objekten. Sie verwenden dieselben grundlegenden Codierungs Muster zum Abfragen und Transformieren von Daten in XML-Dokumenten, SQL-Datenbanken, ADO.NET Datasets und Entitäten, .NET Framework Sammlungen und anderen Quellen oder Formaten, für die ein [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Anbieter verfügbar ist. In diesem Dokument werden die drei Phasen der Erstellung und Verwendung von grundlegenden [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfragen beschrieben.  
  
## <a name="three-stages-of-a-query-operation"></a>Drei Phasen eines Abfrage Vorgangs  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage Vorgänge bestehen aus drei Aktionen:  
  
1. Abrufen der Datenquelle oder der Quellen  
  
2. Erstellen der Abfrage  
  
3. Ausführen der Abfrage  
  
 In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]unterscheidet sich die Ausführung einer Abfrage von der Erstellung der Abfrage. Sie können keine Daten abrufen, indem Sie nur eine Abfrage erstellen. Dieser Punkt wird in diesem Thema an späterer Stelle ausführlicher behandelt.  
  
 Im folgenden Beispiel werden die drei Teile eines Abfrage Vorgangs veranschaulicht. Im Beispiel wird ein Array aus ganzen Zahlen als praktische Datenquelle zu Demonstrationszwecken verwendet. Die gleichen Konzepte gelten jedoch auch für andere Datenquellen.  
  
> [!NOTE]
> Vergewissern Sie sich, dass auf der [Seite Kompilieren der Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)die **Option ableiten** **auf on**festgelegt ist.  
  
 [!code-vb[VbLINQFirstQuery#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#1)]  
  
 Ausgabe:  
  
 `0 2 4 6`  
  
## <a name="the-data-source"></a>Die Datenquelle  
 Da es sich bei der Datenquelle im vorherigen Beispiel um ein Array handelt, unterstützt Sie implizit die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle. Diese Tatsache ermöglicht es Ihnen, ein Array als Datenquelle für eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage zu verwenden. Typen, die <xref:System.Collections.Generic.IEnumerable%601> unterstützen oder eine abgeleitete Schnittstelle, wie z.B. der generische Typ <xref:System.Linq.IQueryable%601>, werden als *abfragbare Typen* bezeichnet.  
  
 Als implizit abfragbarer Typ erfordert das Array keine Änderung oder besondere Behandlung, damit es als [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Datenquelle fungiert. Das gleiche gilt für jeden Sammlungstyp, der <xref:System.Collections.Generic.IEnumerable%601>unterstützt, einschließlich der generischen <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602>und anderer Klassen in der .NET Framework-Klassenbibliothek.  
  
 Wenn die Quelldaten nicht bereits <xref:System.Collections.Generic.IEnumerable%601>implementieren, wird ein [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Anbieter benötigt, um die Funktionalität der *Standard Abfrage Operatoren* für diese Datenquelle zu implementieren. Beispielsweise verarbeitet [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] das Laden eines XML-Dokuments in einen abfragbaren <xref:System.Xml.Linq.XElement> Typ, wie im folgenden Beispiel gezeigt. Weitere Informationen zu Standard Abfrage Operatoren finden Sie unter [Übersicht über Standard Abfrage Operatoren (Visual Basic)](standard-query-operators-overview.md).  
  
 [!code-vb[VbLINQFirstQuery#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#2)]  
  
 Mit [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]erstellen Sie zuerst eine Objekt relationale Zuordnung zur Entwurfszeit, entweder manuell oder mithilfe der [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) in Visual Studio. Sie schreiben die Abfragen anhand der Objekte, und zur Laufzeit übernimmt [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] die Kommunikation mit der Datenbank. Im folgenden Beispiel stellt `customers` eine bestimmte Tabelle in der Datenbank dar, und <xref:System.Data.Linq.Table%601> unterstützt generische <xref:System.Linq.IQueryable%601>.  
  
```vb  
' Create a data source from a SQL table.  
Dim db As New DataContext("C:\Northwind\Northwnd.mdf")  
Dim customers As Table(Of Customer) = db.GetTable(Of Customer)  
```  
  
 Weitere Informationen zum Erstellen bestimmter Typen von Datenquellen finden Sie in der Dokumentation der verschiedenen [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Anbieter. (Eine Liste dieser Anbieter finden Sie unter [LINQ (Language-Integrated Query, sprach integrierte Abfrage)](../../../../visual-basic/programming-guide/concepts/linq/index.md).) Die grundlegende Regel ist einfach: eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Datenquelle ist jedes Objekt, das die generische <xref:System.Collections.Generic.IEnumerable%601> Schnittstelle unterstützt, oder eine Schnittstelle, die von ihr erbt.  
  
> [!NOTE]
> Typen wie <xref:System.Collections.ArrayList>, die die nicht generische <xref:System.Collections.IEnumerable> Schnittstelle unterstützen, können auch als [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Datenquellen verwendet werden. Ein Beispiel für die Verwendung einer <xref:System.Collections.ArrayList>finden Sie unter Gewusst [wie: Abfragen einer ArrayList mit LINQ (Visual Basic)](how-to-query-an-arraylist-with-linq.md).  
  
## <a name="the-query"></a>Die Abfrage  
 In der Abfrage geben Sie an, welche Informationen aus der Datenquelle oder den Quellen abgerufen werden sollen. Sie haben auch die Möglichkeit anzugeben, wie diese Informationen sortiert, gruppiert oder strukturiert werden sollen, bevor Sie zurückgegeben werden. Um die Abfrage Erstellung zu aktivieren, hat Visual Basic neue Abfrage Syntax in die Sprache integriert.  
  
 Wenn die Abfrage im folgenden Beispiel ausgeführt wird, gibt Sie alle geraden Zahlen aus einem ganzzahligen Array zurück, `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#1)]  
  
 Der Abfrage Ausdruck enthält drei Klauseln: `From`, `Where`und `Select`. Die jeweilige Funktion und der Zweck der einzelnen Abfrage Ausdrucks Klauseln wird in [grundlegenden Abfrage Vorgängen (Visual Basic)](basic-query-operations.md)erläutert. Weitere Informationen finden Sie unter [Abfragen](../../../../visual-basic/language-reference/queries/index.md). Beachten Sie, dass in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]häufig eine Abfrage Definition in einer Variablen gespeichert und später ausgeführt wird. Die Abfrage Variable, wie z. b. `evensQuery` im vorherigen Beispiel, muss ein abfragbarer Typ sein. Der Typ der `evensQuery` ist `IEnumerable(Of Integer)`, der vom Compiler mithilfe des lokalen Typrückschlusses zugewiesen wird.  
  
 Beachten Sie, dass die Abfrage Variable selbst keine Aktion durchführt und keine Daten zurückgibt. Die Abfrage Definition wird nur gespeichert. Im vorherigen Beispiel handelt es sich um die `For Each`-Schleife, die die Abfrage ausführt.  
  
## <a name="query-execution"></a>Abfrageausführung  
 Die Abfrage Ausführung ist von der Abfrage Erstellung getrennt. Beim Erstellen der Abfrage wird die Abfrage definiert, aber die Ausführung wird durch einen anderen Mechanismus ausgelöst. Eine Abfrage kann ausgeführt werden, sobald Sie definiert ist (*sofortige Ausführung*), oder die Definition kann gespeichert werden, und die Abfrage kann später ausgeführt werden (*verzögerte Ausführung*).  
  
### <a name="deferred-execution"></a>Verzögerte Ausführung  
 Eine typische [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage ähnelt der im vorherigen Beispiel, in dem `evensQuery` definiert ist. Die Abfrage wird erstellt, aber nicht sofort ausgeführt. Stattdessen wird die Abfrage Definition in der Abfrage Variablen `evensQuery`gespeichert. Sie führen die Abfrage später aus, in der Regel mit einer `For Each`-Schleife, die eine Sequenz von Werten zurückgibt, oder durch Anwenden eines Standard Abfrage Operators (z. b. `Count` oder `Max`). Dieser Prozess wird als *verzögerte Ausführung*bezeichnet.  
  
 [!code-vb[VbLINQFirstQuery#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#7)]  
  
 Für eine Sequenz von-Werten greifen Sie mithilfe der Iterations Variablen in der `For Each`-Schleife (`number` im vorherigen Beispiel) auf die abgerufenen Daten zu. Da die Abfrage Variable `evensQuery`die Abfrage Definition und nicht die Abfrageergebnisse enthält, können Sie eine Abfrage so oft wie gewünscht ausführen, indem Sie die Abfrage Variable mehrmals verwenden. Beispielsweise können Sie über eine Datenbank in der Anwendung verfügen, die fortlaufend von einer separaten Anwendung aktualisiert wird. Nachdem Sie eine Abfrage erstellt haben, mit der Daten aus dieser Datenbank abgerufen werden, können Sie eine `For Each` Schleife verwenden, um die Abfrage wiederholt auszuführen und dabei jedes Mal die neuesten Daten abzurufen.  
  
 Im folgenden Beispiel wird veranschaulicht, wie die verzögerte Ausführung funktioniert. Nachdem `evensQuery2` wie in den vorherigen Beispielen definiert und mit einer `For Each`-Schleife ausgeführt wurde, werden einige Elemente in der Datenquelle `numbers` geändert. Anschließend wird eine zweite `For Each` Schleife wieder `evensQuery2` ausgeführt. Die Ergebnisse unterscheiden sich beim zweiten Mal, da die `For Each`-Schleife die Abfrage erneut ausführt, wobei die neuen Werte in `numbers`verwendet werden.  
  
 [!code-vb[VbLINQFirstQuery#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#3)]  
  
 Ausgabe:  
  
 `Evens in original array:`  
  
 `0  2  4  6`  
  
 `Evens in changed array:`  
  
 `0  10  2  22  8`  
  
### <a name="immediate-execution"></a>Sofortige Ausführung  
 Bei der verzögerten Ausführung von Abfragen wird die Abfrage Definition zur späteren Ausführung in einer Abfrage Variablen gespeichert. Bei sofortiger Ausführung wird die Abfrage zum Zeitpunkt der Definition ausgeführt. Die Ausführung wird ausgelöst, wenn Sie eine Methode anwenden, die Zugriff auf einzelne Elemente des Abfrage Ergebnisses erfordert. Die sofortige Ausführung wird häufig erzwungen, indem einer der Standard Abfrage Operatoren verwendet wird, die einzelne Werte zurückgeben. Beispiele sind `Count`, `Max`, `Average`und `First`. Diese Standard Abfrage Operatoren führen die Abfrage aus, sobald Sie angewendet werden, um ein Singleton-Ergebnis zu berechnen und zurückzugeben. Weitere Informationen zu Standard Abfrage Operatoren, die einzelne Werte zurückgeben, finden Sie unter [Aggregations Vorgänge](aggregation-operations.md), [Element Vorgänge](element-operations.md)und [Quantifizierer-Vorgänge](quantifier-operations.md).  
  
 Die folgende Abfrage gibt die Anzahl der geraden Zahlen in einem Array von ganzen Zahlen zurück. Die Abfrage Definition wird nicht gespeichert, und `numEvens` ist eine einfache `Integer`.  
  
 [!code-vb[VbLINQFirstQuery#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#4)]  
  
 Sie können das gleiche Ergebnis erzielen, indem Sie die `Aggregate`-Methode verwenden.  
  
 [!code-vb[VbLINQFirstQuery#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#5)]  
  
 Sie können auch die Ausführung einer Abfrage erzwingen, indem Sie die `ToList` oder `ToArray`-Methode für eine Abfrage (unmittelbar) oder eine Abfrage Variable (verzögert) aufrufen, wie im folgenden Code gezeigt.  
  
 [!code-vb[VbLINQFirstQuery#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#6)]  
  
 In den vorherigen Beispielen ist `evensQuery3` eine Abfrage Variable, aber `evensList` ist eine Liste, und `evensArray` ist ein Array.  
  
 Die Verwendung von `ToList` oder `ToArray`, um eine sofortige Ausführung zu erzwingen, ist besonders nützlich in Szenarien, in denen die Abfrage sofort ausgeführt und die Ergebnisse in einem einzelnen Auflistungs Objekt zwischengespeichert werden sollen. Weitere Informationen zu diesen Methoden finden Sie unter " [wandeln von Datentypen](converting-data-types.md)".  
  
 Sie können auch bewirken, dass eine Abfrage mit einer `IEnumerable` Methode ausgeführt wird, z. b. mit der <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A>-Methode.  
  
## <a name="see-also"></a>Siehe auch

- [Getting Started with LINQ in Visual Basic (Erste Schritte mit LINQ in Visual Basic)](getting-started-with-linq.md)
- [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](standard-query-operators-overview.md)
- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Abfragen](../../../../visual-basic/language-reference/queries/index.md)
