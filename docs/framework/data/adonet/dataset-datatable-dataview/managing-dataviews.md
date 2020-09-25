---
title: Verwalten von "DataViews"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0b67fab5-1722-4d2b-bfc1-247a75f0f1ee
ms.openlocfilehash: c07f521b94f23b479281b0314d6b89a095ee9624
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181244"
---
# <a name="managing-dataviews"></a><span data-ttu-id="f75c6-102">Verwalten von "DataViews"</span><span class="sxs-lookup"><span data-stu-id="f75c6-102">Managing DataViews</span></span>

<span data-ttu-id="f75c6-103">Mit einem <xref:System.Data.DataViewManager> können Sie die Ansichtseinstellungen für alle Tabellen in einer <xref:System.Data.DataView> verwalten.</span><span class="sxs-lookup"><span data-stu-id="f75c6-103">You can use a <xref:System.Data.DataViewManager> to manage view settings for all the tables in a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="f75c6-104">Wenn Sie über ein Steuerelement verfügen, das Sie an mehrere Tabellen binden möchten, z. b. ein Raster, das Beziehungen navigiert, ist ein **DataViewManager** ideal.</span><span class="sxs-lookup"><span data-stu-id="f75c6-104">If you have a control that you want to bind to multiple tables, such as a grid that navigates relationships, a **DataViewManager** is ideal.</span></span>  
  
 <span data-ttu-id="f75c6-105">Der **DataViewManager** enthält eine Auflistung von- <xref:System.Data.DataViewSetting> Objekten, die zum Festlegen der Ansichts Einstellung der Tabellen in verwendet werden <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="f75c6-105">The **DataViewManager** contains a collection of <xref:System.Data.DataViewSetting> objects that are used to set the view setting of the tables in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="f75c6-106">Die <xref:System.Data.DataViewSettingCollection> enthält ein- <xref:System.Data.DataViewSetting> Objekt für jede Tabelle in einem **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="f75c6-106">The <xref:System.Data.DataViewSettingCollection> contains one <xref:System.Data.DataViewSetting> object for each table in a **DataSet**.</span></span> <span data-ttu-id="f75c6-107">Sie können die Standardeigenschaften **ApplyDefaultSort**, **Sort**, **RowFilter**und **RowStateFilter** der Tabelle, auf die verwiesen wird, mithilfe der **DataViewSetting**-Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="f75c6-107">You can set the default **ApplyDefaultSort**, **Sort**, **RowFilter**, and **RowStateFilter** properties of the referenced table by using its **DataViewSetting**.</span></span> <span data-ttu-id="f75c6-108">Sie können auf die **DataViewSetting** für eine bestimmte Tabelle anhand des Namens oder ordinalverweises verweisen oder indem Sie einen Verweis auf dieses bestimmte Tabellenobjekt übergeben.</span><span class="sxs-lookup"><span data-stu-id="f75c6-108">You can reference the **DataViewSetting** for a particular table by name or ordinal reference, or by passing a reference to that specific table object.</span></span> <span data-ttu-id="f75c6-109">Mithilfe der **DataViewSettings** -Eigenschaft können Sie auf die Auflistung von **DataViewSetting** -Objekten in einem **DataViewManager** zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f75c6-109">You can access the collection of **DataViewSetting** objects in a **DataViewManager** by using the **DataViewSettings** property.</span></span>  
  
 <span data-ttu-id="f75c6-110">Im folgenden Codebeispiel wird ein **DataSet** mit den SQL Server **Northwind** -Datenbanktabellen **Customers**, **Orders**und **Order Details**gefüllt, die Beziehungen zwischen den Tabellen erstellt, **ein DataViewManager** zum Festlegen der standardmäßigen **DataView** -Einstellungen verwendet und ein **DataGrid** an den **DataViewManager**gebunden.</span><span class="sxs-lookup"><span data-stu-id="f75c6-110">The following code example fills a **DataSet** with the SQL Server **Northwind** database tables **Customers**, **Orders**, and **Order Details**, creates the relationships between the tables, uses a **DataViewManager** to set default **DataView** settings, and binds a **DataGrid** to the **DataViewManager**.</span></span> <span data-ttu-id="f75c6-111">Im Beispiel werden die standardmäßigen **DataView** -Einstellungen für alle Tabellen im **DataSet** festgelegt, um nach dem Primärschlüssel der Tabelle (**ApplyDefaultSort**  =  **true**) zu sortieren. Anschließend wird die Sortierreihenfolge der **Customers** -Tabelle geändert, um nach **CompanyName**zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="f75c6-111">The example sets the default **DataView** settings for all tables in the **DataSet** to sort by the primary key of the table (**ApplyDefaultSort** = **true**), and then modifies the sort order of the **Customers** table to sort by **CompanyName**.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection to Northwind.  
