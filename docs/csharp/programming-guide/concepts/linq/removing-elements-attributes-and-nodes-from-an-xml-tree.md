---
title: Entfernen von Elementen, Attributen und Knoten aus einem XML-Baum (C#)
description: Erfahren Sie, wie Sie Elemente, Attribute und Knoten aus einer XML-Struktur entfernen. Hier finden Sie eine Liste mit Entfernungsmethoden und ein Codebeispiel.
ms.date: 07/20/2015
ms.assetid: 07dd06d6-1117-4077-bf98-9120cf51176e
ms.openlocfilehash: 4e753c3d96c4cbc050b08076ca8bff8c17b2e252
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87300045"
---
# <a name="removing-elements-attributes-and-nodes-from-an-xml-tree-c"></a><span data-ttu-id="254ca-104">Entfernen von Elementen, Attributen und Knoten aus einem XML-Baum (C#)</span><span class="sxs-lookup"><span data-stu-id="254ca-104">Removing Elements, Attributes, and Nodes from an XML Tree (C#)</span></span>

<span data-ttu-id="254ca-105">Sie können eine XML-Struktur ändern, indem Sie Elemente, Attribute und andere Knotentypen entfernen.</span><span class="sxs-lookup"><span data-stu-id="254ca-105">You can modify an XML tree, removing elements, attributes, and other types of nodes.</span></span>

<span data-ttu-id="254ca-106">Das Entfernen eines einzelnen Elements oder Attributs aus einem XML-Dokument ist unkompliziert.</span><span class="sxs-lookup"><span data-stu-id="254ca-106">Removing a single element or a single attribute from an XML document is straightforward.</span></span> <span data-ttu-id="254ca-107">Wenn Sie aber Auflistungen von Elementen oder Attributen entfernen, sollten Sie zuerst eine Auflistung in einer Liste materialisieren, bevor Sie die Elemente oder Attribute aus der Liste löschen.</span><span class="sxs-lookup"><span data-stu-id="254ca-107">However, when removing collections of elements or attributes, you should first materialize a collection into a list, and then delete the elements or attributes from the list.</span></span> <span data-ttu-id="254ca-108">Verwenden Sie dazu am besten die <xref:System.Xml.Linq.Extensions.Remove%2A>-Erweiterungsmethode, die diese Aufgabe für Sie übernimmt.</span><span class="sxs-lookup"><span data-stu-id="254ca-108">The best approach is to use the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method, which will do this for you.</span></span>

<span data-ttu-id="254ca-109">Der Hauptgrund für diese Vorgehensweise besteht darin, dass die meisten Auflistungen, die Sie aus einer XML-Struktur abrufen, mit verzögerter Ausführung zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="254ca-109">The main reason for doing this is that most of the collections you retrieve from an XML tree are yielded using deferred execution.</span></span> <span data-ttu-id="254ca-110">Wenn Sie die Auflistungen nicht zunächst in einer Liste materialisieren oder wenn Sie nicht die Erweiterungsmethoden verwenden, kommt es möglicherweise zu einer bestimmten Form von Fehlern.</span><span class="sxs-lookup"><span data-stu-id="254ca-110">If you do not first materialize them into a list, or if you do not use the extension methods, it is possible to encounter a certain class of bugs.</span></span> <span data-ttu-id="254ca-111">Weitere Informationen finden Sie unter [Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (C#) (Fehler durch Vermischung von deklarativem und imperativem Code (LINQ to XML) (C#))](./mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="254ca-111">For more information, see [Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (C#)](./mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).</span></span>

<span data-ttu-id="254ca-112">Die folgenden Methoden entfernen Knoten und Attribute aus einer XML-Struktur.</span><span class="sxs-lookup"><span data-stu-id="254ca-112">The following methods remove nodes and attributes from an XML tree.</span></span>

|<span data-ttu-id="254ca-113">Methode</span><span class="sxs-lookup"><span data-stu-id="254ca-113">Method</span></span>|<span data-ttu-id="254ca-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="254ca-114">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Linq.XAttribute.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="254ca-115">Entfernt einen <xref:System.Xml.Linq.XAttribute> aus seinem übergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="254ca-115">Removes an <xref:System.Xml.Linq.XAttribute> from its parent.</span></span>|
|<xref:System.Xml.Linq.XContainer.RemoveNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="254ca-116">Entfernt die untergeordneten Knoten aus einem <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="254ca-116">Removes the child nodes from an <xref:System.Xml.Linq.XContainer>.</span></span>|
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="254ca-117">Entfernt Inhalt und Attribute aus einem <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="254ca-117">Removes content and attributes from an <xref:System.Xml.Linq.XElement>.</span></span>|
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="254ca-118">Entfernt die Attribute eines <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="254ca-118">Removes the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="254ca-119">Entfernt das Attribut, wenn Sie als Wert `null` übergeben.</span><span class="sxs-lookup"><span data-stu-id="254ca-119">If you pass `null` for value, then removes the attribute.</span></span>|
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="254ca-120">Entfernt das untergeordnete Element, wenn Sie als Wert `null` übergeben.</span><span class="sxs-lookup"><span data-stu-id="254ca-120">If you pass `null` for value, then removes the child element.</span></span>|
|<xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="254ca-121">Entfernt einen <xref:System.Xml.Linq.XNode> aus seinem übergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="254ca-121">Removes an <xref:System.Xml.Linq.XNode> from its parent.</span></span>|
|<xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="254ca-122">Entfernt jedes Attribut oder Element in der Quellauflistung aus seinem übergeordneten Element.</span><span class="sxs-lookup"><span data-stu-id="254ca-122">Removes every attribute or element in the source collection from its parent element.</span></span>|

## <a name="example"></a><span data-ttu-id="254ca-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="254ca-123">Example</span></span>

### <a name="description"></a><span data-ttu-id="254ca-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="254ca-124">Description</span></span>

<span data-ttu-id="254ca-125">In diesem Beispiel werden drei Ansätze zum Entfernen von Elementen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="254ca-125">This example demonstrates three approaches to removing elements.</span></span> <span data-ttu-id="254ca-126">Zuerst entfernt das Beispiel ein einzelnes Element.</span><span class="sxs-lookup"><span data-stu-id="254ca-126">First, it removes a single element.</span></span> <span data-ttu-id="254ca-127">Als Zweites ruft das Beispiel eine Auflistung von Elementen ab, materialisiert sie mit dem <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>-Operator und entfernt die Auflistung.</span><span class="sxs-lookup"><span data-stu-id="254ca-127">Second, it retrieves a collection of elements, materializes them using the <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> operator, and removes the collection.</span></span> <span data-ttu-id="254ca-128">Zum Schluss ruft das Beispiel eine Auflistung von Elementen ab und entfernt diese mit der <xref:System.Xml.Linq.Extensions.Remove%2A>-Erweiterungsmethode.</span><span class="sxs-lookup"><span data-stu-id="254ca-128">Finally, it retrieves a collection of elements and removes them using the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method.</span></span>

<span data-ttu-id="254ca-129">Weitere Informationen zum <xref:System.Linq.Enumerable.ToList%2A>-Operator finden Sie unter [Konvertieren von Datentypen (C#)](./converting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="254ca-129">For more information on the <xref:System.Linq.Enumerable.ToList%2A> operator, see [Converting Data Types (C#)](./converting-data-types.md).</span></span>

### <a name="code"></a><span data-ttu-id="254ca-130">Code</span><span class="sxs-lookup"><span data-stu-id="254ca-130">Code</span></span>

```csharp
XElement root = XElement.Parse(@"<Root>
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
</Root>");
root.Element("Child1").Element("GrandChild1").Remove();
root.Element("Child2").Elements().ToList().Remove();
root.Element("Child3").Elements().Remove();
Console.WriteLine(root);
```

### <a name="comments"></a><span data-ttu-id="254ca-131">Kommentare</span><span class="sxs-lookup"><span data-stu-id="254ca-131">Comments</span></span>

<span data-ttu-id="254ca-132">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="254ca-132">This code produces the following output:</span></span>

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

<span data-ttu-id="254ca-133">Beachten Sie, dass das erste Element der zweiten Unterebene aus `Child1` entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="254ca-133">Notice that the first grandchild element has been removed from `Child1`.</span></span> <span data-ttu-id="254ca-134">Alle Elemente der zweiten Unterebene wurden aus `Child2` und `Child3` entfernt.</span><span class="sxs-lookup"><span data-stu-id="254ca-134">All grandchildren elements have been removed from `Child2` and from `Child3`.</span></span>
