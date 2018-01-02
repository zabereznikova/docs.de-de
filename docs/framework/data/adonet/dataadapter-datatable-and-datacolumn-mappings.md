---
title: "\"DataTable\" und \"DataColumn\"-Zuordnungen mit \"DataAdapter\""
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3df07f8b7bf71d658e9073a8aeb3d51dee087544
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a><span data-ttu-id="68928-102">"DataTable" und "DataColumn"-Zuordnungen mit "DataAdapter"</span><span class="sxs-lookup"><span data-stu-id="68928-102">DataAdapter DataTable and DataColumn Mappings</span></span>
<span data-ttu-id="68928-103">Ein **"DataAdapter"** enthält eine Auflistung von NULL oder mehr <xref:System.Data.Common.DataTableMapping> Objekte in seiner **TableMappings** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="68928-103">A **DataAdapter** contains a collection of zero or more <xref:System.Data.Common.DataTableMapping> objects in its **TableMappings** property.</span></span> <span data-ttu-id="68928-104">Ein **DataTableMapping** bietet eine master-Zuordnung zwischen den Daten aus einer Abfrage für eine Datenquelle zurückgegeben und ein <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="68928-104">A **DataTableMapping** provides a master mapping between the data returned from a query against a data source, and a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="68928-105">Die **DataTableMapping** Namen anstelle von übergeben werden kann die **DataTable** -Namens an die **füllen** Methode der **"DataAdapter"**.</span><span class="sxs-lookup"><span data-stu-id="68928-105">The **DataTableMapping** name can be passed in place of the **DataTable** name to the **Fill** method of the **DataAdapter**.</span></span> <span data-ttu-id="68928-106">Das folgende Beispiel erstellt eine **DataTableMapping** mit dem Namen **AuthorsMapping** für die **Autoren** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="68928-106">The following example creates a **DataTableMapping** named **AuthorsMapping** for the **Authors** table.</span></span>  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 <span data-ttu-id="68928-107">Ein **DataTableMapping** ermöglicht es Ihnen, verwenden Sie die Spaltennamen in einer **DataTable** , die unterscheiden sich von denen in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="68928-107">A **DataTableMapping** enables you to use column names in a **DataTable** that are different from those in the database.</span></span> <span data-ttu-id="68928-108">Die **"DataAdapter"** mithilfe der Zuordnung der Spalten entsprechen, wenn die Tabelle aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="68928-108">The **DataAdapter** uses the mapping to match the columns when the table is updated.</span></span>  
  
 <span data-ttu-id="68928-109">Wenn Sie nicht angeben eine **TableName** oder ein **DataTableMapping** Namen beim Aufrufen der **füllen** oder **Update** Methode der  **"DataAdapter"**, **"DataAdapter"** sucht nach einem **DataTableMapping** mit dem Namen "Table".</span><span class="sxs-lookup"><span data-stu-id="68928-109">If you do not specify a **TableName** or a **DataTableMapping** name when calling the **Fill** or **Update** method of the **DataAdapter**, the **DataAdapter** looks for a **DataTableMapping** named "Table".</span></span> <span data-ttu-id="68928-110">Wenn für das **DataTableMapping** ist nicht vorhanden, die **TableName** von der **DataTable** "Table".</span><span class="sxs-lookup"><span data-stu-id="68928-110">If that **DataTableMapping** does not exist, the **TableName** of the **DataTable** is "Table".</span></span> <span data-ttu-id="68928-111">Sie können einen Standardwert angeben **DataTableMapping** durch das Erstellen einer **DataTableMapping** mit dem Namen "Table".</span><span class="sxs-lookup"><span data-stu-id="68928-111">You can specify a default **DataTableMapping** by creating a **DataTableMapping** with the name of "Table".</span></span>  
  
 <span data-ttu-id="68928-112">Das folgende Codebeispiel erstellt eine **DataTableMapping** (aus der <xref:System.Data.Common> Namespace) und erleichtert die standardzuordnung für den angegebenen **"DataAdapter"** durch benennen "Table".</span><span class="sxs-lookup"><span data-stu-id="68928-112">The following code example creates a **DataTableMapping** (from the <xref:System.Data.Common> namespace) and makes it the default mapping for the specified **DataAdapter** by naming it "Table".</span></span> <span data-ttu-id="68928-113">Das Beispiel ordnet anschließend die Spalten aus der ersten Tabelle in den Abfrageergebnissen (die **Kunden** Tabelle mit den **Northwind** Datenbank) auf eine Gruppe von benutzerfreundlicheren Namen in der **Northwind-Kunden**  -Tabelle in der <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="68928-113">The example then maps the columns from the first table in the query result (the **Customers** table of the **Northwind** database) to a set of more user-friendly names in the **Northwind Customers** table in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="68928-114">Für Spalten, die nicht zugeordnet werden, wird der Name der Spalte in der Datenquelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="68928-114">For columns that are not mapped, the name of the column from the data source is used.</span></span>  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
