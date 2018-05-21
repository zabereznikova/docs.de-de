---
title: 'Vorgehensweise: Suchen nach Attributen von nebengeordneten Elementen mit einem bestimmten Namen (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: c3133d64-523f-422d-8838-73d36b945ca0
ms.openlocfilehash: 0e87208e033c4960843a82c9abd2b4ebd4f74d3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-c"></a><span data-ttu-id="34c5f-102">Vorgehensweise: Suchen nach Attributen von nebengeordneten Elementen mit einem bestimmten Namen (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="34c5f-102">How to: Find Attributes of Siblings with a Specific Name (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="34c5f-103">In diesem Thema wird gezeigt, wie Sie alle Attribute der nebengeordneten Knoten des Kontextknotens ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="34c5f-103">This topic shows how to find all attributes of the siblings of the context node.</span></span> <span data-ttu-id="34c5f-104">In der Auflistung werden nur Attribute mit einem bestimmten Namen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="34c5f-104">Only attributes with a specific name are returned in the collection.</span></span>  
  
 <span data-ttu-id="34c5f-105">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="34c5f-105">The XPath expression is:</span></span>  
  
 `../Book/@id`  
  
## <a name="example"></a><span data-ttu-id="34c5f-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34c5f-106">Example</span></span>  
 <span data-ttu-id="34c5f-107">Dieses Beispiel sucht zuerst nach einem `Book`-Element, als Nächstes nach allen nebengeordneten Elementen mit dem Namen `Book` und zum Schluss nach allen Attributen mit dem Namen `id`.</span><span class="sxs-lookup"><span data-stu-id="34c5f-107">This example first finds a `Book` element, and then finds all sibling elements named `Book`, and then finds all attributes named `id`.</span></span> <span data-ttu-id="34c5f-108">Das Ergebnis ist eine Auflistung von Attributen.</span><span class="sxs-lookup"><span data-stu-id="34c5f-108">The result is a collection of attributes.</span></span>  
  
 <span data-ttu-id="34c5f-109">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Bücher (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="34c5f-109">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement book =   
    books  
    .Root  
    .Element("Book");  
  
// LINQ to XML query  
IEnumerable<XAttribute> list1 =  
    from el in book.Parent.Elements("Book")  
    select el.Attribute("id");  
  
// XPath expression  
IEnumerable<XAttribute> list2 =  
  ((IEnumerable)book.XPathEvaluate("../Book/@id")).Cast<XAttribute>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XAttribute el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="34c5f-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="34c5f-110">This example produces the following output:</span></span>  
  
```  
Results are identical  
id="bk101"  
id="bk102"  
```  
  
## <a name="see-also"></a><span data-ttu-id="34c5f-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34c5f-111">See Also</span></span>  
 [<span data-ttu-id="34c5f-112">LINQ to XML für XPath-Benutzer (C#)</span><span class="sxs-lookup"><span data-stu-id="34c5f-112">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
