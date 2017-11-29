---
title: "Hinzufügen von Spalten zu einer \"DataTable\""
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
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6107c21ed04c9c39d69c5c784244d8f6bf9560e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="adding-columns-to-a-datatable"></a><span data-ttu-id="c0867-102">Hinzufügen von Spalten zu einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="c0867-102">Adding Columns to a DataTable</span></span>
<span data-ttu-id="c0867-103">Ein <xref:System.Data.DataTable> enthält eine Auflistung von <xref:System.Data.DataColumn> -Objekten verwiesen wird, indem Sie die **Spalten** -Eigenschaft der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c0867-103">A <xref:System.Data.DataTable> contains a collection of <xref:System.Data.DataColumn> objects referenced by the **Columns** property of the table.</span></span> <span data-ttu-id="c0867-104">Diese Auflistung von Spalten, zusammen mit allen Einschränkungen, definiert das Schema oder die Struktur der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c0867-104">This collection of columns, along with any constraints, defines the schema, or structure, of the table.</span></span>  
  
 <span data-ttu-id="c0867-105">Sie erstellen **DataColumn** Objekte innerhalb einer Tabelle mithilfe der **DataColumn** -Konstruktor oder durch Aufrufen der **hinzufügen** Methode der **Spalten**-Eigenschaft der Tabelle, also eine <xref:System.Data.DataColumnCollection>.</span><span class="sxs-lookup"><span data-stu-id="c0867-105">You create **DataColumn** objects within a table by using the **DataColumn** constructor, or by calling the **Add** method of the **Columns** property of the table, which is a <xref:System.Data.DataColumnCollection>.</span></span> <span data-ttu-id="c0867-106">Die **hinzufügen** -Methode akzeptiert optional **ColumnName**, **DataType**, und **Ausdruck** Argumente und erstellt einen neuen  **DataColumn** als Member der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="c0867-106">The **Add** method accepts optional **ColumnName**, **DataType**, and **Expression** arguments and creates a new **DataColumn** as a member of the collection.</span></span> <span data-ttu-id="c0867-107">Außerdem akzeptiert eine vorhandene **DataColumn** -Objekt und fügt es der Auflistung hinzu und gibt einen Verweis auf die hinzugefügte **DataColumn** Wenn angefordert.</span><span class="sxs-lookup"><span data-stu-id="c0867-107">It also accepts an existing **DataColumn** object and adds it to the collection, and returns a reference to the added **DataColumn** if requested.</span></span> <span data-ttu-id="c0867-108">Da **DataTable** Objekte sind nicht spezifisch für jede Datenquelle, die .NET Framework-Typen werden verwendet, wenn den Datentyp der Angabe einer **DataColumn**.</span><span class="sxs-lookup"><span data-stu-id="c0867-108">Because **DataTable** objects are not specific to any data source, .NET Framework types are used when specifying the data type of a **DataColumn**.</span></span>  
  
 <span data-ttu-id="c0867-109">Im folgenden Beispiel wird die vier Spalten zu einer **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="c0867-109">The following example adds four columns to a **DataTable**.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
  
Dim workCol As DataColumn = workTable.Columns.Add( _  
    "CustID", Type.GetType("System.Int32"))  
workCol.AllowDBNull = false  
workCol.Unique = true  
  
workTable.Columns.Add("CustLName", Type.GetType("System.String"))  
workTable.Columns.Add("CustFName", Type.GetType("System.String"))  
workTable.Columns.Add("Purchases", Type.GetType("System.Double"))  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
  
DataColumn workCol = workTable.Columns.Add("CustID", typeof(Int32));  
workCol.AllowDBNull = false;  
workCol.Unique = true;  
  
