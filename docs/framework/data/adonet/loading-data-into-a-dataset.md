---
title: Laden von Daten in ein DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: cb5578d790e5d3f54f75f964bb3288d861c9d7c3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074052"
---
# <a name="loading-data-into-a-dataset"></a>Laden von Daten in ein DataSet
Ein <xref:System.Data.DataSet>-Objekt muss zuerst aufgefüllt werden, bevor Sie es mit [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] abfragen können. Das Auffüllen des <xref:System.Data.DataSet>-Objekts kann auf verschiedene Art und Weise erfolgen. Beispielsweise können Sie [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] zum Abfragen der Datenbank, und laden die Ergebnisse in die <xref:System.Data.DataSet>. Weitere Informationen finden Sie unter [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
 Eine andere Möglichkeit, Daten in ein <xref:System.Data.DataSet> zu laden, besteht darin, Daten mithilfe der <xref:System.Data.Common.DataAdapter>-Klasse aus der Datenbank abzurufen. Dies wird im folgenden Beispiel illustriert.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird ein <xref:System.Data.Common.DataAdapter> verwendet, um aus der &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Datenbank Verkaufsinformationen für das Jahr 2002 abzurufen und die Ergebnisse in ein <xref:System.Data.DataSet> zu laden. Nachdem das <xref:System.Data.DataSet> aufgefüllt wurde, können Sie mithilfe von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Abfragen Daten aus ihm abrufen. Die `FillDataSet` -Methode in diesem Beispiel wird verwendet, in den Beispielabfragen in [LINQ to DataSet-Beispielen](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md). Weitere Informationen finden Sie unter [DataSets Abfragen](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [Abfragen von DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [Beispiele für LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
