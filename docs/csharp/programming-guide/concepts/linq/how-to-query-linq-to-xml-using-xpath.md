---
title: 'Vorgehensweise: Abfragen von LINQ to XML mit XPath (C#)'
ms.date: 07/20/2015
ms.assetid: ee5af263-4ab1-45e5-b792-33a3221b426d
ms.openlocfilehash: 61878febd9b4880872b7bc58e4de04b37cff96f8
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344812"
---
# <a name="how-to-query-linq-to-xml-using-xpath-c"></a><span data-ttu-id="d2b20-102">Vorgehensweise: Abfragen von LINQ to XML mit XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="d2b20-102">How to query LINQ to XML using XPath (C#)</span></span>
<span data-ttu-id="d2b20-103">Dieses Thema führt Sie in die Erweiterungsmethoden ein, mit denen Sie zum Abfragen einer XML-Struktur XPath verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d2b20-103">This topic introduces the extension methods that enable you to query an XML tree by using XPath.</span></span> <span data-ttu-id="d2b20-104">Ausführliche Informationen zum Verwenden dieser Erweiterungsmethoden finden Sie unter <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d2b20-104">For detailed information about using these extension methods, see <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="d2b20-105">Sofern Sie keinen besonderen Grund dafür haben, Abfragen mit XPath zu schreiben, z. B. weil in großem Maße Legacy-Code verwendet wird, wird die Verwendung von XPath mit LINQ to XML nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="d2b20-105">Unless you have a very specific reason for querying using XPath, such as extensive use of legacy code, using XPath with LINQ to XML is not recommended.</span></span> <span data-ttu-id="d2b20-106">XPath-Abfragen sind nicht so leistungsfähig wie [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="d2b20-106">XPath queries will not perform as well as [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2b20-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d2b20-107">Example</span></span>  
 <span data-ttu-id="d2b20-108">Das folgende Beispiel erstellt eine kleine XML-Struktur und verwendet zum Auswählen eines Satzes von Elementen <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A>.</span><span class="sxs-lookup"><span data-stu-id="d2b20-108">The following example creates a small XML tree and uses <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> to select a set of elements.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child1", 2),  
    new XElement("Child1", 3),  
    new XElement("Child2", 4),  
    new XElement("Child2", 5),  
    new XElement("Child2", 6)  
);  
IEnumerable<XElement> list = root.XPathSelectElements("./Child2");  
foreach (XElement el in list)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="d2b20-109">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d2b20-109">This example produces the following output:</span></span>  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  