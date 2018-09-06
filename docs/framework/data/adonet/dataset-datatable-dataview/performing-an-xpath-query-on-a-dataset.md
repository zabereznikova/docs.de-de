---
title: Ausführen einer XPath-Abfrage für ein DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: a1718429360d79c4628e9948eb1b052c3ac01964
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43805928"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a>Ausführen einer XPath-Abfrage für ein DataSet
Die Beziehung zwischen einem synchronisierten <xref:System.Data.DataSet> und <xref:System.Xml.XmlDataDocument> können Sie zum Verwenden von XML-Dienste, z. B. der Abfrage XML Path Language (XPath), die Zugriff auf die **XmlDataDocument** und bestimmte Funktionen ausführen können einfacher als der Zugriff auf die **DataSet** direkt. Z. B. statt der **wählen** -Methode der ein <xref:System.Data.DataTable> Navigieren in Beziehungen zu anderen Tabellen im eine **DataSet**, können Sie eine XPath-Abfrage ausführen, auf eine **XmlDataDocument**  synchronisiertes der **DataSet**, um eine Liste von XML-Elementen in Form von erhalten eine <xref:System.Xml.XmlNodeList>. Die Knoten in der **XmlNodeList**, umgewandelte <xref:System.Xml.XmlElement> Knoten, klicken Sie dann an übergeben werden kann die **GetRowFromElement** -Methode der der **XmlDataDocument**, um übereinstimmende zurückzugeben <xref:System.Data.DataRow> Verweise auf die Zeilen der Tabelle im synchronisierten **DataSet**.  
  
 Im folgenden Codebeispiel wird eine XPath-Abfrage für Elemente der zweiten Unterebene ausgeführt. Die **DataSet** mit drei Tabellen gefüllt: **Kunden**, **Bestellungen**, und **OrderDetails**. In diesem Beispiel wird zunächst eine hierarchische Beziehung zwischen erstellt die **Kunden** und **Bestellungen** Tabellen, und zwischen den **Bestellungen** und **OrderDetails** Tabellen. Wird zum Zurückgeben eine XPath-Abfrage ausgeführt ein **XmlNodeList** von **Kunden** Knoten bei einem "Enkel" **OrderDetails** Knoten verfügt über eine **"ProductID"** Knoten mit dem Wert 43. Im Wesentlichen wird im Beispiel die XPath-Abfrage verwenden, um zu bestimmen, welche Kunden das Produkt bestellt haben, die die **"ProductID"** 43.  
  
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
 [DataSet- und XmlDataDocument-Synchronisierung](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
