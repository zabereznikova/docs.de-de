---
title: Verschachteln von "DataRelations"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
ms.openlocfilehash: 9255615c7786773f1d4f453b910fdccdf191721f
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44075532"
---
# <a name="nesting-datarelations"></a><span data-ttu-id="a13b8-102">Verschachteln von "DataRelations"</span><span class="sxs-lookup"><span data-stu-id="a13b8-102">Nesting DataRelations</span></span>
<span data-ttu-id="a13b8-103">Bei einer relationalen Darstellung von Daten enthalten einzelne Tabellen Zeilen, die über eine Spalte oder eine Gruppe von Spalten miteinander in Beziehung stehen.</span><span class="sxs-lookup"><span data-stu-id="a13b8-103">In a relational representation of data, individual tables contain rows that are related to one another using a column or set of columns.</span></span> <span data-ttu-id="a13b8-104">Im ADO.NET-<xref:System.Data.DataSet> wird die Beziehung zwischen Tabellen mit einer <xref:System.Data.DataRelation> implementiert.</span><span class="sxs-lookup"><span data-stu-id="a13b8-104">In the ADO.NET <xref:System.Data.DataSet>, the relationship between tables is implemented using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="a13b8-105">Bei der Erstellung einer **DataRelation**, die Beziehungen zwischen über-und untergeordneten Spalten nur über die Beziehung verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="a13b8-105">When you create a **DataRelation**, the parent-child relationships of the columns are managed only through the relation.</span></span> <span data-ttu-id="a13b8-106">	Die Tabellen und Spalten sind separate Entitäten.</span><span class="sxs-lookup"><span data-stu-id="a13b8-106">The tables and columns are separate entities.</span></span> <span data-ttu-id="a13b8-107">Bei der hierarchischen Darstellung von durch XML bereitgestellten Daten werden die hierarchischen Beziehungen durch übergeordnete Elemente dargestellt, die geschachtelte untergeordnete Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="a13b8-107">In the hierarchical representation of data that XML provides, the parent-child relationships are represented by parent elements that contain nested child elements.</span></span>  
  
 <span data-ttu-id="a13b8-108">Um die Schachtelung von untergeordneten Objekten zu erleichtern bei einer **DataSet** mit synchronisiert wird ein <xref:System.Xml.XmlDataDocument> oder als XML-Daten mit geschrieben **WriteXml**, die **DataRelation** Stellt eine **geschachtelte** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a13b8-108">To facilitate the nesting of child objects when a **DataSet** is synchronized with an <xref:System.Xml.XmlDataDocument> or written as XML data using **WriteXml**, the **DataRelation** exposes a **Nested** property.</span></span> <span data-ttu-id="a13b8-109">Festlegen der **geschachtelte** Eigenschaft eine **DataRelation** zu **"true"** bewirkt, dass die untergeordneten Zeilen der Beziehung innerhalb der übergeordneten Spalte aus, sofern es als XML-Daten geschrieben werden, geschachtelt oder Synchronisierung mit einem **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="a13b8-109">Setting the **Nested** property of a **DataRelation** to **true** causes the child rows of the relation to be nested within the parent column when written as XML data or synchronized with an **XmlDataDocument**.</span></span> <span data-ttu-id="a13b8-110">Die **geschachtelte** Eigenschaft der **DataRelation** ist **"false"**, in der Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="a13b8-110">The **Nested** property of the **DataRelation** is **false**, by default.</span></span>  
  
 <span data-ttu-id="a13b8-111">Betrachten Sie beispielsweise die folgenden **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="a13b8-111">For example, consider the following **DataSet**.</span></span>  
  
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
  
 <span data-ttu-id="a13b8-112">Da die **geschachtelte** Eigenschaft der **DataRelation** Objekt ist nicht festgelegt, um **"true"** für diesen **DataSet**, die untergeordneten Objekte werden nicht verschachtelt werden. innerhalb des übergeordneten Elements bei der dies **DataSet** wird als XML-Daten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a13b8-112">Because the **Nested** property of the **DataRelation** object is not set to **true** for this **DataSet**, the child objects are not nested within the parent elements when this **DataSet** is represented as XML data.</span></span> <span data-ttu-id="a13b8-113">Transformiert die XML-Darstellung einer **DataSet** enthält, die zugehörigen **DataSet**mit nicht geschachtelten datenbeziehungen kann zu Leistungseinbußen führen.</span><span class="sxs-lookup"><span data-stu-id="a13b8-113">Transforming the XML representation of a **DataSet** that contains related **DataSet**s with non-nested data relations can cause slow performance.</span></span> <span data-ttu-id="a13b8-114">Wir empfehlen daher, die Datenbeziehungen zu schachteln.</span><span class="sxs-lookup"><span data-stu-id="a13b8-114">We recommend that you nest the data relations.</span></span> <span data-ttu-id="a13b8-115">Zu diesem Zweck legen Sie die **geschachtelte** Eigenschaft **"true"**.</span><span class="sxs-lookup"><span data-stu-id="a13b8-115">To do this, set the **Nested** property to **true**.</span></span> <span data-ttu-id="a13b8-116">Schreiben Sie dann Code in die XSLT-Formatvorlage, der hierarchische XPath-Abfrageausdrücke in Top-Down-Form verwendet, um die Daten zu finden und zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="a13b8-116">Then write code in the XSLT style sheet that uses top-down hierarchical XPath query expressions to locate and transform the data.</span></span>  
  
 <span data-ttu-id="a13b8-117">Das folgende Codebeispiel zeigt das Ergebnis des Aufrufs **WriteXml** auf die **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="a13b8-117">The following code example shows the result from calling **WriteXml** on the **DataSet**.</span></span>  
  
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
  
 <span data-ttu-id="a13b8-118">Beachten Sie, dass die **Kunden** Element und die **Bestellungen** Elemente werden als nebengeordnete Elemente angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a13b8-118">Note that the **Customers** element and the **Orders** elements are shown as sibling elements.</span></span> <span data-ttu-id="a13b8-119">Falls gewünscht die **Bestellungen** Elemente als untergeordnete Elemente von den entsprechenden übergeordneten Elementen angezeigt wird, wird die **geschachtelte** Eigenschaft der **DataRelation** festgelegtwerdenmüssen **"true"** und würden Sie Folgendes hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="a13b8-119">If you wanted the **Orders** elements to show up as children of their respective parent elements, the **Nested** property of the **DataRelation** would need to be set to **true** and you would add the following:</span></span>  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 <span data-ttu-id="a13b8-120">Der folgende Code zeigt, wie die resultierende Ausgabe aussehen würde mit der **Bestellungen** geschachtelte Elemente in den entsprechenden übergeordneten Elementen.</span><span class="sxs-lookup"><span data-stu-id="a13b8-120">The following code shows what the resulting output would look like, with the **Orders** elements nested within their respective parent elements.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a13b8-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a13b8-121">See Also</span></span>  
 [<span data-ttu-id="a13b8-122">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="a13b8-122">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="a13b8-123">Adding DataRelations (Hinzufügen von DataRelations)</span><span class="sxs-lookup"><span data-stu-id="a13b8-123">Adding DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 [<span data-ttu-id="a13b8-124">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="a13b8-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="a13b8-125">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="a13b8-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
