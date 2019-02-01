---
title: 'Vorgehensweise: Suchen eines einzelnen Nachfolgers mit der Descendants-Methode (C#)'
ms.date: 07/20/2015
ms.assetid: 6f735be9-0293-4680-8007-ca9d96bfebed
ms.openlocfilehash: a13a4aef6a3d22d2b7c3adb8e37996de08978b6e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690526"
---
# <a name="how-to-find-a-single-descendant-using-the-descendants-method-c"></a><span data-ttu-id="75058-102">Vorgehensweise: Suchen eines einzelnen Nachfolgers mit der Descendants-Methode (C#)</span><span class="sxs-lookup"><span data-stu-id="75058-102">How to: Find a Single Descendant Using the Descendants Method (C#)</span></span>
<span data-ttu-id="75058-103">Mit der <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achsenmethode können Sie schnell Code zum Suchen nach einem einzelnen eindeutig benannten Element schreiben.</span><span class="sxs-lookup"><span data-stu-id="75058-103">You can use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis method to quickly write code to find a single uniquely named element.</span></span> <span data-ttu-id="75058-104">Diese Technik ist besonders nützlich, wenn Sie einen bestimmten Nachfolger mit einem bestimmten Namen ermitteln möchten.</span><span class="sxs-lookup"><span data-stu-id="75058-104">This technique is especially useful when you want to find a particular descendant with a specific name.</span></span> <span data-ttu-id="75058-105">Sie könnten den Code zwar so schreiben, dass eine Navigation zum gewünschten Element erfolgt, es ist aber häufig schneller und einfacher, den Code mit der <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achse zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="75058-105">You could write the code to navigate to the desired element, but it is often faster and easier to write the code using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75058-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="75058-106">Example</span></span>  
 <span data-ttu-id="75058-107">In diesem Beispiel wird der <xref:System.Linq.Enumerable.First%2A>-Standardabfrageoperator verwendet.</span><span class="sxs-lookup"><span data-stu-id="75058-107">This example uses the <xref:System.Linq.Enumerable.First%2A> standard query operator.</span></span>  
  
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
  
 <span data-ttu-id="75058-108">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="75058-108">This code produces the following output:</span></span>  
  
```  
GC3 Value  
```  
  
## <a name="example"></a><span data-ttu-id="75058-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="75058-109">Example</span></span>  
 <span data-ttu-id="75058-110">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="75058-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="75058-111">Weitere Informationen finden Sie unter [Working with XML Namespaces (C#) (Arbeiten mit XML-Namespaces (C#))](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="75058-111">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
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
  
 <span data-ttu-id="75058-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="75058-112">This code produces the following output:</span></span>  
  
```  
GC3 Value  
```  
  
## <a name="see-also"></a><span data-ttu-id="75058-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75058-113">See also</span></span>

- [<span data-ttu-id="75058-114">Basic Queries (LINQ to XML) (C#) (Standardabfragen (LINQ to XML) (C#))</span><span class="sxs-lookup"><span data-stu-id="75058-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
