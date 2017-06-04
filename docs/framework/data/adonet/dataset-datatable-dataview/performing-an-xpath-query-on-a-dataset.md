---
title: "Durchf&#252;hren einer XPath-Abfrage f&#252;r ein DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Durchf&#252;hren einer XPath-Abfrage f&#252;r ein DataSet
Die Beziehung zwischen einem synchronisierten <xref:System.Data.DataSet> und einem <xref:System.Xml.XmlDataDocument> ermöglicht das Verwenden von XML\-Diensten, z. B die XPath\-Abfrage \(XML Path Language\), die auf das **XmlDataDocument** zugreifen und bestimmte Funktionen komfortabler ausführen können, als dies bei einem direkten Zugriff auf das **DataSet** der Fall ist.  Anstelle der **Select**\-Methode einer <xref:System.Data.DataTable> können Sie beispielsweise zum Navigieren über Beziehungen zu anderen Tabellen in einem **DataSet** auch eine XPath\-Abfrage für ein mit dem **DataSet** synchronisiertes **XmlDataDocument** ausführen, um eine Liste mit XML\-Elementen als <xref:System.Xml.XmlNodeList> abzurufen.  Die in <xref:System.Xml.XmlElement>\-Knoten umgewandelten Knoten der **XmlNodeList** können der **GetRowFromElement**\-Methode des **XmlDataDocument** übergeben werden, um übereinstimmende <xref:System.Data.DataRow>\-Verweise auf die Tabellenzeilen des synchronisierten **DataSet** zurückzugeben.  
  
 Im folgenden Codebeispiel wird eine XPath\-Abfrage für Elemente der zweiten Unterebene ausgeführt.  Das **DataSet** wird mit drei Tabellen ausgefüllt: **Customers**, **Orders** und **OrderDetails**.  Im Beispiel wird zunächst eine hierarchische Beziehung zwischen der **Customers**\-Tabelle und der **Orders**\-Tabelle sowie zwischen der **Orders**\-Tabelle und der **OrderDetails**\-Tabelle erstellt.  Danach wird eine XPath\-Abfrage ausgeführt, um eine **XmlNodeList** von **Customers**\-Knoten zurückzugeben, bei denen ein der Knoten **OrderDetails** auf der zweiten Unterebene über einen **ProductID**\-Knoten mit dem Wert 43 verfügt.  Im Grunde wird in dem Beispiel eine XPath\-Abfrage verwendet, um zu bestimmen, welche Kunden das Produkt mit der **ProductID** 43 bestellt haben.  
  
```vb  
' Assumes that connection is a valid SqlConnection.  
connection.Open()  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
Dim detailAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM [Order Details]", connection)  
detailAdapter.Fill(dataSet, "OrderDetails")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
dataSet.Relations.Add("OrderDetail", _  
  dataSet.Tables("Orders").Columns("OrderID"), _  
dataSet.Tables("OrderDetails").Columns("OrderID"), false).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)   
  
Dim nodeList As XmlNodeList = xmlDoc.DocumentElement.SelectNodes( _  
  "descendant::Customers[*/OrderDetails/ProductID=43]")  
  
Dim dataRow As DataRow  
Dim xmlNode As XmlNode  
  
For Each xmlNode In nodeList  
  dataRow = xmlDoc.GetRowFromElement(CType(xmlNode, XmlElement))  
  
  If Not dataRow Is Nothing then Console.WriteLine(xmlRow(0).ToString())  
Next  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection.  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(dataSet, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(dataSet, "Orders");  
  
SqlDataAdapter detailAdapter = new SqlDataAdapter(  
  "SELECT * FROM [Order Details]", connection);  
detailAdapter.Fill(dataSet, "OrderDetails");  
  
connection.Close();  
  
dataSet.Relations.Add("CustOrders",  
  dataSet.Tables["Customers"].Columns["CustomerID"],  
 dataSet.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
dataSet.Relations.Add("OrderDetail",  
  dataSet.Tables["Orders"].Columns["OrderID"],  
  dataSet.Tables["OrderDetails"].Columns["OrderID"],   
  false).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);   
  
XmlNodeList nodeList = xmlDoc.DocumentElement.SelectNodes(  
  "descendant::Customers[*/OrderDetails/ProductID=43]");  
  
DataRow dataRow;  
foreach (XmlNode xmlNode in nodeList)  
{  
  dataRow = xmlDoc.GetRowFromElement((XmlElement)xmlNode);  
  if (dataRow != null)  
    Console.WriteLine(dataRow[0]);  
}  
```  
  
## Siehe auch  
 [Synchronisierung zwischen 'DataSet' und 'XmlDataDocument'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)