---
title: Anzeigen von Daten in einer "DataTable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: c13f0b802b2714a17ea4014625a65ebd1b0011f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785851"
---
# <a name="viewing-data-in-a-datatable"></a><span data-ttu-id="81dfc-102">Anzeigen von Daten in einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="81dfc-102">Viewing Data in a DataTable</span></span>

<span data-ttu-id="81dfc-103">Sie können <xref:System.Data.DataTable> auf den Inhalt eines-Objekts zugreifen, indem Sie die **Zeilen** -und **Spalten** Auflistungen der **Daten**Tabelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="81dfc-103">You can access the contents of a <xref:System.Data.DataTable> by using the **Rows** and **Columns** collections of the **DataTable**.</span></span> <span data-ttu-id="81dfc-104">Sie können auch die <xref:System.Data.DataTable.Select%2A> -Methode verwenden, um Teilmengen der Daten in einer **Daten** Tabelle nach Kriterien, einschließlich Suchkriterien, Sortierreihenfolge und Zeilen Status, zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="81dfc-104">You can also use the <xref:System.Data.DataTable.Select%2A> method to return subsets of the data in a **DataTable** according to criteria including search criteria, sort order, and row state.</span></span> <span data-ttu-id="81dfc-105">Darüber hinaus können Sie die <xref:System.Data.DataRowCollection.Find%2A> -Methode der **DataRowCollection** verwenden, wenn Sie mithilfe eines Primärschlüssel Werts eine bestimmte Zeile suchen.</span><span class="sxs-lookup"><span data-stu-id="81dfc-105">Additionally, you can use the <xref:System.Data.DataRowCollection.Find%2A> method of the **DataRowCollection** when searching for a particular row using a primary key value.</span></span>

<span data-ttu-id="81dfc-106">Die **Select** -Methode des **Daten** Tabelle-Objekts gibt eine Gruppe <xref:System.Data.DataRow> von-Objekten zurück, die den angegebenen Kriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="81dfc-106">The **Select** method of the **DataTable** object returns a set of <xref:System.Data.DataRow> objects that match the specified criteria.</span></span> <span data-ttu-id="81dfc-107">**Select** führt optionale Argumente eines Filter Ausdrucks, eines Sortierungs Ausdrucks und von **DataViewRowState**aus.</span><span class="sxs-lookup"><span data-stu-id="81dfc-107">**Select** takes optional arguments of a filter expression, sort expression, and **DataViewRowState**.</span></span> <span data-ttu-id="81dfc-108">Der Filter Ausdruck identifiziert, welche Zeilen basierend auf **datacolenumn** -Werten zurückgegeben werden `LastName = 'Smith'`, z. b.</span><span class="sxs-lookup"><span data-stu-id="81dfc-108">The filter expression identifies which rows to return based on **DataColumn** values, such as `LastName = 'Smith'`.</span></span> <span data-ttu-id="81dfc-109">Der Sortierausdruck folgt den Standard-SQL-Konventionen für die Anordnung von Spalten, z. B. `LastName ASC, FirstName ASC`.</span><span class="sxs-lookup"><span data-stu-id="81dfc-109">The sort expression follows standard SQL conventions for ordering columns, for example `LastName ASC, FirstName ASC`.</span></span> <span data-ttu-id="81dfc-110">Regeln zum Schreiben von Ausdrücken finden Sie unter <xref:System.Data.DataColumn.Expression%2A> der-Eigenschaft der **datacolenumn** -Klasse.</span><span class="sxs-lookup"><span data-stu-id="81dfc-110">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>

> [!TIP]
> <span data-ttu-id="81dfc-111">Wenn Sie eine Reihe von Aufrufen der **Select** -Methode einer **Daten**Tabelle ausführen, können Sie die Leistung steigern, indem Sie zuerst einen <xref:System.Data.DataView> für die **Daten**Tabelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="81dfc-111">If you are performing a number of calls to the **Select** method of a **DataTable**, you can increase performance by first creating a <xref:System.Data.DataView> for the **DataTable**.</span></span> <span data-ttu-id="81dfc-112">Beim Erstellen der **DataView** werden die Zeilen der Tabelle indiziert.</span><span class="sxs-lookup"><span data-stu-id="81dfc-112">Creating the **DataView** indexes the rows of the table.</span></span> <span data-ttu-id="81dfc-113">Die **Select** -Methode verwendet dann diesen Index, wodurch die Zeit zum Generieren des Abfrage Ergebnisses erheblich reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="81dfc-113">The **Select** method then uses that index, significantly reducing the time to generate the query result.</span></span> <span data-ttu-id="81dfc-114">Weitere Informationen zum Erstellen einer **DataView** für eine **Daten**Tabelle finden Sie unter [DataViews](dataviews.md).</span><span class="sxs-lookup"><span data-stu-id="81dfc-114">For information about creating a **DataView** for a **DataTable**, see [DataViews](dataviews.md).</span></span>

