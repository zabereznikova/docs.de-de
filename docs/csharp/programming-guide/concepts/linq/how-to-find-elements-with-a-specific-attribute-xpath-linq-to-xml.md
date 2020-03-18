---
title: 'Vorgehensweise: Suchen nach Elementen mit bestimmten Attributen (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: daed00dd-923a-43be-8a90-eee406f6f574
ms.openlocfilehash: e79cad3ad6fb0bf88e388b552f8e39327acfb4ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141040"
---
# <a name="how-to-find-elements-with-a-specific-attribute-xpath-linq-to-xml-c"></a><span data-ttu-id="c1cf0-102">Vorgehensweise: Suchen nach Elementen mit bestimmten Attributen (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="c1cf0-102">How to find elements with a specific attribute (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="c1cf0-103">Es kann passieren, dass Sie alle Elemente ermitteln möchten, die ein bestimmtes Attribut besitzen.</span><span class="sxs-lookup"><span data-stu-id="c1cf0-103">Sometimes you want to find all elements that have a specific attribute.</span></span> <span data-ttu-id="c1cf0-104">Welchen Inhalt das Attribut hat, ist Ihnen dabei egal.</span><span class="sxs-lookup"><span data-stu-id="c1cf0-104">You are not concerned about the contents of the attribute.</span></span> <span data-ttu-id="c1cf0-105">Alleiniges Kriterium für die Auswahl ist dessen Existenz.</span><span class="sxs-lookup"><span data-stu-id="c1cf0-105">Instead, you want to select based on the existence of the attribute.</span></span>  
  
 <span data-ttu-id="c1cf0-106">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="c1cf0-106">The XPath expression is:</span></span>  
  
 `./*[@Select]`  
  
## <a name="example"></a><span data-ttu-id="c1cf0-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c1cf0-107">Example</span></span>  
 <span data-ttu-id="c1cf0-108">Der folgende Code wählt nur die Elemente aus, die das `Select`-Attribut besitzen:</span><span class="sxs-lookup"><span data-stu-id="c1cf0-108">The following code selects just the elements that have the `Select` attribute.</span></span>  
  
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
  
 <span data-ttu-id="c1cf0-109">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c1cf0-109">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Child2 Select="true">2</Child2>  
<Child4 Select="true">4</Child4>  
```  
  