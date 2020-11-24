---
title: Auswählen von XML-Daten mit 'XPathNavigator'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c268c49e-32b9-4171-b782-dcb7b065fa73
ms.openlocfilehash: 791c1d16db6a2079ccccebf4dc33d5a0eb12d3c5
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824973"
---
# <a name="select-xml-data-using-xpathnavigator"></a><span data-ttu-id="faba7-102">Auswählen von XML-Daten mit 'XPathNavigator'</span><span class="sxs-lookup"><span data-stu-id="faba7-102">Select XML Data Using XPathNavigator</span></span>
<span data-ttu-id="faba7-103">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt eine Gruppe von Methoden bereit, mit denen eine Gruppe von Knoten in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder einem <xref:System.Xml.XmlDocument>-Objekt mithilfe eines XPath-Ausdrucks ausgewählt werden können.</span><span class="sxs-lookup"><span data-stu-id="faba7-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to select a set of nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath expression.</span></span> <span data-ttu-id="faba7-104">Sobald die Knoten ausgewählt sind, können die ausgewählten Knoten durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="faba7-104">Once selected, you can iterate over the selected set of nodes.</span></span>  
  
## <a name="xpathnavigator-selection-methods"></a><span data-ttu-id="faba7-105">Auswahlmethoden von XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="faba7-105">XPathNavigator Selection Methods</span></span>  
 <span data-ttu-id="faba7-106">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt eine Gruppe von Methoden bereit, mit denen eine Gruppe von Knoten in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder einem <xref:System.Xml.XmlDocument>-Objekt mithilfe eines XPath-Ausdrucks ausgewählt werden können.</span><span class="sxs-lookup"><span data-stu-id="faba7-106">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to select a set of nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath expression.</span></span> <span data-ttu-id="faba7-107">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt außerdem eine Gruppe optimierter Methoden bereit, mit denen übergeordnete, direkt untergeordnete und indirekt untergeordnete Knoten schneller als bei Verwendung eines XPath-Ausdrucks ausgewählt werden können.</span><span class="sxs-lookup"><span data-stu-id="faba7-107">The <xref:System.Xml.XPath.XPathNavigator> class also provides a set of optimized methods for selecting ancestor, child and descendant nodes faster than using an XPath expression.</span></span> <span data-ttu-id="faba7-108">Die ausgewählte Knotengruppe wird in einem <xref:System.Xml.XPath.XPathNodeIterator>-Objekt oder (falls es sich um nur einen ausgewählten Knoten handelt) in einem <xref:System.Xml.XPath.XPathNavigator>-Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="faba7-108">The selected set of nodes is returned in an <xref:System.Xml.XPath.XPathNodeIterator> object or an <xref:System.Xml.XPath.XPathNavigator> object in the case of a single selected node.</span></span>  
  
### <a name="selecting-nodes-using-xpath-expressions"></a><span data-ttu-id="faba7-109">Auswählen von Knoten mithilfe von XPath-Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="faba7-109">Selecting Nodes Using XPath Expressions</span></span>  
 <span data-ttu-id="faba7-110">Verwenden Sie eine der folgenden Auswahlmethoden, um eine Gruppe von Knoten mithilfe eines XPath-Ausdrucks auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="faba7-110">To select a set of nodes using an XPath expression, use one of the following selection methods.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
 <span data-ttu-id="faba7-111">Bei einem Aufruf geben diese Methoden eine Knotengruppe zurück, die Sie mithilfe eines <xref:System.Xml.XPath.XPathNodeIterator>-Objekts oder (falls es sich um nur einen ausgewählten Knoten handelt) eines <xref:System.Xml.XPath.XPathNavigator>-Objekts frei durchsuchen können.</span><span class="sxs-lookup"><span data-stu-id="faba7-111">When called, these methods return a set of nodes that you can navigate freely using an <xref:System.Xml.XPath.XPathNodeIterator> object or an <xref:System.Xml.XPath.XPathNavigator> object in the case of a single selected node.</span></span>  
  
 <span data-ttu-id="faba7-112">Das Navigieren mithilfe eines <xref:System.Xml.XPath.XPathNodeIterator>-Objekts hat keine Auswirkungen auf die Position des <xref:System.Xml.XPath.XPathNavigator>-Objekts, das zum Erstellen verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="faba7-112">Navigating with an <xref:System.Xml.XPath.XPathNodeIterator> object does not affect the position of the <xref:System.Xml.XPath.XPathNavigator> object used to create it.</span></span> <span data-ttu-id="faba7-113">Das von der <xref:System.Xml.XPath.XPathNavigator>-Methode zurückgegebene <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>-Objekt wird auf dem einzelnen zurückgegebenen Knoten positioniert und hat keine Auswirkung auf die Position des <xref:System.Xml.XPath.XPathNavigator>-Objekts, mit dem es erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="faba7-113">The <xref:System.Xml.XPath.XPathNavigator> object returned from the <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> methods is positioned on the single returned node and also does not affect the position of the <xref:System.Xml.XPath.XPathNavigator> object used to create it.</span></span>  
  
 <span data-ttu-id="faba7-114">Im folgenden Beispiel wird das Erstellen eines <xref:System.Xml.XPath.XPathNavigator>-Objekts aus einem <xref:System.Xml.XPath.XPathDocument>-Objekts veranschaulicht. Außerdem werden die Verwendung der <xref:System.Xml.XPath.XPathNavigator.Select%2A>-Methode zum Auswählen der Knoten im <xref:System.Xml.XPath.XPathDocument>-Objekt sowie die Verwendung des <xref:System.Xml.XPath.XPathNodeIterator>-Objekts zum Durchlaufen der ausgewählten Knoten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="faba7-114">The following example shows the creation of an <xref:System.Xml.XPath.XPathNavigator> object from an <xref:System.Xml.XPath.XPathDocument> object, the use of the <xref:System.Xml.XPath.XPathNavigator.Select%2A> method to select nodes in the <xref:System.Xml.XPath.XPathDocument> object, and the use of the <xref:System.Xml.XPath.XPathNodeIterator> object to iterate over the selected nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
