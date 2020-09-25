---
title: Verschachteln von "DataRelations"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
ms.openlocfilehash: 8db75f486c7c08b6a02401af35c9edf9969f9063
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201277"
---
# <a name="nesting-datarelations"></a><span data-ttu-id="c9405-102">Verschachteln von "DataRelations"</span><span class="sxs-lookup"><span data-stu-id="c9405-102">Nesting DataRelations</span></span>

<span data-ttu-id="c9405-103">Bei einer relationalen Darstellung von Daten enthalten einzelne Tabellen Zeilen, die über eine Spalte oder eine Gruppe von Spalten miteinander in Beziehung stehen.</span><span class="sxs-lookup"><span data-stu-id="c9405-103">In a relational representation of data, individual tables contain rows that are related to one another using a column or set of columns.</span></span> <span data-ttu-id="c9405-104">Im ADO.NET-<xref:System.Data.DataSet> wird die Beziehung zwischen Tabellen mit einer <xref:System.Data.DataRelation> implementiert.</span><span class="sxs-lookup"><span data-stu-id="c9405-104">In the ADO.NET <xref:System.Data.DataSet>, the relationship between tables is implemented using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="c9405-105">Wenn Sie ein **DataRelations**-Element erstellen, werden die Beziehungen zwischen übergeordneten und untergeordneten Elementen nur über die-Beziehung verwaltet.</span><span class="sxs-lookup"><span data-stu-id="c9405-105">When you create a **DataRelation**, the parent-child relationships of the columns are managed only through the relation.</span></span> <span data-ttu-id="c9405-106">	Die Tabellen und Spalten sind separate Entitäten.</span><span class="sxs-lookup"><span data-stu-id="c9405-106">The tables and columns are separate entities.</span></span> <span data-ttu-id="c9405-107">Bei der hierarchischen Darstellung von durch XML bereitgestellten Daten werden die hierarchischen Beziehungen durch übergeordnete Elemente dargestellt, die geschachtelte untergeordnete Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="c9405-107">In the hierarchical representation of data that XML provides, the parent-child relationships are represented by parent elements that contain nested child elements.</span></span>  
  
 <span data-ttu-id="c9405-108">Um die Schachtelung von untergeordneten Objekten zu vereinfachen, wenn ein **DataSet** mit einem synchronisiert <xref:System.Xml.XmlDataDocument> oder mithilfe von " **Write texml**" als XML-Daten geschrieben **Nested** wird, macht die **datarelierung** eine geschachtelte Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c9405-108">To facilitate the nesting of child objects when a **DataSet** is synchronized with an <xref:System.Xml.XmlDataDocument> or written as XML data using **WriteXml**, the **DataRelation** exposes a **Nested** property.</span></span> <span data-ttu-id="c9405-109">Wenn die **geschachtelte** -Eigenschaft einer **DataRelations** auf **true** festgelegt wird, werden die untergeordneten Zeilen der Beziehung innerhalb der übergeordneten Spalte geschachtelt, wenn Sie als XML-Daten geschrieben oder mit einem **XmlDataDocument**synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="c9405-109">Setting the **Nested** property of a **DataRelation** to **true** causes the child rows of the relation to be nested within the parent column when written as XML data or synchronized with an **XmlDataDocument**.</span></span> <span data-ttu-id="c9405-110">Die **Eigenschaft "** **DataRelations** " ist standardmäßig auf " **false**" fest.</span><span class="sxs-lookup"><span data-stu-id="c9405-110">The **Nested** property of the **DataRelation** is **false**, by default.</span></span>  
  
 <span data-ttu-id="c9405-111">Sehen Sie sich beispielsweise das folgende **DataSet**an.</span><span class="sxs-lookup"><span data-stu-id="c9405-111">For example, consider the following **DataSet**.</span></span>  
  
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
  
 <span data-ttu-id="c9405-112">Da die geschachtelte-Eigenschaft **des DataRelations** -Objekts für dieses **DataSet**nicht auf **true** festgelegt ist, **werden die unter** geordneten Objekte nicht innerhalb der übergeordneten Elemente geschachtelt, wenn dieses **DataSet** als XML-Daten dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c9405-112">Because the **Nested** property of the **DataRelation** object is not set to **true** for this **DataSet**, the child objects are not nested within the parent elements when this **DataSet** is represented as XML data.</span></span> <span data-ttu-id="c9405-113">Das Transformieren der XML-Darstellung eines **DataSets** , das verwandte **DataSets**mit nicht--Daten Beziehungen enthält, kann zu einer langsamen Leistung führen.</span><span class="sxs-lookup"><span data-stu-id="c9405-113">Transforming the XML representation of a **DataSet** that contains related **DataSet**s with non-nested data relations can cause slow performance.</span></span> <span data-ttu-id="c9405-114">Wir empfehlen daher, die Datenbeziehungen zu schachteln.</span><span class="sxs-lookup"><span data-stu-id="c9405-114">We recommend that you nest the data relations.</span></span> <span data-ttu-id="c9405-115">Legen Sie **dazu die Eigenschaft** für die Eigenschaft auf **true**fest.</span><span class="sxs-lookup"><span data-stu-id="c9405-115">To do this, set the **Nested** property to **true**.</span></span> <span data-ttu-id="c9405-116">Schreiben Sie dann Code in die XSLT-Formatvorlage, der hierarchische XPath-Abfrageausdrücke in Top-Down-Form verwendet, um die Daten zu finden und zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="c9405-116">Then write code in the XSLT style sheet that uses top-down hierarchical XPath query expressions to locate and transform the data.</span></span>  
  
 <span data-ttu-id="c9405-117">Das folgende Codebeispiel zeigt das Ergebnis des Aufrufs von " **Write texml** " für das **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="c9405-117">The following code example shows the result from calling **WriteXml** on the **DataSet**.</span></span>  
  
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
  
 <span data-ttu-id="c9405-118">Beachten Sie, dass das **Customers** -Element und die **Orders** -Elemente als gleich geordnete Elemente angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c9405-118">Note that the **Customers** element and the **Orders** elements are shown as sibling elements.</span></span> <span data-ttu-id="c9405-119">Wenn Sie möchten, dass die **Orders** -Elemente als untergeordnete Elemente der entsprechenden übergeordneten Elemente angezeigt werden, muss **die Eigenschaft für die Eigenschaft** " **DataRelations** " auf " **true** " festgelegt werden, und Sie würden Folgendes hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="c9405-119">If you wanted the **Orders** elements to show up as children of their respective parent elements, the **Nested** property of the **DataRelation** would need to be set to **true** and you would add the following:</span></span>  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 <span data-ttu-id="c9405-120">Der folgende Code zeigt, wie die resultierende Ausgabe aussehen würde, wobei die **Orders** -Elemente innerhalb der entsprechenden übergeordneten Elemente geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="c9405-120">The following code shows what the resulting output would look like, with the **Orders** elements nested within their respective parent elements.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c9405-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9405-121">See also</span></span>

- [<span data-ttu-id="c9405-122">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="c9405-122">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="c9405-123">Hinzufügen von "DataRelations"</span><span class="sxs-lookup"><span data-stu-id="c9405-123">Adding DataRelations</span></span>](adding-datarelations.md)
- [<span data-ttu-id="c9405-124">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="c9405-124">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="c9405-125">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c9405-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
