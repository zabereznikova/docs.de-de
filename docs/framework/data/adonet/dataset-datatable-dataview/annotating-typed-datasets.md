---
title: "Hinzuf&#252;gen von Anmerkungen zu typisierten DataSets | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# Hinzuf&#252;gen von Anmerkungen zu typisierten DataSets
Anmerkungen ermöglichen Ihnen die Namensänderung von Elementen in einem typisierten <xref:System.Data.DataSet>, ohne das zugrunde liegende Schema ändern zu müssen.  Wenn Sie die Namen der Elemente im zugrunde liegenden Schema ändern, verweist das typisierte **DataSet** auf Objekte, die nicht in der Datenquelle vorhanden sind, und der Verweis auf die in der Datenquelle vorhandenen Objekte geht verloren.  
  
 Mithilfe von Anmerkungen können Sie die Namen von Objekten im typisierten **DataSet** in aussagekräftigere Namen ändern, sodass der Code leichter lesbar und die Verwendung des typisierten **DataSet** für Clients erleichtert wird, während das zugrunde liegende Schema gleichzeitig erhalten bleibt.  Das folgende Schemaelement für die **Customers**\-Tabelle der **Northwind**\-Datenbank ergibt z. B. einen **DataRow**\-Objektnamen **CustomersRow** und eine <xref:System.Data.DataRowCollection> mit dem Namen **Customers**.  
  
```  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Der **DataRowCollection**\-Name **Customers** im Clientcode ist aussagekräftig, der **DataRow**\-Name **CustomersRow** ist jedoch irreführend, weil es sich um ein einzelnes Objekt handelt.  Außerdem wird in üblichen Szenarien ohne den **Row**\-Bezeichner auf das Objekt verwiesen, d. h., dass stattdessen wird nur als **Customer**\-Objekt darauf verwiesen.  Die Lösung besteht darin, eine Anmerkung für das Schema festzulegen und neue Namen für die Objekte **DataRow** und **DataRowCollection** anzugeben.  Der folgende Code zeigt das vorhergehende Schema mit Anmerkungen.  
  
```  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Wenn Sie einen **typedName**\-Wert für **Customer** angeben, ergibt sich daraus der **DataRow**\-Objektname **Customer**.  Wenn ein **typedPlural**\-Wert für **Customers** angegeben wird, bleibt der **DataRowCollection**\-Name **Customers** erhalten.  
  
 In der folgenden Tabelle sind die möglichen Anmerkungen aufgeführt.  
  
|Anmerkung|Beschreibung|  
|---------------|------------------|  
|**typedName**|Name des Objekts.|  
|**typedPlural**|Name einer Auflistung von Objekten.|  
|**typedParent**|Name des Objekts, wenn in einer übergeordneten Beziehung darauf verwiesen wird.|  
|**typedChildren**|Name der Methode zum Zurückgeben von Objekten aus einer untergeordneten Beziehung.|  
|**nullValue**|Wert, wenn der zugrunde liegende Wert **DBNull** lautet.  Informationen zu **nullValue**\-Anmerkungen finden Sie in der folgenden Tabelle.  Der Standardwert ist **\_throw**.|  
  
 In der folgenden Tabelle sind die Werte aufgeführt, die für die **nullValue**\-Anmerkung angegeben werden können.  
  
|nullValue\-Wert|Beschreibung|  
|---------------------|------------------|  
|*Ersatzwert*|Gibt einen Wert an, der zurückgegeben werden soll.  Der zurückgegebene Wert muss mit dem Elementtyp übereinstimmen.  Verwenden Sie z. B. `nullValue="0"`, um 0 für NULL\-Ganzzahlfelder zurückzugeben.|  
|**\_throw**|Löst eine Ausnahme aus.  Dies ist die Standardeinstellung.|  
|**\_null**|Gibt einen NULL\-Verweis aus oder löst eine Ausnahme aus, wenn ein primitiver Typ festgestellt wird.|  
|**\_empty**|Für Zeichenfolgen wird **String.Empty** zurückgegeben, andernfalls wird ein Objekt zurückgegeben, das aus einem leeren Konstruktor erstellt wurde.  Wenn ein primitiver Typ festgestellt wird, wird eine Ausnahme ausgelöst.|  
  
 In der folgenden Tabelle sind die Standardwerte für Objekte in einem typisierten **DataSet** und die verfügbaren Anmerkungen aufgeführt.  
  
|Objekt\/Methode\/Ereignis|Standard|Anmerkung|  
|-------------------------------|--------------|---------------|  
|**DataTable**|TableNameDataTable|typedPlural|  
|**DataTable**\-Methoden|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**DataRowCollection**|TableName|typedPlural|  
|**DataRow**|TableNameRow|typedName|  
|**DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**Eigenschaft**|PropertyName|typedName|  
|**Child**\-Accessor|GetChildTableNameRows|typedChildren|  
|**Parent**\-Accessor|TableNameRow|typedParent|  
|**DataSet**\-Ereignisse|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 Um typisierte **DataSet**\-Anmerkungen verwenden zu können, müssen Sie den folgenden **xmlns**\-Verweis in das XSD\-Schema \(XML Schema Definition Language\) einfügen.  \(Informationen zur XSD\-Erstellung unter Verwendung von Datenbanktabellen finden Sie unter <xref:System.Data.DataSet.WriteXmlSchema%2A> oder [Arbeiten mit Datasets in Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)\).  
  
```  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 Der folgende Code ist ein Beispielschema mit Anmerkungen, das die **Customers**\-Tabelle der **Northwind**\-Datenbank mit einer Beziehung zur **Orders**\-Tabelle verfügbar macht.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet"   
      xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
      xmlns=""   
      xmlns:xs="http://www.w3.org/2001/XMLSchema"   
      xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers" codegen:typedName="Customer"  
codegen:typedPlural="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID" type="xs:string" minOccurs="0" />  
              <xs:element name="CompanyName"  
codegen:typedName="CompanyName" type="xs:string" minOccurs="0" />  
              <xs:element name="Phone" codegen:typedName="Phone"  
codegen:nullValue="" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="Orders" codegen:typedName="Order"  
codegen:typedPlural="Orders">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="OrderID" codegen:typedName="OrderID"  
type="xs:int" minOccurs="0" />  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID"  
                 codegen:nullValue="" type="xs:string" minOccurs="0" />  
              <xs:element name="EmployeeID"  
codegen:typedName="EmployeeID" codegen:nullValue="0"   
type="xs:int" minOccurs="0" />  
              <xs:element name="OrderAdapter"  
codegen:typedName="OrderAdapter"  
codegen:nullValue="1980-01-01T00:00:00"   
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
  
 Im folgenden Codebeispiel wird ein **DataSet** mit strikter Typbindung verwendet, das aus dem Beispielschema erstellt wurde.  Es verwendet einen <xref:System.Data.SqlClient.SqlDataAdapter> zum Füllen der **Customers**\-Tabelle und einen anderen <xref:System.Data.SqlClient.SqlDataAdapter> zum Füllen der **Orders**\-Tabelle.  Das **DataSet** mit strikter Typbindung definiert die **DataRelations**.  
  
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
  
## Siehe auch  
 <xref:System.Data.DataColumnCollection>   
 <xref:System.Data.DataSet>   
 [Typisierte 'DataSets'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)   
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)