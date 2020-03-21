---
title: Kopieren von DataSet-Inhalten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: de13e07eb5c19b8beffa724fec4a128c418a4fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151363"
---
# <a name="copying-dataset-contents"></a><span data-ttu-id="07983-102">Kopieren von DataSet-Inhalten</span><span class="sxs-lookup"><span data-stu-id="07983-102">Copying DataSet Contents</span></span>
<span data-ttu-id="07983-103">Sie können eine Kopie <xref:System.Data.DataSet> eines erstellen, sodass Sie mit Daten arbeiten können, ohne die ursprünglichen Daten zu beeinflussen, oder mit einer Teilmenge der Daten aus einem **DataSet**arbeiten.</span><span class="sxs-lookup"><span data-stu-id="07983-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="07983-104">Beim Kopieren eines **DataSets**können Sie:</span><span class="sxs-lookup"><span data-stu-id="07983-104">When copying a **DataSet**, you can:</span></span>  
  
- <span data-ttu-id="07983-105">Erstellen Sie eine exakte Kopie des **DataSet**, einschließlich des Schemas, der Daten, der Zeilenstatusinformationen und der Zeilenversionen.</span><span class="sxs-lookup"><span data-stu-id="07983-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
- <span data-ttu-id="07983-106">Erstellen Sie ein **DataSet,** das das Schema eines vorhandenen **DataSets**enthält, jedoch nur Zeilen, die geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="07983-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="07983-107">Sie können alle geänderten Zeilen zurückgeben oder einen bestimmten **DataRowState**angeben.</span><span class="sxs-lookup"><span data-stu-id="07983-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="07983-108">Weitere Informationen zu Zeilenzuständen finden Sie unter [Zeilenzustände und Zeilenversionen](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="07983-108">For more information about row states, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
- <span data-ttu-id="07983-109">Kopieren Sie nur das Schema oder die relationale Struktur des **DataSets,** ohne Zeilen zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="07983-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="07983-110">Zeilen können mit <xref:System.Data.DataTable> in eine vorhandene <xref:System.Data.DataTable.ImportRow%2A> importiert werden.</span><span class="sxs-lookup"><span data-stu-id="07983-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="07983-111">Um eine exakte Kopie des **DataSets** zu erstellen, <xref:System.Data.DataSet.Copy%2A> das sowohl Schema als auch Daten enthält, verwenden Sie die Methode des **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="07983-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="07983-112">Das folgende Codebeispiel zeigt, wie Sie eine exakte Kopie des **DataSet**erstellen.</span><span class="sxs-lookup"><span data-stu-id="07983-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="07983-113">Verwenden Sie die Methode des **DataSet,** um eine Kopie eines **DataSets** zu <xref:System.Data.DataSet.GetChanges%2A> erstellen, das schemas und nur die Daten enthält, die **Added**, **Modified**oder **Deleted** rows darstellen. Verwenden Sie die Methode des DataSet .</span><span class="sxs-lookup"><span data-stu-id="07983-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="07983-114">Sie können **GetChanges** auch verwenden, um nur Zeilen mit einem angegebenen Zeilenstatus zurückzugeben, indem Sie beim Aufrufen von **GetChanges**einen **DataRowState-Wert** übergeben.</span><span class="sxs-lookup"><span data-stu-id="07983-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="07983-115">Das folgende Codebeispiel zeigt, wie ein **DataRowState** beim Aufrufen von **GetChanges**übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="07983-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
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
  
 <span data-ttu-id="07983-116">Um eine Kopie eines **DataSets** zu erstellen, <xref:System.Data.DataSet.Clone%2A> die nur Schema enthält, verwenden Sie die Methode des **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="07983-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="07983-117">Sie können dem geklonten **DataSet** auch vorhandene Zeilen hinzufügen, indem Sie die **ImportRow-Methode** der **DataTable**verwenden.</span><span class="sxs-lookup"><span data-stu-id="07983-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="07983-118">**ImportRow** fügt der angegebenen Tabelle Daten-, Zeilenstatus- und Zeilenversionsinformationen hinzu.</span><span class="sxs-lookup"><span data-stu-id="07983-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="07983-119">Spaltenwerte werden nur hinzugefügt, wenn der Spaltenname übereinstimmt und der Datentyp kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="07983-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="07983-120">Im folgenden Codebeispiel wird ein Klon eines **DataSets** erstellt und dann die Zeilen aus dem ursprünglichen **DataSet** zur **Tabelle Customers** im **DataSet-Klon** für Kunden hinzugefügt, bei denen die **Spalte CountryRegion** den Wert "Deutschland" hat.</span><span class="sxs-lookup"><span data-stu-id="07983-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="07983-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07983-121">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="07983-122">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="07983-122">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="07983-123">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="07983-123">ADO.NET Overview</span></span>](../ado-net-overview.md)
