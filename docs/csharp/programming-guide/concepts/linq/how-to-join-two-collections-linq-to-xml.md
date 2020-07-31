---
title: 'Vorgehensweise: Verknüpfen von zwei Sammlungen (LINQ to XML) (C#)'
description: In diesem C#-Beispiel werden die Elemente in LINQ to XML mit anderen Elementen verknüpft, und es wird ein neues XML-Dokument erstellt.
ms.date: 07/20/2015
ms.assetid: 7b817ede-911a-4cff-9dd3-639c3fc228c9
ms.openlocfilehash: 10792ed4907e778b41821c9b32574bd8fc0ab35f
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104998"
---
# <a name="how-to-join-two-collections-linq-to-xml-c"></a><span data-ttu-id="d7a06-103">Vorgehensweise: Verknüpfen von zwei Sammlungen (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="d7a06-103">How to join two collections (LINQ to XML) (C#)</span></span>

<span data-ttu-id="d7a06-104">Ein Element oder Attribut in einem XML-Dokument kann mitunter auf ein anderes Element oder Attribut verweisen.</span><span class="sxs-lookup"><span data-stu-id="d7a06-104">An element or attribute in an XML document can sometimes refer to another element or attribute.</span></span> <span data-ttu-id="d7a06-105">So enthält das XML-Dokument in [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md) z.B. eine Liste von Kunden und eine Liste von Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="d7a06-105">For example, the [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md) XML document contains a list of customers and a list of orders.</span></span> <span data-ttu-id="d7a06-106">Jedes `Customer`-Element enthält ein `CustomerID`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="d7a06-106">Each `Customer` element contains a `CustomerID` attribute.</span></span> <span data-ttu-id="d7a06-107">Jedes `Order`-Element enthält ein `CustomerID`-Element.</span><span class="sxs-lookup"><span data-stu-id="d7a06-107">Each `Order` element contains a `CustomerID` element.</span></span> <span data-ttu-id="d7a06-108">Das `CustomerID`-Element eines Auftrags verweist auf das `CustomerID`-Attribut eines Kunden.</span><span class="sxs-lookup"><span data-stu-id="d7a06-108">The `CustomerID` element in each order refers to the `CustomerID` attribute in a customer.</span></span>

<span data-ttu-id="d7a06-109">Unter [Beispiel-XSD-Datei: Kunden und Bestellungen](./sample-xsd-file-customers-and-orders1.md) finden Sie ein XML-Schema, das zum Validieren dieses Dokuments verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d7a06-109">The topic [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md) contains an XSD that can be used to validate this document.</span></span> <span data-ttu-id="d7a06-110">Mit den Funktionen `xs:key` und `xs:keyref` des XSD-Schemas wird geprüft, ob das `CustomerID`-Attribut des `Customer`-Elements ein Schlüssel ist. Außerdem wird damit eine Beziehung zwischen dem `CustomerID`-Element in jedem `Order`-Element und dem `CustomerID`-Attribut in jedem `Customer`-Element hergestellt.</span><span class="sxs-lookup"><span data-stu-id="d7a06-110">It uses the `xs:key` and `xs:keyref` features of XSD to establish that the `CustomerID` attribute of the `Customer` element is a key, and to establish a relationship between the `CustomerID` element in each `Order` element and the `CustomerID` attribute in each `Customer` element.</span></span>

<span data-ttu-id="d7a06-111">Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie diese Beziehung durch Verwenden der `join`-Klausel nutzen.</span><span class="sxs-lookup"><span data-stu-id="d7a06-111">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can take advantage of this relationship by using the `join` clause.</span></span>

<span data-ttu-id="d7a06-112">Da kein Index verfügbar ist, führt eine solche Verknüpfung zu einer schlechten Laufzeitleistung.</span><span class="sxs-lookup"><span data-stu-id="d7a06-112">Because there is no index available, such joining will have poor run-time performance.</span></span>

