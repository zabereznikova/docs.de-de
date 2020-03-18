---
title: 'Vorgehensweise: Suchen nach einer Union von zwei Speicherorten (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 069622d3-2b58-4919-8903-710a564c0788
ms.openlocfilehash: 17a3310f367cb68b3b80b1a3f30af40428f6d2c7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141210"
---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-c"></a>Vorgehensweise: Suchen nach einer Union von zwei Speicherorten (XPath-LINQ to XML) (C#)
Mit XPath können Sie nach der Union der Ergebnisse zweier XPath-Speicherortpfade suchen.  
  
 Der XPath-Ausdruck lautet:  
  
 `//Category|//Price`  
  
 Die gleichen Ergebnisse können Sie mit dem <xref:System.Linq.Enumerable.Concat%2A>-Standardabfrageoperator erzielen.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel sucht nach allen `Category`-Elementen und nach allen `Price`-Elementen und verkettet diese in einer einzelnen Auflistung. Beachten Sie, dass die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrage zum Sortieren der Ergebnisse <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> aufruft. Die Reihenfolge der Ergebnisse der XPath-Ausdrucksauswertung entspricht der Reihenfolge im Dokument.  
  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).  
  
```csharp  
XDocument data = XDocument.Load("Data.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    data  
    .Descendants("Category")  
    .Concat(  
        data  
        .Descendants("Price")  
    )  
    .InDocumentOrder();  
  
// XPath expression  
IEnumerable<XElement> list2 = data.XPathSelectElements("//Category|//Price");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```output  
Results are identical  
<Category>A</Category>  
<Price>24.50</Price>  
<Category>B</Category>  
<Price>89.99</Price>  
<Category>A</Category>  
<Price>4.95</Price>  
<Category>A</Category>  
<Price>66.00</Price>  
<Category>B</Category>  
<Price>.99</Price>  
<Category>A</Category>  
<Price>29.00</Price>  
<Category>B</Category>  
<Price>6.99</Price>  
```  
  