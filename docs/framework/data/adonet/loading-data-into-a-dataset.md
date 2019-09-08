---
title: Laden von Daten in ein DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: 53f0f5a589a0033c9612f0465dff090ab04e3fc4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794955"
---
# <a name="loading-data-into-a-dataset"></a>Laden von Daten in ein DataSet
Ein <xref:System.Data.DataSet> -Objekt muss zuerst aufgefüllt werden, bevor es mit LINQ to DataSet abgefragt werden kann. Das Auffüllen des <xref:System.Data.DataSet>-Objekts kann auf verschiedene Art und Weise erfolgen. Beispielsweise können Sie verwenden [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] , um die Datenbank abzufragen und die Ergebnisse in die <xref:System.Data.DataSet>zu laden. Weitere Informationen finden Sie unter [LINQ to SQL](./sql/linq/index.md).  
  
 Eine andere Möglichkeit, Daten in ein <xref:System.Data.DataSet> zu laden, besteht darin, Daten mithilfe der <xref:System.Data.Common.DataAdapter>-Klasse aus der Datenbank abzurufen. Dies wird im folgenden Beispiel illustriert.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird ein <xref:System.Data.Common.DataAdapter> verwendet, um aus der &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Datenbank Verkaufsinformationen für das Jahr 2002 abzurufen und die Ergebnisse in ein <xref:System.Data.DataSet> zu laden. Nachdem der <xref:System.Data.DataSet> aufgefüllt wurde, können Sie Abfragen für ihn mit LINQ to DataSet schreiben. Die `FillDataSet` -Methode in diesem Beispiel wird in den Beispielabfragen in [LINQ to DataSet Beispielen](linq-to-dataset-examples.md)verwendet. Weitere Informationen finden Sie unter [Abfragen von Datasets](querying-datasets-linq-to-dataset.md).  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über LINQ to DataSet](linq-to-dataset-overview.md)
- [Abfragen von DataSets](querying-datasets-linq-to-dataset.md)
- [Beispiele für LINQ to DataSet](linq-to-dataset-examples.md)
