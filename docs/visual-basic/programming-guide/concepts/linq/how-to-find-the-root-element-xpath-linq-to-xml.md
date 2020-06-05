---
title: 'Vorgehensweise: Suchen des Stammelements (XPath-LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 72c3aed5-9522-4454-a876-2070aad13f2e
ms.openlocfilehash: d1a507f97954c62672689bae719f251fed9a298b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364512"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="91969-102">Gewusst wie: Suchen des Stamm Elements (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91969-102">How to: Find the Root Element (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="91969-103">In diesem Thema wird gezeigt, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] das Stammelement ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="91969-103">This topic shows how to get the root element with XPath and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="91969-104">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="91969-104">The XPath expression is:</span></span>  
  
 `/PurchaseOrders`  
  
## <a name="example"></a><span data-ttu-id="91969-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91969-105">Example</span></span>  
 <span data-ttu-id="91969-106">Dieses Beispiel sucht nach dem Stammelement.</span><span class="sxs-lookup"><span data-stu-id="91969-106">This example finds the root element.</span></span>  
  
 <span data-ttu-id="91969-107">Dieses Beispiel verwendet das folgende XML-Dokument: [Beispiel-XML-Datei: mehrfache Bestellung (LINQ to XML)](sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="91969-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XDocument = XDocument.Load("PurchaseOrders.xml")  
  
' LINQ to XML query  
Dim el1 As XElement = po.Root  
  
' XPath expression  
Dim el2 As XElement = po.XPathSelectElement("/PurchaseOrders")  
  
If el1 Is el2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(el1.Name)  
```  
  
 <span data-ttu-id="91969-108">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="91969-108">This example produces the following output:</span></span>  
  
```console  
Results are identical  
PurchaseOrders  
```  
  
## <a name="see-also"></a><span data-ttu-id="91969-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91969-109">See also</span></span>

- [<span data-ttu-id="91969-110">LINQ to XML für XPath-Benutzer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91969-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](linq-to-xml-for-xpath-users.md)
