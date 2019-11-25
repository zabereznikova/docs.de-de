---
title: 'Gewusst wie: Suchen nach einer Union von zwei Speicherorten (XPath-LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: c82c09b4-cb0a-47ec-8cc3-a124144c2788
ms.openlocfilehash: db9ba3f66bfa8643738203ec05a106bab4193fda
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352985"
---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-visual-basic"></a>How to: Find a Union of Two Location Paths (XPath-LINQ to XML) (Visual Basic)
Mit XPath können Sie nach der Union der Ergebnisse zweier XPath-Speicherortpfade suchen.  
  
 Der XPath-Ausdruck lautet:  
  
 `//Category|//Price`  
  
 Die gleichen Ergebnisse können Sie mit dem <xref:System.Linq.Enumerable.Concat%2A>-Standardabfrageoperator erzielen.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel sucht nach allen `Category`-Elementen und nach allen `Price`-Elementen und verkettet diese in einer einzelnen Auflistung. Beachten Sie, dass die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrage zum Sortieren der Ergebnisse <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> aufruft. Die Reihenfolge der Ergebnisse der XPath-Ausdrucksauswertung entspricht der Reihenfolge im Dokument.  
  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).  
  
```vb  
Dim data As XDocument = XDocument.Load("Data.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    data...<Category>.Concat(data...<Price>).InDocumentOrder()  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = _  
    data.XPathSelectElements("//Category|//Price")  
  
If list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```console
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
  
## <a name="see-also"></a>Siehe auch

- [LINQ to XML for XPath Users (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
