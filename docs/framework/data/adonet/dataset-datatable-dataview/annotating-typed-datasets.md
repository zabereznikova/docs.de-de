---
title: Hinzufügen von Anmerkungen zu typisierten "DataSets"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: 79d3913827d5df6f0ac4e77bfdb8f37b553a86d2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203747"
---
# <a name="annotating-typed-datasets"></a>Hinzufügen von Anmerkungen zu typisierten "DataSets"

Anmerkungen ermöglichen Ihnen die Namensänderung von Elementen in einem typisierten <xref:System.Data.DataSet>, ohne das zugrunde liegende Schema ändern zu müssen. Wenn Sie die Namen der Elemente im zugrunde liegenden Schema ändern, verweist das typisierte **DataSet** auf Objekte, die in der Datenquelle nicht vorhanden sind, und Sie verlieren einen Verweis auf die Objekte, die in der Datenquelle vorhanden sind.  
  
 Mit Anmerkungen können Sie die Namen von Objekten in Ihrem typisierten **DataSet** mit aussagekräftigeren Namen anpassen, sodass der Code besser lesbar ist und das typisierte **DataSet** für Clients einfacher zu verwenden ist, während das zugrunde liegende Schema intakt bleibt. Das folgende Schema Element für die **Customers** -Tabelle der **Northwind** -Datenbank würde z. b. den Namen des **DataRow** -Objekts **CustomersRow** und einen <xref:System.Data.DataRowCollection> benannten **Kunden**ergeben.  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Der **DataRowCollection** -Name von **Kunden** ist im Client Code aussagekräftig, aber der **DataRow** -Name **CustomersRow** ist irreführend, da es sich um ein einzelnes Objekt handelt. In gängigen Szenarien wird das Objekt auch ohne den **Zeilen** Bezeichner referenziert und stattdessen einfach als **Customer** -Objekt bezeichnet. Die Lösung besteht darin, das Schema mit Anmerkungen zu versehen und neue Namen für die Objekte **DataRow** und **DataRowCollection** zu ermitteln. Der folgende Code zeigt das vorhergehende Schema mit Anmerkungen.  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Das Angeben eines **typedName** -Werts von **Customer** führt zu einem **DataRow** -Objektnamen von **Customer**. Wenn Sie einen **typedPlural** -Wert von **Kunden** angeben, wird der **DataRowCollection** -Name von **Kunden**beibehalten.  
  
 In der folgenden Tabelle sind die möglichen Anmerkungen aufgeführt.  
  
|Anmerkung|Beschreibung|  
|----------------|-----------------|  
|**typedName**|Name des Objekts.|  
|**typedPlural**|Name einer Auflistung von Objekten.|  
|**typedParent**|Name des Objekts, wenn in einer übergeordneten Beziehung darauf verwiesen wird.|  
|**typedChildren**|Name der Methode zum Zurückgeben von Objekten aus einer untergeordneten Beziehung.|  
|**nullValue**|Wert, wenn der zugrunde liegende Wert **DBNull**ist. In der folgenden Tabelle finden Sie Informationen zu **NullValue** -Anmerkungen. Der Standardwert ist **_throw**.|  
  
 In der folgenden Tabelle sind die Werte aufgeführt, die für die **NullValue** -Anmerkung angegeben werden können.  
  
|nullValue-Wert|Beschreibung|  
|---------------------|-----------------|  
|*Ersatzwert*|Gibt einen Wert an, der zurückgegeben werden soll. Der zurückgegebene Wert muss mit dem Elementtyp übereinstimmen. Verwenden Sie z. B. `nullValue="0"`, um 0 für NULL-Ganzzahlfelder zurückzugeben.|  
|**_throw**|Löst eine Ausnahme aus. Dies ist die Standardeinstellung.|  
|**_null**|Gibt einen NULL-Verweis aus oder löst eine Ausnahme aus, wenn ein primitiver Typ festgestellt wird.|  
|**_empty**|Für Zeichen folgen wird **String. Empty**zurückgegeben, andernfalls wird ein Objekt zurückgegeben, das aus einem leeren Konstruktor erstellt wurde. Wenn ein primitiver Typ festgestellt wird, wird eine Ausnahme ausgelöst.|  
  
 In der folgenden Tabelle werden die Standardwerte für Objekte in einem typisierten **DataSet** und die verfügbaren Anmerkungen angezeigt.  
  
|Objekt/Methode/Ereignis|Standard|Anmerkung|  
|---------------------------|-------------|----------------|  
|**DataTable**|TableNameDataTable|typedPlural|  
|**Daten** Tabelle Anzuwenden|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**DataRowCollection**|TableName|typedPlural|  
|**DataRow**|TableNameRow|typedName|  
|**DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**Eigenschaft**|PropertyName|typedName|  
|**Child** Untergeordnetes Element Accessor|GetChildTableNameRows|typedChildren|  
|Über **geordnetes** Element Accessor|TableNameRow|typedParent|  
|**DataSet** Fall|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 Um typisierte **datasetanmerkungen** verwenden zu können, müssen Sie den folgenden **xmlns** -Verweis in das XSD-Schema (XML Schema Definition Language) einschließen. Informationen zum Erstellen einer XSD aus Datenbanktabellen finden Sie unter <xref:System.Data.DataSet.WriteXmlSchema%2A> oder [Arbeiten mit Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).  
  
```xml  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 Das folgende Beispiel zeigt ein Schema mit Anmerkungen, das die **Customers** -Tabelle der **Northwind** -Datenbank mit einer Beziehung zur Tabelle **Orders** verfügbar macht.  
  
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
  
 Im folgenden Codebeispiel wird ein stark typisiertes **DataSet** verwendet, das aus dem Beispiel Schema erstellt wurde. Er verwendet einen <xref:System.Data.SqlClient.SqlDataAdapter> zum Auffüllen der **Customers** -Tabelle und einen anderen zum Auffüllen <xref:System.Data.SqlClient.SqlDataAdapter> der **Orders** -Tabelle. Das **DataSet** mit starker Typisierung definiert die **DataRelations**.  
  
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
