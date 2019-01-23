---
title: "\"DataRows\" und \"DataRowViews\""
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
ms.openlocfilehash: b7f92c0341a63df6bb5553d656469b374755aae7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562640"
---
# <a name="datarows-and-datarowviews"></a><span data-ttu-id="e9f1d-102">"DataRows" und "DataRowViews"</span><span class="sxs-lookup"><span data-stu-id="e9f1d-102">DataRows and DataRowViews</span></span>
<span data-ttu-id="e9f1d-103">Eine <xref:System.Data.DataView> macht eine aufzählbare Auflistung von <xref:System.Data.DataRowView>-Objekten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e9f1d-103">A <xref:System.Data.DataView> exposes an enumerable collection of <xref:System.Data.DataRowView> objects.</span></span> <span data-ttu-id="e9f1d-104">Die **DataRowView** Objekte verfügbar zu machen Werte als Objektarrays, die durch den Namen oder den Ordnungszahlverweis der Spalte in der zugrunde liegenden Tabelle indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="e9f1d-104">The **DataRowView** objects expose values as object arrays that are indexed by either the name or the ordinal reference of the column in the underlying table.</span></span> <span data-ttu-id="e9f1d-105">Sie erreichen die <xref:System.Data.DataRow> , die von verfügbar gemacht wird der **DataRowView** mithilfe der <xref:System.Data.DataRowView.Row%2A> Eigenschaft der **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="e9f1d-105">You can access the <xref:System.Data.DataRow> that is exposed by the **DataRowView** by using the <xref:System.Data.DataRowView.Row%2A> property of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="e9f1d-106">Beim Anzeigen von Werten mit einer **DataRowView**, wird die <xref:System.Data.DataView.RowStateFilter%2A> Eigenschaft der **DataView** bestimmt, welche Zeilenversion der zugrunde liegenden **DataRow** verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="e9f1d-106">When you view values by using a **DataRowView**, the <xref:System.Data.DataView.RowStateFilter%2A> property of the **DataView** determines which row version of the underlying **DataRow** is exposed.</span></span> <span data-ttu-id="e9f1d-107">Informationen zum Zugreifen auf verschiedene Zeilenversionen mithilfe einer **DataRow**, finden Sie unter [Zeilenstatus und Zeilenversionen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="e9f1d-107">For information about accessing different row versions using a **DataRow**, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="e9f1d-108">Im folgenden Codebeispiel werden alle aktuellen und ursprünglichen Werte in einer Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e9f1d-108">The following code example displays all the current and original values in a table.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e9f1d-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9f1d-109">See also</span></span>
- <xref:System.Data.DataRowVersion>
- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [<span data-ttu-id="e9f1d-110">DataViews</span><span class="sxs-lookup"><span data-stu-id="e9f1d-110">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [<span data-ttu-id="e9f1d-111">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="e9f1d-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
