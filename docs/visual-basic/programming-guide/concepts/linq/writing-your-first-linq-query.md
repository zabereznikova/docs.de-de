---
title: Schreiben der ersten LINQ-Abfrage (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ queries [Visual Basic]
- LINQ [Visual Basic], writing queries
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
caps.latest.revision: "56"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c16bb28189d5525654328da2dc80d868bbe61bf5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="writing-your-first-linq-query-visual-basic"></a>Schreiben der ersten LINQ-Abfrage (Visual Basic)
Eine *Abfrage* ist ein Ausdruck, der Daten von einer Datenquelle abruft. Abfragen werden in einer dedizierten Abfragesprache ausgedrückt. Im Laufe der Zeit wurden verschiedene Sprachen für verschiedene Arten von Datenquellen, beispielsweise SQL für relationale Datenbanken und XQuery für XML entwickelt. Dadurch erforderlich, damit Anwendungsentwickler für jeden Typ von Datenquelle oder Datenformat, das unterstützt wird, wird eine neue Abfragesprache lernen.  
  
 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]vereinfacht diese Situation durch die Bereitstellung eines konsistenten Modells zum Arbeiten mit Daten in verschiedenen Arten von Datenquellen und Formaten. In einer [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrage arbeiten Sie immer mit Objekten. Sie verwenden dieselben grundlegenden Codierungsmuster für Abfrage und Transformation von Daten in XML-Dokumenten, SQL-Datenbanken, ADO.NET-Datasets und Entitäten, .NET Framework-Auflistungen und alle anderen Quelle oder Format für die eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] -Anbieter verfügbar ist. Dieses Dokument beschreibt die drei Phasen der Erstellung und Verwendung von Basic [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfragen.  
  
## <a name="three-stages-of-a-query-operation"></a>Drei Phasen einer Abfrageoperation  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrageoperationen bestehen aus drei Aktionen:  
  
1.  Abrufen der Datenquelle(n).  
  
2.  Erstellen der Abfrage  
  
3.  Ausführen der Abfrage  
  
 In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], die Ausführung einer Abfrage unterscheidet sich von der Erstellung der Abfrage. Durch das bloße Erstellen einer Abfrage werden keine Daten abgerufen werden. Dieser Punkt wird in diesem Thema an späterer Stelle ausführlicher behandelt.  
  
 Das folgende Beispiel veranschaulicht die drei Teile einer Abfrageoperation. Das Beispiel wird ein Array von Ganzzahlen als praktische Datenquelle zu Demonstrationszwecken verwendet. Dieselben Konzepte gelten jedoch auch für andere Datenquellen.  
  
> [!NOTE]
>  Auf der [Seite kompilieren, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), sicher, dass **Option infer** festgelegt ist, um **auf**.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 Ausgabe:  
  
 `0 2 4 6`  
  
