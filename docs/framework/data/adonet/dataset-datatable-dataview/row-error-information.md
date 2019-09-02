---
title: Zeilenfehlerinformationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b1f9070-d032-48c7-b030-bd8fbb2ca59a
ms.openlocfilehash: af000d104a3b0821e69f11c1bce1392f04fe8f5e
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203236"
---
# <a name="row-error-information"></a>Zeilenfehlerinformationen
Um nicht jedes Mal auf einen Zeilenfehler reagieren zu müssen, während Sie Werte in einer <xref:System.Data.DataTable> bearbeiten, können Sie der Zeile die Fehlerinformationen zur späteren Verwendung der Zeile hinzufügen. Das <xref:System.Data.DataRow>-Objekt stellt zu diesem Zweck für jede Zeile eine <xref:System.Data.DataRow.RowError%2A>-Eigenschaft bereit. Durch das Hinzufügen von Daten zur **RowError** -Eigenschaft einer **DataRow** wird die <xref:System.Data.DataRow.HasErrors%2A> -Eigenschaft der **DataRow** auf **true**festgelegt. Wenn die **DataRow** Teil einer **Daten**Tabelle ist und **DataRow. HasErrors** den Wert **true**hat, ist die **Datable. HasErrors** -Eigenschaft ebenfalls **true**. Dies gilt auch für das **DataSet** , zu dem die **Daten** Tabelle gehört. Beim Testen von Fehlern können Sie die **HasErrors** -Eigenschaft überprüfen, um zu ermitteln, ob den Zeilen Fehlerinformationen hinzugefügt wurden. Wenn **HasErrors** den Wert **true**hat, <xref:System.Data.DataTable.GetErrors%2A> können Sie die-Methode der **Daten** Tabelle verwenden, um nur die Zeilen mit Fehlern zurückzugeben und zu überprüfen, wie im folgenden Beispiel gezeigt.  
  
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

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- [Bearbeiten von Daten in einer DataTable](manipulating-data-in-a-datatable.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