workTable.Columns.Add("CustLName", typeof(String));  
workTable.Columns.Add("CustFName", typeof(String));  
workTable.Columns.Add("Purchases", typeof(Double));  
```  
  
 <span data-ttu-id="c0867-110">Im Beispiel beachten Sie, dass die Eigenschaften für die **CustID** Spaltensatz nicht erlauben **DBNull** Werte und Werte eindeutig einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="c0867-110">In the example, notice that the properties for the **CustID** column are set to not allow **DBNull** values and to constrain values to be unique.</span></span> <span data-ttu-id="c0867-111">Jedoch wenn Sie definieren die **CustID** Spalte als die Primärschlüsselspalte der Tabelle, die **AllowDBNull** wird automatisch-Eigenschaftensatz auf **"false"** und die **Unique** wird automatisch-Eigenschaftensatz auf **"true"**.</span><span class="sxs-lookup"><span data-stu-id="c0867-111">However, if you define the **CustID** column as the primary key column of the table, the **AllowDBNull** property will automatically be set to **false** and the **Unique** property will automatically be set to **true**.</span></span> <span data-ttu-id="c0867-112">Weitere Informationen finden Sie unter [Primärschlüssel definieren](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="c0867-112">For more information, see [Defining Primary Keys](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="c0867-113">Wenn ein Spaltenname nicht für eine Spalte angegeben wird, erhält die Spalte einen Standardnamen der Spalte*N,* beginnend mit "Column1", wenn es hinzugefügt wird die **DataColumnCollection**.</span><span class="sxs-lookup"><span data-stu-id="c0867-113">If a column name is not supplied for a column, the column is given an incremental default name of Column*N,* starting with "Column1", when it is added to the **DataColumnCollection**.</span></span> <span data-ttu-id="c0867-114">Es wird empfohlen, dass Sie die Benennungskonvention "Spalte*N*" Wenn Sie einen Spaltennamen angeben, da der Name, die Sie angeben, möglicherweise mit einem bereits vorhandenen Standardspaltennamen in Konflikt der **DataColumnCollection**.</span><span class="sxs-lookup"><span data-stu-id="c0867-114">We recommend that you avoid the naming convention of "Column*N*" when you supply a column name, because the name you supply may conflict with an existing default column name in the **DataColumnCollection**.</span></span> <span data-ttu-id="c0867-115">Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="c0867-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="c0867-116">Wenn Sie das <xref:System.Xml.Linq.XElement>-Element als <xref:System.Data.DataColumn.DataType%2A> einer <xref:System.Data.DataColumn> in der <xref:System.Data.DataTable> verwenden, funktioniert die XML-Serialisierung beim Einlesen von Daten nicht.</span><span class="sxs-lookup"><span data-stu-id="c0867-116">If you are using <xref:System.Xml.Linq.XElement> as the <xref:System.Data.DataColumn.DataType%2A> of a <xref:System.Data.DataColumn> in the <xref:System.Data.DataTable>, XML serialization will not work when you read in data.</span></span> <span data-ttu-id="c0867-117">Wenn Sie beispielsweise ein <xref:System.Xml.XmlDocument> mit der `DataTable.WriteXml`-Methode schreiben, wird bei der Serialisierung in XML ein zusätzlicher übergeordneter Knoten im <xref:System.Xml.Linq.XElement>-Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c0867-117">For example, if you write out a <xref:System.Xml.XmlDocument> by using the `DataTable.WriteXml` method, upon serialization to XML there is an additional parent node in the <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="c0867-118">Um dieses Problem zu umgehen, verwenden Sie den <xref:System.Data.SqlTypes.SqlXml>-Typ statt des <xref:System.Xml.Linq.XElement>-Elements.</span><span class="sxs-lookup"><span data-stu-id="c0867-118">To work around this problem, use the <xref:System.Data.SqlTypes.SqlXml> type instead of <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="c0867-119">`ReadXml` und `WriteXml` funktionieren mit <xref:System.Data.SqlTypes.SqlXml> ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="c0867-119">`ReadXml` and `WriteXml` work correctly with <xref:System.Data.SqlTypes.SqlXml>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0867-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0867-120">See Also</span></span>  
 <xref:System.Data.DataColumn>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="c0867-121">DataTable-Schemadefinition</span><span class="sxs-lookup"><span data-stu-id="c0867-121">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="c0867-122">DataTables</span><span class="sxs-lookup"><span data-stu-id="c0867-122">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="c0867-123">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="c0867-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
