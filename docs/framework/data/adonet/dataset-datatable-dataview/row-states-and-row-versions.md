---
title: Zeilenstatus und Zeilenversionen
ms.date: 07/19/2018
dev_langs:
- csharp
- vb
ms.assetid: 2e6642c9-bfc6-425c-b3a7-e4912ffa6c1f
ms.openlocfilehash: 1b80ae78fad22989f99fb1e992d4978a192e0c66
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204527"
---
# <a name="row-states-and-row-versions"></a><span data-ttu-id="31e3e-102">Zeilenstatus und Zeilenversionen</span><span class="sxs-lookup"><span data-stu-id="31e3e-102">Row States and Row Versions</span></span>

<span data-ttu-id="31e3e-103">ADO.NET verwaltet Zeilen in Tabellen mithilfe des Zeilenstatus und der Zeilenversion.</span><span class="sxs-lookup"><span data-stu-id="31e3e-103">ADO.NET manages rows in tables using row states and versions.</span></span> <span data-ttu-id="31e3e-104">Ein Zeilenstatus gibt den Status einer Zeile an. In Zeilenversionen werden die Werte, die in einer Zeile gespeichert werden, während der Bearbeitung verwaltet. Zu diesen Werten zählen z. B. die Werte current, original und default.</span><span class="sxs-lookup"><span data-stu-id="31e3e-104">A row state indicates the status of a row; row versions maintain the values stored in a row as it is modified, including current, original, and default values.</span></span> <span data-ttu-id="31e3e-105">Wenn Sie beispielsweise eine Spalte in einer Zeile geändert haben, weist die Zeile den Zeilenstatus `Modified` und die folgenden beiden Zeilenversionen auf: `Current` mit den aktuellen Zeilenwerten und `Original` mit den Zeilenwerten vor den Änderungen der Spalte.</span><span class="sxs-lookup"><span data-stu-id="31e3e-105">For example, after you have made a modification to a column in a row, the row will have a row state of `Modified`, and two row versions: `Current`, which contains the current row values, and `Original`, which contains the row values before the column was modified.</span></span>  
  
 <span data-ttu-id="31e3e-106">Jedes <xref:System.Data.DataRow>-Objekt hat eine <xref:System.Data.DataRow.RowState%2A>-Eigenschaft, über die Sie den aktuellen Status der Zeile überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="31e3e-106">Each <xref:System.Data.DataRow> object has a <xref:System.Data.DataRow.RowState%2A> property that you can examine to determine the current state of the row.</span></span> <span data-ttu-id="31e3e-107">Die folgende Tabelle enthält eine kurze Beschreibung aller `RowState`-Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="31e3e-107">The following table gives a brief description of each `RowState` enumeration value.</span></span>  
  
