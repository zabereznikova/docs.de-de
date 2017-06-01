---
title: "Schachteln von &#39;DataRelations&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Schachteln von &#39;DataRelations&#39;
Bei einer relationalen Darstellung von Daten enthalten einzelne Tabellen Zeilen, die über eine Spalte oder eine Gruppe von Spalten miteinander in Beziehung stehen.  Im ADO.NET\-<xref:System.Data.DataSet> wird die Beziehung zwischen Tabellen mit einer <xref:System.Data.DataRelation> implementiert.  Beim Erstellen einer **DataRelation** werden die Beziehungen zwischen übergeordneten und untergeordneten Spalten nur über die Beziehung verwaltet.  	Die Tabellen und Spalten sind separate Entitäten.  Bei der hierarchischen Darstellung von durch XML bereitgestellten Daten werden die hierarchischen Beziehungen durch übergeordnete Elemente dargestellt, die geschachtelte untergeordnete Elemente enthalten.  
  
 Die **DataRelation** macht eine **Nested**\-Eigenschaft verfügbar, um die Schachtelung von untergeordneten Elementen zu vereinfachen, wenn ein **DataSet** mit einem <xref:System.Xml.XmlDataDocument> synchronisiert oder mit **WriteXml** in Form von XML\-Daten geschrieben wird.  Wenn die **Nested**\-Eigenschaft einer **DataRelation** auf **true** festgelegt wird, werden beim Schreiben der Daten in Form von XML\-Daten oder beim Synchronisieren mit einem **XmlDataDocument** die untergeordneten Zeilen der Beziehung innerhalb der übergeordneten Spalte geschachtelt.  Der Standardwert der **Nested**\-Eigenschaft der **DataRelation** lautet **false**.  
  
 Betrachten Sie z. B. das folgende **DataSet**.  
  
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
  
 Da die **Nested**\-Eigenschaft des **DataRelation**\-Objekts für dieses **DataSet** nicht auf **true** festgelegt ist, werden die untergeordneten Elemente beim Schreiben dieses **DataSet** in Form von XML\-Daten nicht innerhalb des übergeordneten Elements geschachtelt.  Das Transformieren der XML\-Darstellung eines **DataSet**, das verknüpfte **DataSets** mit nicht geschachtelten Datenbeziehungen enthält, kann zu Leistungseinbußen führen.  Wir empfehlen daher, die Datenbeziehungen zu schachteln.  Legen Sie zu diesem Zweck die **Nested**\-Eigenschaft auf **true** fest.  Schreiben Sie dann Code in die XSLT\-Formatvorlage, der hierarchische XPath\-Abfrageausdrücke in Top\-Down\-Form verwendet, um die Daten zu finden und zu transformieren.  
  
 Im folgenden Codebeispiel wird das Ergebnis des Aufrufs von **WriteXml** für das **DataSet** gezeigt.  
  
```  
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
  
 Beachten Sie, dass das **Customers**\-Element und das **Orders**\-Element als nebengeordnete Elemente angezeigt werden.  Wenn die **Orders**\-Elemente jeweils als untergeordnete Elemente dargestellt werden sollen, müsste die **Nested**\-Eigenschaft der **DataRelation** auf **true** festgelegt werden, und Sie müssten folgenden Code hinzufügen:  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 Im folgenden Codebeispiel wird gezeigt, wie die resultierende Ausgabe aussehen könnte, wenn die **Orders**\-Elemente innerhalb ihrer zugehörigen übergeordneten Elemente geschachtelt sind.  
  
```  
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
  
## Siehe auch  
 [Verwenden von XML in einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Hinzufügen von 'DataRelations'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)   
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)