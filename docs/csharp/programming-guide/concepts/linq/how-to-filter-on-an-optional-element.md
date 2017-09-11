---
title: 'Vorgehensweise: Filtern nach einem optionalen Element (C#)'
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
ms.assetid: f99e2f93-fca5-403f-8a0c-770761d4905a
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d0d849bb8c6174408810f2d2192faea6db6afd5b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-filter-on-an-optional-element-c"></a><span data-ttu-id="b6e93-102">Vorgehensweise: Filtern nach einem optionalen Element (C#)</span><span class="sxs-lookup"><span data-stu-id="b6e93-102">How to: Filter on an Optional Element (C#)</span></span>
<span data-ttu-id="b6e93-103">Es kann vorkommen, dass Sie nach einem Element filtern möchten, ohne genau zu wissen, ob dieses Element in Ihrem XML-Dokument tatsächlich existiert.</span><span class="sxs-lookup"><span data-stu-id="b6e93-103">Sometimes you want to filter for an element even though you are not sure it exists in your XML document.</span></span> <span data-ttu-id="b6e93-104">Die Suche sollte dann so ausgeführt werden, dass für den Fall, dass das Element das gesuchte untergeordnete Element nicht besitzt, beim Filtern keine Ausnahme wegen eines NULL-Verweises ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="b6e93-104">The search should be executed so that if the particular element does not have the child element, you do not trigger a null reference exception by filtering for it.</span></span> <span data-ttu-id="b6e93-105">Im folgenden Beispiel besitzt das `Child5`-Element kein untergeordnetes `Type`-Element, dennoch wird die Abfrage korrekt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b6e93-105">In the following example, the `Child5` element does not have a `Type` child element, but the query still executes correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6e93-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b6e93-106">Example</span></span>  
 <span data-ttu-id="b6e93-107">Dieses Beispiel verwendet die <xref:System.Xml.Linq.Extensions.Elements%2A>-Erweiterungsmethode:</span><span class="sxs-lookup"><span data-stu-id="b6e93-107">This example uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
  <Child1>  
    <Text>Child One Text</Text>  
    <Type Value=""Yes""/>  
  </Child1>  
  <Child2>  
    <Text>Child Two Text</Text>  
    <Type Value=""Yes""/>  
  </Child2>  
  <Child3>  
    <Text>Child Three Text</Text>  
    <Type Value=""No""/>  
  </Child3>  
  <Child4>  
    <Text>Child Four Text</Text>  
    <Type Value=""Yes""/>  
  </Child4>  
  <Child5>  
    <Text>Child Five Text</Text>  
  </Child5>  
</Root>");  
var cList =  
    from typeElement in root.Elements().Elements("Type")  
    where (string)typeElement.Attribute("Value") == "Yes"  
    select (string)typeElement.Parent.Element("Text");  
foreach(string str in cList)  
    Console.WriteLine(str);  
```  
  
 <span data-ttu-id="b6e93-108">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="b6e93-108">This code produces the following output:</span></span>  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="example"></a><span data-ttu-id="b6e93-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b6e93-109">Example</span></span>  
 <span data-ttu-id="b6e93-110">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b6e93-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="b6e93-111">Weitere Informationen finden Sie unter [Working with XML Namespaces (C#) (Arbeiten mit XML-Namespaces (C#))](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="b6e93-111">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>  
  <Child1>  
    <Text>Child One Text</Text>  
    <Type Value=""Yes""/>  
  </Child1>  
  <Child2>  
    <Text>Child Two Text</Text>  
    <Type Value=""Yes""/>  
  </Child2>  
  <Child3>  
    <Text>Child Three Text</Text>  
    <Type Value=""No""/>  
  </Child3>  
  <Child4>  
    <Text>Child Four Text</Text>  
    <Type Value=""Yes""/>  
  </Child4>  
  <Child5>  
    <Text>Child Five Text</Text>  
  </Child5>  
</Root>");  
XNamespace ad = "http://www.adatum.com";  
var cList =  
    from typeElement in root.Elements().Elements(ad + "Type")  
    where (string)typeElement.Attribute("Value") == "Yes"  
    select (string)typeElement.Parent.Element(ad + "Text");  
foreach (string str in cList)  
    Console.WriteLine(str);  
```  
  
 <span data-ttu-id="b6e93-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="b6e93-112">This code produces the following output:</span></span>  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6e93-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6e93-113">See Also</span></span>  
 <span data-ttu-id="b6e93-114"><xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b6e93-114"><xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="b6e93-115"><xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b6e93-115"><xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="b6e93-116"><xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b6e93-116"><xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="b6e93-117">[Basic Queries (LINQ to XML) (C#) (Standardabfragen (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="b6e93-117">[Basic Queries (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) </span></span>  
 <span data-ttu-id="b6e93-118">[Übersicht über Standardabfrageoperatoren (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="b6e93-118">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 [<span data-ttu-id="b6e93-119">Projection Operations (C#) (Projektionsvorgänge (C#))</span><span class="sxs-lookup"><span data-stu-id="b6e93-119">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)