|<span data-ttu-id="31e3e-108">"RowState"-Wert</span><span class="sxs-lookup"><span data-stu-id="31e3e-108">RowState value</span></span>|<span data-ttu-id="31e3e-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31e3e-109">Description</span></span>|  
|--------------------|-----------------|  
|<xref:System.Data.DataRowState.Unchanged>|<span data-ttu-id="31e3e-110">Seit dem letzten Aufruf von `AcceptChanges` oder seit der Erstellung der Zeile durch `DataAdapter.Fill` wurden keine Änderungen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="31e3e-110">No changes have been made since the last call to `AcceptChanges` or since the row was created by `DataAdapter.Fill`.</span></span>|  
|<xref:System.Data.DataRowState.Added>|<span data-ttu-id="31e3e-111">Die Zeile wurde der Tabelle hinzugefügt, `AcceptChanges` wurde aber nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="31e3e-111">The row has been added to the table, but `AcceptChanges` has not been called.</span></span>|  
|<xref:System.Data.DataRowState.Modified>|<span data-ttu-id="31e3e-112">Ein Element der Zeile wurde geändert.</span><span class="sxs-lookup"><span data-stu-id="31e3e-112">Some element of the row has been changed.</span></span>|  
|<xref:System.Data.DataRowState.Deleted>|<span data-ttu-id="31e3e-113">Die Zeile wurde aus einer Tabelle gelöscht, und `AcceptChanges` wurde nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="31e3e-113">The row has been deleted from a table, and `AcceptChanges` has not been called.</span></span>|  
|<xref:System.Data.DataRowState.Detached>|<span data-ttu-id="31e3e-114">Die Zeile ist nicht Teil einer `DataRowCollection`.</span><span class="sxs-lookup"><span data-stu-id="31e3e-114">The row is not part of any `DataRowCollection`.</span></span> <span data-ttu-id="31e3e-115">Der `RowState` einer neu erstellten Zeile wird auf `Detached` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="31e3e-115">The `RowState` of a newly created row is set to `Detached`.</span></span> <span data-ttu-id="31e3e-116">Nach dem Hinzufügen der neuen `DataRow` zur `DataRowCollection` durch Aufrufen der `Add`-Methode wird der Wert der `RowState`-Eigenschaft auf `Added` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="31e3e-116">After the new `DataRow` is added to the `DataRowCollection` by calling the `Add` method, the value of the `RowState` property is set to `Added`.</span></span><br /><br /> <span data-ttu-id="31e3e-117">`Detached` wird auch für eine Zeile festgelegt, die mit der `DataRowCollection`-Methode bzw. mit der `Remove`-Methode, gefolgt von der `Delete`-Methode, aus einer `AcceptChanges` entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="31e3e-117">`Detached` is also set for a row that has been removed from a `DataRowCollection` using the `Remove` method, or by the `Delete` method followed by the `AcceptChanges` method.</span></span>|  
  
 <span data-ttu-id="31e3e-118">Wenn `AcceptChanges` für einen <xref:System.Data.DataSet>, eine <xref:System.Data.DataTable> oder eine <xref:System.Data.DataRow> aufgerufen wird, werden alle Zeilen mit dem Zeilenstatus `Deleted` entfernt.</span><span class="sxs-lookup"><span data-stu-id="31e3e-118">When `AcceptChanges` is called on a <xref:System.Data.DataSet>, <xref:System.Data.DataTable> , or <xref:System.Data.DataRow>, all rows with a row state of `Deleted` are removed.</span></span> <span data-ttu-id="31e3e-119">Die verbleibenden Zeilen erhalten den Zeilenstatus `Unchanged`, und die Werte in der Zeilenversion `Original` werden mit den Werten der Zeilenversion `Current` überschrieben.</span><span class="sxs-lookup"><span data-stu-id="31e3e-119">The remaining rows are given a row state of `Unchanged`, and the values in the `Original` row version are overwritten with the `Current` row version values.</span></span> <span data-ttu-id="31e3e-120">Wenn `RejectChanges` aufgerufen wird, werden alle Zeilen mit dem Zeilenstatus `Added` entfernt.</span><span class="sxs-lookup"><span data-stu-id="31e3e-120">When `RejectChanges` is called, all rows with a row state of `Added` are removed.</span></span> <span data-ttu-id="31e3e-121">Die verbleibenden Zeilen erhalten den Zeilenstatus `Unchanged`, und die Werte in der Zeilenversion `Current` werden mit den Werten der Zeilenversion `Original` überschrieben.</span><span class="sxs-lookup"><span data-stu-id="31e3e-121">The remaining rows are given a row state of `Unchanged`, and the values in the `Current` row version are overwritten with the `Original` row version values.</span></span>  
  
 <span data-ttu-id="31e3e-122">Sie können die verschiedenen Zeilenversionen einer Zeile anzeigen, indem Sie einen <xref:System.Data.DataRowVersion>-Parameter mit dem Spaltenverweis übergeben. Dies wird im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="31e3e-122">You can view the different row versions of a row by passing a <xref:System.Data.DataRowVersion> parameter with the column reference, as shown in the following example.</span></span>  
  
```vb  
Dim custRow As DataRow = custTable.Rows(0)  
Dim custID As String = custRow("CustomerID", DataRowVersion.Original).ToString()  
```  
  
```csharp  
DataRow custRow = custTable.Rows[0];  
string custID = custRow["CustomerID", DataRowVersion.Original].ToString();  
```  
  
 <span data-ttu-id="31e3e-123">Die folgende Tabelle enthält eine kurze Beschreibung aller `DataRowVersion`-Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="31e3e-123">The following table gives a brief description of each `DataRowVersion` enumeration value.</span></span>  
  