' Create a Connection, DataAdapters, and a DataSet.  
Dim custDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID FROM Orders", connection)  
Dim ordDetDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, ProductID, Quantity FROM [Order Details]", connection)  
  
Dim custDS As DataSet = New DataSet()  
  
' Open the Connection.  
connection.Open()  
  
    ' Fill the DataSet with schema information and data.  
    custDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
    orderDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
    ordDetDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
  
    custDA.Fill(custDS, "Customers")  
    orderDA.Fill(custDS, "Orders")  
    ordDetDA.Fill(custDS, "OrderDetails")  
  
    ' Close the Connection.  
    connection.Close()  
  
    ' Create relationships.  
    custDS.Relations.Add("CustomerOrders", _  
          custDS.Tables("Customers").Columns("CustomerID"), _  
          custDS.Tables("Orders").Columns("CustomerID"))  
  
    custDS.Relations.Add("OrderDetails", _  
          custDS.Tables("Orders").Columns("OrderID"), _  
          custDS.Tables("OrderDetails").Columns("OrderID"))  
  
' Create default DataView settings.  
Dim viewManager As DataViewManager = New DataViewManager(custDS)  
  
Dim viewSetting As DataViewSetting  
For Each viewSetting In viewManager.DataViewSettings  
  viewSetting.ApplyDefaultSort = True  
Next  
  
viewManager.DataViewSettings("Customers").Sort = "CompanyName"  
  
' Bind to a DataGrid.  
Dim grid As System.Windows.Forms.DataGrid = New System.Windows.Forms.DataGrid()  
grid.SetDataBinding(viewManager, "Customers")  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection to Northwind.  
// Create a Connection, DataAdapters, and a DataSet.  
SqlDataAdapter custDA = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderDA = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID FROM Orders", connection);  
SqlDataAdapter ordDetDA = new SqlDataAdapter(  
  "SELECT OrderID, ProductID, Quantity FROM [Order Details]", connection);  
  
DataSet custDS = new DataSet();  
  
// Open the Connection.  
connection.Open();  
  
    // Fill the DataSet with schema information and data.  
    custDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
    orderDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
    ordDetDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
  
    custDA.Fill(custDS, "Customers");  
    orderDA.Fill(custDS, "Orders");  
    ordDetDA.Fill(custDS, "OrderDetails");  
  
    // Close the Connection.  
    connection.Close();  
  
    // Create relationships.  
    custDS.Relations.Add("CustomerOrders",  
          custDS.Tables["Customers"].Columns["CustomerID"],  
          custDS.Tables["Orders"].Columns["CustomerID"]);  
  
    custDS.Relations.Add("OrderDetails",  
          custDS.Tables["Orders"].Columns["OrderID"],  
          custDS.Tables["OrderDetails"].Columns["OrderID"]);  
  
// Create default DataView settings.  
DataViewManager viewManager = new DataViewManager(custDS);  
  
foreach (DataViewSetting viewSetting in viewManager.DataViewSettings)  
  viewSetting.ApplyDefaultSort = true;  
  
viewManager.DataViewSettings["Customers"].Sort = "CompanyName";  
  
// Bind to a DataGrid.  
System.Windows.Forms.DataGrid grid = new System.Windows.Forms.DataGrid();  
grid.SetDataBinding(viewManager, "Customers");  
```  
  
## <a name="see-also"></a><span data-ttu-id="f75c6-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f75c6-112">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataViewManager>
- <xref:System.Data.DataViewSetting>
- <xref:System.Data.DataViewSettingCollection>
- [<span data-ttu-id="f75c6-113">"DataViews"</span><span class="sxs-lookup"><span data-stu-id="f75c6-113">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="f75c6-114">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f75c6-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
