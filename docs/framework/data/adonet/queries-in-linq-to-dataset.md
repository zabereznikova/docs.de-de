---
title: Abfragen in LINQ to DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c1a78fa8-9f0c-40bc-a372-5575a48708fe
ms.openlocfilehash: ef9334eec92ef06e5be07dae4391cdac43fed778
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33362350"
---
# <a name="queries-in-linq-to-dataset"></a>Abfragen in LINQ to DataSet
Eine Abfrage ist ein Ausdruck, der Daten von einer Datenquelle abruft. Abfragen werden in der Regel in einer speziellen Abfragesprache, wie SQL für relationale Datenbanken oder XQuery für XML, geschrieben. Deshalb mussten Entwickler bisher für jeden abzufragenden Datenquellentyp oder Datenformattyp eine neue Abfragesprache lernen. [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] bietet ein einfacheres, konsistentes Modell zum Arbeiten mit Daten über verschiedene Arten von Datenquellen und Formate hinweg. In einer [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-Abfrage arbeiten Sie immer mit Programmierobjekten.  
  
 Eine [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-Abfrageoperation besteht aus drei Aktionen: Abrufen der Datenquelle(n), Erstellen der Abfrage und Ausführen der Abfrage.  
  
 Datenquellen, die die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle implementieren, können über [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] abgefragt werden. Aufrufen von <xref:System.Data.DataTableExtensions.AsEnumerable%2A> auf eine <xref:System.Data.DataTable> gibt ein Objekt, das den generischen implementiert <xref:System.Collections.Generic.IEnumerable%601> -Schnittstelle, die als Datenquelle für dient [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfragen.  
  
 In der Abfrage geben Sie genau die Informationen an, die aus der Datenquelle abgerufen werden sollen. In der Abfrage kann auch angegeben werden, wie die Abfrageergebnisse sortiert, gruppiert und formatiert werden sollen, bevor sie zurückgegeben werden. In [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] wird eine Abfrage in einer Variablen gespeichert. Wenn die Abfrage so eingerichtet ist, dass sie eine Sequenz von Werten zurückgibt, muss die Abfragevariable selbst ein aufzählbarer Typ sein. Diese Abfragevariable führt keine Aktion aus und gibt keine Daten zurück. Sie dient lediglich zur Speicherung der Abfrageinformationen. Nachdem Sie eine Abfrage erstellt haben, müssen Sie sie ausführen, damit Daten abgerufen werden.  
  
 In einer Abfrage, die eine Sequenz von Werten zurückgibt, enthält die Abfragevariable selbst niemals die Abfrageergebnisse, sondern immer nur die Abfragebefehle. Die Ausführung der Abfrage wird verzögert, bis die Abfragevariable in einer `foreach`- oder `For Each`-Schleife durchlaufen wird. Hierbei spricht *verzögerte Ausführung*; d. h. Abfrage wird ausgeführt und einige Zeit, nachdem die Abfrage erstellt wird. Auf diese Weise können Sie die Abfrage so oft ausführen, wie Sie dies wünschen. Dies bietet sich z. B. dann an, wenn Sie eine Datenbank haben, die von anderen Anwendungen aktualisiert wird. Sie können in Ihrer Anwendung eine Abfrage erstellen, mit der die neuesten Informationen abgerufen werden, und diese Abfrage wiederholt ausführen, wobei jedes Mal die aktualisierten Informationen zurückgegeben werden.  
  
 Im Gegensatz zu zurückgestellten Abfragen, die eine Sequenz von Werten zurückgeben, werden Abfragen, die nur einen einzigen Wert zurückgeben (SINGLETON-Abfragen), sofort ausgeführt. Einige Beispiele für SINGLETON-Abfragen sind <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Average%2A> und <xref:System.Linq.Enumerable.First%2A>. Die Ausführung dieser Abfragen erfolgt sofort, weil die Abfrageergebnisse für die Berechnung des SINGLETON-Ergebnisses benötigt werden. Um z. B. den Durchschnittswert der Abfrageergebnisse zu ermitteln, muss die Abfrage so ausgeführt werden, dass die Durchschnittsberechnungsfunktion über Eingabedaten verfügt, mit denen sie arbeiten kann. Zur Erzwingung der sofortigen Ausführung einer Abfrage, die keinen SINGLETON-Wert zurückgibt, können Sie die <xref:System.Linq.Enumerable.ToList%2A>-Methode oder die <xref:System.Linq.Enumerable.ToArray%2A>-Methode verwenden. Dieses Verfahren zur Erzwingung der sofortigen Abfrageausführung kann sinnvoll sein, wenn Sie die Ergebnisse einer Abfrage zwischenspeichern möchten. Weitere Informationen zu verzögerte und unmittelbare abfrageausführung, finden Sie unter [erste Schritte mit LINQ](http://msdn.microsoft.com/library/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9).  
  
## <a name="queries"></a>Abfragen  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfragen können in zwei verschiedenen Syntaxarten formuliert werden: Abfrageausdruckssyntax und mit methodenbasierter Abfragesyntax.  
  
### <a name="query-expression-syntax"></a>Abfrageausdruckssyntax  
 Abfrageausdrücke sind eine deklarative Abfragesyntax. Mit dieser Syntax kann der Entwickler Abfragen in einem SQL-ähnlichen Format in C# oder Visual Basic schreiben. Die Abfrageausdruckssyntax ermöglicht die Ausführung komplexer Filter-, Sortier- und Gruppiervorgänge mit minimalem Codeeinsatz. Weitere Informationen finden Sie unter [LINQ-Abfrageausdrücke](http://msdn.microsoft.com/library/40638f19-fb46-4d26-a2d9-a383b48f5ed4) und [Grundlegende Abfrageoperationen (Visual Basic)](~/docs/visual-basic/programming-guide/concepts/linq/basic-query-operations.md).  
  
 Die Abfrageausdruckssyntax ist eine in C# 3.0 und [!INCLUDE[vb_orcas_long](../../../../includes/vb-orcas-long-md.md)] neu eingeführte Funktion. Beachten Sie jedoch, dass die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Common Language Runtime (CLR) die Abfrageausdruckssyntax selbst nicht lesen kann. Daher werden die Abfrageausdrücke beim Kompilieren in etwas übersetzt, was die CLR versteht: Methodenaufrufe. Diese Methoden werden als bezeichnet den *Standardabfrageoperatoren*. Als Entwickler können Sie entscheiden, ob Sie die Methoden mittels Methodensyntax direkt aufrufen möchten oder ob dafür die Abfragesyntax verwendet werden soll. Weitere Informationen finden Sie unter [Abfragesyntax und Methodensyntax in LINQ](~/docs/csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md). Weitere Informationen zur Verwendung von Standardabfrageoperatoren finden Sie unter [nicht im BUILD: LINQ Allgemein Programmierhandbuch](http://msdn.microsoft.com/library/609c7a6b-cbdd-429d-99f3-78d13d3bc049).  
  
 In den folgenden Beispielen wird die <xref:System.Linq.Enumerable.Select%2A>-Methode verwendet, um alle Zeilen aus der `Product`-Tabelle zurückzugeben und die Produktnamen anzuzeigen.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple1)]  
  
### <a name="method-based-query-syntax"></a>Methodenbasierte Abfragesyntax  
 Statt mit der Abfrageausdruckssyntax können [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Abfragen auch mit der methodenbasierten Abfragesyntax formuliert werden. Dabei handelt es sich um eine Abfolge direkter Methodenaufrufe der [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-Operatormethoden, wobei als Parameter Lambda-Ausdrücke übergeben werden. Weitere Informationen finden Sie unter [Lambdaausdrücke](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 In diesem Beispiel wird <xref:System.Linq.Enumerable.Select%2A> verwendet, um alle Zeilen aus der `Product`-Tabelle zurückzugeben und die Produktnamen anzuzeigen.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
## <a name="composing-queries"></a>Verfassen von Abfragen  
 Wie weiter oben bereits erwähnt, speichert die Abfragevariable selbst nur die Abfragebefehle, sofern die Abfrage eine Sequenz von Werten zurückgeben soll. Wenn die Abfrage keine Methode enthält, die eine sofortige Ausführung erzwingt, wird die Ausführung der Abfrage so lange verzögert, bis die Abfragevariable in einer `foreach`- oder `For Each`-Schleife durchlaufen wird. Die verzögerte Ausführung ermöglicht die Kombination mehrerer Abfragen oder die Erweiterung einer bestehenden Abfrage. durch das Hinzufügen neuer Operationen. Die Änderungen werden dann bei der Ausführung der Abfrage berücksichtigt. Im folgenden Beispiel gibt die erste Abfrage alle Produkte zurück. Die zweite Abfrage erweitert die erste, indem sie `Where` verwendet, um alle Produkte der Größe "L" zurückzugeben:  
  
 [!code-csharp[DP LINQ to DataSet Examples#Composing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#composing)]
 [!code-vb[DP LINQ to DataSet Examples#Composing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#composing)]  
  
 Nach Ausführung der Abfrage können keine weiteren Abfragen mehr verfasst werden. Alle nachfolgenden Abfragen verwenden die im Arbeitsspeicher abgelegten [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-Operatoren. Abfrage wird ausgeführt, wenn Sie die Abfragevariable in Durchlaufen einer `foreach` oder `For Each` -Anweisung oder durch einen Aufruf eines der [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] Konvertierungsoperatoren, die sofortige Ausführung erzwingen. Dabei kann es sich um einen der folgenden Operatoren handeln: <xref:System.Linq.Enumerable.ToList%2A>, <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToLookup%2A> und <xref:System.Linq.Enumerable.ToDictionary%2A>.  
  
 Im folgenden Beispiel gibt die erste Abfrage alle Produkte zurück und sortiert sie nach dem Listenpreis. Um die sofortige Abfrageausführung zu erzwingen, wird die <xref:System.Linq.Enumerable.ToArray%2A>-Methode verwendet:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToArray2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#toarray2)]
 [!code-vb[DP LINQ to DataSet Examples#ToArray2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#toarray2)]  
  
## <a name="see-also"></a>Siehe auch  
 [Programmierhandbuch](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
 [Abfragen von DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [Erste Schritte mit LINQ in C#](~/docs/csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [Getting Started with LINQ in Visual Basic (Erste Schritte mit LINQ in Visual Basic)](~/docs/visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
