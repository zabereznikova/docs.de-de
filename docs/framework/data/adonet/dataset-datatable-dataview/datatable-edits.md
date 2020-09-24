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
# <a name="datatable-edits"></a><span data-ttu-id="ca193-102">Bearbeitungen von "DataTable"</span><span class="sxs-lookup"><span data-stu-id="ca193-102">DataTable Edits</span></span>

<span data-ttu-id="ca193-103">Wenn Sie Änderungen der Spaltenwerte in einer <xref:System.Data.DataRow> vornehmen, werden die Änderungen sofort im aktuellen Zustand der Zeile platziert.</span><span class="sxs-lookup"><span data-stu-id="ca193-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="ca193-104"><xref:System.Data.DataRowState>Wird dann auf **modified**festgelegt, und die Änderungen werden mithilfe der-Methode oder der- <xref:System.Data.DataRow.AcceptChanges%2A> <xref:System.Data.DataRow.RejectChanges%2A> Methode der **DataRow**akzeptiert oder abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="ca193-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="ca193-105">Die **DataRow** bietet auch drei Methoden, die Sie verwenden können, um den Zustand der Zeile während der Bearbeitung anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="ca193-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="ca193-106">Diese Methoden sind <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> und <xref:System.Data.DataRow.CancelEdit%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca193-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="ca193-107">Wenn Sie Spaltenwerte in einer **DataRow** direkt ändern, verwaltet die **DataRow** die Spaltenwerte mithilfe der **aktuellen**, der **Standard**-und der **Original** Zeilen Version.</span><span class="sxs-lookup"><span data-stu-id="ca193-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="ca193-108">Zusätzlich zu diesen Zeilen Versionen verwenden die Methoden **BeginEdit**, **EndEdit**und **CancelEdit** eine vierte Zeilen Version: **vorgeschlagen**.</span><span class="sxs-lookup"><span data-stu-id="ca193-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="ca193-109">Weitere Informationen zu Zeilen Versionen finden Sie unter [Zeilen Status und Zeilen Versionen](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="ca193-109">For more information about row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="ca193-110">Die **vorgeschlagene** Zeilen Version ist während eines Bearbeitungsvorgangs vorhanden, der beginnt, indem **BeginEdit** aufgerufen wird, das entweder mithilfe von **EndEdit** oder **CancelEdit** oder durch Aufrufen von ' **Accept Changes** ' oder ' **RejectChanges**' endet.</span><span class="sxs-lookup"><span data-stu-id="ca193-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="ca193-111">Während des Bearbeitungsvorgangs können Sie Validierungs Logik auf einzelne Spalten anwenden, indem Sie den **ProposedValue** im **ColumnChanged** -Ereignis der **Daten**Tabelle auswerten.</span><span class="sxs-lookup"><span data-stu-id="ca193-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="ca193-112">Das **ColumnChanged** -Ereignis enthält **DataColumnChangeEventArgs** , die einen Verweis auf die geänderte Spalte und den Wert " **ProposedValue**" beibehalten.</span><span class="sxs-lookup"><span data-stu-id="ca193-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="ca193-113">Nachdem der vorgeschlagene Wert ausgewertet wurde, kann dieser Wert geändert oder die Bearbeitung abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="ca193-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="ca193-114">Wenn die Bearbeitung beendet ist, wird die Zeile in den Status " **vorgeschlagen** " versetzt.</span><span class="sxs-lookup"><span data-stu-id="ca193-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="ca193-115">Sie können Änderungen überprüfen, indem Sie **EndEdit**aufrufen, oder Sie können Sie durch Aufrufen von **CancelEdit**abbrechen.</span><span class="sxs-lookup"><span data-stu-id="ca193-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="ca193-116">Beachten Sie, dass **EndEdit** Ihre Bearbeitungen bestätigt, dass das **DataSet** die Änderungen erst akzeptiert, wenn " **Accept Changes** " aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ca193-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="ca193-117">Beachten Sie auch Folgendes: Wenn Sie " **akzeptchanges** " vor dem Beenden der Bearbeitung mit **EndEdit** oder **CancelEdit**aufgerufen haben, wird die Bearbeitung beendet, und die **vorgeschlagenen** Zeilen Werte werden sowohl für die **aktuelle** als auch die **ursprüngliche** Zeilen Version akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="ca193-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="ca193-118">Auf dieselbe Weise beendet der Aufruf von **RejectChanges** die Bearbeitung und verwirft die **aktuelle** und **vorgeschlagene** Zeilen Version.</span><span class="sxs-lookup"><span data-stu-id="ca193-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="ca193-119">Der Aufruf von **EndEdit** oder **CancelEdit** nach dem Aufruf von " **Accept Changes** " oder " **RejectChanges** " hat keine Auswirkungen, da die Bearbeitung bereits beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ca193-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="ca193-120">Im folgenden Beispiel wird die Verwendung von **BeginEdit** mit **EndEdit** und **CancelEdit**veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ca193-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="ca193-121">Im Beispiel wird auch der **ProposedValue** im **ColumnChanged** -Ereignis überprüft und entschieden, ob der Bearbeitungsvorgang abgebrochen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ca193-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ca193-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ca193-122">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [<span data-ttu-id="ca193-123">Bearbeiten von Daten in einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="ca193-123">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="ca193-124">Behandeln von DataTable-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="ca193-124">Handling DataTable Events</span></span>](handling-datatable-events.md)
- [<span data-ttu-id="ca193-125">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ca193-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
