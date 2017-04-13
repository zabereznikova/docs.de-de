---
title: "&#39;DataRows&#39; und &#39;DataRowViews&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# &#39;DataRows&#39; und &#39;DataRowViews&#39;
Eine <xref:System.Data.DataView> macht eine aufzählbare Auflistung von <xref:System.Data.DataRowView>\-Objekten verfügbar.  Die **DataRowView**\-Objekte machen die Werte als Objektarrays verfügbar, die entweder durch den Namen oder den Ordinalzahlverweis der Spalte in der zugrunde liegenden Tabelle indiziert werden.  Sie können auf die von der **DataRowView** verfügbar gemachte <xref:System.Data.DataRow> mit der <xref:System.Data.DataRowView.Row%2A>\-Eigenschaft der **DataRowView** zugreifen.  
  
 Beim Anzeigen von Werten mit einer **DataRowView** legt die <xref:System.Data.DataView.RowStateFilter%2A>\-Eigenschaft der **DataView** fest, welche Zeilenversion der zugrunde liegenden **DataRow** verfügbar gemacht wird.  	Informationen zum Zugriff auf verschiedene Zeilenversionen mithilfe von **DataRow** finden Sie unter [Zeilenstatus und Zeilenversion](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
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
  
## Siehe auch  
 <xref:System.Data.DataRowVersion>   
 <xref:System.Data.DataViewRowState>   
 <xref:System.Data.DataView>   
 <xref:System.Data.DataRowView>   
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)