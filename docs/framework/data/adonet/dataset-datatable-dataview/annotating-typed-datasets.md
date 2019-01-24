---
title: Hinzufügen von Anmerkungen zu typisierten "DataSets"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: 737f98dd11d6172bb79aaa925ac153c64728e9ff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629607"
---
# <a name="annotating-typed-datasets"></a>Hinzufügen von Anmerkungen zu typisierten "DataSets"
Anmerkungen ermöglichen Ihnen die Namensänderung von Elementen in einem typisierten <xref:System.Data.DataSet>, ohne das zugrunde liegende Schema ändern zu müssen. Ändern die Namen der Elemente im zugrunde liegenden Schema würde dazu führen, dass die typisierte **DataSet** zum Verweisen auf Objekte, die nicht in der Datenquelle vorhanden sind, als auch einen Verweis auf die Objekte, die in der Datenquelle vorhanden sind, verlieren.  
  
 Verwenden von Anmerkungen, können Sie die Namen von Objekten in einem typisierten anpassen **DataSet** in aussagekräftigere Namen, sodass Code leichter lesbar und einem typisierten **DataSet** einfacher für Clients verwenden, bleiben zugrunde liegende Schema intakt. Z. B. das folgende Schemaelement für die **Kunden** Tabelle mit den **Northwind** -Datenbank ergibt eine **DataRow** Objektnamen des  **CustomersRow** und <xref:System.Data.DataRowCollection> mit dem Namen **Kunden**.  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Ein **DataRowCollection** Name des **Kunden** ist sinnvoll, im Clientcode, aber ein **DataRow** Name des **CustomersRow** ist irreführend Da es sich um ein einzelnes Objekt handelt. Darüber hinaus in gängigen Szenarien würden werden verweisen auf das Objekt ohne die **Zeile** Bezeichner und stattdessen wäre einfach, die als bezeichnet ein **Kunden** Objekt. Die Lösung besteht darin, kommentieren das Schema, und neue Namen für die **DataRow** und **DataRowCollection** Objekte. Der folgende Code zeigt das vorhergehende Schema mit Anmerkungen.  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Angeben einer **TypedName** Wert **Kunden** führt zu einer **DataRow** Objektnamen des **Kunden**. Angeben einer **TypedPlural** Wert **Kunden** behält die **DataRowCollection** Name des **Kunden**.  
  
 In der folgenden Tabelle sind die möglichen Anmerkungen aufgeführt.  
  
|Anmerkung|Beschreibung|  
|----------------|-----------------|  
|**typedName**|Name des Objekts.|  
|**typedPlural**|Name einer Auflistung von Objekten.|  
|**typedParent**|Name des Objekts, wenn in einer übergeordneten Beziehung darauf verwiesen wird.|  
|**typedChildren**|Name der Methode zum Zurückgeben von Objekten aus einer untergeordneten Beziehung.|  
|**nullValue**|Wenn der zugrunde liegenden Wert ist **DBNull**. Finden Sie in der folgenden Tabelle **NullValue** Anmerkungen. Der Standardwert ist **_throw**.|  
  
 Die folgende Tabelle zeigt die Werte, die für die angegeben werden, können die **NullValue** Anmerkung.  
  
|nullValue-Wert|Beschreibung|  
|---------------------|-----------------|  
|*Ersatzwert*|Gibt einen Wert an, der zurückgegeben werden soll. Der zurückgegebene Wert muss mit dem Elementtyp übereinstimmen. Verwenden Sie z. B. `nullValue="0"`, um 0 für NULL-Ganzzahlfelder zurückzugeben.|  
|**_throw**|Löst eine Ausnahme aus. Dies ist die Standardeinstellung.|  
|**_null**|Gibt einen NULL-Verweis aus oder löst eine Ausnahme aus, wenn ein primitiver Typ festgestellt wird.|  
|**_empty**|Für Zeichenfolgen wird zurückgeben **String.Empty**, ein Objekt aus einem leeren Konstruktor erstellt wird. andernfalls zurückgegeben. Wenn ein primitiver Typ festgestellt wird, wird eine Ausnahme ausgelöst.|  
  
 Die folgende Tabelle zeigt die Standardwerte für Objekte in einem typisierten **DataSet** und die verfügbaren Anmerkungen.  
  
|Objekt/Methode/Ereignis|Standard|Anmerkung|  
|---------------------------|-------------|----------------|  
|**DataTable**|TableNameDataTable|typedPlural|  
|**DataTable** Methoden|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**DataRowCollection**|TableName|typedPlural|  
|**DataRow**|TableNameRow|typedName|  
|**DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**Property**|PropertyName|typedName|  
|**Untergeordnete** Accessor|GetChildTableNameRows|typedChildren|  
|**Übergeordnete** Accessor|TableNameRow|typedParent|  
|**DataSet** Ereignisse|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 Um typisierte **DataSet** Anmerkungen, Sie müssen Folgendes umfassen **Xmlns** Verweis in Ihrem Schema für XML Schema Definition Language (XSD). (Um ein XSD-Schema aus Datenbanktabellen erstellen zu können, finden Sie unter <xref:System.Data.DataSet.WriteXmlSchema%2A> oder [arbeiten mit Datasets in Visual Studio](https://msdn.microsoft.com/library/8bw9ksd6.aspx)).  
  
```  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 Im folgenden finden Sie ein Beispielschema mit Anmerkungen, die verfügbar macht die **Kunden** Tabelle mit der **Northwind** Datenbank mit einer Beziehung zur der **Bestellungen** enthaltene Tabelle.  
  
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
  
 Das folgende Codebeispiel verwendet einen stark typisierten **DataSet** aus dem Beispielschema erstellt. Es verwendet einen <xref:System.Data.SqlClient.SqlDataAdapter> zum Auffüllen der **Kunden** Tabelle und einer <xref:System.Data.SqlClient.SqlDataAdapter> zum Auffüllen der **Bestellungen** Tabelle. Die stark typisierte **DataSet** definiert die **von "DataRelations"**.  
  
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
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [Typed DataSets (Typisierte DataSets)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)
- [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