```  
  
```csharp  
DataTableMapping mapping =   
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 <span data-ttu-id="68928-115">In komplexeren Situationen können Sie entscheiden, dass dem gewünschten **"DataAdapter"** das Laden verschiedener Tabellen mit verschiedenen Zuordnungen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="68928-115">In more advanced situations, you may decide that you want the same **DataAdapter** to support loading different tables with different mappings.</span></span> <span data-ttu-id="68928-116">Zu diesem Zweck fügen Sie einfach zusätzliche **DataTableMapping** Objekte.</span><span class="sxs-lookup"><span data-stu-id="68928-116">To do this, simply add additional **DataTableMapping** objects.</span></span>  
  
 <span data-ttu-id="68928-117">Wenn der **ausfüllen** Methode wird eine Instanz von übergeben eine **DataSet** und eine **DataTableMapping** Namen, sofern eine Zuordnung mit diesem Namen vorhanden ist, andernfalls eine  **DataTable** mit diesem Namen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="68928-117">When the **Fill** method is passed an instance of a **DataSet** and a **DataTableMapping** name, if a mapping with that name exists it is used; otherwise, a **DataTable** with that name is used.</span></span>  
  
 <span data-ttu-id="68928-118">Erstellen Sie in den folgenden Beispielen ein **DataTableMapping** mit dem Namen **Kunden** und ein **DataTable** Name des **BizTalkSchema**.</span><span class="sxs-lookup"><span data-stu-id="68928-118">The following examples create a **DataTableMapping** with a name of **Customers** and a **DataTable** name of **BizTalkSchema**.</span></span> <span data-ttu-id="68928-119">Das Beispiel ordnet dann die von der SELECT-Anweisung zurückgegebenen Zeilen der **BizTalkSchema** **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="68928-119">The example then maps the rows returned by the SELECT statement to the **BizTalkSchema** **DataTable**.</span></span>  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
