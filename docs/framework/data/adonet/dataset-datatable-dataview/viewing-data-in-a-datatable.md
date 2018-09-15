---
title: Anzeigen von Daten in einer "DataTable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: de745633060dd4f7b1610492d0ff57ec7a4f545b
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615780"
---
# <a name="viewing-data-in-a-datatable"></a><span data-ttu-id="7114a-102">Anzeigen von Daten in einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="7114a-102">Viewing Data in a DataTable</span></span>
<span data-ttu-id="7114a-103">Sie können den Inhalt zugreifen eine <xref:System.Data.DataTable> mithilfe der **Zeilen** und **Spalten** Sammlungen von der **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="7114a-103">You can access the contents of a <xref:System.Data.DataTable> by using the **Rows** and **Columns** collections of the **DataTable**.</span></span> <span data-ttu-id="7114a-104">Sie können auch die <xref:System.Data.DataTable.Select%2A> Methode zum Zurückgeben von Teilmengen der Daten in eine **DataTable** gemäß bestimmten Kriterien einschließlich Suchkriterien, Sortierreihenfolge und Zeilenstatus.</span><span class="sxs-lookup"><span data-stu-id="7114a-104">You can also use the <xref:System.Data.DataTable.Select%2A> method to return subsets of the data in a **DataTable** according to criteria including search criteria, sort order, and row state.</span></span> <span data-ttu-id="7114a-105">Darüber hinaus können Sie mithilfe der <xref:System.Data.DataRowCollection.Find%2A> Methode der **DataRowCollection** bei der Suche nach einer bestimmten Zeile, die einen primären Schlüsselwert verwenden.</span><span class="sxs-lookup"><span data-stu-id="7114a-105">Additionally, you can use the <xref:System.Data.DataRowCollection.Find%2A> method of the **DataRowCollection** when searching for a particular row using a primary key value.</span></span>  
  
 <span data-ttu-id="7114a-106">Der **wählen** Methode der **DataTable** -Objekt zurückgibt, eine Reihe von <xref:System.Data.DataRow> Objekte, die den angegebenen Kriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="7114a-106">The **Select** method of the **DataTable** object returns a set of <xref:System.Data.DataRow> objects that match the specified criteria.</span></span> <span data-ttu-id="7114a-107">**Wählen Sie** verwendet optionale Argumente eines Filterausdrucks, Sortierausdrucks und **DataViewRowState**.</span><span class="sxs-lookup"><span data-stu-id="7114a-107">**Select** takes optional arguments of a filter expression, sort expression, and **DataViewRowState**.</span></span> <span data-ttu-id="7114a-108">Der Filterausdruck gibt, welche Zeilen basierend auf zurückzugebenden **DataColumn** Werte, z. B. `LastName = 'Smith'`.</span><span class="sxs-lookup"><span data-stu-id="7114a-108">The filter expression identifies which rows to return based on **DataColumn** values, such as `LastName = 'Smith'`.</span></span> <span data-ttu-id="7114a-109">Der Sortierausdruck folgt den Standard-SQL-Konventionen für die Anordnung von Spalten, z. B. `LastName ASC, FirstName ASC`.</span><span class="sxs-lookup"><span data-stu-id="7114a-109">The sort expression follows standard SQL conventions for ordering columns, for example `LastName ASC, FirstName ASC`.</span></span> <span data-ttu-id="7114a-110">Regeln zum Schreiben von Ausdrücken finden Sie unter den <xref:System.Data.DataColumn.Expression%2A> Eigenschaft der **DataColumn** Klasse.</span><span class="sxs-lookup"><span data-stu-id="7114a-110">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="7114a-111">Wenn Sie eine Anzahl von Aufrufen zum Ausführen der **wählen** -Methode der eine **DataTable**, Sie können die Leistung erhöhen, indem Sie zunächst eine <xref:System.Data.DataView> für die **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="7114a-111">If you are performing a number of calls to the **Select** method of a **DataTable**, you can increase performance by first creating a <xref:System.Data.DataView> for the **DataTable**.</span></span> <span data-ttu-id="7114a-112">Erstellen der **DataView** indiziert die Zeilen der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7114a-112">Creating the **DataView** indexes the rows of the table.</span></span> <span data-ttu-id="7114a-113">Die **wählen** Methode dann Abfrageergebnisses, die indiziert werden, erheblich reduzieren die Zeit, um das Abfrageergebnis zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="7114a-113">The **Select** method then usees that index, significantly reducing the time to generate the query result.</span></span> <span data-ttu-id="7114a-114">Informationen zum Erstellen einer **DataView** für eine **DataTable**, finden Sie unter ["DataViews"](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span><span class="sxs-lookup"><span data-stu-id="7114a-114">For information about creating a **DataView** for a **DataTable**, see [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span></span>  
  
 <span data-ttu-id="7114a-115">Die **wählen** Methode bestimmt, welche Version der Zeilen, die anzeigen oder ändern auf Basis einer <xref:System.Data.DataViewRowState>.</span><span class="sxs-lookup"><span data-stu-id="7114a-115">The **Select** method determines which version of the rows to view or manipulate based on a <xref:System.Data.DataViewRowState>.</span></span> <span data-ttu-id="7114a-116">Die folgende Tabelle beschreibt die möglichen **DataViewRowState** -Enumerationswerte fest.</span><span class="sxs-lookup"><span data-stu-id="7114a-116">The following table describes the possible **DataViewRowState** enumeration values.</span></span>  
  
