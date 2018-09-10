---
title: Navigieren in Knotengruppen mit XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1a954b41-7173-40bc-8544-d430f209b1e5
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f062f7fd58efe6c350b3a119ec3bdd4d27b896db
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086365"
---
# <a name="node-set-navigation-using-xpathnavigator"></a><span data-ttu-id="fdb1d-102">Navigieren in Knotengruppen mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="fdb1d-102">Node Set Navigation Using XPathNavigator</span></span>
<span data-ttu-id="fdb1d-103">Sie können mit den Navigationsmethoden für Knotengruppen der <xref:System.Xml.XPath.XPathDocument>-Klasse durch Knoten in einem <xref:System.Xml.XmlDocument> oder <xref:System.Xml.XPath.XPathNavigator> navigieren.</span><span class="sxs-lookup"><span data-stu-id="fdb1d-103">You can navigate over nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using the node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span> <span data-ttu-id="fdb1d-104">Sie können durch alle Knoten oder durch eine von den Auswahlmethoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse zurückgegebene Gruppe von Knoten navigieren.</span><span class="sxs-lookup"><span data-stu-id="fdb1d-104">You can navigate over all the nodes or over a selected set of nodes returned by one of the selection methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
## <a name="element-node-set-navigation"></a><span data-ttu-id="fdb1d-105">Navigation durch Gruppen von Elementknoten</span><span class="sxs-lookup"><span data-stu-id="fdb1d-105">Element Node Set Navigation</span></span>  
 <span data-ttu-id="fdb1d-106">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt mehrere Methoden zum Navigieren durch Elementknoten bereit.</span><span class="sxs-lookup"><span data-stu-id="fdb1d-106">The <xref:System.Xml.XPath.XPathNavigator> class provides several methods used to navigate element nodes.</span></span> <span data-ttu-id="fdb1d-107">In der folgenden Tabelle sind die verfügbaren Navigationsmethoden mit einer Beschreibung ihrer Wirkungsweise aufgeführt. Methoden zur Navigation durch Attribut- und Namespaceknoten sind nicht aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fdb1d-107">The following table shows the navigation methods available and a description of how they move; this does not include methods used to navigate attribute and namespace nodes.</span></span>  
  
 <span data-ttu-id="fdb1d-108">Weitere Informationen zum Auswählen von Knoten in einem <xref:System.Xml.XPath.XPathNavigator>-Objekt finden Sie unter [Auswählen, Auswerten und Zuordnen von XML-Daten mithilfe von XPathNavigator](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="fdb1d-108">For more information about selecting nodes in an <xref:System.Xml.XPath.XPathNavigator> object, see [Selecting, Evaluating and Matching XML Data using XPathNavigator](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md).</span></span> <span data-ttu-id="fdb1d-109">Weitere Informationen zum Navigieren durch Attribut-und Namespaceknoten finden Sie unter [Navigieren durch Attribut- und Namespaceknoten mit XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="fdb1d-109">For more information about navigating attribute and namespace nodes, see [Attribute and Namespace Node Navigation Using XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md).</span></span>  
  
|<span data-ttu-id="fdb1d-110">Methode</span><span class="sxs-lookup"><span data-stu-id="fdb1d-110">Method</span></span>|<span data-ttu-id="fdb1d-111">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="fdb1d-111">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>|<span data-ttu-id="fdb1d-112">Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf die Position des angegebenen <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="fdb1d-112">Moves the <xref:System.Xml.XPath.XPathNavigator> to the same position of the <xref:System.Xml.XPath.XPathNavigator> specified.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>|<span data-ttu-id="fdb1d-113">Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf einen dem aktuellen Knoten untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="fdb1d-113">Moves the <xref:System.Xml.XPath.XPathNavigator> to a child node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>|<span data-ttu-id="fdb1d-114">Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf den ersten dem aktuellen Knoten nebengeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="fdb1d-114">Moves the <xref:System.Xml.XPath.XPathNavigator> to the first sibling node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>|<span data-ttu-id="fdb1d-115">Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf den ersten dem aktuellen Knoten untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="fdb1d-115">Moves the <xref:System.Xml.XPath.XPathNavigator> to the first child node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFollowing%2A>|<span data-ttu-id="fdb1d-116">Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf das nächste Element in Dokumentreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="fdb1d-116">Moves the <xref:System.Xml.XPath.XPathNavigator> to the specified element in document order.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>|<span data-ttu-id="fdb1d-117">Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf den Knoten, der ein Attribut vom Typ `ID` aufweist und einen dem angegebenen <xref:System.String> entsprechenden Wert besitzt.</span><span class="sxs-lookup"><span data-stu-id="fdb1d-117">Moves the <xref:System.Xml.XPath.XPathNavigator> to the node that has an attribute of type `ID` with a value that matches the given <xref:System.String>.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>|<span data-ttu-id="fdb1d-118">Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf den nächsten dem aktuellen Knoten nebengeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="fdb1d-118">Moves the <xref:System.Xml.XPath.XPathNavigator> to the next sibling node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A>|<span data-ttu-id="fdb1d-119">Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf den dem aktuellen Knoten übergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="fdb1d-119">Moves the <xref:System.Xml.XPath.XPathNavigator> to the parent node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>|<span data-ttu-id="fdb1d-120">Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf den vorhergehenden nebengeordneten Knoten des aktuellen Knotens.</span><span class="sxs-lookup"><span data-stu-id="fdb1d-120">Moves the <xref:System.Xml.XPath.XPathNavigator> to the previous sibling node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToRoot%2A>|<span data-ttu-id="fdb1d-121">Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf den Stammknoten des XML-Dokuments.</span><span class="sxs-lookup"><span data-stu-id="fdb1d-121">Moves the <xref:System.Xml.XPath.XPathNavigator> to the root node of the XML document.</span></span>|  
  
## <a name="comments-and-processing-instruction-node-navigation"></a><span data-ttu-id="fdb1d-122">Navigation durch Kommentare und Knoten mit Verarbeitungsanweisungen</span><span class="sxs-lookup"><span data-stu-id="fdb1d-122">Comments and Processing Instruction Node Navigation</span></span>  
 <span data-ttu-id="fdb1d-123">Die folgenden Methoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse sind zum Positionieren auf Kommentare und Verarbeitungsanweisungen in einem XML-Dokument bestimmt.</span><span class="sxs-lookup"><span data-stu-id="fdb1d-123">The following <xref:System.Xml.XPath.XPathNavigator> class methods are valid for moving to comments or processing instructions from other nodes in an XML document.</span></span>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>  
  
## <a name="see-also"></a><span data-ttu-id="fdb1d-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdb1d-124">See also</span></span>

- <xref:System.Xml.XmlDocument>  
- <xref:System.Xml.XPath.XPathDocument>  
- <xref:System.Xml.XPath.XPathNavigator>  
- [<span data-ttu-id="fdb1d-125">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="fdb1d-125">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
- [<span data-ttu-id="fdb1d-126">Das Navigieren durch Attribut- und Namespaceknoten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="fdb1d-126">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)  
- [<span data-ttu-id="fdb1d-127">Extrahieren von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="fdb1d-127">Extract XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/extract-xml-data-using-xpathnavigator.md)  
- [<span data-ttu-id="fdb1d-128">Zugreifen auf streng typisierte XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="fdb1d-128">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