## <a name="the-data-source"></a>Die Datenquelle  
 Da die Datenquelle im vorherigen Beispiel ein Array ist, unterstützt sie implizit die generische <xref:System.Collections.Generic.IEnumerable%601> Schnittstelle. Dadurch kann, die Ihnen ermöglicht, verwenden ein Array als Datenquelle für eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage. Typen, die <xref:System.Collections.Generic.IEnumerable%601> unterstützen oder eine abgeleitete Schnittstelle, wie z.B. der generische Typ <xref:System.Linq.IQueryable%601>, werden als *abfragbare Typen* bezeichnet.  
  
 Als abfragbarer Typ, Arrays erfordert keine Änderung oder besondere Behandlung, die als dient eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] -Datenquelle. Dasselbe gilt für alle Auflistungstypen, die unterstützt <xref:System.Collections.Generic.IEnumerable%601>, einschließlich den generischen <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602>, und andere Klassen in der .NET Framework-Klassenbibliothek.  
  
 Wenn die Quelldaten nicht bereits implementiert <xref:System.Collections.Generic.IEnumerable%601>, [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Anbieter ist erforderlich, um die Funktionalität eines implementieren die *Standardabfrageoperatoren* für diese Datenquelle. Beispielsweise [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] behandelt die Arbeit des Ladens von XML-Dokument in einen abfragbaren <xref:System.Xml.Linq.XElement> eingeben, wie im folgenden Beispiel gezeigt. Weitere Informationen zu den Standardabfrageoperatoren, finden Sie unter [Standard Übersicht über Standardabfrageoperatoren (Visual Basic)](standard-query-operators-overview.md).  
  
 [!code-vb[VbLINQFirstQuery#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_2.vb)]  
  
 Mit [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], erstellen Sie zunächst eine objektrelationalen Zuordnung zur Entwurfszeit, entweder manuell oder mithilfe der [LINQ to SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) in Visual Studio. Sie schreiben die Abfragen anhand der Objekte, und zur Laufzeit übernimmt [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] die Kommunikation mit der Datenbank. Im folgenden Beispiel `customers` stellt eine bestimmte Tabelle in der Datenbank und <xref:System.Data.Linq.Table%601> unterstützt generische <xref:System.Linq.IQueryable%601>.  
  
```vb  
' Create a data source from a SQL table.  
Dim db As New DataContext("C:\Northwind\Northwnd.mdf")  
Dim customers As Table(Of Customer) = db.GetTable(Of Customer)  
```  
  
 Weitere Informationen zum Erstellen bestimmter Typen von Datenquellen finden Sie in der Dokumentation der verschiedenen [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Anbieter. (Eine Liste dieser Anbieter finden Sie [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).) Die Grundregel ist einfach: eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Datenquelle ist jedes Objekt, das den generischen unterstützt <xref:System.Collections.Generic.IEnumerable%601> Schnittstelle oder eine Schnittstelle, die von ihr erbt.  
  
> [!NOTE]
>  Typen wie <xref:System.Collections.ArrayList> , die nicht generische unterstützen <xref:System.Collections.IEnumerable> Schnittstelle kann auch verwendet werden, als [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Datenquellen. Ein Beispiel, verwendet eine <xref:System.Collections.ArrayList>, finden Sie unter [wie: Abfragen von ArrayList mit LINQ (Visual Basic)](how-to-query-an-arraylist-with-linq.md).  
  
## <a name="the-query"></a>Die Abfrage  
 In der Abfrage geben Sie Informationen aus der Datenquelle bzw. den Datenquellen abgerufen werden sollen. Sie haben auch die Option zum angeben, wie diese Informationen sollten werden sortiert, gruppiert und strukturiert werden, bevor sie zurückgegeben werden. Visual Basic hat neue Abfragesyntax in der Sprache integriert, um die abfrageerstellung zu aktivieren.  
  
 Bei der Ausführung, die Abfrage im folgenden Beispiel gibt alle geraden Zahlen ein Array von Ganzzahlen `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 Der Abfrageausdruck enthält drei Klauseln: `From`, `Where`, und `Select`. Die spezielle Funktion und den Zweck jedes finden [Grundlegende Abfrageoperationen (Visual Basic)](basic-query-operations.md). Weitere Informationen finden Sie unter [Abfragen](../../../../visual-basic/language-reference/queries/queries.md). Beachten Sie, dass in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], eine Abfragedefinition häufig wird in einer Variablen gespeichert, und später ausgeführt. Die Abfrage Variablen, wie z. B. `evensQuery` im vorherigen Beispiel muss ein abfragbarer Typ sein. Der Typ des `evensQuery` ist `IEnumerable(Of Integer)`durch den Compiler, die unter Verwendung des lokalen Typrückschlusses zugewiesen.  
  
 Es ist wichtig zu beachten, dass die Abfragevariable selbst keine Aktion ausführt und keine Daten zurückgibt. Er speichert nur die Abfragedefinition. Im vorherigen Beispiel ist die `For Each` -Schleife, die die Abfrage ausgeführt wird.  
  
## <a name="query-execution"></a>Abfrageausführung  
 Hierbei handelt es sich um eine separate abfrageerstellung abfrageausführung. Erstellung der Abfrage definiert die Abfrage jedoch Ausführung wird durch einen anderen Mechanismus ausgelöst. Eine Abfrage kann ausgeführt werden, sobald sie definiert ist (*unmittelbare Ausführung*), oder die Definition kann gespeichert und die Abfrage kann später ausgeführt werden (*verzögerte Ausführung*).  
  
### <a name="deferred-execution"></a>Verzögerte Ausführung  
 Eine typische [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage ähnelt dem im vorherigen Beispiel, in dem `evensQuery` definiert ist. Die Abfrage erstellt, jedoch nicht sofort ausgeführt. Stattdessen wird die Abfragedefinition gespeichert, in die Abfragevariable `evensQuery`. Die Abfrage wird später ausgeführt, in der Regel mithilfe einer `For Each` -Schleife, die eine Sequenz von Werten oder durch Anwenden von Standardabfrageoperator, z. B. zurückgibt `Count` oder `Max`. Dieser Prozess wird als bezeichnet *verzögerte Ausführung*.  
  
 [!code-vb[VbLINQFirstQuery#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_3.vb)]  
  
 Für eine Sequenz von Werten, Sie die abgerufenen Daten zugreifen, durch die Verwendung der Iterationsvariablen in der `For Each` Schleife (`number` im vorherigen Beispiel). Da die Abfragevariable `evensQuery`, enthält die Ergebnisse der Abfrage, anstatt die Abfragedefinition Ausführen einer Abfrage können Sie beliebig oft mit Abfragevariablen mehr als einmal verwendet werden sollen. Beispielsweise müssen Sie eine Datenbank in der Anwendung möglicherweise, die ständig durch eine separate Anwendung aktualisiert wird. Nachdem Sie eine Abfrage, die Daten aus dieser Datenbank abruft erstellt haben, können Sie mithilfe einer `For Each` Schleife, um die Abfrage wiederholt ausführen Abrufen der neuesten Daten jedes Mal.  
  
 Im folgende Beispiel wird veranschaulicht, wie die verzögerte Ausführung funktioniert. Nach dem `evensQuery2` definiert ist und ausgeführt werden, eine `For Each` wie in den vorherigen Beispielen werden einige Elemente in der Datenquelle Schleife `numbers` geändert werden. Klicken Sie dann eine zweite `For Each` Schleife ausgeführt wird `evensQuery2` erneut aus. Die Ergebnisse unterscheiden zweiten Mal, weil die `For Each` Schleife führt die Abfrage erneut mit den neuen Werten in `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_4.vb)]  
  
 Ausgabe:  
  
 `Evens in original array:`  
  
 `0  2  4  6`  
  
 `Evens in changed array:`  
  
 `0  10  2  22  8`  
  
### <a name="immediate-execution"></a>Sofortige Ausführung  
 Die Abfragedefinition ist bei der verzögerten Ausführung von Abfragen in einer Abfragevariablen zur späteren Ausführung gespeichert. Bei der unmittelbaren Ausführung wird die Abfrage zum Zeitpunkt seiner Definition ausgeführt. Die Ausführung wird immer dann ausgelöst, wenn Sie eine Methode anwenden, die Zugriff auf einzelne Elemente des Abfrageergebnisses erforderlich ist. Sofortige Ausführung gehen häufig wird gezwungen, mithilfe einer der Standardabfrageoperatoren, die einzelne Werte zurückgeben. Beispiele sind `Count`, `Max`, `Average`, und `First`. Diese Standardabfrageoperatoren führen Sie die Abfrage, wie sie angewendet werden, um zu berechnen und ein Singleton-Ergebnis zurück. Weitere Informationen zu den Standardabfrageoperatoren, die einzelne Werte zurückgeben, finden Sie unter [Aggregationsvorgänge](aggregation-operations.md), [Elementvorgänge](element-operations.md), und [Quantifizierer-Vorgänge](quantifier-operations.md).  
  
 Die folgende Abfrage gibt die Anzahl der geraden Zahlen in einem Array von ganzen Zahlen zurück. Die Abfragedefinition wird nicht gespeichert, und `numEvens` zeigt eine einfache `Integer`.  
  
 [!code-vb[VbLINQFirstQuery#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_5.vb)]  
  
 Sie können das gleiche Ergebnis erzielen, indem die `Aggregate` Methode.  
  
 [!code-vb[VbLINQFirstQuery#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_6.vb)]  
  
 Sie können die Ausführung einer Abfrage auch erzwingen, durch Aufrufen der `ToList` oder `ToArray` Methode für eine Abfrage (unmittelbar) oder eine Abfragevariable (zurückgestellt), wie im folgenden Code gezeigt.  
  
 [!code-vb[VbLINQFirstQuery#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_7.vb)]  
  
 In den vorherigen Beispielen `evensQuery3` ist eine Abfrage Variablen, aber `evensList` ist eine Liste und `evensArray` ist ein Array.  
  
 Mit `ToList` oder `ToArray` gezwungen sofortige Ausführung ist besonders nützlich in Szenarien, in dem die Abfrage sofort ausführen und die Ergebnisse in einem einzelnen Auflistungsobjekt zwischengespeichert werden sollen. Weitere Informationen zu diesen Methoden finden Sie unter [Konvertieren von Datentypen](converting-data-types.md).  
  
 Können Sie auch dazu führen, dass eine Abfrage ausgeführt werden soll ein `IEnumerable` Methode z. B. die <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A> Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Getting Started with LINQ in Visual Basic (Erste Schritte mit LINQ in Visual Basic)](getting-started-with-linq.md)  
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](standard-query-operators-overview.md)  
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Abfragen](../../../../visual-basic/language-reference/queries/queries.md)
