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
---
# <a name="datatable-edits"></a><span data-ttu-id="87f4d-102">Bearbeitungen von "DataTable"</span><span class="sxs-lookup"><span data-stu-id="87f4d-102">DataTable Edits</span></span>
<span data-ttu-id="87f4d-103">Wenn Sie Änderungen der Spaltenwerte in einer <xref:System.Data.DataRow> vornehmen, werden die Änderungen sofort im aktuellen Zustand der Zeile platziert.</span><span class="sxs-lookup"><span data-stu-id="87f4d-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="87f4d-104">Die <xref:System.Data.DataRowState> legen Sie dann auf **"geändert"**, und die Änderungen werden akzeptiert oder abgelehnt wird, mithilfe der <xref:System.Data.DataRow.AcceptChanges%2A> oder <xref:System.Data.DataRow.RejectChanges%2A> Methoden die **DataRow**.</span><span class="sxs-lookup"><span data-stu-id="87f4d-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="87f4d-105">Die **DataRow** auch bietet drei Methoden, die Sie verwenden können, um den Zustand der Zeile angehalten, während Sie es bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="87f4d-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="87f4d-106">Diese Methoden sind <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> und <xref:System.Data.DataRow.CancelEdit%2A>.</span><span class="sxs-lookup"><span data-stu-id="87f4d-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="87f4d-107">Beim Ändern von Spaltenwerten in einem **DataRow** direkt die **DataRow** verwaltet die Spaltenwerte mithilfe der **aktuelle**, **Standard**, und **Ursprünglichen** Zeilenversionen.</span><span class="sxs-lookup"><span data-stu-id="87f4d-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="87f4d-108">Zusätzlich zu diesen Zeilenversionen die **BeginEdit**, **EndEdit**, und **CancelEdit** Methoden verwenden eine vierte Zeilenversion: **vorgeschlagen**.</span><span class="sxs-lookup"><span data-stu-id="87f4d-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="87f4d-109">Weitere Informationen zu Zeilenversionen finden Sie unter [Zeilenstatus und Zeilenversionen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="87f4d-109">For more information about row versions, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="87f4d-110">Die **vorgeschlagen** Zeilenversion vorhanden ist, während eines Bearbeitungsvorgangs an, die durch den Aufruf beginnt **BeginEdit** und endet mit **EndEdit** oder **CancelEdit**  oder durch Aufrufen von **AcceptChanges** oder **RejectChanges**.</span><span class="sxs-lookup"><span data-stu-id="87f4d-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="87f4d-111">Während des Bearbeitungsvorgangs können Sie Validierungslogik auf einzelne Spalten angewendet, durch das Auswerten der **ProposedValue** in der **ColumnChanged** -Ereignis für die **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="87f4d-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="87f4d-112">Die **ColumnChanged** Ereignis enthält **DataColumnChangeEventArgs** , die einen Verweis auf die Spalte, die geändert wird und zum Beibehalten der **ProposedValue**.</span><span class="sxs-lookup"><span data-stu-id="87f4d-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="87f4d-113">Nachdem der vorgeschlagene Wert ausgewertet wurde, kann dieser Wert geändert oder die Bearbeitung abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="87f4d-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="87f4d-114">Wenn die Bearbeitung abgeschlossen wurde, verlässt die Zeile aus der **vorgeschlagen** Zustand.</span><span class="sxs-lookup"><span data-stu-id="87f4d-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="87f4d-115">Sie können Änderungen überprüfen, indem Aufrufen **EndEdit**, oder durch Aufrufen von storniert werden **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="87f4d-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="87f4d-116">Beachten Sie, dass **EndEdit** die Bearbeitungen bestätigt die **DataSet** akzeptiert die Änderungen erst nicht tatsächlich **AcceptChanges** aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="87f4d-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="87f4d-117">Beachten Sie auch, dass beim Aufrufen **AcceptChanges** , bevor Sie die Bearbeitung mit beendet haben **EndEdit** oder **CancelEdit**, die Bearbeitung abgeschlossen und die **vorgeschlagen** Zeilenwerte werden für beide akzeptiert die **aktuelle** und **ursprünglichen** Zeilenversionen.</span><span class="sxs-lookup"><span data-stu-id="87f4d-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="87f4d-118">Auf die gleiche Weise aufrufen **RejectChanges** beendet die Bearbeitung und verwirft die **aktuelle** und **vorgeschlagen** Zeilenversionen.</span><span class="sxs-lookup"><span data-stu-id="87f4d-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="87f4d-119">Aufrufen von **EndEdit** oder **CancelEdit** nach dem Aufruf **AcceptChanges** oder **RejectChanges** hat keine Auswirkungen, die Bearbeitung ist bereits vorhanden. wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="87f4d-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="87f4d-120">Im folgenden Beispiel wird veranschaulicht, wie **BeginEdit** mit **EndEdit** und **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="87f4d-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="87f4d-121">Im Beispiel wird außerdem überprüft der **ProposedValue** in der **ColumnChanged** Ereignis und entscheidet, ob die Bearbeitung abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="87f4d-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="87f4d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87f4d-122">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataRowVersion>  
 [<span data-ttu-id="87f4d-123">Bearbeiten von Daten in einer DataTable</span><span class="sxs-lookup"><span data-stu-id="87f4d-123">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="87f4d-124">Behandeln von DataTable-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="87f4d-124">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 [<span data-ttu-id="87f4d-125">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="87f4d-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
