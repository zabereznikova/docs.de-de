---
title: Hinzufügen von Elementen, Attributen und Knoten zu einem XML-Baum (C#)
ms.date: 07/20/2015
ms.assetid: db911e4f-40aa-499a-9500-a9763bb6df56
ms.openlocfilehash: 87b63df1011af9594ff44bed6385f9d82dee08a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585876"
---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-c"></a><span data-ttu-id="138d7-102">Hinzufügen von Elementen, Attributen und Knoten zu einem XML-Baum (C#)</span><span class="sxs-lookup"><span data-stu-id="138d7-102">Adding Elements, Attributes, and Nodes to an XML Tree (C#)</span></span>
<span data-ttu-id="138d7-103">Sie können einer vorhandenen XML-Struktur Inhalt (Elemente, Attribute, Kommentare, Verarbeitungsanweisungen, Text und CDATA) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="138d7-103">You can add content (elements, attributes, comments, processing instructions, text, and CDATA) to an existing XML tree.</span></span>  
  
## <a name="methods-for-adding-content"></a><span data-ttu-id="138d7-104">Methoden zum Hinzufügen von Inhalt</span><span class="sxs-lookup"><span data-stu-id="138d7-104">Methods for Adding Content</span></span>  
 <span data-ttu-id="138d7-105">Die folgenden Methoden fügen einem <xref:System.Xml.Linq.XElement> oder einem <xref:System.Xml.Linq.XDocument> untergeordneten Inhalt hinzu:</span><span class="sxs-lookup"><span data-stu-id="138d7-105">The following methods add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="138d7-106">Methode</span><span class="sxs-lookup"><span data-stu-id="138d7-106">Method</span></span>|<span data-ttu-id="138d7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="138d7-107">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|<span data-ttu-id="138d7-108">Fügt Inhalt am Ende des untergeordneten Inhalts des <xref:System.Xml.Linq.XContainer> hinzu.</span><span class="sxs-lookup"><span data-stu-id="138d7-108">Adds content at the end of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|<span data-ttu-id="138d7-109">Fügt Inhalt vor dem untergeordneten Inhalt des <xref:System.Xml.Linq.XContainer> hinzu.</span><span class="sxs-lookup"><span data-stu-id="138d7-109">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
  
 <span data-ttu-id="138d7-110">Die folgenden Methoden fügen Inhalt als nebengeordnete Knoten eines <xref:System.Xml.Linq.XNode> hinzu.</span><span class="sxs-lookup"><span data-stu-id="138d7-110">The following methods add content as sibling nodes of an <xref:System.Xml.Linq.XNode>.</span></span> <span data-ttu-id="138d7-111">Der Knoten, dem Sie am häufigsten nebengeordneten Inhalt hinzufügen, ist <xref:System.Xml.Linq.XElement>, obwohl Sie gültigen nebengeordneten Inhalt auch anderen Knotentypen hinzufügen können, z. B. <xref:System.Xml.Linq.XText> oder <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="138d7-111">The most common node to which you add sibling content is <xref:System.Xml.Linq.XElement>, although you can add valid sibling content to other types of nodes such as <xref:System.Xml.Linq.XText> or <xref:System.Xml.Linq.XComment>.</span></span>  
  
|<span data-ttu-id="138d7-112">Methode</span><span class="sxs-lookup"><span data-stu-id="138d7-112">Method</span></span>|<span data-ttu-id="138d7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="138d7-113">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<span data-ttu-id="138d7-114">Fügt Inhalt nach dem <xref:System.Xml.Linq.XNode> hinzu.</span><span class="sxs-lookup"><span data-stu-id="138d7-114">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<span data-ttu-id="138d7-115">Fügt Inhalt vor dem <xref:System.Xml.Linq.XNode> hinzu.</span><span class="sxs-lookup"><span data-stu-id="138d7-115">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="138d7-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="138d7-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="138d7-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="138d7-117">Description</span></span>  
 <span data-ttu-id="138d7-118">Das folgende Beispiel erstellt zwei XML-Strukturen und ändert dann eine der beiden Strukturen:</span><span class="sxs-lookup"><span data-stu-id="138d7-118">The following example creates two XML trees, and then modifies one of the trees.</span></span>  
  
### <a name="code"></a><span data-ttu-id="138d7-119">Code</span><span class="sxs-lookup"><span data-stu-id="138d7-119">Code</span></span>  
  
```csharp  
XElement srcTree = new XElement("Root",   
    new XElement("Element1", 1),  
    new XElement("Element2", 2),  
    new XElement("Element3", 3),  
    new XElement("Element4", 4),  
    new XElement("Element5", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child2", 2),  
    new XElement("Child3", 3),  
    new XElement("Child4", 4),  
    new XElement("Child5", 5)  
);  
xmlTree.Add(new XElement("NewChild", "new content"));  
xmlTree.Add(  
    from el in srcTree.Elements()  
    where (int)el > 3  
    select el  
);  
// Even though Child9 does not exist in srcTree, the following statement will not  
// throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"));  
Console.WriteLine(xmlTree);  
```  
  
### <a name="comments"></a><span data-ttu-id="138d7-120">Kommentare</span><span class="sxs-lookup"><span data-stu-id="138d7-120">Comments</span></span>  
 <span data-ttu-id="138d7-121">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="138d7-121">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
  <Child4>4</Child4>  
  <Child5>5</Child5>  
  <NewChild>new content</NewChild>  
  <Element4>4</Element4>  
  <Element5>5</Element5>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="138d7-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="138d7-122">See also</span></span>

- [<span data-ttu-id="138d7-123">Modifying XML Trees (LINQ to XML) (C#) (Ändern von XML-Strukturen (LINQ to XML) (C#))</span><span class="sxs-lookup"><span data-stu-id="138d7-123">Modifying XML Trees (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
