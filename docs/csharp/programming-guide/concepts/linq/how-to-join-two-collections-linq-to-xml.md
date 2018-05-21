---
title: 'Vorgehensweise: Verknüpfen von zwei Auflistungen (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 7b817ede-911a-4cff-9dd3-639c3fc228c9
ms.openlocfilehash: d4e7c73262cce234dc8373d42b2a8cb366316622
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-join-two-collections-linq-to-xml-c"></a><span data-ttu-id="d1b62-102">Vorgehensweise: Verknüpfen von zwei Auflistungen (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="d1b62-102">How to: Join Two Collections (LINQ to XML) (C#)</span></span>
<span data-ttu-id="d1b62-103">Ein Element oder Attribut in einem XML-Dokument kann mitunter auf ein anderes Element oder Attribut verweisen.</span><span class="sxs-lookup"><span data-stu-id="d1b62-103">An element or attribute in an XML document can sometimes refer to another element or attribute.</span></span> <span data-ttu-id="d1b62-104">So enthält das XML-Dokument in [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md) z.B. eine Liste von Kunden und eine Liste von Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="d1b62-104">For example, the [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md) XML document contains a list of customers and a list of orders.</span></span> <span data-ttu-id="d1b62-105">Jedes `Customer`-Element enthält ein `CustomerID`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="d1b62-105">Each `Customer` element contains a `CustomerID` attribute.</span></span> <span data-ttu-id="d1b62-106">Jedes `Order`-Element enthält ein `CustomerID`-Element.</span><span class="sxs-lookup"><span data-stu-id="d1b62-106">Each `Order` element contains a `CustomerID` element.</span></span> <span data-ttu-id="d1b62-107">Das `CustomerID`-Element eines Auftrags verweist auf das `CustomerID`-Attribut eines Kunden.</span><span class="sxs-lookup"><span data-stu-id="d1b62-107">The `CustomerID` element in each order refers to the `CustomerID` attribute in a customer.</span></span>  
  
 <span data-ttu-id="d1b62-108">Das Thema [Beispiel-XSD-Datei: Kunden und Bestellungen](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md) enthält ein XSD-Schema, das zum Validieren dieses Dokuments verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d1b62-108">The topic [Sample XSD File: Customers and Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md) contains an XSD that can be used to validate this document.</span></span> <span data-ttu-id="d1b62-109">Mit den Funktionen `xs:key` und `xs:keyref` des XSD-Schemas wird geprüft, ob das `CustomerID`-Attribut des `Customer`-Elements ein Schlüssel ist. Außerdem wird damit eine Beziehung zwischen dem `CustomerID`-Element in jedem `Order`-Element und dem `CustomerID`-Attribut in jedem `Customer`-Element hergestellt.</span><span class="sxs-lookup"><span data-stu-id="d1b62-109">It uses the `xs:key` and `xs:keyref` features of XSD to establish that the `CustomerID` attribute of the `Customer` element is a key, and to establish a relationship between the `CustomerID` element in each `Order` element and the `CustomerID` attribute in each `Customer` element.</span></span>  
  
 <span data-ttu-id="d1b62-110">Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie diese Beziehung durch Verwenden der `join`-Klausel nutzen.</span><span class="sxs-lookup"><span data-stu-id="d1b62-110">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can take advantage of this relationship by using the `join` clause.</span></span>  
  
 <span data-ttu-id="d1b62-111">Da es keinen Index gibt, führt eine solche Verknüpfung zu einer schlechten Laufzeitleistung.</span><span class="sxs-lookup"><span data-stu-id="d1b62-111">Note that because there is no index available, such joining will have poor runtime performance.</span></span>  
  
 <span data-ttu-id="d1b62-112">Ausführlichere Informationen zu `join` finden Sie unter [Join Operations (C#) (Verknüpfungsvorgänge (C#))](../../../../csharp/programming-guide/concepts/linq/join-operations.md).</span><span class="sxs-lookup"><span data-stu-id="d1b62-112">For more detailed information about `join`, see [Join Operations (C#)](../../../../csharp/programming-guide/concepts/linq/join-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1b62-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d1b62-113">Example</span></span>  
 <span data-ttu-id="d1b62-114">Das folgende Beispiel verknüpft die `Customer`-Elemente mit den `Order`-Elementen und generiert ein neues XML-Dokument, das das `CompanyName`-Element der Aufträge enthält.</span><span class="sxs-lookup"><span data-stu-id="d1b62-114">The following example joins the `Customer` elements to the `Order` elements, and generates a new XML document that includes the `CompanyName` element in the orders.</span></span>  
  
 <span data-ttu-id="d1b62-115">Vor dem Ausführen der Abfrage überprüft das Beispiel, ob das Dokument dem Schema in [Beispiel-XSD-Datei: Kunden und Bestellungen](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md) entspricht.</span><span class="sxs-lookup"><span data-stu-id="d1b62-115">Before executing the query, the example validates that the document complies with the schema in [Sample XSD File: Customers and Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md).</span></span> <span data-ttu-id="d1b62-116">Auf diese Weise wird sichergestellt, dass die JOIN-Klausel immer funktioniert.</span><span class="sxs-lookup"><span data-stu-id="d1b62-116">This ensures that the join clause will always work.</span></span>  
  
 <span data-ttu-id="d1b62-117">Diese Abfrage ruft zuerst alle `Customer`-Elemente ab und verknüpft sie dann mit den `Order`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="d1b62-117">This query first retrieves all `Customer` elements, and then joins them to the `Order` elements.</span></span> <span data-ttu-id="d1b62-118">Sie wählt dabei nur die Aufträge der Kunden aus, deren `CustomerID` größer als "K" ist.</span><span class="sxs-lookup"><span data-stu-id="d1b62-118">It selects only the orders for customers with a `CustomerID` greater than "K".</span></span> <span data-ttu-id="d1b62-119">Anschließend projiziert die Abfrage ein neues `Order`-Element, das die Kundeninformationen in den einzelnen Aufträgen enthält.</span><span class="sxs-lookup"><span data-stu-id="d1b62-119">It then projects a new `Order` element that contains the customer information within each order.</span></span>  
  
 <span data-ttu-id="d1b62-120">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="d1b62-120">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
 <span data-ttu-id="d1b62-121">In diesem Beispiel wird das folgende XML-Schema verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md).</span><span class="sxs-lookup"><span data-stu-id="d1b62-121">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md).</span></span>  
  
 <span data-ttu-id="d1b62-122">Beachten Sie, dass diese Art von Verknüpfungen zu Leistungseinbußen führt.</span><span class="sxs-lookup"><span data-stu-id="d1b62-122">Note that joining in this fashion will not perform very well.</span></span> <span data-ttu-id="d1b62-123">Joins (Verknüpfungen) werden über eine lineare Suche ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d1b62-123">Joins are performed via a linear search.</span></span> <span data-ttu-id="d1b62-124">Es gibt keine Hashtabellen oder Indizes, die die Geschwindigkeit erhöhen könnten.</span><span class="sxs-lookup"><span data-stu-id="d1b62-124">There are no hash tables or indexes to help with performance.</span></span>  
  
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
  
 <span data-ttu-id="d1b62-125">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d1b62-125">This code produces the following output:</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="d1b62-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1b62-126">See Also</span></span>  
 [<span data-ttu-id="d1b62-127">Erweiterte Abfragetechniken (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="d1b62-127">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
