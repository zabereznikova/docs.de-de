---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Konvertierungsoperatoren (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a084c16b-9b55-4690-aefd-f8e0810a92c3
ms.openlocfilehash: 47e2a0a510af86055d93603c8c898b00c8d94c87
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="method-based-query-syntax-examples-conversion-operators-linq-to-dataset"></a>Beispiele für die methodenbasierte Abfragesyntax: Konvertierungsoperatoren (LINQ to DataSet)
In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der Methoden <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> und <xref:System.Linq.Enumerable.ToList%2A> einen Abfrageausdruck sofort ausführen können.  
  
 Die `FillDataSet` in diesen Beispielen verwendete Methode angegeben, [Laden von Daten in ein DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).  
  
 In den Beispielen in diesem Thema wird auf die Tabellen <legacyBold>Contact</legacyBold>, <legacyBold>Address</legacyBold>, <legacyBold>Product</legacyBold>, <legacyBold>SalesOrderHeader</legacyBold> und <legacyBold>SalesOrderDetail</legacyBold> in der <legacyBold>AdventureWorks</legacyBold>-Beispieldatenbank zurückgegriffen.  
  
 In den Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines LINQ to DataSet-Projekt In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="toarray"></a>ToArray  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Linq.Enumerable.ToArray%2A>-Methode verwendet, um ein Array sofort in eine Sequenz umzuwandeln.  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#toarray)]
 [!code-vb[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a>ToDictionary  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Linq.Enumerable.ToDictionary%2A>-Methode verwendet, um eine Sequenz und einen zugehörigen Schlüsselausdruck sofort in ein Wörterbuch umzuwandeln.  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a>ToList  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Linq.Enumerable.ToList%2A>-Methode verwendet, um eine Sequenz sofort in eine <xref:System.Collections.Generic.List%601> umzuwandeln, wobei `T` vom Typ <xref:System.Data.DataRow> ist.  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#tolist)]
 [!code-vb[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a>Siehe auch  
 [Laden von Daten in ein DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [Beispiele für LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [Übersicht über Standardabfrageoperatoren](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
