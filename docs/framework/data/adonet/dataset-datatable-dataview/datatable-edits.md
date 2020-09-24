---
title: Bearbeitungen von "DataTable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: 4fdb19e7fa014bf4a7c924b1fbae53fa44de6e3c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153260"
---
# <a name="datatable-edits"></a>Bearbeitungen von "DataTable"

Wenn Sie Änderungen der Spaltenwerte in einer <xref:System.Data.DataRow> vornehmen, werden die Änderungen sofort im aktuellen Zustand der Zeile platziert. <xref:System.Data.DataRowState>Wird dann auf **modified**festgelegt, und die Änderungen werden mithilfe der-Methode oder der- <xref:System.Data.DataRow.AcceptChanges%2A> <xref:System.Data.DataRow.RejectChanges%2A> Methode der **DataRow**akzeptiert oder abgelehnt. Die **DataRow** bietet auch drei Methoden, die Sie verwenden können, um den Zustand der Zeile während der Bearbeitung anzuhalten. Diese Methoden sind <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> und <xref:System.Data.DataRow.CancelEdit%2A>.  
  
 Wenn Sie Spaltenwerte in einer **DataRow** direkt ändern, verwaltet die **DataRow** die Spaltenwerte mithilfe der **aktuellen**, der **Standard**-und der **Original** Zeilen Version. Zusätzlich zu diesen Zeilen Versionen verwenden die Methoden **BeginEdit**, **EndEdit**und **CancelEdit** eine vierte Zeilen Version: **vorgeschlagen**. Weitere Informationen zu Zeilen Versionen finden Sie unter [Zeilen Status und Zeilen Versionen](row-states-and-row-versions.md).  
  
 Die **vorgeschlagene** Zeilen Version ist während eines Bearbeitungsvorgangs vorhanden, der beginnt, indem **BeginEdit** aufgerufen wird, das entweder mithilfe von **EndEdit** oder **CancelEdit** oder durch Aufrufen von ' **Accept Changes** ' oder ' **RejectChanges**' endet.  
  
 Während des Bearbeitungsvorgangs können Sie Validierungs Logik auf einzelne Spalten anwenden, indem Sie den **ProposedValue** im **ColumnChanged** -Ereignis der **Daten**Tabelle auswerten. Das **ColumnChanged** -Ereignis enthält **DataColumnChangeEventArgs** , die einen Verweis auf die geänderte Spalte und den Wert " **ProposedValue**" beibehalten. Nachdem der vorgeschlagene Wert ausgewertet wurde, kann dieser Wert geändert oder die Bearbeitung abgebrochen werden. Wenn die Bearbeitung beendet ist, wird die Zeile in den Status " **vorgeschlagen** " versetzt.  
  
 Sie können Änderungen überprüfen, indem Sie **EndEdit**aufrufen, oder Sie können Sie durch Aufrufen von **CancelEdit**abbrechen. Beachten Sie, dass **EndEdit** Ihre Bearbeitungen bestätigt, dass das **DataSet** die Änderungen erst akzeptiert, wenn " **Accept Changes** " aufgerufen wird. Beachten Sie auch Folgendes: Wenn Sie " **akzeptchanges** " vor dem Beenden der Bearbeitung mit **EndEdit** oder **CancelEdit**aufgerufen haben, wird die Bearbeitung beendet, und die **vorgeschlagenen** Zeilen Werte werden sowohl für die **aktuelle** als auch die **ursprüngliche** Zeilen Version akzeptiert. Auf dieselbe Weise beendet der Aufruf von **RejectChanges** die Bearbeitung und verwirft die **aktuelle** und **vorgeschlagene** Zeilen Version. Der Aufruf von **EndEdit** oder **CancelEdit** nach dem Aufruf von " **Accept Changes** " oder " **RejectChanges** " hat keine Auswirkungen, da die Bearbeitung bereits beendet wurde.  
  
 Im folgenden Beispiel wird die Verwendung von **BeginEdit** mit **EndEdit** und **CancelEdit**veranschaulicht. Im Beispiel wird auch der **ProposedValue** im **ColumnChanged** -Ereignis überprüft und entschieden, ob der Bearbeitungsvorgang abgebrochen werden soll.  
  
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
