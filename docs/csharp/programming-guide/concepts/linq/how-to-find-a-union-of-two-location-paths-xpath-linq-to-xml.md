---
title: 'Vorgehensweise: Suchen nach einer Union von zwei Speicherorten (XPath-LINQ to XML) (C#)'
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
ms.assetid: 069622d3-2b58-4919-8903-710a564c0788
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b15991b6a97c19cd038114649bcef90f53ea5ace
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-c"></a><span data-ttu-id="06148-102">Vorgehensweise: Suchen nach einer Union von zwei Speicherorten (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="06148-102">How to: Find a Union of Two Location Paths (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="06148-103">Mit XPath können Sie nach der Union der Ergebnisse zweier XPath-Speicherortpfade suchen.</span><span class="sxs-lookup"><span data-stu-id="06148-103">XPath allows you to find the union of the results of two XPath location paths.</span></span>  
  
 <span data-ttu-id="06148-104">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="06148-104">The XPath expression is:</span></span>  
  
 `//Category|//Price`  
  
 <span data-ttu-id="06148-105">Die gleichen Ergebnisse können Sie mit dem <xref:System.Linq.Enumerable.Concat%2A>-Standardabfrageoperator erzielen.</span><span class="sxs-lookup"><span data-stu-id="06148-105">You can achieve the same results by using the <xref:System.Linq.Enumerable.Concat%2A> standard query operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06148-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06148-106">Example</span></span>  
 <span data-ttu-id="06148-107">Dieses Beispiel sucht nach allen `Category`-Elementen und nach allen `Price`-Elementen und verkettet diese in einer einzelnen Auflistung.</span><span class="sxs-lookup"><span data-stu-id="06148-107">This example finds all of the `Category` elements and all of the `Price` elements, and concatenates them into a single collection.</span></span> <span data-ttu-id="06148-108">Beachten Sie, dass die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrage zum Sortieren der Ergebnisse <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> aufruft.</span><span class="sxs-lookup"><span data-stu-id="06148-108">Note that the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query calls <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> to order the results.</span></span> <span data-ttu-id="06148-109">Die Reihenfolge der Ergebnisse der XPath-Ausdrucksauswertung entspricht der Reihenfolge im Dokument.</span><span class="sxs-lookup"><span data-stu-id="06148-109">The results of the XPath expression evaluation are also in document order.</span></span>  
  
 <span data-ttu-id="06148-110">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="06148-110">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="06148-111">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="06148-111">This example produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="06148-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06148-112">See Also</span></span>  
 [<span data-ttu-id="06148-113">LINQ to XML für XPath-Benutzer (C#)</span><span class="sxs-lookup"><span data-stu-id="06148-113">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

