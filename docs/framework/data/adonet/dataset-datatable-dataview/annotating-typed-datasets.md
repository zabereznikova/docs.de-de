---
title: "Hinzufügen von Anmerkungen zu typisierten \"DataSets\""
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
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 4528393d3d9491d9c1f12a867eb093e75d028f3d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="annotating-typed-datasets"></a>Hinzufügen von Anmerkungen zu typisierten "DataSets"
Anmerkungen ermöglichen Ihnen die Namensänderung von Elementen in einem typisierten <xref:System.Data.DataSet>, ohne das zugrunde liegende Schema ändern zu müssen. Die Namen der Elemente im zugrunde liegenden Schema ändern würde das typisierte **DataSet** zum Verweisen auf Objekte, die nicht in der Datenquelle vorhanden sind, als auch verlieren einen Verweis auf die Objekte, die in der Datenquelle vorhanden sind.  
  
 Verwenden von Anmerkungen, können Sie die Namen von Objekten im typisierten anpassen **DataSet** in aussagekräftigere Namen ausführenden Code besser lesbar und Ihre typisierte **DataSet** einfacher für Clients verwenden, lassen zugrunde liegende Schema intakt. Z. B. das folgende Schemaelement für die **Kunden** Tabelle mit den **Northwind** Datenbank würde eine **DataRow** Objektname des  **CustomersRow** und ein <xref:System.Data.DataRowCollection> mit dem Namen **Kunden**.  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Ein **DataRowCollection** Name des **Kunden** ist sinnvoll, im Clientcode, aber ein **DataRow** Name des **CustomersRow** ist irreführend Da es sich um ein einzelnes Objekt handelt. Darüber hinaus gemeinsam Szenarios, das Objekt verwiesen ohne die **Zeile** Bezeichner und stattdessen würde er einfach als bezeichnet eine **Kunden** Objekt. Die Lösung besteht darin, kommentieren das Schema und neue Namen für die **DataRow** und **DataRowCollection** Objekte. Der folgende Code zeigt das vorhergehende Schema mit Anmerkungen.  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Angeben einer **TypedName** Wert **Kunden** führt zu einer **DataRow** Objektname des **Kunden**. Angeben einer **TypedPlural** Wert **Kunden** behält die **DataRowCollection** Name des **Kunden**.  
  
 In der folgenden Tabelle sind die möglichen Anmerkungen aufgeführt.  
  
|Anmerkung|Beschreibung|  
|----------------|-----------------|  
|**typedName**|Name des Objekts.|  
|**typedPlural**|Name einer Auflistung von Objekten.|  
|**typedParent**|Name des Objekts, wenn in einer übergeordneten Beziehung darauf verwiesen wird.|  
|**typedChildren**|Name der Methode zum Zurückgeben von Objekten aus einer untergeordneten Beziehung.|  
|**nullValue**|Wenn die zugrunde liegenden Wert ist **DBNull**. Finden Sie in der folgenden Tabelle **NullValue** Anmerkungen. Die Standardeinstellung ist **_throw**.|  
  
 Die folgende Tabelle zeigt die Werte, die für angegeben werden, können die **NullValue** Anmerkung.  
  
|nullValue-Wert|Beschreibung|  
|---------------------|-----------------|  
|*Ersatzwert*|Gibt einen Wert an, der zurückgegeben werden soll. Der zurückgegebene Wert muss mit dem Elementtyp übereinstimmen. Verwenden Sie z. B. `nullValue="0"`, um 0 für NULL-Ganzzahlfelder zurückzugeben.|  
|**_throw**|Löst eine Ausnahme aus. Dies ist die Standardeinstellung.|  
|**_null**|Gibt einen NULL-Verweis aus oder löst eine Ausnahme aus, wenn ein primitiver Typ festgestellt wird.|  
|**_empty**|Für Zeichenfolgen wird zurückgeben **"String.Empty"**, andernfalls wird ein Objekt aus einem leeren Konstruktor erstellt zurückgegeben. Wenn ein primitiver Typ festgestellt wird, wird eine Ausnahme ausgelöst.|  
  
 Die folgende Tabelle zeigt die Standardwerte für Objekte in einem typisierten **DataSet** und die verfügbaren Anmerkungen.  
  
|Objekt/Methode/Ereignis|Standard|Anmerkung|  
|---------------------------|-------------|----------------|  
|**DataTable**|TableNameDataTable|typedPlural|  
|**DataTable** Methoden|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**DataRowCollection**|TableName|typedPlural|  
|**DataRow**|TableNameRow|typedName|  
|**DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**Property**|PropertyName|typedName|  
|**Untergeordnete** Zugriffsmethode|GetChildTableNameRows|typedChildren|  
|**Übergeordnete** Zugriffsmethode|TableNameRow|typedParent|  
|**DataSet** Ereignisse|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 Um typisierte **DataSet** Anmerkungen, müssen Sie die folgenden einschließen **Xmlns** Verweis in Ihrem Schema für XML Schema Definition Language (XSD). (Um XSD-Code aus Datenbanktabellen erstellen zu können, finden Sie unter <xref:System.Data.DataSet.WriteXmlSchema%2A> oder [arbeiten mit Datasets in Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)).  
  
```  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 Folgender Ausdruck ist ein Beispielschema mit Anmerkungen, die verfügbar macht die **Kunden** Tabelle mit der **Northwind** Datenbank mit einer Beziehung zur der **Aufträge** Tabelle enthalten.  
  
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
  
 Das folgende Codebeispiel verwendet eine stark typisierte **DataSet** aus dem Beispielschema erstellt. Es verwendet einen <xref:System.Data.SqlClient.SqlDataAdapter> zum Auffüllen der **Kunden** Tabelle und ein anderes <xref:System.Data.SqlClient.SqlDataAdapter> zum Auffüllen der **Aufträge** Tabelle. Das stark typisierte **DataSet** definiert die **von "DataRelations"**.  
  
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
    customers.Customers.NewCustomeromer()  
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
    customers.Customers.NewCustomeromer();  
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
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataSet>  
 [Typed DataSets (Typisierte DataSets)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
