---
title: Schreiben der ersten LINQ-Abfrage (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ queries [Visual Basic]
- LINQ [Visual Basic], writing queries
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
ms.openlocfilehash: 4c04c00c5392d8ba363346b06c806ec79041c439
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45597718"
---
# <a name="writing-your-first-linq-query-visual-basic"></a>Schreiben der ersten LINQ-Abfrage (Visual Basic)
Eine *Abfrage* ist ein Ausdruck, der Daten von einer Datenquelle abruft. Abfragen werden in einer dedizierten Abfragesprache ausgedrückt. Im Laufe der Zeit wurden verschiedene Sprachen für verschiedene Arten von Datenquellen, z. B. SQL für relationale Datenbanken und XQuery für XML entwickelt. Dadurch für den Entwickler der Anwendung finden Sie eine neue Abfragesprache für jeden Typ von Datenquelle oder Datenformat, das unterstützt wird.  
  
 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] vereinfacht die Situation durch Bereitstellung eines konsistenten Modells zum Arbeiten mit Daten in verschiedenen Arten von Datenquellen und Formaten. In einer [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrage arbeiten Sie immer mit Objekten. Sie verwenden dieselben grundlegenden Codierungsmuster zum Abfragen und Transformieren von Daten in XML-Dokumenten, SQL-Datenbanken, ADO.NET-Datasets und Entitäten, .NET Framework-Auflistungen, und alle anderen Quelle oder Format für die ein [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] -Anbieter verfügbar ist. Dieses Dokument beschreibt die drei Phasen der Erstellung und Verwendung von Basic [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfragen.  
  
## <a name="three-stages-of-a-query-operation"></a>Drei Phasen einer Abfrageoperation  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] -Abfrageoperationen bestehen aus drei Aktionen:  
  
1.  Abrufen der Datenquelle(n).  
  
2.  Erstellen der Abfrage  
  
3.  Ausführen der Abfrage  
  
 In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], die Ausführung einer Abfrage unterscheidet sich von der Erstellung der Abfrage. Sie sind alle Daten nicht abgerufen werden, indem Sie einfach eine Abfrage erstellen. Dieser Punkt wird in diesem Thema an späterer Stelle ausführlicher behandelt.  
  
 Das folgende Beispiel zeigt die drei Teile einer Abfrageoperation. Im Beispiel wird ein Array von Ganzzahlen als einfache Datenquelle, zu Demonstrationszwecken. Die gleichen Konzepte gelten jedoch auch auf andere Datenquellen.  
  
> [!NOTE]
>  Auf der [Seite "Kompilieren", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), sicher, dass **Option infer-** nastaven NA hodnotu **auf**.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 Ausgabe:  
  
 `0 2 4 6`  
  
## <a name="the-data-source"></a>Die Datenquelle  
 Da die Datenquelle im vorherigen Beispiel ein Array ist, unterstützt sie implizit die generische <xref:System.Collections.Generic.IEnumerable%601> Schnittstelle. Ist diese Tatsache, die Ihnen ermöglicht, verwenden ein Array als Datenquelle für eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage. Typen, die <xref:System.Collections.Generic.IEnumerable%601> unterstützen oder eine abgeleitete Schnittstelle, wie z.B. der generische Typ <xref:System.Linq.IQueryable%601>, werden als *abfragbare Typen* bezeichnet.  
  
 Das Array als ein abfragbarer Typ ist, erfordert, keine Änderung oder besondere Behandlung, der als dient eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] -Datenquelle. Das gleiche gilt für jeden Auflistungstyp, der unterstützt <xref:System.Collections.Generic.IEnumerable%601>, einschließlich den generischen <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602>, und andere Klassen in der .NET Framework-Klassenbibliothek.  
  
 Wenn die Quelldaten nicht bereits implementiert <xref:System.Collections.Generic.IEnumerable%601>, [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Anbieter ist erforderlich, um die Funktionalität implementieren die *Standardabfrageoperatoren* für diese Datenquelle. Z. B. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] übernimmt die Aufgabe beim Laden von XML-Dokument in einen abfragbaren <xref:System.Xml.Linq.XElement> eingeben, wie im folgenden Beispiel gezeigt. Weitere Informationen über Standardabfrageoperatoren finden Sie unter [Standard Query Operators Overview (Visual Basic)](standard-query-operators-overview.md).  
  
 [!code-vb[VbLINQFirstQuery#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_2.vb)]  
  
 Mit [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], Sie zuerst erstellen Sie eine objektrelationale Zuordnung zur Entwurfszeit, entweder manuell oder mithilfe der [LINQ to SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) in Visual Studio. Sie schreiben die Abfragen anhand der Objekte, und zur Laufzeit übernimmt [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] die Kommunikation mit der Datenbank. Im folgenden Beispiel `customers` eine bestimmte Tabelle in der Datenbank und <xref:System.Data.Linq.Table%601> unterstützt generische <xref:System.Linq.IQueryable%601>.  
  
```vb  
' Create a data source from a SQL table.  
Dim db As New DataContext("C:\Northwind\Northwnd.mdf")  
Dim customers As Table(Of Customer) = db.GetTable(Of Customer)  
```  
  
 Weitere Informationen zum Erstellen bestimmter Typen von Datenquellen finden Sie in der Dokumentation der verschiedenen [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Anbieter. (Eine Liste dieser Anbieter wird, finden Sie unter [LINQ (Language-Integrated Query)](../../../../visual-basic/programming-guide/concepts/linq/index.md).) Die Grundregel ist einfach: eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Datenquelle ist jedes Objekt, das die generische unterstützt <xref:System.Collections.Generic.IEnumerable%601> Schnittstelle oder eine Schnittstelle, die von ihr erbt.  
  
> [!NOTE]
>  Typen wie <xref:System.Collections.ArrayList> , die nicht generische unterstützen <xref:System.Collections.IEnumerable> Schnittstelle kann auch verwendet werden, als [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] -Datenquellen. Ein Beispiel für die Verwendung einer <xref:System.Collections.ArrayList>, finden Sie unter [Vorgehensweise: Abfragen von ArrayList mit LINQ (Visual Basic)](how-to-query-an-arraylist-with-linq.md).  
  
## <a name="the-query"></a>Die Abfrage  
 In der Abfrage geben Sie Informationen aus der Datenquelle oder den Datenquellen abgerufen werden sollen. Sie haben auch die Möglichkeit, anzugeben, wie diese Informationen sollten werden sortiert, gruppiert und strukturiert werden, bevor sie zurückgegeben werden. Visual Basic verfügt über neue Abfragesyntax in die Sprache integriert, um die abfrageerstellung zu aktivieren.  
  
 Wenn es ausgeführt wird, gibt die Abfrage im folgenden Beispiel alle geraden Zahlen aus ein Ganzzahlarray, `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 Der Abfrageausdruck enthält drei Klauseln: `From`, `Where`, und `Select`. Die spezielle Funktion und den Zweck der einzelnen Ausdruck Abfrageklausel ausführlicher [Grundlegende Abfrageoperationen (Visual Basic)](basic-query-operations.md). Weitere Informationen finden Sie unter [Abfragen](../../../../visual-basic/language-reference/queries/index.md). Beachten Sie, dass [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], eine Abfragedefinition häufig ist in einer Variablen gespeichert, und später ausgeführt. Die Abfrage Variablen, wie z. B. `evensQuery` im vorherigen Beispiel muss ein abfragbarer Typ sein. Der Typ des `evensQuery` ist `IEnumerable(Of Integer)`, durch den Compiler an, unter Verwendung des lokalen Typrückschlusses zugewiesen.  
  
 Es ist wichtig zu beachten, dass die Abfragevariable selbst führt keine Aktion aus, und keine Daten zurückgibt. Es speichert nur die Abfragedefinition. Im vorherigen Beispiel ist es die `For Each` Schleife, die die Abfrage ausgeführt wird.  
  
## <a name="query-execution"></a>Abfrageausführung  
 Ausführung der Abfrage ist unabhängig von der Erstellung der Abfrage. Erstellung der Abfrage definiert die Abfrage, aber die Ausführung wird durch einen anderen Mechanismus ausgelöst. Eine Abfrage ausgeführt werden kann, sobald er definiert ist (*unmittelbare Ausführung*), oder der Definition kann gespeichert und die Abfrage kann später ausgeführt werden (*verzögerte Ausführung*).  
  
### <a name="deferred-execution"></a>Verzögerte Ausführung  
 Eine typische [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage ähnelt der im vorherigen Beispiel, in dem `evensQuery` definiert ist. Er erstellt die Abfrage jedoch nicht sofort ausgeführt. Stattdessen wird die Abfragedefinition in der Abfragevariablen gespeichert `evensQuery`. Sie führen die Abfrage später in der Regel mithilfe einer `For Each` -Schleife, die eine Sequenz von Werten oder durch Anwenden von ein Standardabfrageoperator, z. B. zurückgibt `Count` oder `Max`. Dieser Prozess wird als bezeichnet *verzögerte Ausführung*.  
  
 [!code-vb[VbLINQFirstQuery#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_3.vb)]  
  
 Für eine Sequenz von Werten, greifen Sie die abgerufenen Daten durch die Verwendung der Iterationsvariablen in der `For Each` Schleife (`number` im vorherigen Beispiel). Da die Abfragevariable `evensQuery`, enthält die Definition der Abfrage anstelle der Ergebnisse der Abfrage können Sie die Abfrage so oft wie gewünscht mit Abfragevariablen mehr als einmal ausführen. Beispielsweise müssen Sie eine Datenbank in Ihrer Anwendung möglicherweise, die ständig durch eine separate Anwendung aktualisiert wird. Nachdem Sie eine Abfrage, die Daten aus dieser Datenbank abruft erstellt haben, können Sie mithilfe einer `For Each` Schleife wiederholt wird, führen Sie die Abfrage zum Abrufen der neuesten Daten jedes Mal.  
  
 Im folgende Beispiel wird veranschaulicht, wie die verzögerte Ausführung funktioniert. Nach dem `evensQuery2` definiert und ausgeführt, die mit einer `For Each` Schleife, wie in den vorherigen Beispielen, einige Elemente in der Datenquelle `numbers` geändert werden. Klicken Sie dann ein zweites `For Each` Schleife ausgeführt wird `evensQuery2` erneut aus. Die Ergebnisse unterscheiden sich bei der zweiten da die `For Each` Schleife führt die Abfrage erneut mit den neuen Werten im `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_4.vb)]  
  
 Ausgabe:  
  
 `Evens in original array:`  
  
 `0  2  4  6`  
  
 `Evens in changed array:`  
  
 `0  10  2  22  8`  
  
### <a name="immediate-execution"></a>Sofortige Ausführung  
 Bei der verzögerten Ausführung von Abfragen wird die Abfragedefinition in eine Abfragevariable zur späteren Ausführung gespeichert. Bei der unmittelbaren Ausführung wird die Abfrage zum Zeitpunkt der Definition ausgeführt. Ausführung wird ausgelöst, wenn Sie eine Methode anwenden, die Zugriff auf einzelne Elemente des Abfrageergebnisses erforderlich sind. Sofortige Ausführung häufig wird erzwungen, mithilfe einer der standardmäßigen Abfrageoperatoren, die einzelne Werte zurückgeben. Beispiele sind `Count`, `Max`, `Average`, und `First`. Diese Standardabfrageoperatoren führen die Abfrage aus, sobald sie angewendet werden, um zu berechnen und ein Singleton-Ergebnis zurück. Weitere Informationen zu den Standardabfrageoperatoren, die einzelne Werte zurückgeben, finden Sie unter [Aggregationsvorgänge](aggregation-operations.md), [Elementvorgänge](element-operations.md), und [Quantifizierer-Vorgänge](quantifier-operations.md).  
  
 Die folgende Abfrage gibt eine Anzahl von geraden Zahlen in ein Array von ganzen Zahlen zurück. Die Abfragedefinition wird nicht gespeichert, und `numEvens` ist eine einfache `Integer`.  
  
 [!code-vb[VbLINQFirstQuery#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_5.vb)]  
  
 Sie können das gleiche Ergebnis erzielen, mit der `Aggregate` Methode.  
  
 [!code-vb[VbLINQFirstQuery#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_6.vb)]  
  
 Sie können die Ausführung einer Abfrage auch erzwingen, durch den Aufruf der `ToList` oder `ToArray` Methode für eine Abfrage (unmittelbar) oder eine Abfragevariable (zurückgestellt), wie im folgenden Code gezeigt.  
  
 [!code-vb[VbLINQFirstQuery#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_7.vb)]  
  
 In den vorherigen Beispielen `evensQuery3` ist eine Abfrage Variablen, aber `evensList` ist eine Liste und `evensArray` ist ein Array.  
  
 Mithilfe von `ToList` oder `ToArray` sofortige erzwingen Ausführung ist besonders nützlich in Szenarien, in dem die Abfrage sofort ausführen und die Ergebnisse in einem einzelnen Auflistungsobjekt zwischengespeichert werden sollen. Weitere Informationen zu diesen Methoden finden Sie unter [Konvertieren von Datentypen](converting-data-types.md).  
  
 Sie können auch veranlassen, eine Abfrage ausgeführt werden soll ein `IEnumerable` Methode, z. B. die <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A> Methode.  
  
## <a name="see-also"></a>Siehe auch

- [Getting Started with LINQ in Visual Basic (Erste Schritte mit LINQ in Visual Basic)](getting-started-with-linq.md)  
- [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](standard-query-operators-overview.md)  
- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
- [Abfragen](../../../../visual-basic/language-reference/queries/index.md)
