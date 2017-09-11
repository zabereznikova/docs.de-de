---
title: 'Gewusst wie: Suchen nach einer Union von zwei Speicherorten (XPath-LINQ to XML) (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: c82c09b4-cb0a-47ec-8cc3-a124144c2788
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 63c3399a60f8c26e39ef9d575a569b85bd7c5f68
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="bd8c2-102">Gewusst wie: Suchen nach einer Union von zwei Speicherorten (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd8c2-102">How to: Find a Union of Two Location Paths (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="bd8c2-103">Mit XPath können Sie nach der Union der Ergebnisse zweier XPath-Speicherortpfade suchen.</span><span class="sxs-lookup"><span data-stu-id="bd8c2-103">XPath allows you to find the union of the results of two XPath location paths.</span></span>  
  
 <span data-ttu-id="bd8c2-104">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="bd8c2-104">The XPath expression is:</span></span>  
  
 `//Category|//Price`  
  
 <span data-ttu-id="bd8c2-105">Sie können die gleichen Ergebnisse erzielen, indem Sie mit der <xref:System.Linq.Enumerable.Concat%2A>Standardabfrageoperator.</xref:System.Linq.Enumerable.Concat%2A></span><span class="sxs-lookup"><span data-stu-id="bd8c2-105">You can achieve the same results by using the <xref:System.Linq.Enumerable.Concat%2A> standard query operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd8c2-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd8c2-106">Example</span></span>  
 <span data-ttu-id="bd8c2-107">Dieses Beispiel sucht nach allen `Category`-Elementen und nach allen `Price`-Elementen und verkettet diese in einer einzelnen Auflistung.</span><span class="sxs-lookup"><span data-stu-id="bd8c2-107">This example finds all of the `Category` elements and all of the `Price` elements, and concatenates them into a single collection.</span></span> <span data-ttu-id="bd8c2-108">Beachten Sie, dass die [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Abfrage ruft <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A>zum Sortieren der Ergebnisse.</xref:System.Xml.Linq.Extensions.InDocumentOrder%2A></span><span class="sxs-lookup"><span data-stu-id="bd8c2-108">Note that the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query calls <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> to order the results.</span></span> <span data-ttu-id="bd8c2-109">Die Reihenfolge der Ergebnisse der XPath-Ausdrucksauswertung entspricht der Reihenfolge im Dokument.</span><span class="sxs-lookup"><span data-stu-id="bd8c2-109">The results of the XPath expression evaluation are also in document order.</span></span>  
  
 <span data-ttu-id="bd8c2-110">Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: numerische Daten (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="bd8c2-110">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="bd8c2-111">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="bd8c2-111">This example produces the following output:</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="bd8c2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd8c2-112">See Also</span></span>  
 [<span data-ttu-id="bd8c2-113">LINQ to XML für XPath-Benutzer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd8c2-113">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

