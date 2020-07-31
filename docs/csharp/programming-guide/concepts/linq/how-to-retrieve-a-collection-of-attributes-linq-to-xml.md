---
title: 'Vorgehensweise: Abrufen einer Attributauflistung (LINQ to XML) (C#)'
description: Die Attributes-Methode in C# ruft die Attribute eines Elements ab. Im folgenden LINQ to XML-Beispiel wird die Sammlung von Attributen eines Elements durchlaufen.
ms.date: 07/20/2015
ms.assetid: a49ee7a3-b2c2-4d49-9b5c-b7c6c41f4f13
ms.openlocfilehash: 5994086db6133530e63eb1328a7b524d30a0797d
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103384"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a><span data-ttu-id="b20f7-104">Vorgehensweise: Abrufen einer Attributauflistung (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b20f7-104">How to retrieve a collection of attributes (LINQ to XML) (C#)</span></span>
<span data-ttu-id="b20f7-105">Dieses Thema enthält eine Einführung in die <xref:System.Xml.Linq.XElement.Attributes%2A>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b20f7-105">This topic introduces the <xref:System.Xml.Linq.XElement.Attributes%2A> method.</span></span> <span data-ttu-id="b20f7-106">Diese Methode ruft die Attribute eines Elements ab.</span><span class="sxs-lookup"><span data-stu-id="b20f7-106">This method retrieves the attributes of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b20f7-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b20f7-107">Example</span></span>  
 <span data-ttu-id="b20f7-108">Im folgenden Beispiel wird gezeigt, wie die Auflistung von Attributen eines Elements durchlaufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b20f7-108">The following example shows how to iterate through the collection of attributes of an element.</span></span>  
  
```csharp  
XElement val = new XElement("Value",  
    new XAttribute("ID", "1243"),  
    new XAttribute("Type", "int"),  
    new XAttribute("ConvertableTo", "double"),  
    "100");  
IEnumerable<XAttribute> listOfAttributes =  
    from att in val.Attributes()  
    select att;  
foreach (XAttribute a in listOfAttributes)  
    Console.WriteLine(a);  
```  
  
 <span data-ttu-id="b20f7-109">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="b20f7-109">This code produces the following output:</span></span>  
  
```output  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a><span data-ttu-id="b20f7-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b20f7-110">See also</span></span>

- [<span data-ttu-id="b20f7-111">LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))</span><span class="sxs-lookup"><span data-stu-id="b20f7-111">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
