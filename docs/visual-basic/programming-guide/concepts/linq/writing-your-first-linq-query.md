---
title: Schreiben der ersten LINQ-Abfrage (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ queries [Visual Basic]
- LINQ [Visual Basic], writing queries
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
caps.latest.revision: 56
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 48f1c5e15654580b6e4d060860a0d7001af5e2ef
ms.lasthandoff: 03/13/2017

---
# <a name="writing-your-first-linq-query-visual-basic"></a>Schreiben der ersten LINQ-Abfrage (Visual Basic)
Ein *Abfrage* ist ein Ausdruck, der Daten aus einer Datenquelle abruft. Abfragen werden in einer dedizierten Abfragesprache ausgedrückt. Im Laufe der Zeit wurden verschiedene Sprachen für verschiedene Arten von Datenquellen, beispielsweise SQL für relationale Datenbanken und XQuery für XML entwickelt. Dies macht es für den Entwickler der Anwendung für jeden Typ von Datenquelle oder Datenformat, das unterstützt wird eine neue Abfragesprache erlernen.  
  
 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]vereinfacht diese Situation durch die Bereitstellung eines konsistenten Modells zum Arbeiten mit Daten in verschiedenen Arten von Datenquellen und Formaten. In einer [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfrage arbeiten Sie immer mit Objekten. Sie verwenden dieselben grundlegenden Codierungsmuster für Abfrage und Transformation von Daten in XML-Dokumenten, SQL-Datenbanken, ADO.NET-Datasets und Entitäten, .NET Framework-Auflistungen und alle anderen Quelle oder Format für die ein [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] -Anbieter verfügbar ist. Dieses Dokument beschreibt die drei Phasen der Erstellung und Verwendung von Basic [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfragen.  
  
## <a name="three-stages-of-a-query-operation"></a>Drei Phasen einer Abfrageoperation  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfrageoperationen bestehen aus drei Aktionen:  
  
1.  Abrufen der Datenquelle(n).  
  
2.  Erstellen der Abfrage  
  
3.  Ausführen der Abfrage  
  
 In [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], die Ausführung einer Abfrage unterscheidet sich von der Erstellung der Abfrage. Alle Daten werden nicht durch das bloße Erstellen einer Abfrageergebnis abgerufen werden. Dieser Punkt wird später in diesem Thema ausführlicher erläutert.  
  
 Das folgende Beispiel veranschaulicht die drei Teile einer Abfrageoperation. Das Beispiel wird ein Array von Ganzzahlen als Datenquelle für eine einfache zu Demonstrationszwecken verwendet. Dieselben Konzepte gelten jedoch auch für andere Datenquellen.  
  
> [!NOTE]
>  Auf der [Seite kompilieren, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic), sicher, dass **Option infer** Wert **auf**.  
  
 [!code-vb[VbLINQFirstQuery&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 Ausgabe:  
  
 `0 2 4 6`  
  
## <a name="the-data-source"></a>Die Datenquelle  
 Da die Datenquelle im vorherigen Beispiel ein Array ist, unterstützt sie implizit die generische <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle.</xref:System.Collections.Generic.IEnumerable%601> Dadurch kann die Möglichkeit, ein Array als Datenquelle für die Verwendung einer [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfrage. Typen, die unterstützen <xref:System.Collections.Generic.IEnumerable%601>oder eine abgeleitete Schnittstelle, wie z. B. die generische <xref:System.Linq.IQueryable%601>heißen *abfragbare Typen*.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601>  
  
 Als ein abfragbarer Typ, Arrays erfordert keine Änderung oder besondere Behandlung notwendig, um als eine [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] -Datenquelle. Das gleiche gilt für alle Auflistungstypen, die unterstützt <xref:System.Collections.Generic.IEnumerable%601>, einschließlich des generischen <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602>, und andere Klassen in der .NET Framework-Klassenbibliothek.</xref:System.Collections.Generic.Dictionary%602> </xref:System.Collections.Generic.List%601> </xref:System.Collections.Generic.IEnumerable%601>  
  
 Wenn die Quelldaten nicht bereits implementiert <xref:System.Collections.Generic.IEnumerable%601>, [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Anbieter ist erforderlich, um die Funktionalität implementieren der *Standardabfrageoperatoren* für diese Datenquelle.</xref:System.Collections.Generic.IEnumerable%601> Beispielsweise [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] übernimmt die Aufgabe Laden ein XML-Dokument in einen abfragbaren <xref:System.Xml.Linq.XElement>eingeben, wie im folgenden Beispiel gezeigt.</xref:System.Xml.Linq.XElement> Weitere Informationen über Standardabfrageoperatoren finden Sie unter [Standard Query Operators Overview (Visual Basic)](standard-query-operators-overview.md).  
  
 [!code-vb[VbLINQFirstQuery&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_2.vb)]  
  
 Mit [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], Sie erstellen eine objektrelationale Zuordnung zur Entwurfszeit, entweder manuell oder mithilfe der [LINQ to SQL-Tools in Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) in Visual Studio. Sie schreiben die Abfragen anhand der Objekte, und zur Laufzeit übernimmt [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] die Kommunikation mit der Datenbank. Im folgenden Beispiel `customers` stellt eine bestimmte Tabelle in der Datenbank und <xref:System.Data.Linq.Table%601>unterstützt generische <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Data.Linq.Table%601>  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Weitere Informationen zum Erstellen bestimmter Typen von Datenquellen finden Sie in der Dokumentation der verschiedenen [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Anbieter. (Eine Liste dieser Anbieter finden Sie unter [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).) Die Grundregel ist einfach: eine [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] -Datenquelle ist jedes Objekt, das die generische <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle oder eine Schnittstelle, die aus dem Array erbt,</xref:System.Collections.Generic.IEnumerable%601> unterstützt  
  
> [!NOTE]
>  Typen wie <xref:System.Collections.ArrayList>, die nicht generische unterstützen <xref:System.Collections.IEnumerable>Schnittstelle kann auch verwendet werden, als [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Datenquellen.</xref:System.Collections.IEnumerable> </xref:System.Collections.ArrayList> Ein Beispiel für die Verwendung einer <xref:System.Collections.ArrayList>, finden Sie unter [Gewusst wie: Abfragen von ArrayList mit LINQ (Visual Basic)](how-to-query-an-arraylist-with-linq.md).</xref:System.Collections.ArrayList>  
  
## <a name="the-query"></a>Die Abfrage  
 In der Abfrage geben Sie die Informationen aus der Datenquelle oder den Datenquellen abgerufen werden sollen. Sie können angeben, wie diese Informationen sollten werden sortiert, gruppiert oder strukturiert werden, bevor er zurückgegeben wird. Um die Abfrage erstellt werden kann, hat Visual Basic neue Abfragesyntax in die Sprache integriert.  
  
 Wenn es ausgeführt wird, gibt die Abfrage im folgenden Beispiel alle geraden Zahlen aus einem Ganzzahlen-Array `numbers`.  
  
 [!code-vb[VbLINQFirstQuery&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 Der Abfrageausdruck enthält drei Klauseln: `From`, `Where`, und `Select`. Die spezielle Funktion und der Zweck jeder behandelt [Grundlegende Abfrageoperationen (Visual Basic)](basic-query-operations.md). Weitere Informationen finden Sie unter [Abfragen](../../../../visual-basic/language-reference/queries/queries.md). Beachten Sie, dass in [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], eine Abfragedefinition häufig in einer Variablen gespeichert und später ausgeführt. Die Abfrage Variablen, wie z. B. `evensQuery` im vorherigen Beispiel, muss ein abfragbarer Typ sein. Der Typ des `evensQuery` ist `IEnumerable(Of Integer)`, durch den Compiler, die unter Verwendung des lokalen Typrückschlusses zugewiesen.  
  
 Es ist wichtig zu beachten, dass die Abfragevariable selbst keine Aktion ausführt und keine Daten zurückgibt. Sie speichert nur die Abfragedefinition. Im vorherigen Beispiel ist die `For Each` -Schleife, die die Abfrage ausgeführt wird.  
  
## <a name="query-execution"></a>Abfrageausführung  
 Ausführung einer Abfrage ist getrennt von der Erstellung der Abfrage. Erstellung der Abfrage die Abfrage definiert, aber die Abfrage wird mit einem anderen Mechanismus ausgelöst. Eine Abfrage kann ausgeführt werden, sobald sie definiert ist (*unmittelbare Ausführung*), oder die Definition kann gespeichert und die Abfrage kann später ausgeführt werden (*verzögerte Ausführung*).  
  
### <a name="deferred-execution"></a>Verzögerte Ausführung  
 Ein herkömmliches [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfrage ähnelt dem im vorherigen Beispiel, in dem `evensQuery` definiert ist. Er erstellt die Abfrage jedoch nicht sofort ausgeführt. Stattdessen wird die Abfragedefinition in der Abfragevariablen gespeichert `evensQuery`. Die Abfrage wird später ausgeführt, in der Regel durch die Verwendung einer `For Each` -Schleife, die eine Sequenz von Werten oder durch Anwenden von Standardabfrageoperator, wie z. B. zurückgibt `Count` oder `Max`. Dieser Prozess wird als bezeichnet *verzögerte Ausführung*.  
  
 [!code-vb[VbLINQFirstQuery&#7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_3.vb)]  
  
 Für eine Sequenz von Werten, greifen Sie die abgerufenen Daten unter Verwendung der Iterationsvariablen in der `For Each` Schleife (`number` im vorherigen Beispiel). Da die Abfragevariable `evensQuery`, enthält die Ergebnisse der Abfrage, anstatt die Abfragedefinition können Sie die Abfrage so oft wie gewünscht mithilfe der Abfragevariablen mehr als einmal ausführen. Beispielsweise müssen Sie eine Datenbank in Ihrer Anwendung möglicherweise, die ständig durch eine separate Anwendung aktualisiert wird. Nachdem Sie eine Abfrage, die Daten aus dieser Datenbank abruft erstellt haben, können Sie mithilfe einer `For Each` Schleife wiederholt wird, führen Sie die Abfrage zum Abrufen der neuesten Daten jedes Mal.  
  
 Im folgende Beispiel wird veranschaulicht, wie die verzögerte Ausführung arbeitet. Nach `evensQuery2` definiert und ausgeführt werden, ein `For Each` wie in den vorherigen Beispielen werden einige Elemente in der Datenquelle Schleife `numbers` geändert werden. Klicken Sie dann ein zweites `For Each` Schleife ausgeführt wird `evensQuery2` erneut. Die Ergebnisse unterscheiden sich das zweite Mal, da die `For Each` Schleife führt die Abfrage erneut mit den neuen Werten in `numbers`.  
  
 [!code-vb[VbLINQFirstQuery&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_4.vb)]  
  
 Ausgabe:  
  
 `Evens in original array:`  
  
 `0  2  4  6`  
  
 `Evens in changed array:`  
  
 `0  10  2  22  8`  
  
### <a name="immediate-execution"></a>Sofortige Ausführung  
 Bei der verzögerten Ausführung von Abfragen wird die Abfragedefinition in einer Abfragevariablen zur späteren Ausführung gespeichert. Bei der unmittelbaren Ausführung wird die Abfrage zum Zeitpunkt seiner Definition ausgeführt. Die Abfrage wird ausgelöst, wenn Sie eine Methode anwenden, die Zugriff auf einzelne Elemente des Abfrageergebnisses erforderlich ist. Unmittelbare Ausführung häufig erzwungen wird, mithilfe einer der Standardabfrageoperatoren, die einzelne Werte zurückgeben. Examples are `Count`, `Max`, `Average`, and `First`. Diese Standardabfrageoperatoren führen die Abfrage aus, sobald sie angewendet werden, um zu berechnen und ein Singleton-Ergebnis zurück. Weitere Informationen über Standardabfrageoperatoren, die einzelne Werte zurückgeben, finden Sie unter [Aggregationsvorgänge](aggregation-operations.md), [Elementvorgänge](element-operations.md), und [Quantifizierer-Vorgänge](quantifier-operations.md).  
  
 Die folgende Abfrage gibt die Anzahl der geraden Zahlen in einem Array von ganzen Zahlen zurück. Die Abfragedefinition wird nicht gespeichert, und `numEvens` ist eine einfache `Integer`.  
  
 [!code-vb[VbLINQFirstQuery&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_5.vb)]  
  
 Sie können das gleiche Ergebnis erzielen, indem Sie mit der `Aggregate` Methode.  
  
 [!code-vb[VbLINQFirstQuery&5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_6.vb)]  
  
 Sie können die Ausführung einer Abfrage auch erzwingen, durch Aufrufen der `ToList` oder `ToArray` Methode für eine Abfrage (unmittelbar) oder eine Abfragevariable (verzögert), wie im folgenden Code gezeigt.  
  
 [!code-vb[VbLINQFirstQuery&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_7.vb)]  
  
 In den vorherigen Beispielen `evensQuery3` ist eine Variable, aber `evensList` ist eine Liste und `evensArray` ist ein Array.  
  
 Mithilfe von `ToList` oder `ToArray` sofortige erzwingen Ausführung ist besonders nützlich in Szenarien, in denen die Abfrage sofort ausführen und die Ergebnisse in einem einzelnen Auflistungsobjekt zwischengespeichert werden soll. Weitere Informationen zu diesen Methoden finden Sie unter [Datentypen konvertieren](converting-data-types.md).  
  
 Kann auch eine Abfrage mithilfe von ausgeführt werden ein `IEnumerable` Methode, z. B. die <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A>-Methode.</xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A>  
  
## <a name="see-also"></a>Siehe auch  
 [Erste Schritte mit LINQ in Visual Basic](getting-started-with-linq.md)   
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Standard Query Operators Overview (Visual Basic)](standard-query-operators-overview.md)   
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Abfragen](../../../../visual-basic/language-reference/queries/queries.md)
