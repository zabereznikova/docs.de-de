---
title: 'Vorgehensweise: Suchen einer Liste von untergeordneten Elementen (XPath-LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 2868abfd-9f7b-412a-9cb5-f643f0fed146
ms.openlocfilehash: 9b852e2a1129dfc9c54357b6c20769e16a992d80
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2018
ms.locfileid: "39296168"
---
# <a name="how-to-find-a-list-of-child-elements-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="46de4-102">Vorgehensweise: Suchen einer Liste von untergeordneten Elementen (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46de4-102">How to: Find a List of Child Elements (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="46de4-103">In diesem Thema wird die Achse der untergeordneten XPath-Elemente mit der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A>-Achse verglichen.</span><span class="sxs-lookup"><span data-stu-id="46de4-103">This topic compares the XPath child elements axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>  
  
 <span data-ttu-id="46de4-104">Der XPath-Ausdruck lautet: `./*`</span><span class="sxs-lookup"><span data-stu-id="46de4-104">The XPath expression is: `./*`</span></span>  
  
## <a name="example"></a><span data-ttu-id="46de4-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46de4-105">Example</span></span>  
 <span data-ttu-id="46de4-106">In diesem Beispiel wird nach allen untergeordneten Elementen des `Address`-Elements gesucht.</span><span class="sxs-lookup"><span data-stu-id="46de4-106">This example finds all of the child elements of the `Address` element.</span></span>  
  
 <span data-ttu-id="46de4-107">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Mehrere Bestellungen (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="46de4-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim cpo As XDocument = XDocument.Load("PurchaseOrders.xml")  
Dim po As XElement = cpo.Root.<PurchaseOrder>.<Address>.FirstOrDefault  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = po.Elements()  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = po.XPathSelectElements("./*")  
  
If (list1.Count() = list2.Count()) AndAlso _  
    (list1.Intersect(list2).Count() = list1.Count()) Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="46de4-108">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="46de4-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Name>Ellen Adams</Name>  
<Street>123 Maple Street</Street>  
<City>Mill Valley</City>  
<State>CA</State>  
<Zip>10999</Zip>  
<Country>USA</Country>  
```  
  
## <a name="see-also"></a><span data-ttu-id="46de4-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46de4-109">See Also</span></span>  
 [<span data-ttu-id="46de4-110">LINQ to XML für XPath-Benutzer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46de4-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
