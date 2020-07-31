---
title: 'Vorgehensweise: Suchen nach dem unmittelbar vorhergehenden nebengeordneten Knoten (XPath-LINQ to XML) (C#)'
description: In diesem C#-Beispiel wird verglichen, wie XPath und LINQ to XML das gleichgeordnete Element finden, das einem Knoten unmittelbar vorangestellt ist.
ms.date: 07/20/2015
ms.assetid: 74c06201-0b1b-4b5e-b3ac-0092980614e6
ms.openlocfilehash: eaee7f1205ce0d0b2a9c2c41d96ba532573a1384
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105205"
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-c"></a><span data-ttu-id="0caa4-103">Vorgehensweise: Suchen nach dem unmittelbar vorhergehenden nebengeordneten Knoten (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="0caa4-103">How to find the immediate preceding sibling (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="0caa4-104">Es kann passieren, dass Sie den unmittelbar vorhergehenden nebengeordneten Knoten eines Knotens ermitteln möchten.</span><span class="sxs-lookup"><span data-stu-id="0caa4-104">Sometimes you want to find the immediate preceding sibling to a node.</span></span> <span data-ttu-id="0caa4-105">Aufgrund des semantischen Unterschieds bei Positionsprädikaten für die Achsen vorhergehender nebengeordneter Knoten in XPath im Vergleich zu [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist dies einer der interessanteren Vergleiche.</span><span class="sxs-lookup"><span data-stu-id="0caa4-105">Due to the difference in the semantics of positional predicates for the preceding sibling axes in XPath as opposed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], this is one of the more interesting comparisons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0caa4-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0caa4-106">Example</span></span>  
 <span data-ttu-id="0caa4-107">In diesem Beispiel verwendet die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrage den <xref:System.Linq.Enumerable.Last%2A>-Operator, um nach dem letzten Knoten in der Auflistung zu suchen, der von <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A> zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="0caa4-107">In this example, the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query uses the <xref:System.Linq.Enumerable.Last%2A> operator to find the last node in the collection returned by <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span></span> <span data-ttu-id="0caa4-108">Im Unterschied dazu verwendet der XPath-Ausdruck für die Suche nach dem unmittelbar vorhergehenden Element ein Prädikat mit dem Wert 1.</span><span class="sxs-lookup"><span data-stu-id="0caa4-108">By contrast, the XPath expression uses a predicate with a value of 1 to find the immediately preceding element.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
    @"<Root>  
    <Child1/>  
    <Child2/>  
    <Child3/>  
    <Child4/>  
</Root>");  
XElement child4 = root.Element("Child4");  
  
// LINQ to XML query  
XElement el1 =  
    child4  
    .ElementsBeforeSelf()  
    .Last();  
  
// XPath expression  
XElement el2 =  
    ((IEnumerable)child4  
                 .XPathEvaluate("preceding-sibling::*[1]"))  
                 .Cast<XElement>()  
                 .First();  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1);  
```  
  
 <span data-ttu-id="0caa4-109">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="0caa4-109">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Child3 />  
```  
