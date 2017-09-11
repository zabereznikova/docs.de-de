---
title: 'Vorgehensweise: Suchen einer Liste untergeordneter Elemente (XPath-LINQ to XML) (C#)'
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
ms.assetid: 7c589dd8-f680-4cdb-9d6a-78d57e2555e8
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fa9a222f7fc32f278968461b30ba7ed8c7f40f9a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-a-list-of-child-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="09363-102">Vorgehensweise: Suchen einer Liste untergeordneter Elemente (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="09363-102">How to: Find a List of Child Elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="09363-103">In diesem Thema wird die Achse der untergeordneten XPath-Elemente mit der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A>-Achse verglichen.</span><span class="sxs-lookup"><span data-stu-id="09363-103">This topic compares the XPath child elements axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>  
  
 <span data-ttu-id="09363-104">Der XPath-Ausdruck lautet: `./*`</span><span class="sxs-lookup"><span data-stu-id="09363-104">The XPath expression is: `./*`</span></span>  
  
## <a name="example"></a><span data-ttu-id="09363-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="09363-105">Example</span></span>  
 <span data-ttu-id="09363-106">In diesem Beispiel wird nach allen untergeordneten Elementen des `Address`-Elements gesucht.</span><span class="sxs-lookup"><span data-stu-id="09363-106">This example finds all of the child elements of the `Address` element.</span></span>  
  
 <span data-ttu-id="09363-107">Dieses Beispiel verwendet das folgende XML-Dokument: [Beispiel-XML-Datei: Mehrere Bestellungen (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="09363-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument cpo = XDocument.Load("PurchaseOrders.xml");  
XElement po = cpo.Root.Element("PurchaseOrder").Element("Address");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = po.Elements();  
  
// XPath expression  
IEnumerable<XElement> list2 = po.XPathSelectElements("./*");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="09363-108">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="09363-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Name>Ellen Adams</Name>  
<Street>123 Maple Street</Street>  
<City>Mill Valley</City>  
<State>CA</State>  
<Zip>10999</Zip>  
<Country>USA</Country>  
```  
  
## <a name="see-also"></a><span data-ttu-id="09363-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09363-109">See Also</span></span>  
 [<span data-ttu-id="09363-110">LINQ to XML für XPath-Benutzer (C#)</span><span class="sxs-lookup"><span data-stu-id="09363-110">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