ITableMapping mapping =   
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
>  <span data-ttu-id="68928-120">Wenn für eine Spaltenzuordnung kein Quellspaltenname bzw. für eine Tabellenzuordnung kein Quelltabellenname angegeben wird, werden automatisch Standardnamen generiert.</span><span class="sxs-lookup"><span data-stu-id="68928-120">If a source column name is not supplied for a column mapping or a source table name is not supplied for a table mapping, default names will be automatically generated.</span></span> <span data-ttu-id="68928-121">Wenn keine Quellspalte für eine spaltenzuordnung angegeben wird, erhält die spaltenzuordnung einen Standardnamen der **SourceColumn** *N,* ab **SourceColumn1**.</span><span class="sxs-lookup"><span data-stu-id="68928-121">If no source column is supplied for a column mapping, the column mapping is given an incremental default name of **SourceColumn** *N,* starting with **SourceColumn1**.</span></span> <span data-ttu-id="68928-122">Wenn für eine tabellenzuordnung kein Quelltabellenname angegeben wird, erhält die tabellenzuordnung einen Standardnamen der **SourceTable** *N*, beginnend mit **SourceTable1**.</span><span class="sxs-lookup"><span data-stu-id="68928-122">If no source table name is supplied for a table mapping, the table mapping is given an incremental default name of **SourceTable** *N*, starting with **SourceTable1**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68928-123">Es wird empfohlen, dass Sie die Benennungskonvention **SourceColumn** *N* für eine spaltenzuordnung oder **SourceTable** *N* für eine Tabelle zuordnen, der Namen, die Sie angeben, ein Konflikt mit einer vorhandenen Zuordnung Standardspaltennamen in kann die **ColumnMappingCollection** oder Zuordnung Tabellennamen in der **DataTableMappingCollection** .</span><span class="sxs-lookup"><span data-stu-id="68928-123">We recommend that you avoid the naming convention of **SourceColumn** *N* for a column mapping, or **SourceTable** *N* for a table mapping, because the name you supply may conflict with an existing default column mapping name in the **ColumnMappingCollection** or table mapping name in the **DataTableMappingCollection**.</span></span> <span data-ttu-id="68928-124">Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="68928-124">If the supplied name already exists, an exception will be thrown.</span></span>  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="68928-125">Umgang mit mehreren Resultsets</span><span class="sxs-lookup"><span data-stu-id="68928-125">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="68928-126">Wenn Ihre **SelectCommand** mehrere Tabellen zurück, die **füllen** generiert automatisch Tabellennamen mit inkrementellen Werten für die Tabellen in der **DataSet**, beginnend mit der Tabellen- und Fortfahren für in der Form angegeben **TableName** *N*, beginnend mit **TableName1**.</span><span class="sxs-lookup"><span data-stu-id="68928-126">If your **SelectCommand** returns multiple tables, **Fill** automatically generates table names with incremental values for the tables in the **DataSet**, starting with the specified table name and continuing on in the form **TableName** *N*, starting with **TableName1**.</span></span> <span data-ttu-id="68928-127">Sie können tabellenzuordnungen können Sie den automatisch generierten Tabellennamen einem Namen zuordnen für die Tabelle im angegebenen soll der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="68928-127">You can use table mappings to map the automatically generated table name to a name you want specified for the table in the **DataSet**.</span></span> <span data-ttu-id="68928-128">Z. B. für eine **SelectCommand** , die zwei Tabellen zurückgibt **Kunden** und **Aufträge**, geben Sie den folgenden Aufruf von **füllen**.</span><span class="sxs-lookup"><span data-stu-id="68928-128">For example, for a **SelectCommand** that returns two tables, **Customers** and **Orders**, issue the following call to **Fill**.</span></span>  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 <span data-ttu-id="68928-129">Werden zwei Tabellen erstellt, der **DataSet**: **Kunden** und **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="68928-129">Two tables are created in the **DataSet**: **Customers** and **Customers1**.</span></span> <span data-ttu-id="68928-130">Sie können tabellenzuordnungen verwenden, um sicherzustellen, dass die zweite Tabelle den Namen **Aufträge** anstelle von **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="68928-130">You can use table mappings to ensure that the second table is named **Orders** instead of **Customers1**.</span></span> <span data-ttu-id="68928-131">Zu diesem Zweck ordnen Sie die Quelltabelle **Customers1** auf die **DataSet** Tabelle **Aufträge**, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="68928-131">To do this, map the source table of **Customers1** to the **DataSet** table **Orders**, as shown in the following example.</span></span>  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## <a name="see-also"></a><span data-ttu-id="68928-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68928-132">See Also</span></span>  
 [<span data-ttu-id="68928-133">DataAdapters und DataReaders</span><span class="sxs-lookup"><span data-stu-id="68928-133">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="68928-134">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="68928-134">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="68928-135">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="68928-135">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