|<span data-ttu-id="31e3e-124">"DataRowVersion"-Wert</span><span class="sxs-lookup"><span data-stu-id="31e3e-124">DataRowVersion value</span></span>|<span data-ttu-id="31e3e-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31e3e-125">Description</span></span>|  
|--------------------------|-----------------|  
|<xref:System.Data.DataRowVersion.Current>|<span data-ttu-id="31e3e-126">Die aktuellen Werte der Zeile.</span><span class="sxs-lookup"><span data-stu-id="31e3e-126">The current values for the row.</span></span> <span data-ttu-id="31e3e-127">Diese Zeilenversion ist für Zeilen, deren `RowState` auf `Deleted` festgelegt ist, nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="31e3e-127">This row version does not exist for rows with a `RowState` of `Deleted`.</span></span>|  
|<xref:System.Data.DataRowVersion.Default>|<span data-ttu-id="31e3e-128">Die Standardzeilenversion einer bestimmten Zeile.</span><span class="sxs-lookup"><span data-stu-id="31e3e-128">The default row version for a particular row.</span></span> <span data-ttu-id="31e3e-129">Die Standardzeilenversion für eine Zeile mit dem Status `Added`, `Modified` oder `Deleted` lautet `Current`.</span><span class="sxs-lookup"><span data-stu-id="31e3e-129">The default row version for an `Added`, `Modified`, or `Deleted` row is `Current`.</span></span> <span data-ttu-id="31e3e-130">Die Standardzeilenversion für eine Zeile mit dem Status `Detached` lautet `Proposed`.</span><span class="sxs-lookup"><span data-stu-id="31e3e-130">The default row version for a `Detached` row is `Proposed`.</span></span>|  
|<xref:System.Data.DataRowVersion.Original>|<span data-ttu-id="31e3e-131">Die ursprünglichen Werte der Zeile.</span><span class="sxs-lookup"><span data-stu-id="31e3e-131">The original values for the row.</span></span> <span data-ttu-id="31e3e-132">Diese Zeilenversion ist für Zeilen, deren `RowState` auf `Added` festgelegt ist, nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="31e3e-132">This row version does not exist for rows with a `RowState` of `Added`.</span></span>|  
|<xref:System.Data.DataRowVersion.Proposed>|<span data-ttu-id="31e3e-133">Die vorgeschlagenen Werte für die Zeile.</span><span class="sxs-lookup"><span data-stu-id="31e3e-133">The proposed values for the row.</span></span> <span data-ttu-id="31e3e-134">Diese Zeilenversion ist während der Bearbeitung einer Zeile vorhanden oder wird für Zeilen verwendet, die nicht Teil einer `DataRowCollection` sind.</span><span class="sxs-lookup"><span data-stu-id="31e3e-134">This row version exists during an edit operation on a row, or for a row that is not part of a `DataRowCollection`.</span></span>|  
  
 <span data-ttu-id="31e3e-135">Sie können überprüfen, ob eine `DataRow` eine bestimmte Zeilenversion aufweist, indem Sie die <xref:System.Data.DataRow.HasVersion%2A>-Methode aufrufen und eine `DataRowVersion` als Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="31e3e-135">You can test whether a `DataRow` has a particular row version by calling the <xref:System.Data.DataRow.HasVersion%2A> method and passing a `DataRowVersion` as an argument.</span></span> <span data-ttu-id="31e3e-136">So gibt z. B. `DataRow.HasVersion(DataRowVersion.Original)` für neu hinzugefügte Zeilen vor dem Aufrufen von `false` den Wert `AcceptChanges` zurück.</span><span class="sxs-lookup"><span data-stu-id="31e3e-136">For example, `DataRow.HasVersion(DataRowVersion.Original)` will return `false` for newly added rows before `AcceptChanges` has been called.</span></span>  
  
 <span data-ttu-id="31e3e-137">Im folgenden Codebeispiel werden die Werte in allen gelöschten Zeilen einer Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="31e3e-137">The following code example displays the values in all the deleted rows of a table.</span></span> <span data-ttu-id="31e3e-138">`Deleted`-Zeilen haben keine `Current`-Zeilenversion. Deshalb müssen Sie beim Zugriff auf die Spaltenwerte `DataRowVersion.Original` übergeben.</span><span class="sxs-lookup"><span data-stu-id="31e3e-138">`Deleted` rows do not have a `Current` row version, so you must pass `DataRowVersion.Original` when accessing the column values.</span></span>  
  
```vb  
Dim catTable As DataTable = catDS.Tables("Categories")  
  
Dim delRows() As DataRow = catTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
Console.WriteLine("Deleted rows:" & vbCrLf)  
  
Dim catCol As DataColumn  
Dim delRow As DataRow  
  
For Each catCol In catTable.Columns  
  Console.Write(catCol.ColumnName & vbTab)  
Next  
Console.WriteLine()  
  
For Each delRow In delRows  
  For Each catCol In catTable.Columns  
    Console.Write(delRow(catCol, DataRowVersion.Original) & vbTab)  
  Next  
  Console.WriteLine()  
Next  
```  
  
```csharp  
DataTable catTable = catDS.Tables["Categories"];  
  
DataRow[] delRows = catTable.Select(null, null, DataViewRowState.Deleted);  
  
Console.WriteLine("Deleted rows:\n");  
  
foreach (DataColumn catCol in catTable.Columns)  
  Console.Write(catCol.ColumnName + "\t");  
Console.WriteLine();  
  
foreach (DataRow delRow in delRows)  
{  
  foreach (DataColumn catCol in catTable.Columns)  
    Console.Write(delRow[catCol, DataRowVersion.Original] + "\t");  
  Console.WriteLine();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="31e3e-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="31e3e-139">See also</span></span>

- [<span data-ttu-id="31e3e-140">Bearbeiten von Daten in einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="31e3e-140">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="31e3e-141">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="31e3e-141">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="31e3e-142">"DataAdapters" und "DataReaders"</span><span class="sxs-lookup"><span data-stu-id="31e3e-142">DataAdapters and DataReaders</span></span>](../dataadapters-and-datareaders.md)
- [<span data-ttu-id="31e3e-143">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="31e3e-143">ADO.NET Overview</span></span>](../ado-net-overview.md)
