---
title: Hinzufügen von Spalten zu einer "DataTable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 105537a5fccef6de7266407c78cc915f8c5d8678
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204057"
---
# <a name="adding-columns-to-a-datatable"></a><span data-ttu-id="369fe-102">Hinzufügen von Spalten zu einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="369fe-102">Adding Columns to a DataTable</span></span>
<span data-ttu-id="369fe-103">Eine <xref:System.Data.DataTable> enthält eine Auflistung von <xref:System.Data.DataColumn> -Objekten, auf die von der **Columns** -Eigenschaft der Tabelle verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="369fe-103">A <xref:System.Data.DataTable> contains a collection of <xref:System.Data.DataColumn> objects referenced by the **Columns** property of the table.</span></span> <span data-ttu-id="369fe-104">Diese Auflistung von Spalten, zusammen mit allen Einschränkungen, definiert das Schema oder die Struktur der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="369fe-104">This collection of columns, along with any constraints, defines the schema, or structure, of the table.</span></span>  
  
 <span data-ttu-id="369fe-105">Sie erstellen **datacolenn** -Objekte innerhalb einer Tabelle mithilfe des **datacolumschlag** -Konstruktors oder durch Aufrufen der **Add** -Methode der **Columns** -Eigenschaft der Tabelle, bei der es sich <xref:System.Data.DataColumnCollection>um eine handelt.</span><span class="sxs-lookup"><span data-stu-id="369fe-105">You create **DataColumn** objects within a table by using the **DataColumn** constructor, or by calling the **Add** method of the **Columns** property of the table, which is a <xref:System.Data.DataColumnCollection>.</span></span> <span data-ttu-id="369fe-106">Die **Add** -Methode akzeptiert optionale **ColumnName**-, **DataType**-und **Expression** -Argumente und erstellt eine neue **datacolenn** als Member der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="369fe-106">The **Add** method accepts optional **ColumnName**, **DataType**, and **Expression** arguments and creates a new **DataColumn** as a member of the collection.</span></span> <span data-ttu-id="369fe-107">Außerdem akzeptiert Sie ein vorhandenes **datacolenumn** -Objekt und fügt es der Collection hinzu und gibt bei Bedarf einen Verweis auf die hinzugefügte **datacolenn** zurück.</span><span class="sxs-lookup"><span data-stu-id="369fe-107">It also accepts an existing **DataColumn** object and adds it to the collection, and returns a reference to the added **DataColumn** if requested.</span></span> <span data-ttu-id="369fe-108">Da Datentabelle nicht spezifisch für Datenquellen ist, werden .NET Framework Typen beim Angeben des Datentyps einer **datacolenumn**verwendet.</span><span class="sxs-lookup"><span data-stu-id="369fe-108">Because **DataTable** objects are not specific to any data source, .NET Framework types are used when specifying the data type of a **DataColumn**.</span></span>  
  
 <span data-ttu-id="369fe-109">Im folgenden Beispiel werden vier Spalten zu einer **Daten**Tabelle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="369fe-109">The following example adds four columns to a **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="369fe-110">Beachten Sie im Beispiel, dass die Eigenschaften für die **CustId-** Spalte so festgelegt sind, dass **DBNull** -Werte nicht zulässig sind, und dass die Werte als eindeutig festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="369fe-110">In the example, notice that the properties for the **CustID** column are set to not allow **DBNull** values and to constrain values to be unique.</span></span> <span data-ttu-id="369fe-111">Wenn Sie die **CustId-** Spalte jedoch als Primärschlüssel Spalte der Tabelle definieren, wird die **AllowDBNull** -Eigenschaft automatisch auf **false** festgelegt, und die **Unique** -Eigenschaft wird automatisch auf **true**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="369fe-111">However, if you define the **CustID** column as the primary key column of the table, the **AllowDBNull** property will automatically be set to **false** and the **Unique** property will automatically be set to **true**.</span></span> <span data-ttu-id="369fe-112">Weitere Informationen finden Sie unter [Definieren von primär Schlüsseln](defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="369fe-112">For more information, see [Defining Primary Keys](defining-primary-keys.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="369fe-113">Wenn für eine Spalte kein Spaltenname angegeben wird, erhält die Spalte einen inkrementellen Standardnamen von Spalte*N,* beginnend mit "Column1", wenn Sie der **datacolenncollection**hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="369fe-113">If a column name is not supplied for a column, the column is given an incremental default name of Column*N,* starting with "Column1", when it is added to the **DataColumnCollection**.</span></span> <span data-ttu-id="369fe-114">Es wird empfohlen, dass Sie die Benennungs Konvention "Column*N*" vermeiden, wenn Sie einen Spaltennamen angeben, da der von Ihnen bereitgestellte Name möglicherweise mit einem vorhandenen Standard Spaltennamen in der **datacolenncollection**in Konflikt steht.</span><span class="sxs-lookup"><span data-stu-id="369fe-114">We recommend that you avoid the naming convention of "Column*N*" when you supply a column name, because the name you supply may conflict with an existing default column name in the **DataColumnCollection**.</span></span> <span data-ttu-id="369fe-115">Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="369fe-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="369fe-116">Wenn Sie das <xref:System.Xml.Linq.XElement>-Element als <xref:System.Data.DataColumn.DataType%2A> einer <xref:System.Data.DataColumn> in der <xref:System.Data.DataTable> verwenden, funktioniert die XML-Serialisierung beim Einlesen von Daten nicht.</span><span class="sxs-lookup"><span data-stu-id="369fe-116">If you are using <xref:System.Xml.Linq.XElement> as the <xref:System.Data.DataColumn.DataType%2A> of a <xref:System.Data.DataColumn> in the <xref:System.Data.DataTable>, XML serialization will not work when you read in data.</span></span> <span data-ttu-id="369fe-117">Wenn Sie beispielsweise ein <xref:System.Xml.XmlDocument> mit der `DataTable.WriteXml`-Methode schreiben, wird bei der Serialisierung in XML ein zusätzlicher übergeordneter Knoten im <xref:System.Xml.Linq.XElement>-Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="369fe-117">For example, if you write out a <xref:System.Xml.XmlDocument> by using the `DataTable.WriteXml` method, upon serialization to XML there is an additional parent node in the <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="369fe-118">Um dieses Problem zu umgehen, verwenden Sie den <xref:System.Data.SqlTypes.SqlXml>-Typ statt des <xref:System.Xml.Linq.XElement>-Elements.</span><span class="sxs-lookup"><span data-stu-id="369fe-118">To work around this problem, use the <xref:System.Data.SqlTypes.SqlXml> type instead of <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="369fe-119">`ReadXml` und `WriteXml` funktionieren mit <xref:System.Data.SqlTypes.SqlXml> ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="369fe-119">`ReadXml` and `WriteXml` work correctly with <xref:System.Data.SqlTypes.SqlXml>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="369fe-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="369fe-120">See also</span></span>

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="369fe-121">DataTable-Schemadefinition</span><span class="sxs-lookup"><span data-stu-id="369fe-121">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="369fe-122">DataTables</span><span class="sxs-lookup"><span data-stu-id="369fe-122">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="369fe-123">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="369fe-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