Dim nodes As XPathNodeIterator = navigator.Select("/bookstore/book")  
  
While nodes.MoveNext()  
    Console.WriteLine(nodes.Current.Name)  
End While  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
XPathNodeIterator nodes = navigator.Select("/bookstore/book");  
  
while(nodes.MoveNext())  
{  
    Console.WriteLine(nodes.Current.Name);  
}  
```  
  
 <span data-ttu-id="faba7-115">In diesem Beispiel wird die Datei `books.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="faba7-115">The example takes the `books.xml` file as input.</span></span>  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### <a name="optimized-selection-methods"></a><span data-ttu-id="faba7-116">Optimierte Auswahlmethoden</span><span class="sxs-lookup"><span data-stu-id="faba7-116">Optimized Selection Methods</span></span>  
 <span data-ttu-id="faba7-117">Die Methoden <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A> und <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> der <xref:System.Xml.XPath.XPathNavigator>-Klasse stellen XPath-Ausdrücke dar, mit denen normalerweise direkt untergeordnete sowie indirekt untergeordnete und übergeordnete Knoten abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="faba7-117">The <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A>, and <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class represent XPath expressions commonly used to retrieve child, descendant, and ancestor nodes.</span></span> <span data-ttu-id="faba7-118">Diese Methoden tragen zur Leistungsoptimierung bei und sind schneller als die entsprechenden XPath-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="faba7-118">These methods are optimized for performance and are faster than their corresponding XPath expressions.</span></span> <span data-ttu-id="faba7-119">Die Methoden <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A> und <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> wählen übergeordnete, direkt untergeordnete und indirekt untergeordnete Knoten auf der Grundlage eines <xref:System.Xml.XPath.XPathNodeType>-Werts oder des lokalen Namens und des Namespace-URIs der auszuwählenden Knoten aus.</span><span class="sxs-lookup"><span data-stu-id="faba7-119">The <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A>, and <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> methods selects ancestor, child, and descendant nodes based on an <xref:System.Xml.XPath.XPathNodeType> value or the local name and namespace URI of the nodes to select.</span></span> <span data-ttu-id="faba7-120">Die ausgewählten übergeordneten, direkt untergeordneten und indirekt untergeordneten Knoten werden in einem <xref:System.Xml.XPath.XPathNodeIterator>-Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="faba7-120">The selected ancestor, child, and descendant nodes are returned in an <xref:System.Xml.XPath.XPathNodeIterator> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faba7-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="faba7-121">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="faba7-122">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="faba7-122">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="faba7-123">Auswerten von XPath-Ausdrücken mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="faba7-123">Evaluate XPath Expressions using XPathNavigator</span></span>](evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="faba7-124">Vergleich von Knoten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="faba7-124">Matching Nodes using XPathNavigator</span></span>](matching-nodes-using-xpathnavigator.md)
- [<span data-ttu-id="faba7-125">In XPath-Abfragen erkannte Knotentypen</span><span class="sxs-lookup"><span data-stu-id="faba7-125">Node Types Recognized with XPath Queries</span></span>](node-types-recognized-with-xpath-queries.md)
- [<span data-ttu-id="faba7-126">XPath-Abfragen und Namespaces</span><span class="sxs-lookup"><span data-stu-id="faba7-126">XPath Queries and Namespaces</span></span>](xpath-queries-and-namespaces.md)
- [<span data-ttu-id="faba7-127">Kompilierte XPath-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="faba7-127">Compiled XPath Expressions</span></span>](compiled-xpath-expressions.md)
