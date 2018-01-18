---
title: Zeilenfehlerinformationen
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
ms.assetid: 8b1f9070-d032-48c7-b030-bd8fbb2ca59a
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3e8b2e486f33cbe3851b0d24911f5976a1a4b3c6
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="row-error-information"></a>Zeilenfehlerinformationen
Um nicht jedes Mal auf einen Zeilenfehler reagieren zu müssen, während Sie Werte in einer <xref:System.Data.DataTable> bearbeiten, können Sie der Zeile die Fehlerinformationen zur späteren Verwendung der Zeile hinzufügen. Das <xref:System.Data.DataRow>-Objekt stellt zu diesem Zweck für jede Zeile eine <xref:System.Data.DataRow.RowError%2A>-Eigenschaft bereit. Hinzufügen von Daten zu der **RowError** Eigenschaft eine **DataRow** legt der <xref:System.Data.DataRow.HasErrors%2A> Eigenschaft der **DataRow** zu **"true"**. Wenn die **DataRow** ist Teil einer **DataTable**, und **DataRow.HasErrors** ist **"true"**, **DataTable.HasErrors** -Eigenschaft ist ebenfalls **"true"**. Dies gilt auch für die **DataSet** , der die **DataTable** gehört. Beim Testen der Fehler sehen Sie sich die **HasErrors** -Eigenschaft können Sie bestimmen, ob alle Zeilen Fehlerinformationen hinzugefügt wurden. Wenn **HasErrors** ist **"true"**, können Sie die <xref:System.Data.DataTable.GetErrors%2A> Methode der **DataTable** zurückgeben, und überprüfen nur die Zeilen mit Fehlern aus, wie im folgenden Beispiel gezeigt.  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
workTable.Columns.Add("CustID", Type.GetType("System.Int32"))  
workTable.Columns.Add("Total", Type.GetType("System.Double"))  
  
AddHandler workTable.RowChanged, New DataRowChangeEventHandler(AddressOf OnRowChanged)  
  
Dim i  As Int32  
  
For i  = 0 To 10  
  workTable.Rows.Add(New Object() {i , i *100})  
Next  
  
If workTable.HasErrors Then  
  Console.WriteLine("Errors in Table " & workTable.TableName)  
  
  Dim myRow As DataRow  
  
  For Each myRow In workTable.GetErrors()  
    Console.WriteLine("CustID = " & myRow("CustID").ToString())  
    Console.WriteLine(" Error = " & myRow.RowError & vbCrLf)  
  Next  
End If  
  
Private Shared Sub OnRowChanged( _  
    sender As Object, args As DataRowChangeEventArgs)  
  ' Check for zero values.  
  If CDbl(args.Row("Total")) = 0 Then args.Row.RowError = _  
      "Total cannot be 0."  
End Sub  
```  
  
```csharp  
DataTable  workTable = new DataTable("Customers");  
workTable.Columns.Add("CustID", typeof(Int32));  
workTable.Columns.Add("Total", typeof(Double));  
  
workTable.RowChanged += new DataRowChangeEventHandler(OnRowChanged);  
  
for (int i = 0; i < 10; i++)  
  workTable.Rows.Add(new Object[] {i, i*100});  
  
if (workTable.HasErrors)  
{  
  Console.WriteLine("Errors in Table " + workTable.TableName);  
  
  foreach (DataRow myRow in workTable.GetErrors())  
  {  
    Console.WriteLine("CustID = " + myRow["CustID"]);  
    Console.WriteLine(" Error = " + myRow.RowError + "\n");  
  }  
}  
  
protected static void OnRowChanged(  
    Object sender, DataRowChangeEventArgs args)  
{  
  // Check for zero values.  
  if (args.Row["Total"].Equals(0D))  
    args.Row.RowError = "Total cannot be 0.";  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataTable>  
 [Bearbeiten von Daten in einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
