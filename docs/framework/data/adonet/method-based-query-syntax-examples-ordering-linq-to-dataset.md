---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Sortieren (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f9ce4fd-e84f-48c0-bb64-89e217236d3e
ms.openlocfilehash: 76bc4751a25e82a731e136f838d12b8d1c1d691f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119560"
---
# <a name="method-based-query-syntax-examples-ordering-linq-to-dataset"></a>Beispiele für die methodenbasierte Abfragesyntax: Sortieren (LINQ to DataSet)
In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der <xref:System.Linq.Enumerable.OrderBy%2A>-Methode, der <xref:System.Linq.Enumerable.Reverse%2A>-Methode und der <xref:System.Linq.Enumerable.ThenBy%2A>-Methode sowie der methodenbasierten Abfragesyntax ein <xref:System.Data.DataSet> abfragen und die Reihenfolge der Ergebnisse festlegen können.  
  
 Die `FillDataSet` in diesen Beispielen verwendete Methode angegeben ist, im [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).  
  
 In den Beispielen in diesem Thema wird auf die Tabellen &lt;legacyBold&gt;Contact&lt;/legacyBold&gt;, &lt;legacyBold&gt;Address&lt;/legacyBold&gt;, &lt;legacyBold&gt;Product&lt;/legacyBold&gt;, &lt;legacyBold&gt;SalesOrderHeader&lt;/legacyBold&gt; und &lt;legacyBold&gt;SalesOrderDetail&lt;/legacyBold&gt; in der &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Beispieldatenbank zurückgegriffen.  
  
 In die Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie eine LINQ to DataSet-Projekt In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="orderby"></a>OrderBy  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Linq.Enumerable.OrderBy%2A>-Methode mit einem benutzerdefinierten Vergleich verwendet, um die Nachnamen ohne Berücksichtigung der Groß- oder Kleinschreibung zu sortieren.  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbycomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbycomparer_mq)]  
  
## <a name="reverse"></a>Reverse  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Linq.Enumerable.Reverse%2A>-Methode verwendet, um eine Liste der Aufträge zu erstellen, bei denen der `OrderDate`-Wert vor dem 20. Februar 2002 liegt.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenby"></a>ThenBy  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel werden die Methoden <xref:System.Linq.Enumerable.OrderBy%2A> und <xref:System.Linq.Enumerable.ThenBy%2A> mit einem benutzerdefinierten Vergleich verwendet, um die Daten zuerst nach dem Listenpreis zu und dann nach dem Produktnamen (ohne Berücksichtigung der Groß- oder Kleinschreibung) zu sortieren.  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingcomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingcomparer_mq)]  
  
## <a name="see-also"></a>Siehe auch

- [Laden von Daten in ein DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [Beispiele für LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [Übersicht über Standardabfrageoperatoren (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Standard Query Operators Overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
