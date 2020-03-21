---
title: Hinzufügen von Anmerkungen zu typisierten "DataSets"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: 757a87f92d8dc6049de1844fed892d95dc57c990
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151519"
---
# <a name="annotating-typed-datasets"></a>Hinzufügen von Anmerkungen zu typisierten "DataSets"
Anmerkungen ermöglichen Ihnen die Namensänderung von Elementen in einem typisierten <xref:System.Data.DataSet>, ohne das zugrunde liegende Schema ändern zu müssen. Das Ändern der Namen der Elemente im zugrunde liegenden Schema würde dazu führen, dass das typisierte **DataSet** auf Objekte verweist, die in der Datenquelle nicht vorhanden sind, und einen Verweis auf die Objekte verliert, die in der Datenquelle vorhanden sind.  
  
 Mithilfe von Anmerkungen können Sie die Namen von Objekten in Ihrem typisierten **DataSet** mit aussagekräftigeren Namen anpassen, wodurch Code besser lesbar und Das typisierte **DataSet** für Clients einfacher zu verwenden ist, während das zugrunde liegende Schema intakt bleibt. Das folgende Schemaelement für die **Customers-Tabelle** der **Northwind-Datenbank** würde z. B. <xref:System.Data.DataRowCollection> zu einem **DataRow-Objektnamen** von **CustomersRow** und einem benannten **Customers**führen.  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Ein **DataRowCollection-Name** von **Customers** ist im Clientcode sinnvoll, aber ein **DataRow-Name** von **CustomersRow** ist irreführend, da es sich um ein einzelnes Objekt handelt. Außerdem wird in allgemeinen Szenarien das Objekt **Row** ohne den Zeilenbezeichner und stattdessen einfach als **Customer-Objekt** bezeichnet. Die Lösung besteht darin, das Schema zu kommentieren und neue Namen für die **DataRow-** und **DataRowCollection-Objekte** zu identifizieren. Der folgende Code zeigt das vorhergehende Schema mit Anmerkungen.  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Die Angabe eines **typisiertenNamenswerts** von **Customer** führt zu einem **DataRow-Objektnamen** von **Customer**. Durch die Angabe eines **typdPlural-Werts** von **Customers** wird der **DataRowCollection-Name** von **Customers**beibehalten.  
  
 In der folgenden Tabelle sind die möglichen Anmerkungen aufgeführt.  
  
|Anmerkung|Beschreibung|  
|----------------|-----------------|  
|**typedName**|Name des Objekts.|  
|**typedPlural**|Name einer Auflistung von Objekten.|  
|**typedParent**|Name des Objekts, wenn in einer übergeordneten Beziehung darauf verwiesen wird.|  
|**typedChildren**|Name der Methode zum Zurückgeben von Objekten aus einer untergeordneten Beziehung.|  
|**nullValue**|Wert, wenn der zugrunde liegende Wert **DBNull**ist. Siehe die folgende **nullValue** Tabelle für nullValue-Anmerkungen. Der Standardwert ist **_throw**.|  
  
 Die folgende Tabelle zeigt die Werte, die für die **nullValue-Anmerkung** angegeben werden können.  
  
|nullValue-Wert|Beschreibung|  
|---------------------|-----------------|  
|*Ersatzwert*|Gibt einen Wert an, der zurückgegeben werden soll. Der zurückgegebene Wert muss mit dem Elementtyp übereinstimmen. Verwenden Sie z. B. `nullValue="0"`, um 0 für NULL-Ganzzahlfelder zurückzugeben.|  
|**_throw**|Löst eine Ausnahme aus. Dies ist die Standardoption.|  
|**_null**|Gibt einen NULL-Verweis aus oder löst eine Ausnahme aus, wenn ein primitiver Typ festgestellt wird.|  
|**_empty**|Geben Sie für Zeichenfolgen **String.Empty**zurück, andernfalls gibt sie ein Objekt zurück, das von einem leeren Konstruktor erstellt wurde. Wenn ein primitiver Typ festgestellt wird, wird eine Ausnahme ausgelöst.|  
  
 Die folgende Tabelle zeigt Standardwerte für Objekte in einem typisierten **DataSet** und die verfügbaren Anmerkungen.  
  
|Objekt/Methode/Ereignis|Standard|Anmerkung|  
|---------------------------|-------------|----------------|  
|**DataTable**|TableNameDataTable|typedPlural|  
|**DataTable** Methoden|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**DataRowCollection**|TableName|typedPlural|  
|**Datarow**|TableNameRow|typedName|  
|**DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**Eigenschaft**|PropertyName|typedName|  
|**Kind** Accessor|GetChildTableNameRows|typedChildren|  
|**Eltern** Accessor|TableNameRow|typedParent|  
|**DataSet** Ereignisse|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 Um typisierte **DataSet-Anmerkungen** zu verwenden, müssen Sie den folgenden **XMLns-Verweis** in Ihr XSD-Schema (XML Schema Definition Language) aufnehmen. Informationen zum Erstellen eines xsd <xref:System.Data.DataSet.WriteXmlSchema%2A> aus Datenbanktabellen finden Sie unter oder [Arbeiten mit Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).  
  
