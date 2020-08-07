---
title: 'Vorgehensweise: Suchen nach einer Union von zwei Speicherorten (XPath-LINQ to XML) (C#)'
description: Erfahren Sie, wie Sie mithilfe eines XPath-Ausdrucks nach einer Union aus zwei XPath-Speicherpfaden suchen. Hier finden Sie ein Codebeispiel, das eine XML-Beispieldatei verwendet.
ms.date: 07/20/2015
ms.assetid: 069622d3-2b58-4919-8903-710a564c0788
ms.openlocfilehash: 65b20fe25a0990fd82ce3bd08c3433499e728512
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303321"
---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-c"></a><span data-ttu-id="b9d59-104">Vorgehensweise: Suchen nach einer Union von zwei Speicherorten (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b9d59-104">How to find a union of two location paths (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="b9d59-105">Mit XPath können Sie nach der Union der Ergebnisse zweier XPath-Speicherortpfade suchen.</span><span class="sxs-lookup"><span data-stu-id="b9d59-105">XPath allows you to find the union of the results of two XPath location paths.</span></span>  
  
 <span data-ttu-id="b9d59-106">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="b9d59-106">The XPath expression is:</span></span>  
  
 `//Category|//Price`  
  
 <span data-ttu-id="b9d59-107">Die gleichen Ergebnisse können Sie mit dem <xref:System.Linq.Enumerable.Concat%2A>-Standardabfrageoperator erzielen.</span><span class="sxs-lookup"><span data-stu-id="b9d59-107">You can achieve the same results by using the <xref:System.Linq.Enumerable.Concat%2A> standard query operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9d59-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9d59-108">Example</span></span>  
 <span data-ttu-id="b9d59-109">Dieses Beispiel sucht nach allen `Category`-Elementen und nach allen `Price`-Elementen und verkettet diese in einer einzelnen Auflistung.</span><span class="sxs-lookup"><span data-stu-id="b9d59-109">This example finds all of the `Category` elements and all of the `Price` elements, and concatenates them into a single collection.</span></span> <span data-ttu-id="b9d59-110">Beachten Sie, dass die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrage zum Sortieren der Ergebnisse <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> aufruft.</span><span class="sxs-lookup"><span data-stu-id="b9d59-110">Note that the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query calls <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> to order the results.</span></span> <span data-ttu-id="b9d59-111">Die Reihenfolge der Ergebnisse der XPath-Ausdrucksauswertung entspricht der Reihenfolge im Dokument.</span><span class="sxs-lookup"><span data-stu-id="b9d59-111">The results of the XPath expression evaluation are also in document order.</span></span>  
  
 <span data-ttu-id="b9d59-112">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b9d59-112">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="b9d59-113">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="b9d59-113">This example produces the following output:</span></span>  
  
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
  