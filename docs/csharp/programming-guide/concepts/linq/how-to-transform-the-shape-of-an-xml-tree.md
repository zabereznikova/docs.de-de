---
title: 'Vorgehensweise: Transformieren der Form einer XML-Struktur (C#)'
ms.date: 07/20/2015
ms.assetid: 93c5d426-dea2-4709-a991-60204de42e8f
ms.openlocfilehash: 91f91ed6fea5371fae2ce67a413f4825f37af6c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75347307"
---
# <a name="how-to-transform-the-shape-of-an-xml-tree-c"></a>Vorgehensweise: Transformieren der Form einer XML-Struktur (C#)
Die *Form* eines XML-Dokuments wird von dessen Elementnamen, Attributnamen und den Merkmalen seiner Hierarchie bestimmt.  
  
 Es kann passieren, dass Sie die Form eines XML-Dokuments ändern müssen. Dies kann z. B. der Fall sein, wenn Sie ein vorhandenes XML-Dokument an ein anderes System senden müssen, das andere Element- und Attributnamen verlangt. Sie können das Dokument zwar selbst durchgehen und die Elemente nach Bedarf löschen und umbenennen, bei Verwendung der funktionalen Konstruktion erhalten Sie aber besser lesbaren und verwaltbaren Code. Weitere Informationen zu funktionalen Konstruktionen finden Sie unter [Functional Construction (LINQ to XML) (C#) (Funktionale Konstruktion (LINQ to XML) (C#))](./functional-construction-linq-to-xml.md).  
  
 Das erste Beispiel ändert die Organisation des XML-Dokuments. Dabei werden komplexe Elemente von einer Position in der Struktur an eine andere verschoben.  
  
 Das zweite Beispiel in diesem Thema erstellt ein XML-Dokument, dessen Form sich von der Form des Quelldokuments unterscheidet. Es ändert die Groß- und Kleinschreibung der Elementnamen, benennt einige Elemente um und lässt einige Elemente aus der Quellstruktur aus der transformierten Struktur heraus.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code ändert die Form einer XML-Datei, die eingebettete Abfrageausdrücke verwendet.  
  
 Das XML-Quelldokument in diesem Beispiel enthält unter dem `Customers`-Element ein `Root`-Element, das alle Kunden enthält. Außerdem enthält es unter dem `Orders`-Element ein `Root`-Element, das alle Aufträge enthält. Dieses Beispiel erstellt eine neue XML-Struktur, in der die Aufträge der einzelnen Kunden in einem `Orders`-Element innerhalb des `Customer`-Elements enthalten sind. Das Originaldokument enthält auch ein `CustomerID`-Element im `Order`-Element; dieses Element wird aus dem neu geformten Dokument entfernt.  
  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).  
  
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
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
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
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel benennt einige Elemente um und wandelt einige Attribute in Elemente um.  
  
 Der Code ruft `ConvertAddress` auf, wodurch eine Liste von <xref:System.Xml.Linq.XElement>-Objekten zurückgegeben wird. Das Argument für die Methode ist eine Abfrage, die das komplexe `Address`-Element bestimmt, wobei das `Type`-Attribut den Wert `"Shipping"` hat.  
  
 Dieses Beispiel verwendet das folgende XML-Dokument: [Beispiel-XML-Datei: Typische Bestellung (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).  
  
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
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
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
