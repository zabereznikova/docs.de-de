---
title: Schreiben der ersten LINQ-Abfrage (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ queries [Visual Basic]
- LINQ [Visual Basic], writing queries
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
ms.openlocfilehash: 5c83d888f65ce5c216327e94c5d4d1267fb93c29
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951999"
---
# <a name="writing-your-first-linq-query-visual-basic"></a>Schreiben der ersten LINQ-Abfrage (Visual Basic)
Eine *Abfrage* ist ein Ausdruck, der Daten von einer Datenquelle abruft. Abfragen werden in einer dedizierten Abfragesprache ausgedrückt. Im Laufe der Zeit wurden verschiedene Sprachen für verschiedene Arten von Datenquellen entwickelt, beispielsweise SQL für relationale Datenbanken und XQuery für XML. Dadurch muss der Anwendungsentwickler für jeden unterstützten Typ von Datenquelle oder Datenformat eine neue Abfragesprache erlernen.  
  
 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]vereinfacht die Situation durch Bereitstellung eines konsistenten Modells zum Arbeiten mit Daten in verschiedenen Arten von Datenquellen und Formaten. In einer [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrage arbeiten Sie immer mit Objekten. Sie verwenden dieselben grundlegenden Codierungs Muster zum Abfragen und Transformieren von Daten in XML-Dokumenten, SQL-Datenbanken, ADO.NET Datasets und Entitäten, .NET Framework Auflistungen und anderen [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Quellen oder Formaten, für die ein Anbieter verfügbar ist. In diesem Dokument werden die drei Phasen der Erstellung und Verwendung von Grund [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Legenden Abfragen beschrieben.  
  
## <a name="three-stages-of-a-query-operation"></a>Drei Phasen eines Abfrage Vorgangs  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]Abfrage Vorgänge bestehen aus drei Aktionen:  
  
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
 Da es sich bei der Datenquelle im vorherigen Beispiel um ein Array handelt, unterstützt <xref:System.Collections.Generic.IEnumerable%601> Sie implizit die generische-Schnittstelle. Diese Tatsache ermöglicht es Ihnen, ein Array als Datenquelle für eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage zu verwenden. Typen, die <xref:System.Collections.Generic.IEnumerable%601> unterstützen oder eine abgeleitete Schnittstelle, wie z.B. der generische Typ <xref:System.Linq.IQueryable%601>, werden als *abfragbare Typen* bezeichnet.  
  
 Als implizit abfragbarer Typ erfordert das Array keine Änderung oder besondere Behandlung als [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Datenquelle. Das gleiche gilt für jeden Auflistungstyp, <xref:System.Collections.Generic.IEnumerable%601>der unterstützt, <xref:System.Collections.Generic.List%601>einschließlich <xref:System.Collections.Generic.Dictionary%602>der generischen,-und anderen Klassen in der .NET Framework-Klassenbibliothek.  
  
 Wenn die Quelldaten nicht bereits implementiert <xref:System.Collections.Generic.IEnumerable%601>sind, ist ein [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Anbieter erforderlich, um die Funktionalität der *Standard Abfrage Operatoren* für diese Datenquelle zu implementieren. Beispielsweise [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] verarbeitet das Laden eines XML-Dokuments in einen <xref:System.Xml.Linq.XElement> abfragbaren Typ, wie im folgenden Beispiel gezeigt. Weitere Informationen zu Standard Abfrage Operatoren finden Sie unter [Übersicht über Standard Abfrage Operatoren (Visual Basic)](standard-query-operators-overview.md).  
  
 [!code-vb[VbLINQFirstQuery#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#2)]  
  
 Mit [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]erstellen Sie zuerst eine Objekt relationale Zuordnung zur Entwurfszeit, entweder manuell oder mithilfe der [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) in Visual Studio. Sie schreiben die Abfragen anhand der Objekte, und zur Laufzeit übernimmt [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] die Kommunikation mit der Datenbank. Im folgenden Beispiel `customers` stellt eine bestimmte Tabelle in der Datenbank dar und <xref:System.Data.Linq.Table%601> unterstützt generisch <xref:System.Linq.IQueryable%601>.  
  
```vb  
' Create a data source from a SQL table.  
Dim db As New DataContext("C:\Northwind\Northwnd.mdf")  
Dim customers As Table(Of Customer) = db.GetTable(Of Customer)  
```  
  
 Weitere Informationen zum Erstellen bestimmter Typen von Datenquellen finden Sie in der Dokumentation der verschiedenen [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Anbieter. (Eine Liste dieser Anbieter finden Sie unter [LINQ (Language-Integrated Query, sprach integrierte Abfrage)](../../../../visual-basic/programming-guide/concepts/linq/index.md).) Die grundlegende Regel ist einfach: [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] eine Datenquelle ist ein beliebiges Objekt, <xref:System.Collections.Generic.IEnumerable%601> das die generische-Schnittstelle unterstützt, oder eine Schnittstelle, die von ihr erbt.  
  
> [!NOTE]
> Typen wie <xref:System.Collections.ArrayList> , die die nicht generische <xref:System.Collections.IEnumerable> -Schnittstelle unterstützen, können auch [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] als Datenquellen verwendet werden. Ein Beispiel für die Verwendung <xref:System.Collections.ArrayList>von finden [Sie unter Gewusst wie: Abfragen einer ArrayList mit LINQ (Visual Basic)](how-to-query-an-arraylist-with-linq.md).  
  
## <a name="the-query"></a>Die Abfrage  
 In der Abfrage geben Sie an, welche Informationen aus der Datenquelle oder den Quellen abgerufen werden sollen. Sie haben auch die Möglichkeit anzugeben, wie diese Informationen sortiert, gruppiert oder strukturiert werden sollen, bevor Sie zurückgegeben werden. Um die Abfrage Erstellung zu aktivieren, hat Visual Basic neue Abfrage Syntax in die Sprache integriert.  
  
 Wenn die Abfrage ausgeführt wird, gibt die Abfrage im folgenden Beispiel alle geraden Zahlen aus einem ganzzahligen Array `numbers`zurück.  
  
 [!code-vb[VbLINQFirstQuery#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#1)]  
  
 Der Abfrage Ausdruck enthält drei Klauseln: `From`, `Where`und `Select`. Die jeweilige Funktion und der Zweck der einzelnen Abfrage Ausdrucks Klauseln wird in [grundlegenden Abfrage Vorgängen (Visual Basic)](basic-query-operations.md)erläutert. Weitere Informationen finden Sie unter [Abfragen](../../../../visual-basic/language-reference/queries/index.md). Beachten Sie, [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]dass eine Abfrage Definition in häufig in einer Variablen gespeichert und später ausgeführt wird. Die Abfrage Variable (z `evensQuery` . b. im vorherigen Beispiel) muss ein abfragbarer Typ sein. Der Typ von `evensQuery` ist `IEnumerable(Of Integer)`, der vom Compiler mithilfe von lokalem Typrückschluss zugewiesen wird.  
  
 Beachten Sie, dass die Abfrage Variable selbst keine Aktion durchführt und keine Daten zurückgibt. Die Abfrage Definition wird nur gespeichert. Im vorherigen Beispiel ist dies die `For Each` Schleife, die die Abfrage ausführt.  
  
## <a name="query-execution"></a>Abfrageausführung  
 Die Abfrage Ausführung ist von der Abfrage Erstellung getrennt. Beim Erstellen der Abfrage wird die Abfrage definiert, aber die Ausführung wird durch einen anderen Mechanismus ausgelöst. Eine Abfrage kann ausgeführt werden, sobald Sie definiert ist (*sofortige Ausführung*), oder die Definition kann gespeichert werden, und die Abfrage kann später ausgeführt werden (*verzögerte Ausführung*).  
  
### <a name="deferred-execution"></a>Verzögerte Ausführung  
 Eine typische [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage ähnelt der im vorherigen Beispiel, in der `evensQuery` definiert ist. Die Abfrage wird erstellt, aber nicht sofort ausgeführt. Stattdessen wird die Abfrage Definition in der Abfrage Variablen `evensQuery`gespeichert. Sie führen die Abfrage später aus, in der Regel `For Each` mit einer-Schleife, die eine Sequenz von-Werten zurückgibt, oder durch Anwenden eines Standard `Count` Abfrage `Max`Operators, z. b. oder. Dieser Prozess wird als *verzögerte Ausführung*bezeichnet.  
  
 [!code-vb[VbLINQFirstQuery#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#7)]  
  
 Für eine Sequenz von-Werten greifen Sie auf die abgerufenen Daten zu, indem Sie die Iterations Variable`number` in der `For Each` -Schleife verwenden (im vorherigen Beispiel). Da die Abfrage Variable `evensQuery`,, die Abfrage Definition und nicht die Abfrageergebnisse enthält, können Sie eine Abfrage so oft wie gewünscht ausführen, indem Sie die Abfrage Variable mehrmals verwenden. Beispielsweise können Sie über eine Datenbank in der Anwendung verfügen, die fortlaufend von einer separaten Anwendung aktualisiert wird. Nachdem Sie eine Abfrage erstellt haben, mit der Daten aus dieser Datenbank abgerufen werden, können Sie `For Each` eine Schleife verwenden, um die Abfrage wiederholt auszuführen und dabei jedes Mal die neuesten Daten abzurufen.  
  
 Im folgenden Beispiel wird veranschaulicht, wie die verzögerte Ausführung funktioniert. Nachdem `evensQuery2` definiert und mit einer `For Each` -Schleife ausgeführt wurde, wie in den vorherigen Beispielen, werden einige Elemente in der `numbers` Datenquelle geändert. Anschließend wird eine `For Each` zweite `evensQuery2` Schleife erneut ausgeführt. Die Ergebnisse unterscheiden sich beim zweiten Mal, da `For Each` die-Schleife die Abfrage erneut ausführt, wobei die neuen `numbers`Werte in verwendet werden.  
  
 [!code-vb[VbLINQFirstQuery#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#3)]  
  
 Ausgabe:  
  
 `Evens in original array:`  
  
 `0  2  4  6`  
  
 `Evens in changed array:`  
  
 `0  10  2  22  8`  
  
### <a name="immediate-execution"></a>Sofortige Ausführung  
 Bei der verzögerten Ausführung von Abfragen wird die Abfrage Definition zur späteren Ausführung in einer Abfrage Variablen gespeichert. Bei sofortiger Ausführung wird die Abfrage zum Zeitpunkt der Definition ausgeführt. Die Ausführung wird ausgelöst, wenn Sie eine Methode anwenden, die Zugriff auf einzelne Elemente des Abfrage Ergebnisses erfordert. Die sofortige Ausführung wird häufig erzwungen, indem einer der Standard Abfrage Operatoren verwendet wird, die einzelne Werte zurückgeben. Beispiele hierfür `Count`sind `Max`, `Average`, und `First`. Diese Standard Abfrage Operatoren führen die Abfrage aus, sobald Sie angewendet werden, um ein Singleton-Ergebnis zu berechnen und zurückzugeben. Weitere Informationen zu Standard Abfrage Operatoren, die einzelne Werte zurückgeben, finden Sie unter [Aggregations Vorgänge](aggregation-operations.md), [Element Vorgänge](element-operations.md)und Quantifizierer- [Vorgänge](quantifier-operations.md).  
  
 Die folgende Abfrage gibt die Anzahl der geraden Zahlen in einem Array von ganzen Zahlen zurück. Die Abfrage Definition wird nicht gespeichert und `numEvens` ist einfach. `Integer`  
  
 [!code-vb[VbLINQFirstQuery#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#4)]  
  
 Sie können das gleiche Ergebnis erzielen, indem Sie `Aggregate` die-Methode verwenden.  
  
 [!code-vb[VbLINQFirstQuery#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#5)]  
  
 Sie können auch die Ausführung einer Abfrage erzwingen, indem Sie `ToList` die `ToArray` -Methode oder die-Methode für eine Abfrage (unmittelbar) oder eine Abfrage Variable (verzögert) aufrufen, wie im folgenden Code gezeigt.  
  
 [!code-vb[VbLINQFirstQuery#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#6)]  
  
 In den vorherigen Beispielen `evensQuery3` ist eine Abfrage Variable, aber `evensList` eine Liste und `evensArray` ist ein Array.  
  
 Die `ToList` Verwendung `ToArray` von oder, um die sofortige Ausführung zu erzwingen, ist besonders nützlich in Szenarien, in denen die Abfrage sofort ausgeführt und die Ergebnisse in einem einzelnen Auflistungs Objekt zwischengespeichert werden sollen. Weitere Informationen zu diesen Methoden finden Sie unter " [wandeln von Datentypen](converting-data-types.md)".  
  
 Sie können auch bewirken, dass eine Abfrage mit einer `IEnumerable` -Methode wie der <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A> -Methode ausgeführt wird.  
  
## <a name="see-also"></a>Siehe auch

- [Getting Started with LINQ in Visual Basic (Erste Schritte mit LINQ in Visual Basic)](getting-started-with-linq.md)
- [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](standard-query-operators-overview.md)
- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Abfragen](../../../../visual-basic/language-reference/queries/index.md)
