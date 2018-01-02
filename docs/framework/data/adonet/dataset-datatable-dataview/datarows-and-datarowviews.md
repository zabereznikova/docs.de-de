---
title: "\"DataRows\" und \"DataRowViews\""
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ac8209432cd975539983226cfba51f229d696bd4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="datarows-and-datarowviews"></a>"DataRows" und "DataRowViews"
Eine <xref:System.Data.DataView> macht eine aufzählbare Auflistung von <xref:System.Data.DataRowView>-Objekten verfügbar. Die **DataRowView** Objekte, die Werte als Objektarrays, die durch den Namen oder den Ordinalzahlverweis der Spalte in der zugrunde liegenden Tabelle indiziert werden verfügbar gemacht. Sie erreichen die <xref:System.Data.DataRow> , verfügbar gemacht wird durch die **DataRowView** mithilfe der <xref:System.Data.DataRowView.Row%2A> Eigenschaft der **DataRowView**.  
  
 Beim Anzeigen von Werten mit einer **DataRowView**, die <xref:System.Data.DataView.RowStateFilter%2A> Eigenschaft von der **"DataView"** bestimmt, welche Zeilenversion der zugrunde liegenden **DataRow** verfügbar gemacht wird. Informationen zum Zugreifen auf unterschiedliche Zeilenversionen, die mit einem **DataRow**, finden Sie unter [Zeilenstatus und Zeilenversionen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
 Im folgenden Codebeispiel werden alle aktuellen und ursprünglichen Werte in einer Tabelle angezeigt.  
  
```vb  
Dim catView As DataView = New DataView(catDS.Tables("Categories"))  
Console.WriteLine("Current Values:")  
WriteView(catView)  
Console.WriteLine("Original Values:")  
catView.RowStateFilter = DataViewRowState.ModifiedOriginal  
WriteView(catView)      
  
Public Shared Sub WriteView(thisDataView As DataView)  
  Dim rowView As DataRowView  
  Dim i As Integer  
  
  For Each rowView In thisDataView  
    For i = 0 To thisDataView.Table.Columns.Count - 1  
      Console.Write(rowView(i) & vbTab)  
    Next  
    Console.WriteLine()  
  Next  
End Sub  
```  
  
```csharp  
DataView catView = new DataView(catDS.Tables["Categories"]);  
Console.WriteLine("Current Values:");  
WriteView(catView);  
Console.WriteLine("Original Values:");  
catView.RowStateFilter = DataViewRowState.ModifiedOriginal;  
WriteView(catView);  
  
public static void WriteView(DataView thisDataView)  
{  
  foreach (DataRowView rowView in thisDataView)  
  {  
    for (int i = 0; i < thisDataView.Table.Columns.Count; i++)  
      Console.Write(rowView[i] + "\t");  
    Console.WriteLine();  
  }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataRowVersion>  
 <xref:System.Data.DataViewRowState>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
