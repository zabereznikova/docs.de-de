---
title: "\"DataRows\" und \"DataRowViews\""
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
ms.openlocfilehash: 8a98dc44eda9ebda09235193c58bd831fc52d04d
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205094"
---
# <a name="datarows-and-datarowviews"></a>"DataRows" und "DataRowViews"
Eine <xref:System.Data.DataView> macht eine aufzählbare Auflistung von <xref:System.Data.DataRowView>-Objekten verfügbar. Die **DataRowView** -Objekte machen Werte als Objekt Arrays verfügbar, die entweder durch den Namen oder den Ordinalverweis der Spalte in der zugrunde liegenden Tabelle indiziert werden. Sie können auf das <xref:System.Data.DataRow> zugreifen, das von der **DataRowView** verfügbar gemacht wird <xref:System.Data.DataRowView.Row%2A> , indem Sie die-Eigenschaft der **DataRowView**verwenden.  
  
 Wenn Sie Werte mithilfe einer **DataRowView**anzeigen, bestimmt die <xref:System.Data.DataView.RowStateFilter%2A> -Eigenschaft der **DataView** , welche Zeilen Version der zugrunde liegenden **DataRow** verfügbar gemacht wird. Informationen zum Zugriff auf verschiedene Zeilen Versionen mithilfe einer **DataRow**finden Sie unter [Zeilen Status und Zeilen Versionen](row-states-and-row-versions.md).  
  
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

- <xref:System.Data.DataRowVersion>
- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [DataViews](dataviews.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
