---
title: In XPath-Abfragen erkannte Knotentypen
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1d33e22d-18e5-43f8-a466-2e3d0a8dd094
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aa004f0def04c7efe2ba7450050a899760b0bbcd
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64590187"
---
# <a name="node-types-recognized-with-xpath-queries"></a><span data-ttu-id="3f6df-102">In XPath-Abfragen erkannte Knotentypen</span><span class="sxs-lookup"><span data-stu-id="3f6df-102">Node Types Recognized with XPath Queries</span></span>
<span data-ttu-id="3f6df-103">Die in einer XPath-Abfrage erkannten Knotentypen sind nicht dieselben wie die Knotentypen des DOM (Document Object Model).</span><span class="sxs-lookup"><span data-stu-id="3f6df-103">The types of nodes recognized in an XPath query are not the same node types found in the Document Object Model (DOM).</span></span>  
  
## <a name="w3c-xpath-node-types"></a><span data-ttu-id="3f6df-104">W3C-XPath-Knotentypen</span><span class="sxs-lookup"><span data-stu-id="3f6df-104">W3C XPath Node Types</span></span>  
 <span data-ttu-id="3f6df-105">Die in einer XPath-Abfrage erkannten Knotentypen sind nicht dieselben Knotentypen wie die Knotentypen des DOM (Document Object Model).</span><span class="sxs-lookup"><span data-stu-id="3f6df-105">The types of nodes recognized in an XPath query are not the types of nodes found in the Document Object Model (DOM).</span></span> <span data-ttu-id="3f6df-106">Es folgen die von der <xref:System.Xml.XPath.XPathNodeType>-Enumeration dargestellten XPath-Knotentypen.</span><span class="sxs-lookup"><span data-stu-id="3f6df-106">The following are the XPath node types represented by the <xref:System.Xml.XPath.XPathNodeType> enumeration.</span></span>  
  
- <xref:System.Xml.XPath.XPathNodeType.All>  
  
- <xref:System.Xml.XPath.XPathNodeType.Attribute>  
  
- <xref:System.Xml.XPath.XPathNodeType.Comment>  
  
- <xref:System.Xml.XPath.XPathNodeType.Element>  
  
- <xref:System.Xml.XPath.XPathNodeType.Namespace>  
  
- <xref:System.Xml.XPath.XPathNodeType.ProcessingInstruction>  
  
- <xref:System.Xml.XPath.XPathNodeType.Root>  
  
- <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace>  
  
- <xref:System.Xml.XPath.XPathNodeType.Text>  
  
- <xref:System.Xml.XPath.XPathNodeType.Whitespace>  
  
 <span data-ttu-id="3f6df-107">Diesen Knotentypen liegt das XPath-Datenmodell zu Grunde, dessen Knoten vom XML-Infoset abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="3f6df-107">These node types are based on the XPath data model, where the nodes are derived from the XML Information Set.</span></span> <span data-ttu-id="3f6df-108">Der <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace>-Knotentyp und der <xref:System.Xml.XPath.XPathNodeType.Whitespace>-Knotentyp sind Microsoft .NET Framework-Erweiterungen der im XPath-Datenmodell beschriebenen Basisknotentypen.</span><span class="sxs-lookup"><span data-stu-id="3f6df-108">The <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace> and <xref:System.Xml.XPath.XPathNodeType.Whitespace> node types are Microsoft .NET Framework extensions to the base node types described in the XPath data model.</span></span>  
  
 <span data-ttu-id="3f6df-109">Der Attributknotentyp wird im XPath-Datenmodell und im DOM unterschiedlich verwendet.</span><span class="sxs-lookup"><span data-stu-id="3f6df-109">The attribute node type is used differently in the XPath data model than it is in the DOM.</span></span> <span data-ttu-id="3f6df-110">Im XPath-Datenmodell ist dem Elementknoten eine Gruppe von Attributknoten zugeordnet, und der Elementknoten ist der übergeordnete Knoten jedes Attributknotens.</span><span class="sxs-lookup"><span data-stu-id="3f6df-110">In the XPath data model, the element node has a set of attribute nodes related to it and the element node is the parent of each attribute node.</span></span> <span data-ttu-id="3f6df-111">Im DOM ist der Elementknoten dagegen der Besitzer und nicht der übergeordnete Knoten.</span><span class="sxs-lookup"><span data-stu-id="3f6df-111">However, in the DOM, the element node is the owner and not the parent.</span></span> <span data-ttu-id="3f6df-112">In beiden Modellen werden Attribut- und Namespaceknoten nicht als untergeordnete Knoten des Elementknotens betrachtet.</span><span class="sxs-lookup"><span data-stu-id="3f6df-112">In both models, attribute and namespace nodes are not considered child nodes of the element node.</span></span>  
  
 <span data-ttu-id="3f6df-113">Der Namespaceknotentyp ist eine Erweiterung des XPath-Datenmodells, der nicht als DOM-Knotentyp erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="3f6df-113">The namespace node type is an addition to the XPath data model and is not a recognized DOM node type.</span></span>  
  
 <span data-ttu-id="3f6df-114">Weitere Informationen zum Navigieren durch Element-, Attribut-und Namespaceknoten finden Sie in den Themen [Navigieren in Knotengruppen mit XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md) und [Navigieren durch Attribut- und Namespaceknoten mit XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="3f6df-114">For more information about navigating element, attribute, and namespace nodes, see the [Node Set Navigation Using XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md) and [Attribute and Namespace Node Navigation Using XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md) topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f6df-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f6df-115">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="3f6df-116">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="3f6df-116">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="3f6df-117">Auswählen von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="3f6df-117">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="3f6df-118">Auswerten von XPath-Ausdrücken mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="3f6df-118">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="3f6df-119">Vergleich von Knoten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="3f6df-119">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)
- [<span data-ttu-id="3f6df-120">XPath-Abfragen und Namespaces</span><span class="sxs-lookup"><span data-stu-id="3f6df-120">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)
- [<span data-ttu-id="3f6df-121">Kompilierte XPath-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="3f6df-121">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
