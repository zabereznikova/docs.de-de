---
title: 'Vorgehensweise: Suchen nach Elementen mit bestimmten Attributen (XPath-LINQ to XML) (C#)'
description: In diesem C#-Beispiel wird verglichen, wie XPath und LINQ to XML Elemente mit einem bestimmten Attribut finden.
ms.date: 07/20/2015
ms.assetid: daed00dd-923a-43be-8a90-eee406f6f574
ms.openlocfilehash: eb0b5c27fb3993b487c5e8d70c6562c1d0562860
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105261"
---
# <a name="how-to-find-elements-with-a-specific-attribute-xpath-linq-to-xml-c"></a><span data-ttu-id="20136-103">Vorgehensweise: Suchen nach Elementen mit bestimmten Attributen (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="20136-103">How to find elements with a specific attribute (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="20136-104">Es kann passieren, dass Sie alle Elemente ermitteln möchten, die ein bestimmtes Attribut besitzen.</span><span class="sxs-lookup"><span data-stu-id="20136-104">Sometimes you want to find all elements that have a specific attribute.</span></span> <span data-ttu-id="20136-105">Welchen Inhalt das Attribut hat, ist Ihnen dabei egal.</span><span class="sxs-lookup"><span data-stu-id="20136-105">You are not concerned about the contents of the attribute.</span></span> <span data-ttu-id="20136-106">Alleiniges Kriterium für die Auswahl ist dessen Existenz.</span><span class="sxs-lookup"><span data-stu-id="20136-106">Instead, you want to select based on the existence of the attribute.</span></span>  
  
 <span data-ttu-id="20136-107">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="20136-107">The XPath expression is:</span></span>  
  
 `./*[@Select]`  
  
## <a name="example"></a><span data-ttu-id="20136-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="20136-108">Example</span></span>  
 <span data-ttu-id="20136-109">Der folgende Code wählt nur die Elemente aus, die das `Select`-Attribut besitzen:</span><span class="sxs-lookup"><span data-stu-id="20136-109">The following code selects just the elements that have the `Select` attribute.</span></span>  
  
```csharp  
XElement doc = XElement.Parse(  
@"<Root>  
    <Child1>1</Child1>  
    <Child2 Select='true'>2</Child2>  
    <Child3>3</Child3>  
    <Child4 Select='true'>4</Child4>  
    <Child5>5</Child5>  
</Root>");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    from el in doc.Elements()  
    where el.Attribute("Select") != null  
    select el;  
  
// XPath expression  
IEnumerable<XElement> list2 =  
    ((IEnumerable)doc.XPathEvaluate("./*[@Select]")).Cast<XElement>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="20136-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="20136-110">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Child2 Select="true">2</Child2>  
<Child4 Select="true">4</Child4>  
```  
  