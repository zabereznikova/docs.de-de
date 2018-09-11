---
title: 'Vorgehensweise: Suchen des Stammelements (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 4fd824e0-4d39-429b-b092-f6a5c046ee6c
ms.openlocfilehash: a0197a34f2e9d1b42a71d3c8cb1a4281ba495c4f
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44261086"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-c"></a><span data-ttu-id="40f10-102">Vorgehensweise: Suchen des Stammelements (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="40f10-102">How to: Find the Root Element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="40f10-103">In diesem Thema wird gezeigt, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] das Stammelement ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="40f10-103">This topic shows how to get the root element with XPath and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="40f10-104">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="40f10-104">The XPath expression is:</span></span>  
  
 `/PurchaseOrders`  
  
## <a name="example"></a><span data-ttu-id="40f10-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="40f10-105">Example</span></span>  
 <span data-ttu-id="40f10-106">Dieses Beispiel sucht nach dem Stammelement.</span><span class="sxs-lookup"><span data-stu-id="40f10-106">This example finds the root element.</span></span>  
  
 <span data-ttu-id="40f10-107">Dieses Beispiel verwendet das folgende XML-Dokument: [Beispiel-XML-Datei: Mehrere Bestellungen (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="40f10-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
XElement el1 = po.Root;  
  
// XPath expression  
XElement el2 = po.XPathSelectElement("/PurchaseOrders");  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1.Name);  
```  
  
 <span data-ttu-id="40f10-108">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="40f10-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
PurchaseOrders  
```  
  
## <a name="see-also"></a><span data-ttu-id="40f10-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40f10-109">See Also</span></span>

- [<span data-ttu-id="40f10-110">LINQ to XML für XPath-Benutzer (C#)</span><span class="sxs-lookup"><span data-stu-id="40f10-110">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
