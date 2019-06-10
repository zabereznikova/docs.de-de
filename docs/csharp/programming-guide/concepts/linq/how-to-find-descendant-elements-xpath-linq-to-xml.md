---
title: 'Vorgehensweise: Suchen von Nachfolgerelementen (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: b318da39-bb8b-4c56-a019-e13b12b01831
ms.openlocfilehash: 99f5f552935d6169537ccfbadff2a21396828e47
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486772"
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="d7825-102">Vorgehensweise: Suchen von Nachfolgerelementen (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="d7825-102">How to: Find Descendant Elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="d7825-103">In diesem Thema wird gezeigt, wie Sie die Nachfolgerelemente mit einem bestimmten Namen ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="d7825-103">This topic shows how to get the descendant elements with a particular name.</span></span>  
  
 <span data-ttu-id="d7825-104">Der XPath-Ausdruck lautet `//Name`.</span><span class="sxs-lookup"><span data-stu-id="d7825-104">The XPath expression is `//Name`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7825-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7825-105">Example</span></span>  
 <span data-ttu-id="d7825-106">Dieses Beispiel sucht nach allen Nachfolgern mit dem Namen `Name`.</span><span class="sxs-lookup"><span data-stu-id="d7825-106">This example finds all descendants named `Name`.</span></span>  
  
 <span data-ttu-id="d7825-107">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Mehrere Bestellungen (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="d7825-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = po.Root.Descendants("Name");  
  
// XPath expression  
IEnumerable<XElement> list2 = po.XPathSelectElements("//Name");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="d7825-108">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d7825-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