|<span data-ttu-id="7114a-117">"DataViewRowState"-Wert</span><span class="sxs-lookup"><span data-stu-id="7114a-117">DataViewRowState value</span></span>|<span data-ttu-id="7114a-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7114a-118">Description</span></span>|  
|----------------------------|-----------------|  
|<span data-ttu-id="7114a-119">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="7114a-119">**CurrentRows**</span></span>|<span data-ttu-id="7114a-120">Aktuelle Zeilen, einschließlich nicht geänderter, hinzugefügter und geänderter Zeilen.</span><span class="sxs-lookup"><span data-stu-id="7114a-120">Current rows including unchanged, added, and modified rows.</span></span>|  
|<span data-ttu-id="7114a-121">**Gelöscht**</span><span class="sxs-lookup"><span data-stu-id="7114a-121">**Deleted**</span></span>|<span data-ttu-id="7114a-122">Eine gelöschte Zeile.</span><span class="sxs-lookup"><span data-stu-id="7114a-122">A deleted row.</span></span>|  
|<span data-ttu-id="7114a-123">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="7114a-123">**ModifiedCurrent**</span></span>|<span data-ttu-id="7114a-124">Eine aktuelle Version, die eine geänderte Version der ursprünglichen Daten darstellt.</span><span class="sxs-lookup"><span data-stu-id="7114a-124">A current version, which is a modified version of original data.</span></span> <span data-ttu-id="7114a-125">(Finden Sie unter **ModifiedOriginal**.)</span><span class="sxs-lookup"><span data-stu-id="7114a-125">(See **ModifiedOriginal**.)</span></span>|  
|<span data-ttu-id="7114a-126">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="7114a-126">**ModifiedOriginal**</span></span>|<span data-ttu-id="7114a-127">Die ursprüngliche Version aller geänderten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="7114a-127">The original version of all modified rows.</span></span> <span data-ttu-id="7114a-128">Die aktuelle Version ist verfügbar mit **ModifiedCurrent**.</span><span class="sxs-lookup"><span data-stu-id="7114a-128">The current version is available using **ModifiedCurrent**.</span></span>|  
|<span data-ttu-id="7114a-129">**Hinzugefügt**</span><span class="sxs-lookup"><span data-stu-id="7114a-129">**Added**</span></span>|<span data-ttu-id="7114a-130">Eine neue Zeile.</span><span class="sxs-lookup"><span data-stu-id="7114a-130">A new row.</span></span>|  
|<span data-ttu-id="7114a-131">**Keine**</span><span class="sxs-lookup"><span data-stu-id="7114a-131">**None**</span></span>|<span data-ttu-id="7114a-132">Keine</span><span class="sxs-lookup"><span data-stu-id="7114a-132">None.</span></span>|  
|<span data-ttu-id="7114a-133">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="7114a-133">**OriginalRows**</span></span>|<span data-ttu-id="7114a-134">Ursprüngliche Zeilen, einschließlich nicht geänderter und gelöschter Zeilen.</span><span class="sxs-lookup"><span data-stu-id="7114a-134">Original rows, including unchanged and deleted rows.</span></span>|  
|<span data-ttu-id="7114a-135">**unverändert**</span><span class="sxs-lookup"><span data-stu-id="7114a-135">**Unchanged**</span></span>|<span data-ttu-id="7114a-136">Eine nicht geänderte Zeile.</span><span class="sxs-lookup"><span data-stu-id="7114a-136">An unchanged row.</span></span>|  
  
 <span data-ttu-id="7114a-137">Im folgenden Beispiel die **DataSet** das Objekt wird gefiltert, sodass nur Zeilen, deren Arbeit mit **DataViewRowState** nastaven NA hodnotu **CurrentRows**.</span><span class="sxs-lookup"><span data-stu-id="7114a-137">In the following example, the **DataSet** object is filtered so that you are only working with rows whose **DataViewRowState** is set to **CurrentRows**.</span></span>  
  
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
  
 <span data-ttu-id="7114a-138">Die **wählen** Methode kann verwendet werden, um das Zurückgeben von Zeilen mit abweichenden **RowState** -Werten oder Feldwerten.</span><span class="sxs-lookup"><span data-stu-id="7114a-138">The **Select** method can be used to return rows with differing **RowState** values or field values.</span></span> <span data-ttu-id="7114a-139">Das folgende Beispiel gibt eine **DataRow** Array, das alle Zeilen verweist, wurde gelöscht, und eine andere **DataRow** Array, das alle Zeilen verweist, geordnet nach **CustLName**, wobei die **CustID** Spalte größer als 5 ist.</span><span class="sxs-lookup"><span data-stu-id="7114a-139">The following example returns a **DataRow** array that references all rows that have been deleted, and returns another **DataRow** array that references all rows, ordered by **CustLName**, where the **CustID** column is greater than 5.</span></span> <span data-ttu-id="7114a-140">Informationen zum Anzeigen von Informationen in den **gelöschte** Zeile, finden Sie unter [Zeilenstatus und Zeilenversionen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="7114a-140">For information about how to view the information in the **Deleted** row, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7114a-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7114a-141">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataViewRowState>  
 [<span data-ttu-id="7114a-142">Bearbeiten von Daten in einer DataTable</span><span class="sxs-lookup"><span data-stu-id="7114a-142">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="7114a-143">Zeilenstatus und Zeilenversionen</span><span class="sxs-lookup"><span data-stu-id="7114a-143">Row States and Row Versions</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 [<span data-ttu-id="7114a-144">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="7114a-144">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
