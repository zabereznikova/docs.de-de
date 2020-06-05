---
title: 'Vorgehensweise: Verknüpfen zweier Auflistungen (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 5a5758d4-906b-4285-908d-5b930db192e6
ms.openlocfilehash: dc3cfd19d990fa81e00f4781cb15bf07eb9a80ea
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398050"
---
# <a name="how-to-join-two-collections-linq-to-xml-visual-basic"></a><span data-ttu-id="b7a02-102">Vorgehensweise: Verknüpfen von zwei Auflistungen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7a02-102">How to: Join Two Collections (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="b7a02-103">Ein Element oder Attribut in einem XML-Dokument kann mitunter auf ein anderes Element oder Attribut verweisen.</span><span class="sxs-lookup"><span data-stu-id="b7a02-103">An element or attribute in an XML document can sometimes refer to another element or attribute.</span></span> <span data-ttu-id="b7a02-104">So enthält das XML-Dokument in [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md) z.B. eine Liste von Kunden und eine Liste von Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="b7a02-104">For example, the [Sample XML File: Customers and Orders (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md) XML document contains a list of customers and a list of orders.</span></span> <span data-ttu-id="b7a02-105">Jedes `Customer`-Element enthält ein `CustomerID`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="b7a02-105">Each `Customer` element contains a `CustomerID` attribute.</span></span> <span data-ttu-id="b7a02-106">Jedes `Order`-Element enthält ein `CustomerID`-Element.</span><span class="sxs-lookup"><span data-stu-id="b7a02-106">Each `Order` element contains a `CustomerID` element.</span></span> <span data-ttu-id="b7a02-107">Das `CustomerID`-Element eines Auftrags verweist auf das `CustomerID`-Attribut eines Kunden.</span><span class="sxs-lookup"><span data-stu-id="b7a02-107">The `CustomerID` element in each order refers to the `CustomerID` attribute in a customer.</span></span>  
  
 <span data-ttu-id="b7a02-108">Das Thema [Beispiel-XSD-Datei: Kunden und Bestellungen](sample-xsd-file-customers-and-orders.md) enthält ein XSD-Schema, das zum Validieren dieses Dokuments verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b7a02-108">The topic [Sample XSD File: Customers and Orders](sample-xsd-file-customers-and-orders.md) contains an XSD that can be used to validate this document.</span></span> <span data-ttu-id="b7a02-109">Mit den Funktionen `xs:key` und `xs:keyref` des XSD-Schemas wird geprüft, ob das `CustomerID`-Attribut des `Customer`-Elements ein Schlüssel ist. Außerdem wird damit eine Beziehung zwischen dem `CustomerID`-Element in jedem `Order`-Element und dem `CustomerID`-Attribut in jedem `Customer`-Element hergestellt.</span><span class="sxs-lookup"><span data-stu-id="b7a02-109">It uses the `xs:key` and `xs:keyref` features of XSD to establish that the `CustomerID` attribute of the `Customer` element is a key, and to establish a relationship between the `CustomerID` element in each `Order` element and the `CustomerID` attribute in each `Customer` element.</span></span>  
  
 <span data-ttu-id="b7a02-110">Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie diese Beziehung durch Verwenden der `Join`-Klausel nutzen.</span><span class="sxs-lookup"><span data-stu-id="b7a02-110">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can take advantage of this relationship by using the `Join` clause.</span></span>  
  
 <span data-ttu-id="b7a02-111">Da es keinen Index gibt, führt eine solche Verknüpfung zu einer schlechten Laufzeitleistung.</span><span class="sxs-lookup"><span data-stu-id="b7a02-111">Note that because there is no index available, such joining will have poor runtime performance.</span></span>  
  
 <span data-ttu-id="b7a02-112">Ausführlichere Informationen zu `Join` finden Sie unter [joinvorgänge (Visual Basic)](join-operations.md).</span><span class="sxs-lookup"><span data-stu-id="b7a02-112">For more detailed information about `Join`, see [Join Operations (Visual Basic)](join-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7a02-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b7a02-113">Example</span></span>  
 <span data-ttu-id="b7a02-114">Das folgende Beispiel verknüpft die `Customer`-Elemente mit den `Order`-Elementen und generiert ein neues XML-Dokument, das das `CompanyName`-Element der Aufträge enthält.</span><span class="sxs-lookup"><span data-stu-id="b7a02-114">The following example joins the `Customer` elements to the `Order` elements, and generates a new XML document that includes the `CompanyName` element in the orders.</span></span>  
  
 <span data-ttu-id="b7a02-115">Vor dem Ausführen der Abfrage überprüft das Beispiel, ob das Dokument dem Schema in [Beispiel-XSD-Datei: Kunden und Bestellungen](sample-xsd-file-customers-and-orders.md) entspricht.</span><span class="sxs-lookup"><span data-stu-id="b7a02-115">Before executing the query, the example validates that the document complies with the schema in [Sample XSD File: Customers and Orders](sample-xsd-file-customers-and-orders.md).</span></span> <span data-ttu-id="b7a02-116">Auf diese Weise wird sichergestellt, dass die JOIN-Klausel immer funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b7a02-116">This ensures that the join clause will always work.</span></span>  
  
 <span data-ttu-id="b7a02-117">Diese Abfrage ruft zuerst alle `Customer`-Elemente ab und verknüpft sie dann mit den `Order`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="b7a02-117">This query first retrieves all `Customer` elements, and then joins them to the `Order` elements.</span></span> <span data-ttu-id="b7a02-118">Sie wählt dabei nur die Aufträge der Kunden aus, deren `CustomerID` größer als "K" ist.</span><span class="sxs-lookup"><span data-stu-id="b7a02-118">It selects only the orders for customers with a `CustomerID` greater than "K".</span></span> <span data-ttu-id="b7a02-119">Anschließend projiziert die Abfrage ein neues `Order`-Element, das die Kundeninformationen in den einzelnen Aufträgen enthält.</span><span class="sxs-lookup"><span data-stu-id="b7a02-119">It then projects a new `Order` element that contains the customer information within each order.</span></span>  
  
 <span data-ttu-id="b7a02-120">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b7a02-120">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="b7a02-121">In diesem Beispiel wird das folgende XML-Schema verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](sample-xsd-file-customers-and-orders.md).</span><span class="sxs-lookup"><span data-stu-id="b7a02-121">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](sample-xsd-file-customers-and-orders.md).</span></span>  
  
 <span data-ttu-id="b7a02-122">Beachten Sie, dass diese Art von Verknüpfungen zu Leistungseinbußen führt.</span><span class="sxs-lookup"><span data-stu-id="b7a02-122">Note that joining in this fashion will not perform very well.</span></span> <span data-ttu-id="b7a02-123">Joins (Verknüpfungen) werden über eine lineare Suche ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b7a02-123">Joins are performed via a linear search.</span></span> <span data-ttu-id="b7a02-124">Es gibt keine Hashtabellen oder Indizes, die die Geschwindigkeit erhöhen könnten.</span><span class="sxs-lookup"><span data-stu-id="b7a02-124">There are no hash tables or indexes to help with performance.</span></span>  
  
```vb  
Public Class Program  
    Public Shared errors As Boolean = False  
  
    Public Shared Function LamValidEvent(ByVal o As Object, _  
                 ByVal e As ValidationEventArgs) As Boolean  
        Console.WriteLine("{0}", e.Message)  
        errors = True  
    End Function  
  
    Shared Sub Main()  
        Dim schemas As New XmlSchemaSet()  
        schemas.Add("", "CustomersOrders.xsd")  
  
        Console.Write("Attempting to validate, ")  
        Dim custOrdDoc As XDocument = XDocument.Load("CustomersOrders.xml")  
  
        custOrdDoc.Validate(schemas, Function(o, e) LamValidEvent(0, e))  
        If errors Then  
            Console.WriteLine("custOrdDoc did not validate")  
        Else  
            Console.WriteLine("custOrdDoc validated")  
        End If  
  
        If Not errors Then  
            'Join customers and orders, and create a new XML document with  
            ' a different shape.  
            'The new document contains orders only for customers with a  
            ' CustomerID > 'K'.  
            Dim custOrd As XElement = custOrdDoc.<Root>.FirstOrDefault  
            Dim newCustOrd As XElement = _  
                <Root>  
                    <%= From c In custOrd.<Customers>.<Customer> _  
                        Join o In custOrd.<Orders>.<Order> _  
                        On c.@CustomerID Equals o.<CustomerID>.Value _  
                        Where c.@CustomerID.CompareTo("K") > 0 _  
                        Select _  
                        <Order>  
                            <CustomerID><%= c.@CustomerID %></CustomerID>  
                            <%= c.<CompanyName> %>  
                            <%= c.<ContactName> %>  
                            <%= o.<EmployeeID> %>  
                            <%= o.<OrderDate> %>  
                        </Order> _  
                    %>  
                </Root>  
            Console.WriteLine(newCustOrd)  
        End If  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="b7a02-125">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="b7a02-125">This code produces the following output:</span></span>  
  
```console
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
  
## <a name="see-also"></a><span data-ttu-id="b7a02-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7a02-126">See also</span></span>

- [<span data-ttu-id="b7a02-127">Erweiterte Abfrage Techniken (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7a02-127">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](advanced-query-techniques-linq-to-xml.md)
