---
title: 'Gewusst wie: Suchen nach verwandten Elementen (XPath-LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 6b0ef058-d704-48a5-98cd-33f00d088af9
ms.openlocfilehash: e250572e7bd73e769e4ab06b7b7ff9e3b3d38c47
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344647"
---
# <a name="how-to-find-related-elements-xpath-linq-to-xml-visual-basic"></a>Gewusst wie: Suchen nach verwandten Elementen (XPath-LINQ to XML) (Visual Basic)
In diesem Thema wird gezeigt, wie Sie ein Element abrufen können, das auf der Basis eines Attributs ausgewählt wird, auf das vom Wert eines anderen Elements verwiesen wird.  
  
 Der XPath-Ausdruck lautet:  
  
 `.//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]`  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel sucht nach dem 12. `Order`-Element und ermittelt anschließend den Kunden für diesen Auftrag.  
  
 Beachten Sie, dass beim Indizieren von Listen in .NET die Zählung mit 0 (Null) beginnt. Beim Indizieren einer Auflistung von Knoten in einem XPath-Prädikat beginnt die Zählung dagegen mit 1. Dieser Unterschied wird im folgenden Beispiel verdeutlicht.  
  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).  
  
```vb  
Dim co As XDocument = XDocument.Load("CustomersOrders.xml")  
  
' LINQ to XML query  
Dim customer1 As XElement = ( _  
    From el In co...<Customer> _  
    Where el.@CustomerID = co.<Root>.<Orders>.<Order>. _  
        ToList()(11).<CustomerID>(0).Value _  
    Select el).First()  
  
' An alternate way to write the query that avoids creation  
' of a System.Collections.Generic.List:  
Dim customer2 As XElement = ( _  
    From el In co...<Customer> _  
    Where el.@CustomerID = co.<Root>.<Orders>.<Order>. _  
        Skip(11).First().<CustomerID>(0).Value _  
    Select el).First()  
  
' XPath expression  
Dim customer3 As XElement = co.XPathSelectElement _  
    (".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]")  
  
If customer1 Is customer2 And customer1 Is customer3 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(customer1)  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```console
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
  
## <a name="see-also"></a>Siehe auch

- [LINQ to XML für XPath-Benutzer (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
