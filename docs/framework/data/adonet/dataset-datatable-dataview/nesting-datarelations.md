---
title: Verschachteln von "DataRelations"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
ms.openlocfilehash: 08149de9222c34928078c0ca9d88096f7a4a88d1
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203269"
---
# <a name="nesting-datarelations"></a>Verschachteln von "DataRelations"
Bei einer relationalen Darstellung von Daten enthalten einzelne Tabellen Zeilen, die über eine Spalte oder eine Gruppe von Spalten miteinander in Beziehung stehen. Im ADO.NET-<xref:System.Data.DataSet> wird die Beziehung zwischen Tabellen mit einer <xref:System.Data.DataRelation> implementiert. Wenn Sie ein **DataRelations**-Element erstellen, werden die Beziehungen zwischen übergeordneten und untergeordneten Elementen nur über die-Beziehung verwaltet. Die Tabellen und Spalten sind separate Entitäten. Bei der hierarchischen Darstellung von durch XML bereitgestellten Daten werden die hierarchischen Beziehungen durch übergeordnete Elemente dargestellt, die geschachtelte untergeordnete Elemente enthalten.  
  
 Um die Schachtelung von untergeordneten Objekten zu vereinfachen, wenn ein **DataSet** mit einem <xref:System.Xml.XmlDataDocument> synchronisiert oder mithilfe von " **Write texml**" als XML-Daten geschrieben wird, macht die **datarelierung** eine geschachtelte Eigenschaft verfügbar. Wenn die **geschachtelte** -Eigenschaft einer **DataRelations** auf **true** festgelegt wird, werden die untergeordneten Zeilen der Beziehung innerhalb der übergeordneten Spalte geschachtelt, wenn Sie als XML-Daten geschrieben oder mit einem **XmlDataDocument**synchronisiert werden. Die Eigenschaft " **DataRelations** " ist standardmäßig auf " **false**" fest.  
  
 Sehen Sie sich beispielsweise das folgende **DataSet**an.  
  
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
  
 Da die geschachtelte-Eigenschaft des **DataRelations** -Objekts für dieses **DataSet**nicht auf **true** festgelegt ist, werden die untergeordneten Objekte nicht innerhalb der übergeordneten Elemente geschachtelt, wenn dieses **DataSet** als XML-Daten dargestellt wird. Das Transformieren der XML-Darstellung eines **DataSets** , das verwandte **DataSets**mit nicht--Daten Beziehungen enthält, kann zu einer langsamen Leistung führen. Wir empfehlen daher, die Datenbeziehungen zu schachteln. Legen Sie dazu die Eigenschaft für die Eigenschaft auf **true**fest. Schreiben Sie dann Code in die XSLT-Formatvorlage, der hierarchische XPath-Abfrageausdrücke in Top-Down-Form verwendet, um die Daten zu finden und zu transformieren.  
  
 Das folgende Codebeispiel zeigt das Ergebnis des Aufrufs von " **Write texml** " für das **DataSet**.  
  
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
  
 Beachten Sie, dass das **Customers** -Element und die **Orders** -Elemente als gleich geordnete Elemente angezeigt werden. Wenn Sie möchten, dass die **Orders** -Elemente als untergeordnete Elemente der entsprechenden übergeordneten Elemente angezeigt werden, muss die Eigenschaft für die Eigenschaft " **DataRelations** " auf " **true** " festgelegt werden, und Sie würden Folgendes hinzufügen:  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 Der folgende Code zeigt, wie die resultierende Ausgabe aussehen würde, wobei die **Orders** -Elemente innerhalb der entsprechenden übergeordneten Elemente geschachtelt sind.  
  
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

- [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md)
- [Adding DataRelations (Hinzufügen von DataRelations)](adding-datarelations.md)
- [DataSets, DataTables und DataViews](index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
