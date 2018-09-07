---
title: Hinzufügen von vorhandenen Einschränkungen zu einem "DataSet"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: 90aa1e5dceb3cac87d330837496b9dc467dc1876
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44064201"
---
# <a name="adding-existing-constraints-to-a-dataset"></a><span data-ttu-id="50720-102">Hinzufügen von vorhandenen Einschränkungen zu einem "DataSet"</span><span class="sxs-lookup"><span data-stu-id="50720-102">Adding Existing Constraints to a DataSet</span></span>
<span data-ttu-id="50720-103">Die **füllen** -Methode der der **DataAdapter** füllt eine <xref:System.Data.DataSet> nur mit Spalten und Zeilen aus einer Datenquelle jedoch Einschränkungen sind häufig festgelegt, indem die Datenquelle, die **Füllen** Methode fügt diese Schemainformationen nicht der **DataSet** standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="50720-103">The **Fill** method of the **DataAdapter** fills a <xref:System.Data.DataSet> only with table columns and rows from a data source; though constraints are commonly set by the data source, the **Fill** method does not add this schema information to the **DataSet** by default.</span></span> <span data-ttu-id="50720-104">Zum Auffüllen einer **DataSet** mit vorhandenen primary Key-Einschränkungsinformationen aus einer Datenquelle können Sie entweder Aufruf der **FillSchema** -Methode der der **DataAdapter**, oder legen Sie die **MissingSchemaAction** Eigenschaft der **DataAdapter** zu **AddWithKey** vor dem Aufruf **füllen**.</span><span class="sxs-lookup"><span data-stu-id="50720-104">To populate a **DataSet** with existing primary key constraint information from a data source, you can either call the **FillSchema** method of the **DataAdapter**, or set the **MissingSchemaAction** property of the **DataAdapter** to **AddWithKey** before calling **Fill**.</span></span> <span data-ttu-id="50720-105">Dadurch wird sichergestellt, dass die Einschränkungen in der **DataSet** widerzuspiegeln, die in der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="50720-105">This will ensure that primary key constraints in the **DataSet** reflect those at the data source.</span></span> <span data-ttu-id="50720-106">Foreign Key-Einschränkungsinformationen nicht enthalten ist, und muss erstellt werden, siehe explizit [DataTable-Einschränkungen](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="50720-106">Foreign key constraint information is not included and must be created explicitly, as shown in [DataTable Constraints](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="50720-107">Schemainformationen Hinzufügen einer **DataSet** vor dem Füllen mit Daten stellt sicher, dass die primary Key-Einschränkungen enthalten sind die <xref:System.Data.DataTable> Objekte in der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="50720-107">Adding schema information to a **DataSet** before filling it with data ensures that primary key constraints are included with the <xref:System.Data.DataTable> objects in the **DataSet**.</span></span> <span data-ttu-id="50720-108">Als Ergebnis bei weiteren Aufrufen zum Füllen der **DataSet** vorgenommen werden, wird die primäre Schlüsselspalteninformationen wird verwendet, um neue Zeilen aus der Datenquelle mit den aktuellen Zeilen in jeder entsprechen **DataTable**, und aktuellen Daten in die Tabellen mit Daten aus der Datenquelle überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="50720-108">As a result, when additional calls to fill the **DataSet** are made, the primary key column information is used to match new rows from the data source with current rows in each **DataTable**, and current data in the tables is overwritten with data from the data source.</span></span> <span data-ttu-id="50720-109">Ohne die Schemainformationen werden die neuen Zeilen aus der Datenquelle angefügt, um die **DataSet**, wodurch doppelte Zeilen.</span><span class="sxs-lookup"><span data-stu-id="50720-109">Without the schema information, the new rows from the data source are appended to the **DataSet**, resulting in duplicate rows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50720-110">Wenn eine Spalte in einer Datenquelle als automatisch erhöht, identifiziert wird die **FillSchema** -Methode, oder die **füllen** -Methode mit einer **MissingSchemaAction** von  **AddWithKey**, erstellt eine **DataColumn** mit einer **AutoIncrement** -Eigenschaftensatz auf `true`.</span><span class="sxs-lookup"><span data-stu-id="50720-110">If a column in a data source is identified as auto-incrementing, the **FillSchema** method, or the **Fill** method with a **MissingSchemaAction** of **AddWithKey**, creates a **DataColumn** with an **AutoIncrement** property set to `true`.</span></span> <span data-ttu-id="50720-111">Allerdings müssen Sie zum Festlegen der **AutoIncrementStep** und **AutoIncrementSeed** Werte selbst.</span><span class="sxs-lookup"><span data-stu-id="50720-111">However, you will need to set the **AutoIncrementStep** and **AutoIncrementSeed** values yourself.</span></span> <span data-ttu-id="50720-112">Weitere Informationen zu Spalten automatisch erhöht, finden Sie unter [Erstellen von AutoIncrement-Spalten](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).</span><span class="sxs-lookup"><span data-stu-id="50720-112">For more information about auto-incrementing columns, see [Creating AutoIncrement Columns](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).</span></span>  
  
 <span data-ttu-id="50720-113">Mithilfe von **FillSchema** oder einer Einstellung der **MissingSchemaAction** zu **AddWithKey** erfordert zusätzliche Verarbeitungsschritte an der Datenquelle um Primärschlüsselspalte Informationen zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="50720-113">Using **FillSchema** or setting the **MissingSchemaAction** to **AddWithKey** requires extra processing at the data source to determine primary key column information.</span></span> <span data-ttu-id="50720-114">Diese zusätzlichen Verarbeitungsschritte können zu einem Leistungsabfall führen.</span><span class="sxs-lookup"><span data-stu-id="50720-114">This additional processing can hinder performance.</span></span> <span data-ttu-id="50720-115">Wenn Sie die Primärschlüsselinformationen zur Entwurfszeit kennen, empfiehlt es sich, zum Erzielen einer optimalen Leistung die Primärschlüsselspalte(n) explizit in der richtigen Reihenfolge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="50720-115">If you know the primary key information at design time, we recommend that you explicitly specify the primary key column or columns in order to achieve optimal performance.</span></span> <span data-ttu-id="50720-116">Informationen zum expliziten Festlegen von Primärschlüsselinformationen für eine Tabelle finden Sie unter [Definieren von Primärschlüsseln](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="50720-116">For information about explicitly setting primary key information for a table, see [Defining Primary Keys](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
 <span data-ttu-id="50720-117">Im folgenden Codebeispiel wird veranschaulicht, das Hinzufügen von Schemainformationen einer **DataSet** mit **FillSchema**.</span><span class="sxs-lookup"><span data-stu-id="50720-117">The following code example shows how to add schema information to a **DataSet** using **FillSchema**.</span></span>  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
 <span data-ttu-id="50720-118">Im folgenden Codebeispiel wird veranschaulicht, das Hinzufügen von Schemainformationen einer **DataSet** mithilfe der **MissingSchemaAction.AddWithKey** Eigenschaft der **füllen** Methode.</span><span class="sxs-lookup"><span data-stu-id="50720-118">The following code example shows how to add schema information to a **DataSet** using the **MissingSchemaAction.AddWithKey** property of the **Fill** method.</span></span>  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="50720-119">Umgang mit mehreren Resultsets</span><span class="sxs-lookup"><span data-stu-id="50720-119">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="50720-120">Wenn die **DataAdapter** erkennt mehrere Resultsets aus der **SelectCommand**, erstellt es mehrere Tabellen in der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="50720-120">If the **DataAdapter** encounters multiple result sets returned from the **SelectCommand**, it will create multiple tables in the **DataSet**.</span></span> <span data-ttu-id="50720-121">Die Tabellen erhält einen standardmäßig nullbasierte Namen **Tabelle** *N*, beginnend mit **Tabelle** anstelle von "Table0".</span><span class="sxs-lookup"><span data-stu-id="50720-121">The tables will be given a zero-based incremental default name of **Table** *N*, starting with **Table** instead of "Table0".</span></span> <span data-ttu-id="50720-122">Wenn ein Tabellenname als Argument übergeben wird die **FillSchema** -Methode, die Tabellen erhält einen nullbasierten Namen **TableName** *N*, beginnend mit **TableName** anstelle von "TableName0".</span><span class="sxs-lookup"><span data-stu-id="50720-122">If a table name is passed as an argument to the **FillSchema** method, the tables will be given a zero-based incremental name of **TableName** *N*, starting with **TableName** instead of "TableName0".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50720-123">Wenn die **FillSchema** Methode der **OleDbDataAdapter** -Objekts aufgerufen wird, für einen Befehl aus, die mehrere Resultsets zurückgibt, wird nur die Schemainformationen aus dem ersten Resultset zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="50720-123">If the **FillSchema** method of the **OleDbDataAdapter** object is called for a command that returns multiple result sets, only the schema information from the first result set is returned.</span></span> <span data-ttu-id="50720-124">Wenn Schemainformationen für mehrere Resultsets zurückgeben Sätze unter Verwendung der **OleDbDataAdapter**, es wird empfohlen, die Sie angeben, ein **MissingSchemaAction** von **AddWithKey** und rufen Sie die Schemainformationen beim Aufruf der **füllen** Methode.</span><span class="sxs-lookup"><span data-stu-id="50720-124">When returning schema information for multiple result sets using the **OleDbDataAdapter**, it is recommended that you specify a **MissingSchemaAction** of **AddWithKey** and obtain the schema information when calling the **Fill** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50720-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50720-125">See Also</span></span>  
 [<span data-ttu-id="50720-126">DataAdapters und DataReaders</span><span class="sxs-lookup"><span data-stu-id="50720-126">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="50720-127">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="50720-127">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="50720-128">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="50720-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="50720-129">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="50720-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
