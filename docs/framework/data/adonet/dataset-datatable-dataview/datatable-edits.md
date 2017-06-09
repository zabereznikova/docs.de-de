---
title: "&#39;Edit&#39;-Methoden f&#252;r eine &#39;DataTable&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# &#39;Edit&#39;-Methoden f&#252;r eine &#39;DataTable&#39;
Wenn Sie Änderungen der Spaltenwerte in einer <xref:System.Data.DataRow> vornehmen, werden die Änderungen sofort im aktuellen Zustand der Zeile platziert.  Der <xref:System.Data.DataRowState> wird dann auf **Modified** festgelegt, und die Änderungen werden mithilfe der <xref:System.Data.DataRow.AcceptChanges%2A>\-Methode oder der <xref:System.Data.DataRow.RejectChanges%2A>\-Methode von **DataRow** akzeptiert oder abgelehnt.  Die **DataRow** stellt auch drei Methoden bereit, mit denen der Zustand der Zeile während der Bearbeitung ausgesetzt werden kann.  Diese Methoden sind <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> und <xref:System.Data.DataRow.CancelEdit%2A>.  
  
 Wenn Spaltenwerte direkt in einer **DataRow** geändert werden, verwaltet **DataRow** die Spaltenwerte mithilfe der Zeilenversionen **Current**, **Default** und **Original**.  Zusätzlich zu diesen Zeilenversionen verwenden die Methoden **BeginEdit**, **EndEdit** und **CancelEdit** eine vierte Zeilenversion: **Proposed**.  Weitere Informationen zu Zeilenversionen finden Sie unter [Zeilenstatus und Zeilenversion](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
 Die **Proposed**\-Zeilenversion ist während eines Bearbeitungsvorgangs vorhanden, der mit dem Aufrufen von **BeginEdit** beginnt, und entweder mit dem Verwenden von **EndEdit** oder **CancelEdit** oder durch Aufrufen von **AcceptChanges** oder **RejectChanges** endet.  
  
 Während des Bearbeitungsvorgangs kann eine Validierungslogik auf einzelne Spalten angewendet werden, indem **ProposedValue** im **ColumnChanged**\-Ereignis der **DataTable** ausgewertet wird.  Das **ColumnChanged**\-Ereignis enthält **DataColumnChangeEventArgs**, die einen Verweis auf die sich ändernde Spalte und auf den **ProposedValue** enthalten.  Nachdem der vorgeschlagene Wert ausgewertet wurde, kann dieser Wert geändert oder die Bearbeitung abgebrochen werden.  Wenn die Bearbeitung abgeschlossen wurde, verlässt die Zeile den **Proposed**\-Zustand.  
  
 Bearbeitungen können durch das Aufrufen von **EndEdit** bestätigt werden, oder sie können durch Aufrufen von **CancelEdit** abgebrochen werden.  Beachten Sie, dass **EndEdit** die Bearbeitungen bestätigt, und **DataSet** die Änderungen erst akzeptiert, wenn **AcceptChanges** aufgerufen wird.  Beachten Sie auch Folgendes: Wenn Sie **AcceptChanges** aufrufen, bevor die Bearbeitung mit **EndEdit** oder **CancelEdit** abgeschlossen wurde, wird die Bearbeitung abgeschlossen und die **Proposed**\-Zeilenwerte für die **Current**\-Zeilenversion und die **Original**\-Zeilenversion werden akzeptiert.  Auf die gleiche Weise beendet das Aufrufen von **RejectChanges** die Bearbeitung und verwirft die **Current**\-Zeilenversion und die **Proposed**\-Zeilenversion.  Das Aufrufen von **EndEdit** oder **CancelEdit** nach dem Aufrufen von **AcceptChanges** oder **RejectChanges** hat keine Auswirkungen, da die Bearbeitung bereits abgeschlossen wurde.  
  
 Das folgende Beispiel veranschaulicht, wie **BeginEdit** mit **EndEdit** und **CancelEdit** verwendet wird.  Im Beispiel wird auch der **ProposedValue** im **ColumnChanged**\-Ereignis überprüft und entschieden, ob die Bearbeitung abgebrochen werden soll.  
  
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
  
## Siehe auch  
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataRowVersion>   
 [Bearbeiten von Daten in einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [Behandlung von DataTable\-Ereignissen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)