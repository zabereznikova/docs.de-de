---
title: Ausführen einer XPath-Abfrage für ein DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: 5e9a00ab78a57c3c1686d7c87ed8b45d9b2649af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150830"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a>Ausführen einer XPath-Abfrage für ein DataSet
Die Beziehung zwischen <xref:System.Data.DataSet> einem <xref:System.Xml.XmlDataDocument> synchronisierten und ermöglicht es Ihnen, XML-Dienste zu verwenden, wie z. B. die XML Path Language (XPath)-Abfrage, die auf **das XmlDataDocument** zugreifen und bestimmte Funktionen bequemer ausführen können als den direkten Zugriff auf das **DataSet.** Anstatt beispielsweise die **Select-Methode** von <xref:System.Data.DataTable> a zum Navigieren von Beziehungen zu anderen Tabellen in einem **DataSet**zu verwenden, können Sie eine XPath-Abfrage für ein <xref:System.Xml.XmlNodeList> **XmlDataDocument** ausführen, das mit dem **DataSet**synchronisiert wird, um eine Liste von XML-Elementen in Form eines abzufragen. Die Knoten in der **XmlNodeList**, <xref:System.Xml.XmlElement> die als Knoten gecastet werden, können dann an die **GetRowFromElement-Methode** des **XmlDataDocument**übergeben werden, um übereinstimmende <xref:System.Data.DataRow> Verweise auf die Zeilen der Tabelle im synchronisierten **DataSet**zurückzugeben.  
  
 Im folgenden Codebeispiel wird eine XPath-Abfrage für Elemente der zweiten Unterebene ausgeführt. Das **DataSet** ist mit drei Tabellen gefüllt: **Customers**, **Orders**und **OrderDetails**. Im Beispiel wird zunächst eine Parent-Child-Beziehung zwischen den Tabellen **Debitoren** und **Orders** sowie zwischen den Tabellen **Orders** und **OrderDetails** erstellt. Eine XPath-Abfrage wird dann ausgeführt, um eine **XmlNodeList** von **Customers-Knoten** zurückzugeben, bei denen ein Enkelknoten **OrderDetails** über einen **ProductID-Knoten** mit dem Wert 43 verfügt. Im Wesentlichen verwendet das Beispiel die XPath-Abfrage, um zu bestimmen, welche Kunden das Produkt mit der **ProductID** 43 bestellt haben.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [DataSet- und XmlDataDocument-Synchronisierung](dataset-and-xmldatadocument-synchronization.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
