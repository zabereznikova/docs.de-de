---
title: 'Vorgehensweise: Suchen nach verwandten Elementen (XPath-LINQ to XML) (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 41b386ee-562d-4841-bd6b-e44a7eb69f26
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3cc73ab69adb66fd1158637a8a3c67008d8e8663
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-related-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="1d4e0-102">Vorgehensweise: Suchen nach verwandten Elementen (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="1d4e0-102">How to: Find Related Elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="1d4e0-103">In diesem Thema wird gezeigt, wie Sie ein Element abrufen können, das auf der Basis eines Attributs ausgewählt wird, auf das vom Wert eines anderen Elements verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1d4e0-103">This topic shows how to get an element selecting on an attribute that is referred to by the value of another element.</span></span>  
  
 <span data-ttu-id="1d4e0-104">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="1d4e0-104">The XPath expression is:</span></span>  
  
 `.//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]`  
  
## <a name="example"></a><span data-ttu-id="1d4e0-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1d4e0-105">Example</span></span>  
 <span data-ttu-id="1d4e0-106">Dieses Beispiel sucht nach dem 12. `Order`-Element und ermittelt anschließend den Kunden für diesen Auftrag.</span><span class="sxs-lookup"><span data-stu-id="1d4e0-106">This example finds the 12th `Order` element, and then finds the customer for that order.</span></span>  
  
 <span data-ttu-id="1d4e0-107">Beachten Sie, dass beim Indizieren von Listen in .Net die Zählung mit 0 (Null) beginnt.</span><span class="sxs-lookup"><span data-stu-id="1d4e0-107">Note that indexing into a list in .Net is 'zero' based.</span></span> <span data-ttu-id="1d4e0-108">Beim Indizieren einer Auflistung von Knoten in einem XPath-Prädikat beginnt die Zählung dagegen mit 1.</span><span class="sxs-lookup"><span data-stu-id="1d4e0-108">Indexing into a collection of nodes in an XPath predicate is 'one' based.</span></span> <span data-ttu-id="1d4e0-109">Dieser Unterschied wird im folgenden Beispiel verdeutlicht.</span><span class="sxs-lookup"><span data-stu-id="1d4e0-109">This example reflects this difference.</span></span>  
  
 <span data-ttu-id="1d4e0-110">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="1d4e0-110">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
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
  
 <span data-ttu-id="1d4e0-111">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1d4e0-111">This example produces the following output:</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="1d4e0-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d4e0-112">See Also</span></span>  
 [<span data-ttu-id="1d4e0-113">LINQ to XML für XPath-Benutzer (C#)</span><span class="sxs-lookup"><span data-stu-id="1d4e0-113">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

