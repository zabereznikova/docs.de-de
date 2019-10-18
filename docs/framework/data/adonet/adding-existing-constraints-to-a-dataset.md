---
title: Hinzufügen von vorhandenen Einschränkungen zu einem "DataSet"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: 267d6489d39f86fc06b35de8cf30dad74f501b0b
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523232"
---
# <a name="adding-existing-constraints-to-a-dataset"></a><span data-ttu-id="abc0c-102">Hinzufügen von vorhandenen Einschränkungen zu einem "DataSet"</span><span class="sxs-lookup"><span data-stu-id="abc0c-102">Adding Existing Constraints to a DataSet</span></span>

<span data-ttu-id="abc0c-103">Die **Fill** -Methode des **DataAdapter** füllt eine <xref:System.Data.DataSet> nur mit Tabellen Spalten und Zeilen aus einer Datenquelle. Obwohl Einschränkungen häufig von der Datenquelle festgelegt werden, werden diese Schema Informationen von der **Fill** -Methode nicht standardmäßig dem **DataSet** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="abc0c-103">The **Fill** method of the **DataAdapter** fills a <xref:System.Data.DataSet> only with table columns and rows from a data source; though constraints are commonly set by the data source, the **Fill** method does not add this schema information to the **DataSet** by default.</span></span> <span data-ttu-id="abc0c-104">Zum Auffüllen eines **DataSets** mit vorhandenen Primärschlüssel-Einschränkungs Informationen aus einer Datenquelle können Sie entweder die **FillSchema** -Methode des **DataAdapter**-Objekts oder die **MissingSchemaAction** -Eigenschaft des **DataAdapter** -Objekts festlegen. an **AddWithKey** , bevor **Fill**aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="abc0c-104">To populate a **DataSet** with existing primary key constraint information from a data source, you can either call the **FillSchema** method of the **DataAdapter**, or set the **MissingSchemaAction** property of the **DataAdapter** to **AddWithKey** before calling **Fill**.</span></span> <span data-ttu-id="abc0c-105">Dadurch wird sichergestellt, dass die PRIMARY KEY-Einschränkungen im **DataSet** den Werten in der Datenquelle entsprechen.</span><span class="sxs-lookup"><span data-stu-id="abc0c-105">This will ensure that primary key constraints in the **DataSet** reflect those at the data source.</span></span> <span data-ttu-id="abc0c-106">Informationen zu Fremdschlüssel Einschränkungen sind nicht eingeschlossen und müssen explizit erstellt werden, wie in [datensierungseinschränkungen](./dataset-datatable-dataview/datatable-constraints.md)gezeigt.</span><span class="sxs-lookup"><span data-stu-id="abc0c-106">Foreign key constraint information is not included and must be created explicitly, as shown in [DataTable Constraints](./dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
<span data-ttu-id="abc0c-107">Wenn einem **DataSet** Schema Informationen hinzugefügt werden, bevor es mit Daten gefüllt wird, wird sichergestellt, dass PRIMARY KEY-Einschränkungen in den <xref:System.Data.DataTable> Objekten im **DataSet**enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="abc0c-107">Adding schema information to a **DataSet** before filling it with data ensures that primary key constraints are included with the <xref:System.Data.DataTable> objects in the **DataSet**.</span></span> <span data-ttu-id="abc0c-108">Wenn zusätzliche Aufrufe zum Auffüllen des **DataSets** durchgeführt werden, werden die Primärschlüssel Spalten-Informationen verwendet, um neue Zeilen aus der Datenquelle mit den aktuellen Zeilen in jeder Datentabelle abzugleichen. die aktuellen Daten in den **Tabellen werden mit**Daten aus der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="abc0c-108">As a result, when additional calls to fill the **DataSet** are made, the primary key column information is used to match new rows from the data source with current rows in each **DataTable**, and current data in the tables is overwritten with data from the data source.</span></span> <span data-ttu-id="abc0c-109">Ohne die Schema Informationen werden die neuen Zeilen aus der Datenquelle an das **DataSet**angefügt, sodass doppelte Zeilen entstehen.</span><span class="sxs-lookup"><span data-stu-id="abc0c-109">Without the schema information, the new rows from the data source are appended to the **DataSet**, resulting in duplicate rows.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="abc0c-110">Wenn eine Spalte in einer Datenquelle als automatische Inkrementierung identifiziert wird, die **FillSchema** -Methode oder die **Fill** -Methode mit der **MissingSchemaAction** -Eigenschaft **AddWithKey**, erstellt eine **datacolenn** mit einer **AutoIncrement** -Eigenschaft. Legen Sie auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="abc0c-110">If a column in a data source is identified as auto-incrementing, the **FillSchema** method, or the **Fill** method with a **MissingSchemaAction** of **AddWithKey**, creates a **DataColumn** with an **AutoIncrement** property set to `true`.</span></span> <span data-ttu-id="abc0c-111">Sie müssen jedoch die Werte **AutoIncrementStep** und **AutoIncrementSeed** selbst festlegen.</span><span class="sxs-lookup"><span data-stu-id="abc0c-111">However, you will need to set the **AutoIncrementStep** and **AutoIncrementSeed** values yourself.</span></span> <span data-ttu-id="abc0c-112">Weitere Informationen zum automatischen Inkrementieren von Spalten finden Sie unter [Erstellen von AutoIncrement-Spalten](./dataset-datatable-dataview/creating-autoincrement-columns.md).</span><span class="sxs-lookup"><span data-stu-id="abc0c-112">For more information about auto-incrementing columns, see [Creating AutoIncrement Columns](./dataset-datatable-dataview/creating-autoincrement-columns.md).</span></span>  
  
<span data-ttu-id="abc0c-113">Die Verwendung von **FillSchema** oder das Festlegen der **MissingSchemaAction** auf **AddWithKey** erfordert zusätzliche Verarbeitung an der Datenquelle, um Informationen zur Primärschlüssel Spalte zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="abc0c-113">Using **FillSchema** or setting the **MissingSchemaAction** to **AddWithKey** requires extra processing at the data source to determine primary key column information.</span></span> <span data-ttu-id="abc0c-114">Diese zusätzlichen Verarbeitungsschritte können zu einem Leistungsabfall führen.</span><span class="sxs-lookup"><span data-stu-id="abc0c-114">This additional processing can hinder performance.</span></span> <span data-ttu-id="abc0c-115">Wenn Sie die Primärschlüsselinformationen zur Entwurfszeit kennen, empfiehlt es sich, zum Erzielen einer optimalen Leistung die Primärschlüsselspalte(n) explizit in der richtigen Reihenfolge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="abc0c-115">If you know the primary key information at design time, we recommend that you explicitly specify the primary key column or columns in order to achieve optimal performance.</span></span> <span data-ttu-id="abc0c-116">Informationen zum expliziten Festlegen von Primärschlüssel Informationen für eine Tabelle finden Sie unter [Definieren von primär Schlüsseln](./dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="abc0c-116">For information about explicitly setting primary key information for a table, see [Defining Primary Keys](./dataset-datatable-dataview/defining-primary-keys.md).</span></span>
  
<span data-ttu-id="abc0c-117">Im folgenden Codebeispiel wird gezeigt, wie einem **DataSet** mithilfe von **FillSchema**Schema Informationen hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="abc0c-117">The following code example shows how to add schema information to a **DataSet** using **FillSchema**:</span></span>
  
```vb  
Dim custDataSet As New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
var custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
<span data-ttu-id="abc0c-118">Im folgenden Codebeispiel wird gezeigt, wie Schema Informationen mithilfe der **MissingSchemaAction. AddWithKey** -Eigenschaft der **Fill** -Methode einem **DataSet** hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="abc0c-118">The following code example shows how to add schema information to a **DataSet** using the **MissingSchemaAction.AddWithKey** property of the **Fill** method:</span></span>
  
```vb  
Dim custDataSet As New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
var custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="abc0c-119">Verarbeiten mehrerer Resultsets</span><span class="sxs-lookup"><span data-stu-id="abc0c-119">Handling multiple result sets</span></span>  

<span data-ttu-id="abc0c-120">Wenn der **DataAdapter** auf mehrere Resultsets stößt, die von **SelectCommand**zurückgegeben werden, werden mehrere Tabellen im **DataSet**erstellt.</span><span class="sxs-lookup"><span data-stu-id="abc0c-120">If the **DataAdapter** encounters multiple result sets returned from the **SelectCommand**, it will create multiple tables in the **DataSet**.</span></span> <span data-ttu-id="abc0c-121">Den Tabellen wird ein NULL basierter inkrementeller Standardname von **Tabelle** *N*zugewiesen, beginnend mit **Table** anstelle von "Table0".</span><span class="sxs-lookup"><span data-stu-id="abc0c-121">The tables will be given a zero-based incremental default name of **Table** *N*, starting with **Table** instead of "Table0".</span></span> <span data-ttu-id="abc0c-122">Wenn ein Tabellenname als Argument an die **FillSchema** -Methode übergeben wird, erhalten die Tabellen den NULL basierten inkrementellen Namen **TableName** *N*, beginnend mit **TableName** anstelle von "TableName0".</span><span class="sxs-lookup"><span data-stu-id="abc0c-122">If a table name is passed as an argument to the **FillSchema** method, the tables will be given a zero-based incremental name of **TableName** *N*, starting with **TableName** instead of "TableName0".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="abc0c-123">Wenn die **FillSchema** -Methode des **OleDbDataAdapter** -Objekts für einen Befehl aufgerufen wird, der mehrere Resultsets zurückgibt, werden nur die Schema Informationen aus dem ersten Resultset zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="abc0c-123">If the **FillSchema** method of the **OleDbDataAdapter** object is called for a command that returns multiple result sets, only the schema information from the first result set is returned.</span></span> <span data-ttu-id="abc0c-124">Beim Zurückgeben von Schema Informationen für mehrere Resultsets mit dem **OleDbDataAdapter**wird empfohlen, dass Sie die **MissingSchemaAction-Aktion** von **AddWithKey** angeben und die Schema Informationen beim Aufrufen der **Füllung** abrufen. anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="abc0c-124">When returning schema information for multiple result sets using the **OleDbDataAdapter**, it is recommended that you specify a **MissingSchemaAction** of **AddWithKey** and obtain the schema information when calling the **Fill** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abc0c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abc0c-125">See also</span></span>

- [<span data-ttu-id="abc0c-126">DataAdapters und DataReaders</span><span class="sxs-lookup"><span data-stu-id="abc0c-126">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="abc0c-127">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="abc0c-127">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="abc0c-128">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="abc0c-128">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="abc0c-129">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="abc0c-129">ADO.NET Overview</span></span>](ado-net-overview.md)
