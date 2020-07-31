---
title: 'Vorgehensweise: Suchen nach verwandten Elementen (XPath-LINQ to XML) (C#)'
description: In diesem C#-Beispiel wird verglichen, wie Sie mit XPath und LINQ to XML Elemente abrufen können, indem Sie ein Attribut auswählen, auf das der Wert eines anderen Elements verweist.
ms.date: 07/20/2015
ms.assetid: 41b386ee-562d-4841-bd6b-e44a7eb69f26
ms.openlocfilehash: 4423e7d719d39e71bcbcc9e88d052c6aff4ffb05
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105255"
---
# <a name="how-to-find-related-elements-xpath-linq-to-xml-c"></a>Vorgehensweise: Suchen nach verwandten Elementen (XPath-LINQ to XML) (C#)
In diesem Thema wird gezeigt, wie Sie ein Element abrufen können, das auf der Basis eines Attributs ausgewählt wird, auf das vom Wert eines anderen Elements verwiesen wird.  
  
 Der XPath-Ausdruck lautet:  
  
 `.//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]`  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel sucht nach dem 12. `Order`-Element und ermittelt anschließend den Kunden für diesen Auftrag.  
  
 Beachten Sie, dass beim Indizieren von Listen in .NET die Zählung mit 0 (Null) beginnt. Beim Indizieren einer Auflistung von Knoten in einem XPath-Prädikat beginnt die Zählung dagegen mit 1. Dieser Unterschied wird im folgenden Beispiel verdeutlicht.  
  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).  
  
```csharp  
XDocument co = XDocument.Load("CustomersOrders.xml");  
  
// LINQ to XML query  
XElement customer1 =  
    (from el in co.Descendants("Customer")  
     where (string)el.Attribute("CustomerID") ==  
          (string)(co  
              .Element("Root")  
              .Element("Orders")  
              .Elements("Order")  
              .ToList()[11]  
              .Element("CustomerID"))  
    select el)  
    .First();  
  
// An alternate way to write the query that avoids creation  
// of a System.Collections.Generic.List:  
XElement customer2 =  
    (from el in co.Descendants("Customer")  
     where (string)el.Attribute("CustomerID") ==  
          (string)(co  
              .Element("Root")  
              .Element("Orders")  
              .Elements("Order")  
              .Skip(11).First()  
              .Element("CustomerID"))  
    select el)  
    .First();  
  
// XPath expression  
XElement customer3 = co.XPathSelectElement(  
  ".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]");  
  
if (customer1 == customer2 && customer1 == customer3)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(customer1);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```output  
Results are identical  
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
</Customer>  
```  
