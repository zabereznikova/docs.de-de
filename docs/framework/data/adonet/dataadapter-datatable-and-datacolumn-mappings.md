---
title: "\"DataTable\" und \"DataColumn\"-Zuordnungen mit \"DataAdapter\""
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 357812aa95ea731fe86fbe49b2cb1b2806e3915a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784868"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a><span data-ttu-id="cf193-102">"DataTable" und "DataColumn"-Zuordnungen mit "DataAdapter"</span><span class="sxs-lookup"><span data-stu-id="cf193-102">DataAdapter DataTable and DataColumn Mappings</span></span>
<span data-ttu-id="cf193-103">Ein **DataAdapter** enthält eine Auflistung von 0 (NULL <xref:System.Data.Common.DataTableMapping> ) oder mehr Objekten in der **TableMappings** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="cf193-103">A **DataAdapter** contains a collection of zero or more <xref:System.Data.Common.DataTableMapping> objects in its **TableMappings** property.</span></span> <span data-ttu-id="cf193-104">Eine **DataTableMapping** bietet eine Master Zuordnung zwischen den Daten, die von einer Abfrage an eine Datenquelle zurückgegeben <xref:System.Data.DataTable>werden, und einem.</span><span class="sxs-lookup"><span data-stu-id="cf193-104">A **DataTableMapping** provides a master mapping between the data returned from a query against a data source, and a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="cf193-105">Der **DataTableMapping** -Name kann anstelle des Namen der **Daten** Tabelle an die **Fill** -Methode von **DataAdapter**weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cf193-105">The **DataTableMapping** name can be passed in place of the **DataTable** name to the **Fill** method of the **DataAdapter**.</span></span> <span data-ttu-id="cf193-106">Im folgenden Beispiel wird eine **DataTableMapping** mit dem Namen " **AuthorsMapping** " für die Tabelle " **Authors** " erstellt.</span><span class="sxs-lookup"><span data-stu-id="cf193-106">The following example creates a **DataTableMapping** named **AuthorsMapping** for the **Authors** table.</span></span>  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 <span data-ttu-id="cf193-107">Eine **DataTableMapping** -Funktion ermöglicht es Ihnen, Spaltennamen in einer **Daten** Tabelle zu verwenden, die sich von denen in der Datenbank unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="cf193-107">A **DataTableMapping** enables you to use column names in a **DataTable** that are different from those in the database.</span></span> <span data-ttu-id="cf193-108">Der **DataAdapter** verwendet die Zuordnung, um die Spalten zu vergleichen, wenn die Tabelle aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="cf193-108">The **DataAdapter** uses the mapping to match the columns when the table is updated.</span></span>  
  
 <span data-ttu-id="cf193-109">Wenn Sie beim Aufrufen der **Fill** -oder **Update** -Methode von **DataAdapter**keinen **TableName** -oder **DataTableMapping** -Namen angeben, sucht der **DataAdapter** nach einem **DataTableMapping** mit dem Namen "Table".</span><span class="sxs-lookup"><span data-stu-id="cf193-109">If you do not specify a **TableName** or a **DataTableMapping** name when calling the **Fill** or **Update** method of the **DataAdapter**, the **DataAdapter** looks for a **DataTableMapping** named "Table".</span></span> <span data-ttu-id="cf193-110">Wenn dieses **DataTableMapping** -Element nicht vorhanden ist, lautet der **TableName** der **Daten** Tabelle "Table".</span><span class="sxs-lookup"><span data-stu-id="cf193-110">If that **DataTableMapping** does not exist, the **TableName** of the **DataTable** is "Table".</span></span> <span data-ttu-id="cf193-111">Sie können eine **DataTableMapping** -Standard Zuordnung angeben, indem Sie eine **DataTableMapping** mit dem Namen "Table" erstellen.</span><span class="sxs-lookup"><span data-stu-id="cf193-111">You can specify a default **DataTableMapping** by creating a **DataTableMapping** with the name of "Table".</span></span>  
  
 <span data-ttu-id="cf193-112">Im folgenden Codebeispiel wird eine **DataTableMapping** (aus dem <xref:System.Data.Common> -Namespace) erstellt und als Standard Zuordnung für den angegebenen **DataAdapter** festgelegt, indem Sie "Table" benannt wird.</span><span class="sxs-lookup"><span data-stu-id="cf193-112">The following code example creates a **DataTableMapping** (from the <xref:System.Data.Common> namespace) and makes it the default mapping for the specified **DataAdapter** by naming it "Table".</span></span> <span data-ttu-id="cf193-113">Im Beispiel werden dann die Spalten aus der ersten Tabelle im Abfrageergebnis (die **Customers** -Tabelle der **Northwind** -Datenbank) einem Satz benutzerfreundlicher Namen in der **Northwind** - <xref:System.Data.DataSet>Kunden Tabelle in zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="cf193-113">The example then maps the columns from the first table in the query result (the **Customers** table of the **Northwind** database) to a set of more user-friendly names in the **Northwind Customers** table in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="cf193-114">Für Spalten, die nicht zugeordnet werden, wird der Name der Spalte in der Datenquelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="cf193-114">For columns that are not mapped, the name of the column from the data source is used.</span></span>  
  
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
  
 <span data-ttu-id="cf193-115">In komplexeren Situationen können Sie festlegen, dass der gleiche **DataAdapter** das Laden verschiedener Tabellen mit unterschiedlichen Zuordnungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cf193-115">In more advanced situations, you may decide that you want the same **DataAdapter** to support loading different tables with different mappings.</span></span> <span data-ttu-id="cf193-116">Fügen Sie zu diesem Zweck einfach weitere **DataTableMapping** -Objekte hinzu.</span><span class="sxs-lookup"><span data-stu-id="cf193-116">To do this, simply add additional **DataTableMapping** objects.</span></span>  
  
 <span data-ttu-id="cf193-117">Wenn die **Fill** -Methode an eine Instanz eines **DataSets** und einen **DataTableMapping** -Namen übertragen wird, wird Sie verwendet, wenn eine Zuordnung mit diesem Namen vorhanden ist. Andernfalls wird eine **Daten** Tabelle mit diesem Namen verwendet.</span><span class="sxs-lookup"><span data-stu-id="cf193-117">When the **Fill** method is passed an instance of a **DataSet** and a **DataTableMapping** name, if a mapping with that name exists it is used; otherwise, a **DataTable** with that name is used.</span></span>  
  
 <span data-ttu-id="cf193-118">In den folgenden Beispielen wird eine **DataTableMapping** mit dem Namen **Customers** und dem Namen der **Daten** Tabelle **BizTalkSchema**erstellt.</span><span class="sxs-lookup"><span data-stu-id="cf193-118">The following examples create a **DataTableMapping** with a name of **Customers** and a **DataTable** name of **BizTalkSchema**.</span></span> <span data-ttu-id="cf193-119">Im Beispiel werden dann die von der SELECT-Anweisung zurückgegebenen Zeilen der **BizTalkSchema** - **Daten**Tabelle zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="cf193-119">The example then maps the rows returned by the SELECT statement to the **BizTalkSchema** **DataTable**.</span></span>  
  
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
> <span data-ttu-id="cf193-120">Wenn für eine Spaltenzuordnung kein Quellspaltenname bzw. für eine Tabellenzuordnung kein Quelltabellenname angegeben wird, werden automatisch Standardnamen generiert.</span><span class="sxs-lookup"><span data-stu-id="cf193-120">If a source column name is not supplied for a column mapping or a source table name is not supplied for a table mapping, default names will be automatically generated.</span></span> <span data-ttu-id="cf193-121">Wenn für eine Spalten Zuordnung keine Quell Spalte bereitgestellt wird, erhält die Spalten Zuordnung den inkrementellen Standardnamen **sourcecolnumn** *N,* beginnend mit **SourceColumn1**.</span><span class="sxs-lookup"><span data-stu-id="cf193-121">If no source column is supplied for a column mapping, the column mapping is given an incremental default name of **SourceColumn** *N,* starting with **SourceColumn1**.</span></span> <span data-ttu-id="cf193-122">Wenn für eine Tabellen Zuordnung kein Quell Tabellenname angegeben wird, erhält die Tabellen Zuordnung einen inkrementellen Standardnamen für **SourceTable** *N*, beginnend mit **SourceTable1**.</span><span class="sxs-lookup"><span data-stu-id="cf193-122">If no source table name is supplied for a table mapping, the table mapping is given an incremental default name of **SourceTable** *N*, starting with **SourceTable1**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cf193-123">Es wird empfohlen, dass Sie die Benennungs Konvention von **sourcecolnumn** *N* für eine Spalten Zuordnung oder **SourceTable** *n* für eine Tabellen Zuordnung vermeiden, da der von Ihnen bereitgestellte Name in Konflikt mit einem vorhandenen Standard Spalten-Zuordnungsnamen im  **ColumnMappingCollection** oder Tabellen Zuordnung Name in **DataTableMappingCollection**.</span><span class="sxs-lookup"><span data-stu-id="cf193-123">We recommend that you avoid the naming convention of **SourceColumn** *N* for a column mapping, or **SourceTable** *N* for a table mapping, because the name you supply may conflict with an existing default column mapping name in the **ColumnMappingCollection** or table mapping name in the **DataTableMappingCollection**.</span></span> <span data-ttu-id="cf193-124">Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="cf193-124">If the supplied name already exists, an exception will be thrown.</span></span>  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="cf193-125">Umgang mit mehreren Resultsets</span><span class="sxs-lookup"><span data-stu-id="cf193-125">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="cf193-126">Wenn der **SelectCommand** mehrere Tabellen zurückgibt, generiert **Fill** automatisch Tabellennamen mit inkrementellen Werten für die Tabellen im **DataSet**, beginnend mit dem angegebenen Tabellennamen und fortsetzen in der Form **TableName** . *N*, beginnend mit **TableName1**.</span><span class="sxs-lookup"><span data-stu-id="cf193-126">If your **SelectCommand** returns multiple tables, **Fill** automatically generates table names with incremental values for the tables in the **DataSet**, starting with the specified table name and continuing on in the form **TableName** *N*, starting with **TableName1**.</span></span> <span data-ttu-id="cf193-127">Sie können Tabellen Zuordnungen verwenden, um den automatisch generierten Tabellennamen einem Namen zuzuordnen, den Sie für die Tabelle im **DataSet**angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="cf193-127">You can use table mappings to map the automatically generated table name to a name you want specified for the table in the **DataSet**.</span></span> <span data-ttu-id="cf193-128">Geben Sie beispielsweise für einen **SelectCommand** , der zwei Tabellen, **Kunden** und **Bestellungen**zurückgibt, den folgenden **Auffüll**Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="cf193-128">For example, for a **SelectCommand** that returns two tables, **Customers** and **Orders**, issue the following call to **Fill**.</span></span>  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 <span data-ttu-id="cf193-129">Im **DataSet**werden zwei Tabellen erstellt: **Kunden** und **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="cf193-129">Two tables are created in the **DataSet**: **Customers** and **Customers1**.</span></span> <span data-ttu-id="cf193-130">Sie können Tabellen **Zuordnungen** verwenden, um sicherzustellen, dass die zweite Tabelle den Namen Orders anstelle von **Customers1**hat.</span><span class="sxs-lookup"><span data-stu-id="cf193-130">You can use table mappings to ensure that the second table is named **Orders** instead of **Customers1**.</span></span> <span data-ttu-id="cf193-131">Ordnen Sie zu diesem Zweck die Quell Tabelle von **Customers1** den **DataSet** -Tabellen **Bestellungen**zu, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cf193-131">To do this, map the source table of **Customers1** to the **DataSet** table **Orders**, as shown in the following example.</span></span>  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf193-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf193-132">See also</span></span>

- [<span data-ttu-id="cf193-133">DataAdapters und DataReaders</span><span class="sxs-lookup"><span data-stu-id="cf193-133">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="cf193-134">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cf193-134">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="cf193-135">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cf193-135">ADO.NET Overview</span></span>](ado-net-overview.md)
