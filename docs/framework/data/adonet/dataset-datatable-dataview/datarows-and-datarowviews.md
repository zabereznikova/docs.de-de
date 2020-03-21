---
title: "\"DataRows\" und \"DataRowViews\""
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
ms.openlocfilehash: 14e7e1ccb051410c351e49afee9f2d6809264833
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151298"
---
# <a name="datarows-and-datarowviews"></a>"DataRows" und "DataRowViews"
Eine <xref:System.Data.DataView> macht eine aufzählbare Auflistung von <xref:System.Data.DataRowView>-Objekten verfügbar. Die **DataRowView-Objekte** machen Werte als Objektarrays verfügbar, die entweder durch den Namen oder den Ordinalverweis der Spalte in der zugrunde liegenden Tabelle indiziert werden. Sie können <xref:System.Data.DataRow> auf die zugreifen, die von <xref:System.Data.DataRowView.Row%2A> **DataRowView** verfügbar gemacht wird, indem Sie die Eigenschaft der **DataRowView**verwenden.  
  
 Wenn Sie Werte mithilfe einer **DataRowView**anzeigen, bestimmt die <xref:System.Data.DataView.RowStateFilter%2A> Eigenschaft **dataView,** welche Zeilenversion des zugrunde liegenden **DataRow** verfügbar gemacht wird. Informationen zum Zugriff auf verschiedene Zeilenversionen mit einem **DataRow**finden Sie unter [Zeilenzustände und Zeilenversionen](row-states-and-row-versions.md).  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Data.DataRowVersion>
- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- ["DataViews"](dataviews.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
