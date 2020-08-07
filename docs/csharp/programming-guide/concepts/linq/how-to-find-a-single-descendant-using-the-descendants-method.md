---
title: 'Vorgehensweise: Suchen eines einzelnen Nachfolgers mit der Descendants-Methode (C#)'
description: Erfahren Sie, wie Sie mithilfe der Descendants-Achsenmethode nach einem einzelnen Nachfolger suchen. Diese Methode ist nützlich, um einen bestimmten Nachfolger mit einem bestimmten Namen zu finden.
ms.date: 07/20/2015
ms.assetid: 6f735be9-0293-4680-8007-ca9d96bfebed
ms.openlocfilehash: 993e2b45f93509cf526d0c8c5de488b50de3efef
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303334"
---
# <a name="how-to-find-a-single-descendant-using-the-descendants-method-c"></a><span data-ttu-id="a689b-104">Vorgehensweise: Suchen eines einzelnen Nachfolgers mit der Descendants-Methode (C#)</span><span class="sxs-lookup"><span data-stu-id="a689b-104">How to find a single descendant using the descendants method (C#)</span></span>
<span data-ttu-id="a689b-105">Mit der <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achsenmethode können Sie schnell Code zum Suchen nach einem einzelnen eindeutig benannten Element schreiben.</span><span class="sxs-lookup"><span data-stu-id="a689b-105">You can use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis method to quickly write code to find a single uniquely named element.</span></span> <span data-ttu-id="a689b-106">Diese Technik ist besonders nützlich, wenn Sie einen bestimmten Nachfolger mit einem bestimmten Namen ermitteln möchten.</span><span class="sxs-lookup"><span data-stu-id="a689b-106">This technique is especially useful when you want to find a particular descendant with a specific name.</span></span> <span data-ttu-id="a689b-107">Sie könnten den Code zwar so schreiben, dass eine Navigation zum gewünschten Element erfolgt, es ist aber häufig schneller und einfacher, den Code mit der <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achse zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="a689b-107">You could write the code to navigate to the desired element, but it is often faster and easier to write the code using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a689b-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a689b-108">Example</span></span>  
 <span data-ttu-id="a689b-109">In diesem Beispiel wird der <xref:System.Linq.Enumerable.First%2A>-Standardabfrageoperator verwendet.</span><span class="sxs-lookup"><span data-stu-id="a689b-109">This example uses the <xref:System.Linq.Enumerable.First%2A> standard query operator.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
  <Child1>  
    <GrandChild1>GC1 Value</GrandChild1>  
  </Child1>  
  <Child2>  
    <GrandChild2>GC2 Value</GrandChild2>  
  </Child2>  
  <Child3>  
    <GrandChild3>GC3 Value</GrandChild3>  
  </Child3>  
  <Child4>  
    <GrandChild4>GC4 Value</GrandChild4>  
  </Child4>  
</Root>");  
string grandChild3 = (string)  
    (from el in root.Descendants("GrandChild3")  
    select el).First();  
Console.WriteLine(grandChild3);  
```  
  
 <span data-ttu-id="a689b-110">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a689b-110">This code produces the following output:</span></span>  
  
```output  
GC3 Value  
```  
  
## <a name="example"></a><span data-ttu-id="a689b-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a689b-111">Example</span></span>  
 <span data-ttu-id="a689b-112">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a689b-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="a689b-113">Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a689b-113">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
  <aw:Child1>  
    <aw:GrandChild1>GC1 Value</aw:GrandChild1>  
  </aw:Child1>  
  <aw:Child2>  
    <aw:GrandChild2>GC2 Value</aw:GrandChild2>  
  </aw:Child2>  
  <aw:Child3>  
    <aw:GrandChild3>GC3 Value</aw:GrandChild3>  
  </aw:Child3>  
  <aw:Child4>  
    <aw:GrandChild4>GC4 Value</aw:GrandChild4>  
  </aw:Child4>  
</aw:Root>");  
XNamespace aw = "http://www.adventure-works.com";  
string grandChild3 = (string)  
    (from el in root.Descendants(aw + "GrandChild3")  
     select el).First();  
Console.WriteLine(grandChild3);  
```  
  
 <span data-ttu-id="a689b-114">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a689b-114">This code produces the following output:</span></span>  
  
```output  
GC3 Value  
```  
