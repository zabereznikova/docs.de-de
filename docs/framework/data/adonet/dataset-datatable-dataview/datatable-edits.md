---
title: Bearbeitungen von "DataTable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: 9e8c4204b51121b147fc7614066d9b849a687574
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151259"
---
# <a name="datatable-edits"></a>Bearbeitungen von "DataTable"
Wenn Sie Änderungen der Spaltenwerte in einer <xref:System.Data.DataRow> vornehmen, werden die Änderungen sofort im aktuellen Zustand der Zeile platziert. Der <xref:System.Data.DataRowState> wird dann auf **Geändert**festgelegt, und die <xref:System.Data.DataRow.AcceptChanges%2A> <xref:System.Data.DataRow.RejectChanges%2A> Änderungen werden mit den oder Methoden der **DataRow**akzeptiert oder abgelehnt. **DataRow** bietet außerdem drei Methoden, mit denen Sie den Status der Zeile während der Bearbeitung anhalten können. Diese Methoden sind <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> und <xref:System.Data.DataRow.CancelEdit%2A>.  
  
 Wenn Sie Spaltenwerte in einem **DataRow** direkt ändern, verwaltet **DataRow** die Spaltenwerte mithilfe der Zeilenversionen **Aktuelle**, **Standard**und **Original.** Zusätzlich zu diesen Zeilenversionen verwenden die Methoden **BeginEdit**, **EndEdit**und **CancelEdit** eine vierte Zeilenversion: **Vorgeschlagen**. Weitere Informationen zu Zeilenversionen finden Sie unter [Zeilenzustände und Zeilenversionen](row-states-and-row-versions.md).  
  
 Die **vorgeschlagene** Zeilenversion ist während eines Bearbeitungsvorgangs vorhanden, der mit dem Aufruf von **BeginEdit** beginnt und entweder mit **EndEdit** oder **CancelEdit** oder mit **AcceptChanges** oder **RejectChanges**endet.  
  
 Während des Bearbeitungsvorgangs können Sie Validierungslogik auf einzelne Spalten anwenden, indem Sie den **ProposedValue** im **ColumnChanged-Ereignis** der **DataTable**auswerten. Das **ColumnChanged-Ereignis** enthält **DataColumnChangeEventArgs,** die einen Verweis auf die Spalte beibehalten, die sich ändert, und auf den **ProposedValue**. Nachdem der vorgeschlagene Wert ausgewertet wurde, kann dieser Wert geändert oder die Bearbeitung abgebrochen werden. Wenn die Bearbeitung beendet ist, wird die Zeile aus dem Status **Vorgeschlagen** verschoben.  
  
 Sie können Bearbeitungen bestätigen, indem Sie **EndEdit**aufrufen, oder Sie können sie abbrechen, indem Sie **CancelEdit**aufrufen. Beachten Sie, dass **EndEdit** zwar Ihre Änderungen bestätigt, das **DataSet** die Änderungen jedoch erst akzeptiert, wenn **AcceptChanges** aufgerufen wird. Beachten Sie auch, dass, wenn Sie **AcceptChanges** aufrufen, bevor Sie die Bearbeitung mit **EndEdit** oder **CancelEdit**beendet haben, die Bearbeitung beendet wird und die **vorgeschlagenen** Zeilenwerte sowohl für die **aktuelle** als auch für die **ursprüngliche** Zeilenversion akzeptiert werden. Auf die gleiche Weise beendet das Aufrufen von **RejectChanges** die Bearbeitung und verwirft die **aktuellen** und **vorgeschlagenen** Zeilenversionen. Das Aufrufen von **EndEdit** oder **CancelEdit** nach dem Aufrufen von **AcceptChanges** oder **RejectChanges** hat keine Auswirkungen, da die Bearbeitung bereits beendet wurde.  
  
 Im folgenden Beispiel wird veranschaulicht, wie **BeginEdit** mit **EndEdit** und **CancelEdit**verwendet wird. Das Beispiel überprüft auch den **ProposedValue** im **ColumnChanged-Ereignis** und entscheidet, ob die Bearbeitung abgebrochen werden soll.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [Bearbeiten von Daten in einer "DataTable"](manipulating-data-in-a-datatable.md)
- [Behandeln von DataTable-Ereignissen](handling-datatable-events.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
