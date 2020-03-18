---
title: 'Vorgehensweise: Verknüpfen von zwei Sammlungen (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 7b817ede-911a-4cff-9dd3-639c3fc228c9
ms.openlocfilehash: a5044778bbfd9529faf5fe63c72076f6a973c815
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75345861"
---
# <a name="how-to-join-two-collections-linq-to-xml-c"></a>Vorgehensweise: Verknüpfen von zwei Sammlungen (LINQ to XML) (C#)

Ein Element oder Attribut in einem XML-Dokument kann mitunter auf ein anderes Element oder Attribut verweisen. So enthält das XML-Dokument in [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md) z.B. eine Liste von Kunden und eine Liste von Aufträgen. Jedes `Customer`-Element enthält ein `CustomerID`-Attribut. Jedes `Order`-Element enthält ein `CustomerID`-Element. Das `CustomerID`-Element eines Auftrags verweist auf das `CustomerID`-Attribut eines Kunden.

Das Thema [Beispiel-XSD-Datei: Kunden und Bestellungen](./sample-xsd-file-customers-and-orders1.md) enthält ein XSD-Schema, das zum Validieren dieses Dokuments verwendet werden kann. Mit den Funktionen `xs:key` und `xs:keyref` des XSD-Schemas wird geprüft, ob das `CustomerID`-Attribut des `Customer`-Elements ein Schlüssel ist. Außerdem wird damit eine Beziehung zwischen dem `CustomerID`-Element in jedem `Order`-Element und dem `CustomerID`-Attribut in jedem `Customer`-Element hergestellt.

Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie diese Beziehung durch Verwenden der `join`-Klausel nutzen.

Da kein Index verfügbar ist, führt eine solche Verknüpfung zu einer schlechten Laufzeitleistung.

Ausführlichere Informationen zu `join` finden Sie unter [Join Operations (C#) (Verknüpfungsvorgänge (C#))](./join-operations.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel verknüpft die `Customer`-Elemente mit den `Order`-Elementen und generiert ein neues XML-Dokument, das das `CompanyName`-Element der Aufträge enthält.

Vor dem Ausführen der Abfrage überprüft das Beispiel, ob das Dokument dem Schema in [Beispiel-XSD-Datei: Kunden und Bestellungen](./sample-xsd-file-customers-and-orders1.md) entspricht. Auf diese Weise wird sichergestellt, dass die JOIN-Klausel immer funktioniert.

Diese Abfrage ruft zuerst alle `Customer`-Elemente ab und verknüpft sie dann mit den `Order`-Elementen. Sie wählt dabei nur die Aufträge der Kunden aus, deren `CustomerID` größer als "K" ist. Anschließend projiziert die Abfrage ein neues `Order`-Element, das die Kundeninformationen in den einzelnen Aufträgen enthält.

In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).

In diesem Beispiel wird das folgende XML-Schema verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](./sample-xsd-file-customers-and-orders1.md).

Diese Art von Verknüpfungen führt zu Leistungseinbußen. Joins (Verknüpfungen) werden über eine lineare Suche ausgeführt. Es gibt keine Hashtabellen oder Indizes, die die Geschwindigkeit erhöhen könnten.

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

Dieser Code erzeugt die folgende Ausgabe:

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
