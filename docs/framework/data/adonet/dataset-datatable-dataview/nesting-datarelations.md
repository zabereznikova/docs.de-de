---
title: Verschachteln von "DataRelations"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
ms.openlocfilehash: 9255615c7786773f1d4f453b910fdccdf191721f
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45513741"
---
# <a name="nesting-datarelations"></a>Verschachteln von "DataRelations"
Bei einer relationalen Darstellung von Daten enthalten einzelne Tabellen Zeilen, die über eine Spalte oder eine Gruppe von Spalten miteinander in Beziehung stehen. Im ADO.NET-<xref:System.Data.DataSet> wird die Beziehung zwischen Tabellen mit einer <xref:System.Data.DataRelation> implementiert. Bei der Erstellung einer **DataRelation**, die Beziehungen zwischen über-und untergeordneten Spalten nur über die Beziehung verwaltet werden. 	Die Tabellen und Spalten sind separate Entitäten. Bei der hierarchischen Darstellung von durch XML bereitgestellten Daten werden die hierarchischen Beziehungen durch übergeordnete Elemente dargestellt, die geschachtelte untergeordnete Elemente enthalten.  
  
 Um die Schachtelung von untergeordneten Objekten zu erleichtern bei einer **DataSet** mit synchronisiert wird ein <xref:System.Xml.XmlDataDocument> oder als XML-Daten mit geschrieben **WriteXml**, die **DataRelation** Stellt eine **geschachtelte** Eigenschaft. Festlegen der **geschachtelte** Eigenschaft eine **DataRelation** zu **"true"** bewirkt, dass die untergeordneten Zeilen der Beziehung innerhalb der übergeordneten Spalte aus, sofern es als XML-Daten geschrieben werden, geschachtelt oder Synchronisierung mit einem **XmlDataDocument**. Die **geschachtelte** Eigenschaft der **DataRelation** ist **"false"**, in der Standardeinstellung.  
  
 Betrachten Sie beispielsweise die folgenden **DataSet**.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection)  
  
connection.Open()  
  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
customerAdapter.Fill(dataSet, "Customers")  
orderAdapter.Fill(dataSet, "Orders")  
  
connection.Close()  
  
Dim customerOrders As DataRelation = dataSet.Relations.Add( _  
  "CustOrders", dataSet.Tables("Customers").Columns("CustomerID"), _  
  dataSet.Tables("Orders").Columns("CustomerID"))  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection);  
  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
customerAdapter.Fill(dataSet, "Customers");  
orderAdapter.Fill(dataSet, "Orders");  
  
connection.Close();  
  
DataRelation customerOrders = dataSet.Relations.Add(  
  "CustOrders", dataSet.Tables["Customers"].Columns["CustomerID"],  
  dataSet.Tables["Orders"].Columns["CustomerID"]);  
```  
  
 Da die **geschachtelte** Eigenschaft der **DataRelation** Objekt ist nicht festgelegt, um **"true"** für diesen **DataSet**, die untergeordneten Objekte werden nicht verschachtelt werden. innerhalb des übergeordneten Elements bei der dies **DataSet** wird als XML-Daten dargestellt. Transformiert die XML-Darstellung einer **DataSet** enthält, die zugehörigen **DataSet**mit nicht geschachtelten datenbeziehungen kann zu Leistungseinbußen führen. Wir empfehlen daher, die Datenbeziehungen zu schachteln. Zu diesem Zweck legen Sie die **geschachtelte** Eigenschaft **"true"**. Schreiben Sie dann Code in die XSLT-Formatvorlage, der hierarchische XPath-Abfrageausdrücke in Top-Down-Form verwendet, um die Daten zu finden und zu transformieren.  
  
 Das folgende Codebeispiel zeigt das Ergebnis des Aufrufs **WriteXml** auf die **DataSet**.  
  
```xml  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
  <Orders>  
    <OrderID>10643</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-08-25T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10692</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-10-03T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10308</OrderID>  
    <CustomerID>ANATR</CustomerID>  
    <OrderDate>1996-09-18T00:00:00</OrderDate>  
  </Orders>  
</CustomerOrders>  
```  
  
 Beachten Sie, dass die **Kunden** Element und die **Bestellungen** Elemente werden als nebengeordnete Elemente angezeigt. Falls gewünscht die **Bestellungen** Elemente als untergeordnete Elemente von den entsprechenden übergeordneten Elementen angezeigt wird, wird die **geschachtelte** Eigenschaft der **DataRelation** festgelegtwerdenmüssen **"true"** und würden Sie Folgendes hinzufügen:  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 Der folgende Code zeigt, wie die resultierende Ausgabe aussehen würde mit der **Bestellungen** geschachtelte Elemente in den entsprechenden übergeordneten Elementen.  
  
```xml  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <Orders>  
      <OrderID>10643</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-08-25T00:00:00</OrderDate>  
    </Orders>  
    <Orders>  
      <OrderID>10692</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-10-03T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <Orders>  
      <OrderID>10308</OrderID>  
      <CustomerID>ANATR</CustomerID>  
      <OrderDate>1996-09-18T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
</CustomerOrders>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Adding DataRelations (Hinzufügen von DataRelations)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