<span data-ttu-id="81dfc-115">Die **Select** -Methode bestimmt, welche Version der Zeilen basierend auf einem <xref:System.Data.DataViewRowState>angezeigt oder bearbeitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="81dfc-115">The **Select** method determines which version of the rows to view or manipulate based on a <xref:System.Data.DataViewRowState>.</span></span> <span data-ttu-id="81dfc-116">In der folgenden Tabelle werden die möglichen **DataViewRowState** -Enumerationswerte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="81dfc-116">The following table describes the possible **DataViewRowState** enumeration values.</span></span>

|<span data-ttu-id="81dfc-117">"DataViewRowState"-Wert</span><span class="sxs-lookup"><span data-stu-id="81dfc-117">DataViewRowState value</span></span>|<span data-ttu-id="81dfc-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81dfc-118">Description</span></span>|
|----------------------------|-----------------|
|<span data-ttu-id="81dfc-119">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="81dfc-119">**CurrentRows**</span></span>|<span data-ttu-id="81dfc-120">Aktuelle Zeilen, einschließlich nicht geänderter, hinzugefügter und geänderter Zeilen.</span><span class="sxs-lookup"><span data-stu-id="81dfc-120">Current rows including unchanged, added, and modified rows.</span></span>|
|<span data-ttu-id="81dfc-121">**Lö**</span><span class="sxs-lookup"><span data-stu-id="81dfc-121">**Deleted**</span></span>|<span data-ttu-id="81dfc-122">Eine gelöschte Zeile.</span><span class="sxs-lookup"><span data-stu-id="81dfc-122">A deleted row.</span></span>|
|<span data-ttu-id="81dfc-123">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="81dfc-123">**ModifiedCurrent**</span></span>|<span data-ttu-id="81dfc-124">Eine aktuelle Version, die eine geänderte Version der ursprünglichen Daten darstellt.</span><span class="sxs-lookup"><span data-stu-id="81dfc-124">A current version, which is a modified version of original data.</span></span> <span data-ttu-id="81dfc-125">(Siehe **ModifiedOriginal**.)</span><span class="sxs-lookup"><span data-stu-id="81dfc-125">(See **ModifiedOriginal**.)</span></span>|
|<span data-ttu-id="81dfc-126">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="81dfc-126">**ModifiedOriginal**</span></span>|<span data-ttu-id="81dfc-127">Die ursprüngliche Version aller geänderten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="81dfc-127">The original version of all modified rows.</span></span> <span data-ttu-id="81dfc-128">Die aktuelle Version ist mit **ModifiedCurrent**verfügbar.</span><span class="sxs-lookup"><span data-stu-id="81dfc-128">The current version is available using **ModifiedCurrent**.</span></span>|
|<span data-ttu-id="81dfc-129">**Hinzugefügt**</span><span class="sxs-lookup"><span data-stu-id="81dfc-129">**Added**</span></span>|<span data-ttu-id="81dfc-130">Eine neue Zeile.</span><span class="sxs-lookup"><span data-stu-id="81dfc-130">A new row.</span></span>|
|<span data-ttu-id="81dfc-131">**Keine**</span><span class="sxs-lookup"><span data-stu-id="81dfc-131">**None**</span></span>|<span data-ttu-id="81dfc-132">Keine</span><span class="sxs-lookup"><span data-stu-id="81dfc-132">None.</span></span>|
|<span data-ttu-id="81dfc-133">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="81dfc-133">**OriginalRows**</span></span>|<span data-ttu-id="81dfc-134">Ursprüngliche Zeilen, einschließlich nicht geänderter und gelöschter Zeilen.</span><span class="sxs-lookup"><span data-stu-id="81dfc-134">Original rows, including unchanged and deleted rows.</span></span>|
|<span data-ttu-id="81dfc-135">**Unverändert**</span><span class="sxs-lookup"><span data-stu-id="81dfc-135">**Unchanged**</span></span>|<span data-ttu-id="81dfc-136">Eine nicht geänderte Zeile.</span><span class="sxs-lookup"><span data-stu-id="81dfc-136">An unchanged row.</span></span>|

