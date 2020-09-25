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
# <a name="managing-dataviews"></a>Verwalten von "DataViews"

Mit einem <xref:System.Data.DataViewManager> können Sie die Ansichtseinstellungen für alle Tabellen in einer <xref:System.Data.DataView> verwalten. Wenn Sie über ein Steuerelement verfügen, das Sie an mehrere Tabellen binden möchten, z. b. ein Raster, das Beziehungen navigiert, ist ein **DataViewManager** ideal.  
  
 Der **DataViewManager** enthält eine Auflistung von- <xref:System.Data.DataViewSetting> Objekten, die zum Festlegen der Ansichts Einstellung der Tabellen in verwendet werden <xref:System.Data.DataSet> . Die <xref:System.Data.DataViewSettingCollection> enthält ein- <xref:System.Data.DataViewSetting> Objekt für jede Tabelle in einem **DataSet**. Sie können die Standardeigenschaften **ApplyDefaultSort**, **Sort**, **RowFilter**und **RowStateFilter** der Tabelle, auf die verwiesen wird, mithilfe der **DataViewSetting**-Eigenschaft festlegen. Sie können auf die **DataViewSetting** für eine bestimmte Tabelle anhand des Namens oder ordinalverweises verweisen oder indem Sie einen Verweis auf dieses bestimmte Tabellenobjekt übergeben. Mithilfe der **DataViewSettings** -Eigenschaft können Sie auf die Auflistung von **DataViewSetting** -Objekten in einem **DataViewManager** zugreifen.  
  
 Im folgenden Codebeispiel wird ein **DataSet** mit den SQL Server **Northwind** -Datenbanktabellen **Customers**, **Orders**und **Order Details**gefüllt, die Beziehungen zwischen den Tabellen erstellt, **ein DataViewManager** zum Festlegen der standardmäßigen **DataView** -Einstellungen verwendet und ein **DataGrid** an den **DataViewManager**gebunden. Im Beispiel werden die standardmäßigen **DataView** -Einstellungen für alle Tabellen im **DataSet** festgelegt, um nach dem Primärschlüssel der Tabelle (**ApplyDefaultSort**  =  **true**) zu sortieren. Anschließend wird die Sortierreihenfolge der **Customers** -Tabelle geändert, um nach **CompanyName**zu sortieren.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Data.DataSet>
- <xref:System.Data.DataViewManager>
- <xref:System.Data.DataViewSetting>
- <xref:System.Data.DataViewSettingCollection>
- ["DataViews"](dataviews.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
