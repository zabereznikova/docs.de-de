---
title: Entfernen von Elementen, Attributen und Knoten aus einer XML-Struktur (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 5cf21919-4360-4b49-b29d-58ea3164ac72
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8842858080ce1f27d997e6af61a8dd2301cdc2bc
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017


---
# <a name="removing-elements-attributes-and-nodes-from-an-xml-tree-visual-basic"></a><span data-ttu-id="c7437-102">Entfernen von Elementen, Attributen und Knoten aus einer XML-Struktur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7437-102">Removing Elements, Attributes, and Nodes from an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="c7437-103">Sie können eine XML-Struktur ändern, indem Sie Elemente, Attribute und andere Knotentypen entfernen.</span><span class="sxs-lookup"><span data-stu-id="c7437-103">You can modify an XML tree, removing elements, attributes, and other types of nodes.</span></span>  
  
 <span data-ttu-id="c7437-104">Das Entfernen eines einzelnen Elements oder Attributs aus einem XML-Dokument ist unkompliziert.</span><span class="sxs-lookup"><span data-stu-id="c7437-104">Removing a single element or a single attribute from an XML document is straightforward.</span></span> <span data-ttu-id="c7437-105">Wenn Sie aber Auflistungen von Elementen oder Attributen entfernen, sollten Sie zuerst eine Auflistung in einer Liste materialisieren, bevor Sie die Elemente oder Attribute aus der Liste löschen.</span><span class="sxs-lookup"><span data-stu-id="c7437-105">However, when removing collections of elements or attributes, you should first materialize a collection into a list, and then delete the elements or attributes from the list.</span></span> <span data-ttu-id="c7437-106">Der beste Ansatz ist die Verwendung der <xref:System.Xml.Linq.Extensions.Remove%2A>Erweiterungsmethode, was dies für Sie durchführen werden.</xref:System.Xml.Linq.Extensions.Remove%2A></span><span class="sxs-lookup"><span data-stu-id="c7437-106">The best approach is to use the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method, which will do this for you.</span></span>  
  
 <span data-ttu-id="c7437-107">Der Hauptgrund für diese Vorgehensweise besteht darin, dass die meisten Auflistungen, die Sie aus einer XML-Struktur abrufen, mit verzögerter Ausführung zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c7437-107">The main reason for doing this is that most of the collections you retrieve from an XML tree are yielded using deferred execution.</span></span> <span data-ttu-id="c7437-108">Wenn Sie die Auflistungen nicht zunächst in einer Liste materialisieren oder wenn Sie nicht die Erweiterungsmethoden verwenden, kommt es möglicherweise zu einer bestimmten Form von Fehlern.</span><span class="sxs-lookup"><span data-stu-id="c7437-108">If you do not first materialize them into a list, or if you do not use the extension methods, it is possible to encounter a certain class of bugs.</span></span> <span data-ttu-id="c7437-109">Weitere Informationen finden Sie unter [Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c7437-109">For more information, see [Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="c7437-110">Die folgenden Methoden entfernen Knoten und Attribute aus einer XML-Struktur.</span><span class="sxs-lookup"><span data-stu-id="c7437-110">The following methods remove nodes and attributes from an XML tree.</span></span>  
  
|<span data-ttu-id="c7437-111">Methode</span><span class="sxs-lookup"><span data-stu-id="c7437-111">Method</span></span>|<span data-ttu-id="c7437-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7437-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c7437-113">[XAttribute.Remove](https://msdn.microsoft.com/library/system.xml.linq.xattribute.remove\(v=vs.110\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c7437-113">[XAttribute.Remove](https://msdn.microsoft.com/library/system.xml.linq.xattribute.remove\(v=vs.110\).aspx)</span></span>|<span data-ttu-id="c7437-114">Entfernt eine <xref:System.Xml.Linq.XAttribute>vom übergeordneten.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="c7437-114">Removes an <xref:System.Xml.Linq.XAttribute> from its parent.</span></span>|  
|<span data-ttu-id="c7437-115">[XContainer.RemoveNodes](https://msdn.microsoft.com/library/system.xml.linq.xcontainer.removenodes\(v=vs.110\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c7437-115">[XContainer.RemoveNodes](https://msdn.microsoft.com/library/system.xml.linq.xcontainer.removenodes\(v=vs.110\).aspx)</span></span>|<span data-ttu-id="c7437-116">Entfernt die untergeordneten Knoten aus einer <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="c7437-116">Removes the child nodes from an <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<span data-ttu-id="c7437-117"><xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c7437-117"><xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></span></span>|<span data-ttu-id="c7437-118">Entfernt Inhalt und Attribute aus einem <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="c7437-118">Removes content and attributes from an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="c7437-119"><xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c7437-119"><xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="c7437-120">Entfernt die Attribute einer <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="c7437-120">Removes the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="c7437-121"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c7437-121"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="c7437-122">Entfernt das Attribut, wenn Sie als Wert `null` übergeben.</span><span class="sxs-lookup"><span data-stu-id="c7437-122">If you pass `null` for value, then removes the attribute.</span></span>|  
|<span data-ttu-id="c7437-123"><xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c7437-123"><xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="c7437-124">Entfernt das untergeordnete Element, wenn Sie als Wert `null` übergeben.</span><span class="sxs-lookup"><span data-stu-id="c7437-124">If you pass `null` for value, then removes the child element.</span></span>|  
|<span data-ttu-id="c7437-125"><xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c7437-125"><xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=fullName></span></span>|<span data-ttu-id="c7437-126">Entfernt eine <xref:System.Xml.Linq.XNode>vom übergeordneten.</xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="c7437-126">Removes an <xref:System.Xml.Linq.XNode> from its parent.</span></span>|  
|<span data-ttu-id="c7437-127"><xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=fullName></xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c7437-127"><xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=fullName></span></span>|<span data-ttu-id="c7437-128">Entfernt jedes Attribut oder Element in der Quellauflistung aus seinem übergeordneten Element.</span><span class="sxs-lookup"><span data-stu-id="c7437-128">Removes every attribute or element in the source collection from its parent element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c7437-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7437-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c7437-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7437-130">Description</span></span>  
 <span data-ttu-id="c7437-131">In diesem Beispiel werden drei Ansätze zum Entfernen von Elementen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7437-131">This example demonstrates three approaches to removing elements.</span></span> <span data-ttu-id="c7437-132">Zuerst entfernt das Beispiel ein einzelnes Element.</span><span class="sxs-lookup"><span data-stu-id="c7437-132">First, it removes a single element.</span></span> <span data-ttu-id="c7437-133">Zweitens: er ruft eine Auflistung von Elementen ab, materialisiert sie mit der <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>-Operator, und entfernt die Auflistung.</xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c7437-133">Second, it retrieves a collection of elements, materializes them using the <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> operator, and removes the collection.</span></span> <span data-ttu-id="c7437-134">Schließlich ruft eine Auflistung von Elementen ab und entfernt diese mit der <xref:System.Xml.Linq.Extensions.Remove%2A>-Erweiterungsmethode.</xref:System.Xml.Linq.Extensions.Remove%2A></span><span class="sxs-lookup"><span data-stu-id="c7437-134">Finally, it retrieves a collection of elements and removes them using the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method.</span></span>  
  
 <span data-ttu-id="c7437-135">Weitere Informationen zu den <xref:System.Linq.Enumerable.ToList%2A>Operator finden Sie unter [Konvertieren von Datentypen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).</xref:System.Linq.Enumerable.ToList%2A></span><span class="sxs-lookup"><span data-stu-id="c7437-135">For more information on the <xref:System.Linq.Enumerable.ToList%2A> operator, see [Converting Data Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).</span></span>  
  
### <a name="code"></a><span data-ttu-id="c7437-136">Code</span><span class="sxs-lookup"><span data-stu-id="c7437-136">Code</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>  
            <GrandChild1/>  
            <GrandChild2/>  
            <GrandChild3/>  
        </Child1>  
        <Child2>  
            <GrandChild4/>  
            <GrandChild5/>  
            <GrandChild6/>  
        </Child2>  
        <Child3>  
            <GrandChild7/>  
            <GrandChild8/>  
            <GrandChild9/>  
        </Child3>  
    </Root>  
root.<Child1>.<GrandChild1>.Remove()  
root.<Child2>.Elements().ToList().Remove()  
root.<Child3>.Elements().Remove()  
Console.WriteLine(root)  
  
```  
  
### <a name="comments"></a><span data-ttu-id="c7437-137">Kommentare</span><span class="sxs-lookup"><span data-stu-id="c7437-137">Comments</span></span>  
 <span data-ttu-id="c7437-138">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c7437-138">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>  
    <GrandChild2 />  
    <GrandChild3 />  
  </Child1>  
  <Child2 />  
  <Child3 />  
</Root>  
```  
  
 <span data-ttu-id="c7437-139">Beachten Sie, dass das erste Element der zweiten Unterebene aus `Child1` entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="c7437-139">Notice that the first grandchild element has been removed from `Child1`.</span></span> <span data-ttu-id="c7437-140">Alle Elemente der zweiten Unterebene wurden aus `Child2` und `Child3` entfernt.</span><span class="sxs-lookup"><span data-stu-id="c7437-140">All grandchildren elements have been removed from `Child2` and from `Child3`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7437-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7437-141">See Also</span></span>  
 [<span data-ttu-id="c7437-142">Ändern von XML-Strukturen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7437-142">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
