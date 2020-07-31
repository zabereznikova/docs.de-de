---
title: 'Vorgehensweise: Ändern des Namespaces für einen gesamten XML-Baum (C#)'
description: Hier erfahren Sie, wie Sie den Namespace für ein Element oder Attribut in LINQ to XML in C# programmgesteuert ändern.
ms.date: 07/20/2015
ms.assetid: 1584ff3b-c77d-4241-ab62-80adfb7bfc1b
ms.openlocfilehash: 0bf4c9d8f3cf569f14b654dfd0c4291a7eb647df
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105369"
---
# <a name="how-to-change-the-namespace-for-an-entire-xml-tree-c"></a><span data-ttu-id="1d0ce-103">Vorgehensweise: Ändern des Namespaces für einen gesamten XML-Baum (C#)</span><span class="sxs-lookup"><span data-stu-id="1d0ce-103">How to change the namespace for an entire XML tree (C#)</span></span>
<span data-ttu-id="1d0ce-104">Es kann passieren, dass Sie den Namespace für ein Element oder Attribut programmgesteuert ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-104">You sometimes have to programmatically change the namespace for an element or an attribute.</span></span> <span data-ttu-id="1d0ce-105">Mit LINQ to XML ist dies ganz einfach.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-105">LINQ to XML makes this easy.</span></span> <span data-ttu-id="1d0ce-106">Sie können die <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType>-Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-106">The <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType> property can be set.</span></span> <span data-ttu-id="1d0ce-107">Die <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType>-Eigenschaft kann nicht festgelegt werden, Sie können aber problemlos die Attribute in eine <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> kopieren, die vorhandenen Attribute entfernen und dann neue Attribute hinzufügen, die sich im neuen gewünschten Namespace befinden.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-107">The <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType> property cannot be set, but you can easily copy the attributes into a <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, remove the existing attributes, and then add new attributes that are in the new desired namespace.</span></span>  
  
 <span data-ttu-id="1d0ce-108">Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="1d0ce-108">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d0ce-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1d0ce-109">Example</span></span>  
 <span data-ttu-id="1d0ce-110">Der folgende Code erstellt zwei XML-Strukturen, die sich in keinem Namespace befinden.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-110">The following code creates two XML trees in no namespace.</span></span> <span data-ttu-id="1d0ce-111">Er ändert dann den Namespace beider Strukturen und fasst die Strukturen in einer gemeinsamen Struktur zusammen.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-111">It then changes the namespace of each of the trees, and combines them into a single tree.</span></span>  
  
```csharp  
XElement tree1 = new XElement("Data",  
    new XElement("Child", "content",  
        new XAttribute("MyAttr", "content")  
    )  
);  
XElement tree2 = new XElement("Data",  
    new XElement("Child", "content",  
        new XAttribute("MyAttr", "content")  
    )  
);  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace ad = "http://www.adatum.com";  
// change the namespace of every element and attribute in the first tree  
foreach (XElement el in tree1.DescendantsAndSelf())  
{  
    el.Name = aw.GetName(el.Name.LocalName);  
    List<XAttribute> atList = el.Attributes().ToList();  
    el.Attributes().Remove();  
    foreach (XAttribute at in atList)  
        el.Add(new XAttribute(aw.GetName(at.Name.LocalName), at.Value));  
}  
// change the namespace of every element and attribute in the second tree  
foreach (XElement el in tree2.DescendantsAndSelf())  
{  
    el.Name = ad.GetName(el.Name.LocalName);  
    List<XAttribute> atList = el.Attributes().ToList();  
    el.Attributes().Remove();  
    foreach (XAttribute at in atList)  
        el.Add(new XAttribute(ad.GetName(at.Name.LocalName), at.Value));  
}  
// add attribute namespaces so that the tree will be serialized with  
// the aw and ad namespace prefixes  
tree1.Add(  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com")  
);  
tree2.Add(  
    new XAttribute(XNamespace.Xmlns + "ad", "http://www.adatum.com")  
);  
// create a new composite tree  
XElement root = new XElement("Root",  
    tree1,  
    tree2  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="1d0ce-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1d0ce-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <aw:Data xmlns:aw="http://www.adventure-works.com">  
    <aw:Child aw:MyAttr="content">content</aw:Child>  
  </aw:Data>  
  <ad:Data xmlns:ad="http://www.adatum.com">  
    <ad:Child ad:MyAttr="content">content</ad:Child>  
  </ad:Data>  
</Root>  
```  
