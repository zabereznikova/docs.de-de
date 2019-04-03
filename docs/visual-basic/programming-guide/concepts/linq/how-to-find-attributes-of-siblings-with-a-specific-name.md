---
title: 'Vorgehensweise: Suchen nach Attributen von nebengeordneten Elementen mit einem bestimmten Namen (XPath-LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 83b3ddca-830a-4b71-9756-9e4bdf907302
ms.openlocfilehash: 07fb5647950c450d08ab3235ac8cb396eff15305
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839053"
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="ee848-102">Vorgehensweise: Suchen nach Attributen von nebengeordneten Elementen mit einem bestimmten Namen (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee848-102">How to: Find Attributes of Siblings with a Specific Name (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="ee848-103">In diesem Thema wird gezeigt, wie Sie alle Attribute der nebengeordneten Knoten des Kontextknotens ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="ee848-103">This topic shows how to find all attributes of the siblings of the context node.</span></span> <span data-ttu-id="ee848-104">In der Auflistung werden nur Attribute mit einem bestimmten Namen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ee848-104">Only attributes with a specific name are returned in the collection.</span></span>  
  
 <span data-ttu-id="ee848-105">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="ee848-105">The XPath expression is:</span></span>  
  
 `../Book/@id`  
  
## <a name="example"></a><span data-ttu-id="ee848-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ee848-106">Example</span></span>  
 <span data-ttu-id="ee848-107">Dieses Beispiel sucht zuerst nach einem `Book`-Element, als Nächstes nach allen nebengeordneten Elementen mit dem Namen `Book` und zum Schluss nach allen Attributen mit dem Namen `id`.</span><span class="sxs-lookup"><span data-stu-id="ee848-107">This example first finds a `Book` element, and then finds all sibling elements named `Book`, and then finds all attributes named `id`.</span></span> <span data-ttu-id="ee848-108">Das Ergebnis ist eine Auflistung von Attributen.</span><span class="sxs-lookup"><span data-stu-id="ee848-108">The result is a collection of attributes.</span></span>  
  
 <span data-ttu-id="ee848-109">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Bücher (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="ee848-109">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```vb  
Dim books as XDocument = XDocument.Load("Books.xml")  
Dim book As XElement = books.Root.<Book>(0)  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XAttribute) = _  
    From el In book.Parent.<Book> _  
    Select el.Attribute("id")  
  
' XPath expression  
Dim list2 As IEnumerable(Of XAttribute) = DirectCast(book. _  
    XPathEvaluate("../Book/@id"), IEnumerable).Cast(Of XAttribute)()  
  
If list1.Count() = list2.Count() And _  
        (list1.Intersect(list2)).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
  
For Each el As XAttribute In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="ee848-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="ee848-110">This example produces the following output:</span></span>  
  
```  
Results are identical  
id="bk101"  
id="bk102"  
```  
  
## <a name="see-also"></a><span data-ttu-id="ee848-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee848-111">See also</span></span>

- [<span data-ttu-id="ee848-112">LINQ to XML für XPath-Benutzer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee848-112">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
