---
title: Ausführen einer XPath-Abfrage für ein DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: d7897815874f2e9de2f4c24d3c141d464a296b31
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201238"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a>Ausführen einer XPath-Abfrage für ein DataSet

Die Beziehung zwischen einem synchronisierten <xref:System.Data.DataSet> und <xref:System.Xml.XmlDataDocument> ermöglicht Ihnen die Verwendung von XML-Diensten, z. b. der XPath-Abfrage (XML Path Language), die auf das **xmldatadocumschlag** zugreifen und eine bestimmte Funktionalität leichter ausführen können als das direkte zugreifen auf das **DataSet** . Anstatt z. b. die **Select** -Methode von <xref:System.Data.DataTable> zum Navigieren von Beziehungen zu anderen Tabellen in einem **DataSet**zu verwenden, können Sie eine XPath-Abfrage für ein **xmldatadocreent** ausführen, das mit dem **DataSet**synchronisiert wird, um eine Liste der XML-Elemente in Form eines-Elements zu erhalten <xref:System.Xml.XmlNodeList> . Die Knoten in der **xmlnodelta ist**, die als <xref:System.Xml.XmlElement> Knoten umgewandelt werden, können dann an die **getrowfromelements** -Methode von **XmlDataDocument**übergeben werden, um übereinstimmende <xref:System.Data.DataRow> Verweise auf die Zeilen der Tabelle im synchronisierten **DataSet**zurückzugeben.  
  
 Im folgenden Codebeispiel wird eine XPath-Abfrage für Elemente der zweiten Unterebene ausgeführt. Das **DataSet** ist mit drei Tabellen gefüllt: **Customers**, **Orders**und **Order Details**. Im Beispiel wird zuerst zwischen den Tabellen **Customers** und **Orders** und zwischen den Tabellen **Orders** und **Order Details** eine Beziehung zwischen über-und untergeordneten Elementen erstellt. Anschließend wird eine XPath-Abfrage ausgeführt, um eine **xmlnoschist** von **Customers** -Knoten zurückzugeben, bei denen ein zweiter untergeordneter **Order Details** -Knoten über einen **ProductID-** Knoten mit dem Wert 43 verfügt. Im Wesentlichen verwendet das Beispiel die XPath-Abfrage, um zu bestimmen, welche Kunden das Produkt mit der **ProductID** 43 bestellt haben.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [DataSet- und XmlDataDocument-Synchronisierung](dataset-and-xmldatadocument-synchronization.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
