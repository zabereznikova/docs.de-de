---
title: 'Vorgehensweise: Filtern nach einem optionalen Element (C#)'
ms.date: 07/20/2015
ms.assetid: f99e2f93-fca5-403f-8a0c-770761d4905a
ms.openlocfilehash: c9f844619cbb3d7a66ca66989baa900e0fd7bc2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141251"
---
# <a name="how-to-filter-on-an-optional-element-c"></a><span data-ttu-id="35099-102">Vorgehensweise: Filtern nach einem optionalen Element (C#)</span><span class="sxs-lookup"><span data-stu-id="35099-102">How to filter on an optional element (C#)</span></span>
<span data-ttu-id="35099-103">Es kann vorkommen, dass Sie nach einem Element filtern möchten, ohne genau zu wissen, ob dieses Element in Ihrem XML-Dokument tatsächlich existiert.</span><span class="sxs-lookup"><span data-stu-id="35099-103">Sometimes you want to filter for an element even though you are not sure it exists in your XML document.</span></span> <span data-ttu-id="35099-104">Die Suche sollte dann so ausgeführt werden, dass für den Fall, dass das Element das gesuchte untergeordnete Element nicht besitzt, beim Filtern keine Ausnahme wegen eines NULL-Verweises ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="35099-104">The search should be executed so that if the particular element does not have the child element, you do not trigger a null reference exception by filtering for it.</span></span> <span data-ttu-id="35099-105">Im folgenden Beispiel besitzt das `Child5`-Element kein untergeordnetes `Type`-Element, dennoch wird die Abfrage korrekt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="35099-105">In the following example, the `Child5` element does not have a `Type` child element, but the query still executes correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35099-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="35099-106">Example</span></span>  
 <span data-ttu-id="35099-107">Dieses Beispiel verwendet die <xref:System.Xml.Linq.Extensions.Elements%2A>-Erweiterungsmethode:</span><span class="sxs-lookup"><span data-stu-id="35099-107">This example uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method.</span></span>  
  
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
  
 <span data-ttu-id="35099-108">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="35099-108">This code produces the following output:</span></span>  
  
```output  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="example"></a><span data-ttu-id="35099-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="35099-109">Example</span></span>  
 <span data-ttu-id="35099-110">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="35099-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="35099-111">Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="35099-111">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="35099-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="35099-112">This code produces the following output:</span></span>  
  
```output  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="see-also"></a><span data-ttu-id="35099-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="35099-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="35099-114">Standard Query Operators Overview (C#) (Übersicht der Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="35099-114">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="35099-115">Projection Operations (C#) (Projektionsvorgänge (C#))</span><span class="sxs-lookup"><span data-stu-id="35099-115">Projection Operations (C#)</span></span>](./projection-operations.md)
