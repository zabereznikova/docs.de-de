---
title: 'Vorgehensweise: Transformieren der Form einer XML-Struktur (C#)'
ms.date: 07/20/2015
ms.assetid: 93c5d426-dea2-4709-a991-60204de42e8f
ms.openlocfilehash: 91f91ed6fea5371fae2ce67a413f4825f37af6c3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347307"
---
# <a name="how-to-transform-the-shape-of-an-xml-tree-c"></a><span data-ttu-id="e98c1-102">Vorgehensweise: Transformieren der Form einer XML-Struktur (C#)</span><span class="sxs-lookup"><span data-stu-id="e98c1-102">How to transform the shape of an XML tree (C#)</span></span>
<span data-ttu-id="e98c1-103">Die *Form* eines XML-Dokuments wird von dessen Elementnamen, Attributnamen und den Merkmalen seiner Hierarchie bestimmt.</span><span class="sxs-lookup"><span data-stu-id="e98c1-103">The *shape* of an XML document refers to its element names, attribute names, and the characteristics of its hierarchy.</span></span>  
  
 <span data-ttu-id="e98c1-104">Es kann passieren, dass Sie die Form eines XML-Dokuments ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="e98c1-104">Sometimes you will have to change the shape of an XML document.</span></span> <span data-ttu-id="e98c1-105">Dies kann z. B. der Fall sein, wenn Sie ein vorhandenes XML-Dokument an ein anderes System senden müssen, das andere Element- und Attributnamen verlangt.</span><span class="sxs-lookup"><span data-stu-id="e98c1-105">For example, you might have to send an existing XML document to another system that requires different element and attribute names.</span></span> <span data-ttu-id="e98c1-106">Sie können das Dokument zwar selbst durchgehen und die Elemente nach Bedarf löschen und umbenennen, bei Verwendung der funktionalen Konstruktion erhalten Sie aber besser lesbaren und verwaltbaren Code.</span><span class="sxs-lookup"><span data-stu-id="e98c1-106">You could go through the document, deleting and renaming elements as required, but using functional construction results in more readable and maintainable code.</span></span> <span data-ttu-id="e98c1-107">Weitere Informationen zu funktionalen Konstruktionen finden Sie unter [Functional Construction (LINQ to XML) (C#) (Funktionale Konstruktion (LINQ to XML) (C#))](./functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e98c1-107">For more information about functional construction, see [Functional Construction (LINQ to XML) (C#)](./functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="e98c1-108">Das erste Beispiel ändert die Organisation des XML-Dokuments.</span><span class="sxs-lookup"><span data-stu-id="e98c1-108">The first example changes the organization of the XML document.</span></span> <span data-ttu-id="e98c1-109">Dabei werden komplexe Elemente von einer Position in der Struktur an eine andere verschoben.</span><span class="sxs-lookup"><span data-stu-id="e98c1-109">It moves complex elements from one location in the tree to another.</span></span>  
  
 <span data-ttu-id="e98c1-110">Das zweite Beispiel in diesem Thema erstellt ein XML-Dokument, dessen Form sich von der Form des Quelldokuments unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="e98c1-110">The second example in this topic creates an XML document with a different shape than the source document.</span></span> <span data-ttu-id="e98c1-111">Es ändert die Groß- und Kleinschreibung der Elementnamen, benennt einige Elemente um und lässt einige Elemente aus der Quellstruktur aus der transformierten Struktur heraus.</span><span class="sxs-lookup"><span data-stu-id="e98c1-111">It changes the casing of the element names, renames some elements, and leaves some elements from the source tree out of the transformed tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e98c1-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e98c1-112">Example</span></span>  
 <span data-ttu-id="e98c1-113">Der folgende Code ändert die Form einer XML-Datei, die eingebettete Abfrageausdrücke verwendet.</span><span class="sxs-lookup"><span data-stu-id="e98c1-113">The following code changes the shape of an XML file using embedded query expressions.</span></span>  
  
 <span data-ttu-id="e98c1-114">Das XML-Quelldokument in diesem Beispiel enthält unter dem `Customers`-Element ein `Root`-Element, das alle Kunden enthält.</span><span class="sxs-lookup"><span data-stu-id="e98c1-114">The source XML document in this example contains a `Customers` element under the `Root` element that contains all customers.</span></span> <span data-ttu-id="e98c1-115">Außerdem enthält es unter dem `Orders`-Element ein `Root`-Element, das alle Aufträge enthält.</span><span class="sxs-lookup"><span data-stu-id="e98c1-115">It also contains an `Orders` element under the `Root` element that contains all orders.</span></span> <span data-ttu-id="e98c1-116">Dieses Beispiel erstellt eine neue XML-Struktur, in der die Aufträge der einzelnen Kunden in einem `Orders`-Element innerhalb des `Customer`-Elements enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e98c1-116">This example creates a new XML tree in which the orders for each customer are contained in an `Orders` element within the `Customer` element.</span></span> <span data-ttu-id="e98c1-117">Das Originaldokument enthält auch ein `CustomerID`-Element im `Order`-Element; dieses Element wird aus dem neu geformten Dokument entfernt.</span><span class="sxs-lookup"><span data-stu-id="e98c1-117">The original document also contains a `CustomerID` element in the `Order` element; this element will be removed from the re-shaped document.</span></span>  
  
 <span data-ttu-id="e98c1-118">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="e98c1-118">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
XElement co = XElement.Load("CustomersOrders.xml");  
XElement newCustOrd =  
    new XElement("Root",  
        from cust in co.Element("Customers").Elements("Customer")  
        select new XElement("Customer",  
            cust.Attributes(),  
            cust.Elements(),  
            new XElement("Orders",  
                from ord in co.Element("Orders").Elements("Order")  
                where (string)ord.Element("CustomerID") == (string)cust.Attribute("CustomerID")  
                select new XElement("Order",  
                    ord.Attributes(),  
                    ord.Element("EmployeeID"),  
                    ord.Element("OrderDate"),  
                    ord.Element("RequiredDate"),  
                    ord.Element("ShipInfo")  
                )  
            )  
        )  
    );  
Console.WriteLine(newCustOrd);  
```  
  
 <span data-ttu-id="e98c1-119">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e98c1-119">This code produces the following output:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="e98c1-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e98c1-120">Example</span></span>  
 <span data-ttu-id="e98c1-121">Dieses Beispiel benennt einige Elemente um und wandelt einige Attribute in Elemente um.</span><span class="sxs-lookup"><span data-stu-id="e98c1-121">This example renames some elements and converts some attributes to elements.</span></span>  
  
 <span data-ttu-id="e98c1-122">Der Code ruft `ConvertAddress` auf, wodurch eine Liste von <xref:System.Xml.Linq.XElement>-Objekten zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e98c1-122">The code calls `ConvertAddress`, which returns a list of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="e98c1-123">Das Argument für die Methode ist eine Abfrage, die das komplexe `Address`-Element bestimmt, wobei das `Type`-Attribut den Wert `"Shipping"` hat.</span><span class="sxs-lookup"><span data-stu-id="e98c1-123">The argument to the method is a query that determines the `Address` complex element where the `Type` attribute has a value of `"Shipping"`.</span></span>  
  
 <span data-ttu-id="e98c1-124">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Typische Bestellung (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="e98c1-124">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
static IEnumerable<XElement> ConvertAddress(XElement add)  
{  
    List<XElement> fragment = new List<XElement>() {  
        new XElement("NAME", (string)add.Element("Name")),  
        new XElement("STREET", (string)add.Element("Street")),  
        new XElement("CITY", (string)add.Element("City")),  
        new XElement("ST", (string)add.Element("State")),  
        new XElement("POSTALCODE", (string)add.Element("Zip")),  
        new XElement("COUNTRY", (string)add.Element("Country"))  
    };  
    return fragment;  
}  
  
static void Main(string[] args)  
{  
    XElement po = XElement.Load("PurchaseOrder.xml");  
    XElement newPo = new XElement("PO",  
        new XElement("ID", (string)po.Attribute("PurchaseOrderNumber")),  
        new XElement("DATE", (DateTime)po.Attribute("OrderDate")),  
        ConvertAddress(  
            (from el in po.Elements("Address")  
            where (string)el.Attribute("Type") == "Shipping"  
            select el)  
            .First()  
        )  
    );  
    Console.WriteLine(newPo);  
}  
```  
  
 <span data-ttu-id="e98c1-125">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e98c1-125">This code produces the following output:</span></span>  
  
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