```xml  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 Im Folgenden finden Sie ein mit Anmerkungen des Beispiels ananmerkungsiertes Schema, das die **Customers-Tabelle** der **Northwind-Datenbank** mit einer Beziehung zur enthaltenen **Tabelle "Orders"** verfügbar macht.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet"
      xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
      xmlns=""
      xmlns:xs="http://www.w3.org/2001/XMLSchema"
      xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID" type="xs:string" minOccurs="0" />  
              <xs:element name="CompanyName"  
codegen:typedName="CompanyName" type="xs:string" minOccurs="0" />  
              <xs:element name="Phone" codegen:typedName="Phone" codegen:nullValue="" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="Orders" codegen:typedName="Order" codegen:typedPlural="Orders">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="OrderID" codegen:typedName="OrderID"  
type="xs:int" minOccurs="0" />  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID"                  codegen:nullValue="" type="xs:string" minOccurs="0" />  
              <xs:element name="EmployeeID"  
codegen:typedName="EmployeeID" codegen:nullValue="0"
type="xs:int" minOccurs="0" />  
              <xs:element name="OrderAdapter"  
codegen:typedName="OrderAdapter" codegen:nullValue="1980-01-01T00:00:00"
type="xs:dateTime" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
    <xs:unique name="Constraint1">  
      <xs:selector xpath=".//Customers" />  
      <xs:field xpath="CustomerID" />  
    </xs:unique>  
    <xs:keyref name="CustOrders" refer="Constraint1"  
codegen:typedParent="Customer" codegen:typedChildren="GetOrders">  
      <xs:selector xpath=".//Orders" />  
      <xs:field xpath="CustomerID" />  
    </xs:keyref>  
  </xs:element>  
</xs:schema>  
```  
  
 Im folgenden Codebeispiel wird ein stark typisiertes **DataSet** verwendet, das aus dem Beispielschema erstellt wurde. Es verwendet <xref:System.Data.SqlClient.SqlDataAdapter> eine, um die **Customers-Tabelle** aufzufüllen, und eine andere, <xref:System.Data.SqlClient.SqlDataAdapter> um die Tabelle **"Bestellungen"** aufzufüllen. Das stark typisierte **DataSet** definiert **dataRelations**.  
  
```vb  
' Assumes a valid SqlConnection object named connection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT CustomerID, CompanyName, Phone FROM Customers", &  
    connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders", &  
    connection)  
  
' Populate a strongly typed DataSet.  
connection.Open()  
Dim customers As CustomerDataSet = New CustomerDataSet()  
customerAdapter.Fill(customers, "Customers")  
orderAdapter.Fill(customers, "Orders")  
connection.Close()  
  
' Add a strongly typed event.  
AddHandler customers.Customers.CustomerChanged, &  
    New CustomerDataSet.CustomerChangeEventHandler( _  
    AddressOf OnCustomerChanged)  
  
' Add a strongly typed DataRow.  
Dim newCustomer As CustomerDataSet.Customer = _  
    customers.Customers.NewCustomer()  
newCustomer.CustomerID = "NEW01"  
newCustomer.CompanyName = "My New Company"  
customers.Customers.AddCustomer(newCustomer)  
  
' Navigate the child relation.  
Dim customer As CustomerDataSet.Customer  
Dim order As CustomerDataSet.Order  
  
For Each customer In customers.Customers  
  Console.WriteLine(customer.CustomerID)  
  For Each order In customer.GetOrders()  
    Console.WriteLine(vbTab & order.OrderID)  
  Next  
Next  
  
Private Shared Sub OnCustomerChanged( _  
    sender As Object, e As CustomerDataSet.CustomerChangeEvent)  
  
End Sub  
```  
  
```csharp  
// Assumes a valid SqlConnection object named connection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
    "SELECT CustomerID, CompanyName, Phone FROM Customers",  
    connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders",
    connection);  
  
// Populate a strongly typed DataSet.  
connection.Open();  
CustomerDataSet customers = new CustomerDataSet();  
customerAdapter.Fill(customers, "Customers");  
orderAdapter.Fill(customers, "Orders");  
connection.Close();  
  
// Add a strongly typed event.  
customers.Customers.CustomerChanged += new
  CustomerDataSet.CustomerChangeEventHandler(OnCustomerChanged);  
  
// Add a strongly typed DataRow.  
CustomerDataSet.Customer newCustomer =
    customers.Customers.NewCustomer();  
newCustomer.CustomerID = "NEW01";  
newCustomer.CompanyName = "My New Company";  
customers.Customers.AddCustomer(newCustomer);  
  
// Navigate the child relation.  
foreach(CustomerDataSet.Customer customer in customers.Customers)  
{  
  Console.WriteLine(customer.CustomerID);  
  foreach(CustomerDataSet.Order order in customer.GetOrders())  
    Console.WriteLine("\t" + order.OrderID);  
}  
  
protected static void OnCustomerChanged(object sender, CustomerDataSet.CustomerChangeEvent e)  
    {  
  
    }  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [Typisierte "DataSets"](typed-datasets.md)
- ["DataSets", "DataTables" und "DataViews"](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
