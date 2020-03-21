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
# <a name="datatable-edits"></a><span data-ttu-id="c9c61-102">Bearbeitungen von "DataTable"</span><span class="sxs-lookup"><span data-stu-id="c9c61-102">DataTable Edits</span></span>
<span data-ttu-id="c9c61-103">Wenn Sie Änderungen der Spaltenwerte in einer <xref:System.Data.DataRow> vornehmen, werden die Änderungen sofort im aktuellen Zustand der Zeile platziert.</span><span class="sxs-lookup"><span data-stu-id="c9c61-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="c9c61-104">Der <xref:System.Data.DataRowState> wird dann auf **Geändert**festgelegt, und die <xref:System.Data.DataRow.AcceptChanges%2A> <xref:System.Data.DataRow.RejectChanges%2A> Änderungen werden mit den oder Methoden der **DataRow**akzeptiert oder abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="c9c61-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="c9c61-105">**DataRow** bietet außerdem drei Methoden, mit denen Sie den Status der Zeile während der Bearbeitung anhalten können.</span><span class="sxs-lookup"><span data-stu-id="c9c61-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="c9c61-106">Diese Methoden sind <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> und <xref:System.Data.DataRow.CancelEdit%2A>.</span><span class="sxs-lookup"><span data-stu-id="c9c61-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="c9c61-107">Wenn Sie Spaltenwerte in einem **DataRow** direkt ändern, verwaltet **DataRow** die Spaltenwerte mithilfe der Zeilenversionen **Aktuelle**, **Standard**und **Original.**</span><span class="sxs-lookup"><span data-stu-id="c9c61-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="c9c61-108">Zusätzlich zu diesen Zeilenversionen verwenden die Methoden **BeginEdit**, **EndEdit**und **CancelEdit** eine vierte Zeilenversion: **Vorgeschlagen**.</span><span class="sxs-lookup"><span data-stu-id="c9c61-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="c9c61-109">Weitere Informationen zu Zeilenversionen finden Sie unter [Zeilenzustände und Zeilenversionen](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="c9c61-109">For more information about row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="c9c61-110">Die **vorgeschlagene** Zeilenversion ist während eines Bearbeitungsvorgangs vorhanden, der mit dem Aufruf von **BeginEdit** beginnt und entweder mit **EndEdit** oder **CancelEdit** oder mit **AcceptChanges** oder **RejectChanges**endet.</span><span class="sxs-lookup"><span data-stu-id="c9c61-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="c9c61-111">Während des Bearbeitungsvorgangs können Sie Validierungslogik auf einzelne Spalten anwenden, indem Sie den **ProposedValue** im **ColumnChanged-Ereignis** der **DataTable**auswerten.</span><span class="sxs-lookup"><span data-stu-id="c9c61-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="c9c61-112">Das **ColumnChanged-Ereignis** enthält **DataColumnChangeEventArgs,** die einen Verweis auf die Spalte beibehalten, die sich ändert, und auf den **ProposedValue**.</span><span class="sxs-lookup"><span data-stu-id="c9c61-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="c9c61-113">Nachdem der vorgeschlagene Wert ausgewertet wurde, kann dieser Wert geändert oder die Bearbeitung abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="c9c61-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="c9c61-114">Wenn die Bearbeitung beendet ist, wird die Zeile aus dem Status **Vorgeschlagen** verschoben.</span><span class="sxs-lookup"><span data-stu-id="c9c61-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="c9c61-115">Sie können Bearbeitungen bestätigen, indem Sie **EndEdit**aufrufen, oder Sie können sie abbrechen, indem Sie **CancelEdit**aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c9c61-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="c9c61-116">Beachten Sie, dass **EndEdit** zwar Ihre Änderungen bestätigt, das **DataSet** die Änderungen jedoch erst akzeptiert, wenn **AcceptChanges** aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c9c61-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="c9c61-117">Beachten Sie auch, dass, wenn Sie **AcceptChanges** aufrufen, bevor Sie die Bearbeitung mit **EndEdit** oder **CancelEdit**beendet haben, die Bearbeitung beendet wird und die **vorgeschlagenen** Zeilenwerte sowohl für die **aktuelle** als auch für die **ursprüngliche** Zeilenversion akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="c9c61-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="c9c61-118">Auf die gleiche Weise beendet das Aufrufen von **RejectChanges** die Bearbeitung und verwirft die **aktuellen** und **vorgeschlagenen** Zeilenversionen.</span><span class="sxs-lookup"><span data-stu-id="c9c61-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="c9c61-119">Das Aufrufen von **EndEdit** oder **CancelEdit** nach dem Aufrufen von **AcceptChanges** oder **RejectChanges** hat keine Auswirkungen, da die Bearbeitung bereits beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="c9c61-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="c9c61-120">Im folgenden Beispiel wird veranschaulicht, wie **BeginEdit** mit **EndEdit** und **CancelEdit**verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c9c61-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="c9c61-121">Das Beispiel überprüft auch den **ProposedValue** im **ColumnChanged-Ereignis** und entscheidet, ob die Bearbeitung abgebrochen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c9c61-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c9c61-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9c61-122">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [<span data-ttu-id="c9c61-123">Bearbeiten von Daten in einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="c9c61-123">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="c9c61-124">Behandeln von DataTable-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="c9c61-124">Handling DataTable Events</span></span>](handling-datatable-events.md)
- [<span data-ttu-id="c9c61-125">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c9c61-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