<span data-ttu-id="81dfc-137">Im folgenden Beispiel wird das **DataSet** -Objekt so gefiltert, dass Sie nur mit Zeilen arbeiten, deren **DataViewRowState** auf **CurrentRows**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="81dfc-137">In the following example, the **DataSet** object is filtered so that you are only working with rows whose **DataViewRowState** is set to **CurrentRows**.</span></span>

```vb
Dim column As DataColumn
Dim row As DataRow

Dim currentRows() As DataRow = _
    workTable.Select(Nothing, Nothing, DataViewRowState.CurrentRows)

If (currentRows.Length < 1 ) Then
  Console.WriteLine("No Current Rows Found")
Else
  For Each column in workTable.Columns
    Console.Write(vbTab & column.ColumnName)
  Next

  Console.WriteLine(vbTab & "RowState")

  For Each row In currentRows
    For Each column In workTable.Columns
      Console.Write(vbTab & row(column).ToString())
    Next

    Dim rowState As String = _
        System.Enum.GetName(row.RowState.GetType(), row.RowState)
    Console.WriteLine(vbTab & rowState)
  Next
End If
```

```csharp
DataRow[] currentRows = workTable.Select(
    null, null, DataViewRowState.CurrentRows);

if (currentRows.Length < 1 )
  Console.WriteLine("No Current Rows Found");
else
{
  foreach (DataColumn column in workTable.Columns)
    Console.Write("\t{0}", column.ColumnName);

  Console.WriteLine("\tRowState");

  foreach (DataRow row in currentRows)
  {
    foreach (DataColumn column in workTable.Columns)
      Console.Write("\t{0}", row[column]);

    Console.WriteLine("\t" + row.RowState);
  }
}
```

<span data-ttu-id="81dfc-138">Die **Select** -Methode kann verwendet werden, um Zeilen mit unterschiedlichen **RowState** -Werten oder Feldwerten zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="81dfc-138">The **Select** method can be used to return rows with differing **RowState** values or field values.</span></span> <span data-ttu-id="81dfc-139">Im folgenden Beispiel wird ein **DataRow** -Array zurückgegeben, das auf alle gelöschten Zeilen verweist, und es wird ein weiteres **DataRow** -Array zurückgegeben, das auf alle Zeilen verweist, geordnet nach **CustLName**, wobei die **CustId-** Spalte größer als 5 ist.</span><span class="sxs-lookup"><span data-stu-id="81dfc-139">The following example returns a **DataRow** array that references all rows that have been deleted, and returns another **DataRow** array that references all rows, ordered by **CustLName**, where the **CustID** column is greater than 5.</span></span> <span data-ttu-id="81dfc-140">Informationen dazu, wie Sie die Informationen in der **gelöschten** Zeile anzeigen, finden Sie unter [Zeilen Status und Zeilen Versionen](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="81dfc-140">For information about how to view the information in the **Deleted** row, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>

```vb
' Retrieve all deleted rows.
Dim deletedRows() As DataRow = workTable.Select(Nothing, Nothing, DataViewRowState.Deleted)

' Retrieve rows where CustID > 5, and order by CustLName.
Dim custRows() As DataRow = workTable.Select( _
    "CustID > 5", "CustLName ASC")
```

```csharp
// Retrieve all deleted rows.
DataRow[] deletedRows = workTable.Select(
    null, null, DataViewRowState.Deleted);

// Retrieve rows where CustID > 5, and order by CustLName.
DataRow[] custRows = workTable.Select("CustID > 5", "CustLName ASC");
```

## <a name="see-also"></a><span data-ttu-id="81dfc-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81dfc-141">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataViewRowState>
- [<span data-ttu-id="81dfc-142">Bearbeiten von Daten in einer DataTable</span><span class="sxs-lookup"><span data-stu-id="81dfc-142">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="81dfc-143">Zeilenstatus und Zeilenversionen</span><span class="sxs-lookup"><span data-stu-id="81dfc-143">Row States and Row Versions</span></span>](row-states-and-row-versions.md)
- [<span data-ttu-id="81dfc-144">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="81dfc-144">ADO.NET Overview</span></span>](../ado-net-overview.md)