<span data-ttu-id="d7a06-113">Ausführlichere Informationen zu `join` finden Sie unter [Join Operations (C#) (Verknüpfungsvorgänge (C#))](./join-operations.md).</span><span class="sxs-lookup"><span data-stu-id="d7a06-113">For more detailed information about `join`, see [Join Operations (C#)](./join-operations.md).</span></span>

## <a name="example"></a><span data-ttu-id="d7a06-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7a06-114">Example</span></span>

<span data-ttu-id="d7a06-115">Das folgende Beispiel verknüpft die `Customer`-Elemente mit den `Order`-Elementen und generiert ein neues XML-Dokument, das das `CompanyName`-Element der Aufträge enthält.</span><span class="sxs-lookup"><span data-stu-id="d7a06-115">The following example joins the `Customer` elements to the `Order` elements, and generates a new XML document that includes the `CompanyName` element in the orders.</span></span>

<span data-ttu-id="d7a06-116">Vor dem Ausführen der Abfrage überprüft das Beispiel, ob das Dokument dem Schema in [Beispiel-XSD-Datei: Kunden und Bestellungen](./sample-xsd-file-customers-and-orders1.md) entspricht.</span><span class="sxs-lookup"><span data-stu-id="d7a06-116">Before executing the query, the example validates that the document complies with the schema in [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md).</span></span> <span data-ttu-id="d7a06-117">Auf diese Weise wird sichergestellt, dass die JOIN-Klausel immer funktioniert.</span><span class="sxs-lookup"><span data-stu-id="d7a06-117">This ensures that the join clause will always work.</span></span>

<span data-ttu-id="d7a06-118">Diese Abfrage ruft zuerst alle `Customer`-Elemente ab und verknüpft sie dann mit den `Order`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="d7a06-118">This query first retrieves all `Customer` elements, and then joins them to the `Order` elements.</span></span> <span data-ttu-id="d7a06-119">Sie wählt dabei nur die Aufträge der Kunden aus, deren `CustomerID` größer als "K" ist.</span><span class="sxs-lookup"><span data-stu-id="d7a06-119">It selects only the orders for customers with a `CustomerID` greater than "K".</span></span> <span data-ttu-id="d7a06-120">Anschließend projiziert die Abfrage ein neues `Order`-Element, das die Kundeninformationen in den einzelnen Aufträgen enthält.</span><span class="sxs-lookup"><span data-stu-id="d7a06-120">It then projects a new `Order` element that contains the customer information within each order.</span></span>

<span data-ttu-id="d7a06-121">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="d7a06-121">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>

<span data-ttu-id="d7a06-122">In diesem Beispiel wird das folgende XSD-Schema verwendet: [Beispiel-XSD-Datei: Kunden und Bestellungen](./sample-xsd-file-customers-and-orders1.md).</span><span class="sxs-lookup"><span data-stu-id="d7a06-122">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md).</span></span>

<span data-ttu-id="d7a06-123">Diese Art von Verknüpfungen führt zu Leistungseinbußen.</span><span class="sxs-lookup"><span data-stu-id="d7a06-123">Joining in this fashion will not perform well.</span></span> <span data-ttu-id="d7a06-124">Joins (Verknüpfungen) werden über eine lineare Suche ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d7a06-124">Joins are performed via a linear search.</span></span> <span data-ttu-id="d7a06-125">Es gibt keine Hashtabellen oder Indizes, die die Geschwindigkeit erhöhen könnten.</span><span class="sxs-lookup"><span data-stu-id="d7a06-125">There are no hash tables or indexes to help with performance.</span></span>

```csharp
XmlSchemaSet schemas = new XmlSchemaSet();
schemas.Add("", "CustomersOrders.xsd");

Console.Write("Attempting to validate, ");
XDocument custOrdDoc = XDocument.Load("CustomersOrders.xml");

bool errors = false;
custOrdDoc.Validate(schemas, (o, e) =>
                     {
                         Console.WriteLine("{0}", e.Message);
                         errors = true;
                     });
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");

if (!errors)
{
    // Join customers and orders, and create a new XML document with
    // a different shape.

    // The new document contains orders only for customers with a
    // CustomerID > 'K'
    XElement custOrd = custOrdDoc.Element("Root");
    XElement newCustOrd = new XElement("Root",
        from c in custOrd.Element("Customers").Elements("Customer")
        join o in custOrd.Element("Orders").Elements("Order")
                   on (string)c.Attribute("CustomerID") equals
                      (string)o.Element("CustomerID")
        where ((string)c.Attribute("CustomerID")).CompareTo("K") > 0
        select new XElement("Order",
            new XElement("CustomerID", (string)c.Attribute("CustomerID")),
            new XElement("CompanyName", (string)c.Element("CompanyName")),
            new XElement("ContactName", (string)c.Element("ContactName")),
            new XElement("EmployeeID", (string)o.Element("EmployeeID")),
            new XElement("OrderDate", (DateTime)o.Element("OrderDate"))
        )
    );
    Console.WriteLine(newCustOrd);
}
```

<span data-ttu-id="d7a06-126">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d7a06-126">This code produces the following output:</span></span>

```output
Attempting to validate, custOrdDoc validated
<Root>
  <Order>
    <CustomerID>LAZYK</CustomerID>
    <CompanyName>Lazy K Kountry Store</CompanyName>
    <ContactName>John Steel</ContactName>
    <EmployeeID>1</EmployeeID>
    <OrderDate>1997-03-21T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LAZYK</CustomerID>
    <CompanyName>Lazy K Kountry Store</CompanyName>
    <ContactName>John Steel</ContactName>
    <EmployeeID>8</EmployeeID>
    <OrderDate>1997-05-22T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>1</EmployeeID>
    <OrderDate>1997-06-25T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>8</EmployeeID>
    <OrderDate>1997-10-27T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>6</EmployeeID>
    <OrderDate>1997-11-10T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>4</EmployeeID>
    <OrderDate>1998-02-12T00:00:00</OrderDate>
  </Order>
</Root>
```
