---
title: Ausführen einer XPath-Abfrage für ein DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: c785cc69289440918f45974c711ae0b112130c5d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="performing-an-xpath-query-on-a-dataset"></a><span data-ttu-id="88472-102">Ausführen einer XPath-Abfrage für ein DataSet</span><span class="sxs-lookup"><span data-stu-id="88472-102">Performing an XPath Query on a DataSet</span></span>
<span data-ttu-id="88472-103">Die Beziehung zwischen einem synchronisierten <xref:System.Data.DataSet> und <xref:System.Xml.XmlDataDocument> bietet die Möglichkeit zum Verwenden von XML-Diensten, z. B. die XML Path Language (XPath)-Abfrage, die auf die **XmlDataDocument** und bestimmte Funktionen ausführen können Komfortabler Zugriff auf die **DataSet** direkt.</span><span class="sxs-lookup"><span data-stu-id="88472-103">The relationship between a synchronized <xref:System.Data.DataSet> and <xref:System.Xml.XmlDataDocument> allows you to make use of XML services, such as the XML Path Language (XPath) query, that access the **XmlDataDocument** and can perform certain functionality more conveniently than accessing the **DataSet** directly.</span></span> <span data-ttu-id="88472-104">Z. B. statt der **wählen** Methode eine <xref:System.Data.DataTable> beim Navigieren von Beziehungen zu anderen Tabellen in eine **DataSet**, können Sie eine XPath-Abfrage ausführen, auf ein **XmlDataDocument**  synchronisiertes der **DataSet**, um eine Liste von XML-Elementen in Form von erhalten eine <xref:System.Xml.XmlNodeList>.</span><span class="sxs-lookup"><span data-stu-id="88472-104">For example, rather than using the **Select** method of a <xref:System.Data.DataTable> to navigate relationships to other tables in a **DataSet**, you can perform an XPath query on an **XmlDataDocument** that is synchronized with the **DataSet**, to get a list of XML elements in the form of an <xref:System.Xml.XmlNodeList>.</span></span> <span data-ttu-id="88472-105">Die Knoten in der **XmlNodeList**, umgewandelt als <xref:System.Xml.XmlElement> Knoten, klicken Sie dann auf übergeben werden kann die **GetRowFromElement** Methode der **XmlDataDocument**Übereinstimmung zurückgegeben <xref:System.Data.DataRow> Verweise auf die Zeilen der Tabelle in der synchronisierten **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="88472-105">The nodes in the **XmlNodeList**, cast as <xref:System.Xml.XmlElement> nodes, can then be passed to the **GetRowFromElement** method of the **XmlDataDocument**, to return matching <xref:System.Data.DataRow> references to the rows of the table in the synchronized **DataSet**.</span></span>  
  
 <span data-ttu-id="88472-106">Im folgenden Codebeispiel wird eine XPath-Abfrage für Elemente der zweiten Unterebene ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="88472-106">For example, the following code sample performs a "grandchild" XPath query.</span></span> <span data-ttu-id="88472-107">Die **DataSet** wird mit drei Tabellen ausgefüllt: **Kunden**, **Aufträge**, und **OrderDetails**.</span><span class="sxs-lookup"><span data-stu-id="88472-107">The **DataSet** is filled with three tables: **Customers**, **Orders**, and **OrderDetails**.</span></span> <span data-ttu-id="88472-108">Im Beispiel wird zunächst eine hierarchische Beziehung zwischen erstellt die **Kunden** und **Aufträge** Tabellen, und zwischen den **Aufträge** und **OrderDetails** Tabellen.</span><span class="sxs-lookup"><span data-stu-id="88472-108">In the sample, a parent-child relation is first created between the **Customers** and **Orders** tables, and between the **Orders** and **OrderDetails** tables.</span></span> <span data-ttu-id="88472-109">Eine XPath-Abfrage ausgeführt, um zurückgeben ein **XmlNodeList** von **Kunden** Knoten bei einem zwei Ebenen untergeordneten **OrderDetails** Knoten verfügt über eine **"ProductID"** Knoten mit dem Wert 43 verfügt.</span><span class="sxs-lookup"><span data-stu-id="88472-109">An XPath query is then performed to return an **XmlNodeList** of **Customers** nodes where a grandchild **OrderDetails** node has a **ProductID** node with the value of 43.</span></span> <span data-ttu-id="88472-110">Im Wesentlichen wird im Beispiel die XPath-Abfrage verwenden, um zu bestimmen, welche Kunden das Produkt bestellt haben, die verfügt die **"ProductID"** 43 verfügt.</span><span class="sxs-lookup"><span data-stu-id="88472-110">In essence, the sample is using the XPath query to determine which customers have ordered the product that has the **ProductID** of 43.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="88472-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88472-111">See Also</span></span>  
 [<span data-ttu-id="88472-112">DataSet- und XmlDataDocument-Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="88472-112">DataSet and XmlDataDocument Synchronization</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 [<span data-ttu-id="88472-113">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="88472-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
