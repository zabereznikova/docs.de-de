---
title: 'Vorgehensweise: Suchen von Descendant-Elementen (XPath-LINQ to XML) (C#)'
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
ms.assetid: b318da39-bb8b-4c56-a019-e13b12b01831
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 27b9b08fea2cfed476f4caf10b65b2b7e5eb74c5
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="1db8c-102">Vorgehensweise: Suchen von Descendant-Elementen (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="1db8c-102">How to: Find Descendant Elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="1db8c-103">In diesem Thema wird gezeigt, wie Sie die Nachfolgerelemente mit einem bestimmten Namen ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="1db8c-103">This topic shows how to get the descendant elements with a particular name.</span></span>  
  
 <span data-ttu-id="1db8c-104">Der XPath-Ausdruck lautet `//Name`.</span><span class="sxs-lookup"><span data-stu-id="1db8c-104">The XPath expression is `//Name`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1db8c-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1db8c-105">Example</span></span>  
 <span data-ttu-id="1db8c-106">Dieses Beispiel sucht nach allen Nachfolgern mit dem Namen `Name`.</span><span class="sxs-lookup"><span data-stu-id="1db8c-106">This example finds all descendants named `Name`.</span></span>  
  
 <span data-ttu-id="1db8c-107">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Mehrere Bestellungen (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="1db8c-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="1db8c-108">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1db8c-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1db8c-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1db8c-109">See Also</span></span>  
 [<span data-ttu-id="1db8c-110">LINQ to XML für XPath-Benutzer (C#)</span><span class="sxs-lookup"><span data-stu-id="1db8c-110">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

