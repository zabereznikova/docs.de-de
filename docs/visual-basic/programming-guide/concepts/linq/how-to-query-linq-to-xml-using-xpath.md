---
title: 'Vorgehensweise: Abfragen von LINQ to XML mit XPath (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1f69a20-1efa-452d-9089-c472fa84b3d5
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 97f885a76a79832b06f2f5d4a270d418bf244cb2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-query-linq-to-xml-using-xpath-visual-basic"></a><span data-ttu-id="255b4-102">Vorgehensweise: Abfragen von LINQ to XML mit XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="255b4-102">How to: Query LINQ to XML Using XPath (Visual Basic)</span></span>
<span data-ttu-id="255b4-103">Dieses Thema führt Sie in die Erweiterungsmethoden ein, mit denen Sie zum Abfragen einer XML-Struktur XPath verwenden können.</span><span class="sxs-lookup"><span data-stu-id="255b4-103">This topic introduces the extension methods that enable you to query an XML tree by using XPath.</span></span> <span data-ttu-id="255b4-104">Ausführliche Informationen zum Verwenden dieser Erweiterungsmethoden finden Sie unter <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="255b4-104">For detailed information about using these extension methods, see <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="255b4-105">Sofern Sie keinen besonderen Grund dafür haben, Abfragen mit XPath zu schreiben, z. B. weil in großem Maße Legacy-Code verwendet wird, wird die Verwendung von XPath mit LINQ to XML nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="255b4-105">Unless you have a very specific reason for querying using XPath, such as extensive use of legacy code, using XPath with LINQ to XML is not recommended.</span></span> <span data-ttu-id="255b4-106">XPath-Abfragen sind nicht so leistungsfähig wie [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="255b4-106">XPath queries will not perform as well as [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="255b4-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="255b4-107">Example</span></span>  
 <span data-ttu-id="255b4-108">Das folgende Beispiel erstellt eine kleine XML-Struktur und verwendet zum Auswählen eines Satzes von Elementen <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A>.</span><span class="sxs-lookup"><span data-stu-id="255b4-108">The following example creates a small XML tree and uses <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> to select a set of elements.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>1</Child1>  
        <Child1>2</Child1>  
        <Child1>3</Child1>  
        <Child2>4</Child2>  
        <Child2>5</Child2>  
        <Child2>6</Child2>  
    </Root>  
  
Dim list As IEnumerable(Of XElement) = root.XPathSelectElements("./Child2")  
For Each el As XElement In list  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="255b4-109">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="255b4-109">This example produces the following output:</span></span>  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  
## <a name="see-also"></a><span data-ttu-id="255b4-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="255b4-110">See Also</span></span>  
 [<span data-ttu-id="255b4-111">Erweiterte Abfragetechniken (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="255b4-111">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
