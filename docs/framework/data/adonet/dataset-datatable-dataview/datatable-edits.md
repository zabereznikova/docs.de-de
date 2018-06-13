---
title: Bearbeitungen von "DataTable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: b806e642a5cce6a55ff0dcecc9b018f3ee78bad8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758619"
---
# <a name="datatable-edits"></a>Bearbeitungen von "DataTable"
Wenn Sie Änderungen der Spaltenwerte in einer <xref:System.Data.DataRow> vornehmen, werden die Änderungen sofort im aktuellen Zustand der Zeile platziert. Die <xref:System.Data.DataRowState> legen Sie dann auf **"geändert"**, und die Änderungen werden akzeptiert oder abgelehnt wird, mithilfe der <xref:System.Data.DataRow.AcceptChanges%2A> oder <xref:System.Data.DataRow.RejectChanges%2A> Methoden die **DataRow**. Die **DataRow** auch bietet drei Methoden, die Sie verwenden können, um den Zustand der Zeile angehalten, während Sie es bearbeiten. Diese Methoden sind <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> und <xref:System.Data.DataRow.CancelEdit%2A>.  
  
 Beim Ändern von Spaltenwerten in einem **DataRow** direkt die **DataRow** verwaltet die Spaltenwerte mithilfe der **aktuelle**, **Standard**, und **Ursprünglichen** Zeilenversionen. Zusätzlich zu diesen Zeilenversionen die **BeginEdit**, **EndEdit**, und **CancelEdit** Methoden verwenden eine vierte Zeilenversion: **vorgeschlagen**. Weitere Informationen zu Zeilenversionen finden Sie unter [Zeilenstatus und Zeilenversionen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
 Die **vorgeschlagen** Zeilenversion vorhanden ist, während eines Bearbeitungsvorgangs an, die durch den Aufruf beginnt **BeginEdit** und endet mit **EndEdit** oder **CancelEdit**  oder durch Aufrufen von **AcceptChanges** oder **RejectChanges**.  
  
 Während des Bearbeitungsvorgangs können Sie Validierungslogik auf einzelne Spalten angewendet, durch das Auswerten der **ProposedValue** in der **ColumnChanged** -Ereignis für die **DataTable**. Die **ColumnChanged** Ereignis enthält **DataColumnChangeEventArgs** , die einen Verweis auf die Spalte, die geändert wird und zum Beibehalten der **ProposedValue**. Nachdem der vorgeschlagene Wert ausgewertet wurde, kann dieser Wert geändert oder die Bearbeitung abgebrochen werden. Wenn die Bearbeitung abgeschlossen wurde, verlässt die Zeile aus der **vorgeschlagen** Zustand.  
  
 Sie können Änderungen überprüfen, indem Aufrufen **EndEdit**, oder durch Aufrufen von storniert werden **CancelEdit**. Beachten Sie, dass **EndEdit** die Bearbeitungen bestätigt die **DataSet** akzeptiert die Änderungen erst nicht tatsächlich **AcceptChanges** aufgerufen wird. Beachten Sie auch, dass beim Aufrufen **AcceptChanges** , bevor Sie die Bearbeitung mit beendet haben **EndEdit** oder **CancelEdit**, die Bearbeitung abgeschlossen und die **vorgeschlagen** Zeilenwerte werden für beide akzeptiert die **aktuelle** und **ursprünglichen** Zeilenversionen. Auf die gleiche Weise aufrufen **RejectChanges** beendet die Bearbeitung und verwirft die **aktuelle** und **vorgeschlagen** Zeilenversionen. Aufrufen von **EndEdit** oder **CancelEdit** nach dem Aufruf **AcceptChanges** oder **RejectChanges** hat keine Auswirkungen, die Bearbeitung ist bereits vorhanden. wurde beendet.  
  
 Im folgenden Beispiel wird veranschaulicht, wie **BeginEdit** mit **EndEdit** und **CancelEdit**. Im Beispiel wird außerdem überprüft der **ProposedValue** in der **ColumnChanged** Ereignis und entscheidet, ob die Bearbeitung abgebrochen.  
  
```vb  
Dim workTable As DataTable = New DataTable  
workTable.Columns.Add("LastName", Type.GetType("System.String"))  
  
AddHandler workTable.ColumnChanged, _  
  New DataColumnChangeEventHandler(AddressOf OnColumnChanged)  
  
Dim workRow As DataRow = workTable.NewRow()  
workRow(0) = "Smith"  
workTable.Rows.Add(workRow)  
  
workRow.BeginEdit()  
' Causes the ColumnChanged event to write a message and cancel the edit.  
workRow(0) = ""       
workRow.EndEdit()  
  
' Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow(0), workRow.RowState)  
  
Private Shared Sub OnColumnChanged( _  
  sender As Object, args As DataColumnChangeEventArgs)  
  If args.Column.ColumnName = "LastName" Then  
    If args.ProposedValue.ToString() = "" Then  
      Console.WriteLine("Last Name cannot be blank.  Edit canceled.")  
      args.Row.CancelEdit()  
    End If  
  End If  
End Sub  
```  
  
```csharp  
DataTable workTable  = new DataTable();  
workTable.Columns.Add("LastName", typeof(String));  
  
workTable.ColumnChanged +=   
  new DataColumnChangeEventHandler(OnColumnChanged);  
  
DataRow workRow = workTable.NewRow();  
workRow[0] = "Smith";  
workTable.Rows.Add(workRow);  
  
workRow.BeginEdit();  
// Causes the ColumnChanged event to write a message and cancel the edit.  
workRow[0] = "";       
workRow.EndEdit();  
  
// Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow[0], workRow.RowState);    
  
protected static void OnColumnChanged(  
  Object sender, DataColumnChangeEventArgs args)  
{  
  if (args.Column.ColumnName == "LastName")  
    if (args.ProposedValue.ToString() == "")  
    {  
      Console.WriteLine("Last Name cannot be blank. Edit canceled.");  
      args.Row.CancelEdit();  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataRowVersion>  
 [Bearbeiten von Daten in einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Behandeln von DataTable-Ereignissen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
