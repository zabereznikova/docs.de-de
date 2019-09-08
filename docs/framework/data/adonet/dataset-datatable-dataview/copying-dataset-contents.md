---
title: Kopieren von DataSet-Inhalten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: d8a7762c4ec5d650295ca0626180285723549051
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786514"
---
# <a name="copying-dataset-contents"></a><span data-ttu-id="421eb-102">Kopieren von DataSet-Inhalten</span><span class="sxs-lookup"><span data-stu-id="421eb-102">Copying DataSet Contents</span></span>
<span data-ttu-id="421eb-103">Sie können eine Kopie von <xref:System.Data.DataSet> erstellen, damit Sie mit Daten arbeiten können, ohne dass sich dies auf die ursprünglichen Daten auswirkt, oder mit einer Teilmenge der Daten aus einem **DataSet**arbeiten.</span><span class="sxs-lookup"><span data-stu-id="421eb-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="421eb-104">Beim Kopieren eines **DataSets**können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="421eb-104">When copying a **DataSet**, you can:</span></span>  
  
- <span data-ttu-id="421eb-105">Erstellen Sie eine exakte Kopie des **DataSets**, einschließlich Schema, Daten, Zeilen Zustandsinformationen und Zeilen Versionen.</span><span class="sxs-lookup"><span data-stu-id="421eb-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
- <span data-ttu-id="421eb-106">Erstellen Sie ein **DataSet** , das das Schema eines vorhandenen **DataSets**enthält, aber nur Zeilen, die geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="421eb-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="421eb-107">Sie können alle geänderten Zeilen oder einen bestimmten **DataRowState**-Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="421eb-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="421eb-108">Weitere Informationen zu Zeilen Zuständen finden Sie unter [Zeilen Status und Zeilen Versionen](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="421eb-108">For more information about row states, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
- <span data-ttu-id="421eb-109">Kopieren Sie das Schema oder die relationale Struktur des **DataSets** nur, ohne Zeilen zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="421eb-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="421eb-110">Zeilen können mit <xref:System.Data.DataTable> in eine vorhandene <xref:System.Data.DataTable.ImportRow%2A> importiert werden.</span><span class="sxs-lookup"><span data-stu-id="421eb-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="421eb-111">Verwenden Sie die <xref:System.Data.DataSet.Copy%2A> -Methode des **DataSets**, um eine exakte Kopie des **DataSets** zu erstellen, das sowohl das Schema als auch die Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="421eb-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="421eb-112">Im folgenden Codebeispiel wird gezeigt, wie eine exakte Kopie des **DataSets**erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="421eb-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="421eb-113">Verwenden Sie die<xref:System.Data.DataSet.GetChanges%2A> -Methode des **DataSets**, um eine Kopie eines **DataSets** zu erstellen, das Schema und nur die Daten enthält, die **hinzugefügte**, geänderte oder **Gelöschte** Zeilen darstellen.</span><span class="sxs-lookup"><span data-stu-id="421eb-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="421eb-114">Sie können **GetChanges** auch verwenden, um nur Zeilen mit einem angegebenen Zeilen Status zurückzugeben, indem Sie beim Aufrufen von **GetChanges**einen **DataRowState** -Wert übergeben.</span><span class="sxs-lookup"><span data-stu-id="421eb-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="421eb-115">Im folgenden Codebeispiel wird gezeigt, wie ein **DataRowState** beim Aufrufen von **GetChanges**übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="421eb-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
```vb  
' Copy all changes.  
Dim changeDataSet As DataSet = customerDataSet.GetChanges()  
' Copy only new rows.  
Dim addedDataSetAs DataSet = _  
    customerDataSet.GetChanges(DataRowState.Added)  
```  
  
```csharp  
// Copy all changes.  
DataSet changeDataSet = customerDataSet.GetChanges();  
// Copy only new rows.  
DataSet addedDataSet= customerDataSet.GetChanges(DataRowState.Added);  
```  
  
 <span data-ttu-id="421eb-116">Um eine Kopie eines **DataSets** zu erstellen, das nur das Schema enthält, <xref:System.Data.DataSet.Clone%2A> verwenden Sie die-Methode des **DataSets**.</span><span class="sxs-lookup"><span data-stu-id="421eb-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="421eb-117">Sie können dem geklonten **DataSet** auch vorhandene Zeilen mithilfe der **ImportRow** -Methode der **Daten**Tabelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="421eb-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="421eb-118">**ImportRow** fügt der angegebenen Tabelle Informationen zu Daten, Zeilen Status und Zeilen Version hinzu.</span><span class="sxs-lookup"><span data-stu-id="421eb-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="421eb-119">Spaltenwerte werden nur hinzugefügt, wenn der Spaltenname übereinstimmt und der Datentyp kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="421eb-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="421eb-120">Im folgenden Codebeispiel wird ein Klon eines **DataSets** erstellt und dann die Zeilen aus dem ursprünglichen **DataSet** der **Customers** -Tabelle im **DataSet** -Klon für Kunden hinzugefügt, in der die **CountryRegion** -Spalte den Wert "Deutschland ".</span><span class="sxs-lookup"><span data-stu-id="421eb-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
```vb  
Dim customerDataSet As New DataSet  
        customerDataSet.Tables.Add(New DataTable("Customers"))  
        customerDataSet.Tables("Customers").Columns.Add("Name", GetType(String))  
        customerDataSet.Tables("Customers").Columns.Add("CountryRegion", GetType(String))  
        customerDataSet.Tables("Customers").Rows.Add("Juan", "Spain")  
        customerDataSet.Tables("Customers").Rows.Add("Johann", "Germany")  
        customerDataSet.Tables("Customers").Rows.Add("John", "UK")  
  
Dim germanyCustomers As DataSet = customerDataSet.Clone()  
  
Dim copyRows() As DataRow = _  
  customerDataSet.Tables("Customers").Select("CountryRegion = 'Germany'")  
  
Dim customerTable As DataTable = germanyCustomers.Tables("Customers")  
Dim copyRow As DataRow  
  
For Each copyRow In copyRows  
  customerTable.ImportRow(copyRow)  
Next  
```  
  
```csharp  
DataSet customerDataSet = new DataSet();  
customerDataSet.Tables.Add(new DataTable("Customers"));  
customerDataSet.Tables["Customers"].Columns.Add("Name", typeof(string));  
customerDataSet.Tables["Customers"].Columns.Add("CountryRegion", typeof(string));  
customerDataSet.Tables["Customers"].Rows.Add("Juan", "Spain");  
customerDataSet.Tables["Customers"].Rows.Add("Johann", "Germany");  
customerDataSet.Tables["Customers"].Rows.Add("John", "UK");  
  
DataSet germanyCustomers = customerDataSet.Clone();  
  
DataRow[] copyRows =   
  customerDataSet.Tables["Customers"].Select("CountryRegion = 'Germany'");  
  
DataTable customerTable = germanyCustomers.Tables["Customers"];  
  
foreach (DataRow copyRow in copyRows)  
  customerTable.ImportRow(copyRow);  
```  
  
## <a name="see-also"></a><span data-ttu-id="421eb-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="421eb-121">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="421eb-122">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="421eb-122">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="421eb-123">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="421eb-123">ADO.NET Overview</span></span>](../ado-net-overview.md)
