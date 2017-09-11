---
title: 'Gewusst wie: Transformieren der Form einer XML-Struktur (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 84b60854-48b2-452c-87f2-77d53e1d653a
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 9c535a06e70ebd299d7f6646576e703d7a0dda84
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-transform-the-shape-of-an-xml-tree-visual-basic"></a><span data-ttu-id="2a2d7-102">Gewusst wie: Transformieren der Form einer XML-Struktur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a2d7-102">How to: Transform the Shape of an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="2a2d7-103">Die *Form* eines XML-Dokument, dessen Elementnamen, Attributnamen und den Merkmalen seiner Hierarchie bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2a2d7-103">The *shape* of an XML document refers to its element names, attribute names, and the characteristics of its hierarchy.</span></span>  
  
 <span data-ttu-id="2a2d7-104">Es kann passieren, dass Sie die Form eines XML-Dokuments ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="2a2d7-104">Sometimes you will have to change the shape of an XML document.</span></span> <span data-ttu-id="2a2d7-105">Dies kann z. B. der Fall sein, wenn Sie ein vorhandenes XML-Dokument an ein anderes System senden müssen, das andere Element- und Attributnamen verlangt.</span><span class="sxs-lookup"><span data-stu-id="2a2d7-105">For example, you might have to send an existing XML document to another system that requires different element and attribute names.</span></span> <span data-ttu-id="2a2d7-106">Sie können das Dokument zwar selbst durchgehen und die Elemente nach Bedarf löschen und umbenennen, bei Verwendung der funktionalen Konstruktion erhalten Sie aber besser lesbaren und verwaltbaren Code.</span><span class="sxs-lookup"><span data-stu-id="2a2d7-106">You could go through the document, deleting and renaming elements as required, but using functional construction results in more readable and maintainable code.</span></span> <span data-ttu-id="2a2d7-107">Weitere Informationen zur funktionalen Konstruktion finden Sie unter [funktionale Konstruktion (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2a2d7-107">For more information about functional construction, see [Functional Construction (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="2a2d7-108">Das erste Beispiel ändert die Organisation des XML-Dokuments.</span><span class="sxs-lookup"><span data-stu-id="2a2d7-108">The first example changes the organization of the XML document.</span></span> <span data-ttu-id="2a2d7-109">Dabei werden komplexe Elemente von einer Position in der Struktur an eine andere verschoben.</span><span class="sxs-lookup"><span data-stu-id="2a2d7-109">It moves complex elements from one location in the tree to another.</span></span>  
  
 <span data-ttu-id="2a2d7-110">Das zweite Beispiel in diesem Thema erstellt ein XML-Dokument, dessen Form sich von der Form des Quelldokuments unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="2a2d7-110">The second example in this topic creates an XML document with a different shape than the source document.</span></span> <span data-ttu-id="2a2d7-111">Es ändert die Groß- und Kleinschreibung der Elementnamen, benennt einige Elemente um und lässt einige Elemente aus der Quellstruktur aus der transformierten Struktur heraus.</span><span class="sxs-lookup"><span data-stu-id="2a2d7-111">It changes the casing of the element names, renames some elements, and leaves some elements from the source tree out of the transformed tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a2d7-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2a2d7-112">Example</span></span>  
 <span data-ttu-id="2a2d7-113">Der folgende Code ändert die Form einer XML-Datei, die eingebettete Abfrageausdrücke verwendet.</span><span class="sxs-lookup"><span data-stu-id="2a2d7-113">The following code changes the shape of an XML file using embedded query expressions.</span></span>  
  
 <span data-ttu-id="2a2d7-114">Das XML-Quelldokument in diesem Beispiel enthält unter dem `Customers`-Element ein `Root`-Element, das alle Kunden enthält.</span><span class="sxs-lookup"><span data-stu-id="2a2d7-114">The source XML document in this example contains a `Customers` element under the `Root` element that contains all customers.</span></span> <span data-ttu-id="2a2d7-115">Außerdem enthält es unter dem `Orders`-Element ein `Root`-Element, das alle Aufträge enthält.</span><span class="sxs-lookup"><span data-stu-id="2a2d7-115">It also contains an `Orders` element under the `Root` element that contains all orders.</span></span> <span data-ttu-id="2a2d7-116">Dieses Beispiel erstellt eine neue XML-Struktur, in der die Aufträge der einzelnen Kunden in einem `Orders`-Element innerhalb des `Customer`-Elements enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2a2d7-116">This example creates a new XML tree in which the orders for each customer are contained in an `Orders` element within the `Customer` element.</span></span> <span data-ttu-id="2a2d7-117">Das Originaldokument enthält auch ein `CustomerID`-Element im `Order`-Element; dieses Element wird aus dem neu geformten Dokument entfernt.</span><span class="sxs-lookup"><span data-stu-id="2a2d7-117">The original document also contains a `CustomerID` element in the `Order` element; this element will be removed from the re-shaped document.</span></span>  
  
 <span data-ttu-id="2a2d7-118">Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: Kunden und Bestellungen (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2a2d7-118">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim co As XElement = XElement.Load("CustomersOrders.xml")  
Dim newCustOrd = _  
    <Root>  
        <%= From cust In co.<Customers>.<Customer> _  
            Select _  
            <Customer>  
                <%= cust.Attributes() %>  
                <%= cust.Elements() %>  
                <Orders>  
                    <%= From ord In co.<Orders>.<Order> _  
                        Where ord.<CustomerID>.Value = cust.@CustomerID _  
                        Select _  
                        <Order>  
                            <%= ord.Attributes() %>  
                            <%= ord.<EmployeeID> %>  
                            <%= ord.<OrderDate> %>  
                            <%= ord.<RequiredDate> %>  
                            <%= ord.<ShipInfo> %>  
                        </Order> _  
                    %>  
                </Orders>  
            </Customer> _  
        %>  
    </Root>  
Console.WriteLine(newCustOrd)  
```  
  
 <span data-ttu-id="2a2d7-119">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="2a2d7-119">This code produces the following output:</span></span>  
  
```xml  
        <Root>  
<Customer CustomerID="GREAL">  
  <CompanyName>Great Lakes Food Market</CompanyName>  
  <ContactName>Howard Snyder</ContactName>  
  <ContactTitle>Marketing Manager</ContactTitle>  
  <Phone>(503) 555-7555</Phone>  
  <FullAddress>  
    <Address>2732 Baker Blvd.</Address>  
    <City>Eugene</City>  
    <Region>OR</Region>  
    <PostalCode>97403</PostalCode>  
    <Country>USA</Country>  
  </FullAddress>  
  <Orders />  
</Customer>  
<Customer CustomerID="HUNGC">  
  <CompanyName>Hungry Coyote Import Store</CompanyName>  
  <ContactName>Yoshi Latimer</ContactName>  
  <ContactTitle>Sales Representative</ContactTitle>  
  <Phone>(503) 555-6874</Phone>  
  <Fax>(503) 555-2376</Fax>  
  <FullAddress>  
    <Address>City Center Plaza 516 Main St.</Address>  
    <City>Elgin</City>  
    <Region>OR</Region>  
    <PostalCode>97827</PostalCode>  
    <Country>USA</Country>  
  </FullAddress>  
  <Orders />  
</Customer>  
. . .  
```  
  
## <a name="example"></a><span data-ttu-id="2a2d7-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2a2d7-120">Example</span></span>  
 <span data-ttu-id="2a2d7-121">Dieses Beispiel benennt einige Elemente um und wandelt einige Attribute in Elemente um.</span><span class="sxs-lookup"><span data-stu-id="2a2d7-121">This example renames some elements and converts some attributes to elements.</span></span>  
  
 <span data-ttu-id="2a2d7-122">Der Code ruft `ConvertAddress`, womit eine Liste der <xref:System.Xml.Linq.XElement>Objekte.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="2a2d7-122">The code calls `ConvertAddress`, which returns a list of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="2a2d7-123">Das Argument für die Methode ist eine Abfrage, die das komplexe `Address`-Element bestimmt, wobei das `Type`-Attribut den Wert `"Shipping"` hat.</span><span class="sxs-lookup"><span data-stu-id="2a2d7-123">The argument to the method is a query that determines the `Address` complex element where the `Type` attribute has a value of `"Shipping"`.</span></span>  
  
 <span data-ttu-id="2a2d7-124">Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2a2d7-124">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Function ConvertAddress(ByVal add As XElement) As IEnumerable(Of XElement)  
    Dim fragment = New List(Of XElement)  
    fragment.Add(<NAME><%= add.<Name>.Value %></NAME>)  
    fragment.Add(<STREET><%= add.<Street>.Value %></STREET>)  
    fragment.Add(<CITY><%= add.<City>.Value %></CITY>)  
    fragment.Add(<ST><%= add.<State>.Value %></ST>)  
    fragment.Add(<POSTALCODE><%= add.<Zip>.Value %></POSTALCODE>)  
    fragment.Add(<COUNTRY><%= add.<Country>.Value %></COUNTRY>)  
    Return fragment  
End Function  
  
Sub Main()  
    Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
    Dim newPo As XElement = _  
        <PO>  
            <ID><%= po.@PurchaseOrderNumber %></ID>  
            <DATE><%= CDate(po.@OrderDate) %></DATE>  
            <%= _  
                ConvertAddress( _  
                (From el In po.<Address> _  
                Where el.@Type = "Shipping" _  
                Select el) _  
                .First() _  
                ) _  
            %>  
        </PO>  
    Console.WriteLine(newPo)  
End Sub  
```  
  
 <span data-ttu-id="2a2d7-125">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="2a2d7-125">This code produces the following output:</span></span>  
  
```xml  
<PO>  
  <ID>99503</ID>  
  <DATE>1999-10-20T00:00:00</DATE>  
  <NAME>Ellen Adams</NAME>  
  <STREET>123 Maple Street</STREET>  
  <CITY>Mill Valley</CITY>  
  <ST>CA</ST>  
  <POSTALCODE>10999</POSTALCODE>  
  <COUNTRY>USA</COUNTRY>  
</PO>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a2d7-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a2d7-126">See Also</span></span>  
 [<span data-ttu-id="2a2d7-127">Projektionen und Transformationen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a2d7-127">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)

