---
title: In XPath-Abfragen erkannte Knotentypen
ms.date: 03/30/2017
ms.assetid: 1d33e22d-18e5-43f8-a466-2e3d0a8dd094
ms.openlocfilehash: bfc94958dbe54f05773a3adfcdfa9bf1c7ee8037
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734082"
---
# <a name="node-types-recognized-with-xpath-queries"></a><span data-ttu-id="553c7-102">In XPath-Abfragen erkannte Knotentypen</span><span class="sxs-lookup"><span data-stu-id="553c7-102">Node Types Recognized with XPath Queries</span></span>

<span data-ttu-id="553c7-103">Die in einer XPath-Abfrage erkannten Knotentypen sind nicht dieselben wie die Knotentypen des DOM (Document Object Model).</span><span class="sxs-lookup"><span data-stu-id="553c7-103">The types of nodes recognized in an XPath query are not the same node types found in the Document Object Model (DOM).</span></span>  
  
## <a name="w3c-xpath-node-types"></a><span data-ttu-id="553c7-104">W3C-XPath-Knotentypen</span><span class="sxs-lookup"><span data-stu-id="553c7-104">W3C XPath Node Types</span></span>  

 <span data-ttu-id="553c7-105">Die in einer XPath-Abfrage erkannten Knotentypen sind nicht dieselben Knotentypen wie die Knotentypen des DOM (Document Object Model).</span><span class="sxs-lookup"><span data-stu-id="553c7-105">The types of nodes recognized in an XPath query are not the types of nodes found in the Document Object Model (DOM).</span></span> <span data-ttu-id="553c7-106">Es folgen die von der <xref:System.Xml.XPath.XPathNodeType>-Enumeration dargestellten XPath-Knotentypen.</span><span class="sxs-lookup"><span data-stu-id="553c7-106">The following are the XPath node types represented by the <xref:System.Xml.XPath.XPathNodeType> enumeration.</span></span>  
  
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
  
 <span data-ttu-id="553c7-107">Diesen Knotentypen liegt das XPath-Datenmodell zu Grunde, dessen Knoten vom XML-Infoset abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="553c7-107">These node types are based on the XPath data model, where the nodes are derived from the XML Information Set.</span></span> <span data-ttu-id="553c7-108">Der <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace>-Knotentyp und der <xref:System.Xml.XPath.XPathNodeType.Whitespace>-Knotentyp sind Microsoft .NET Framework-Erweiterungen der im XPath-Datenmodell beschriebenen Basisknotentypen.</span><span class="sxs-lookup"><span data-stu-id="553c7-108">The <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace> and <xref:System.Xml.XPath.XPathNodeType.Whitespace> node types are Microsoft .NET Framework extensions to the base node types described in the XPath data model.</span></span>  
  
 <span data-ttu-id="553c7-109">Der Attributknotentyp wird im XPath-Datenmodell und im DOM unterschiedlich verwendet.</span><span class="sxs-lookup"><span data-stu-id="553c7-109">The attribute node type is used differently in the XPath data model than it is in the DOM.</span></span> <span data-ttu-id="553c7-110">Im XPath-Datenmodell ist dem Elementknoten eine Gruppe von Attributknoten zugeordnet, und der Elementknoten ist der übergeordnete Knoten jedes Attributknotens.</span><span class="sxs-lookup"><span data-stu-id="553c7-110">In the XPath data model, the element node has a set of attribute nodes related to it and the element node is the parent of each attribute node.</span></span> <span data-ttu-id="553c7-111">Im DOM ist der Elementknoten dagegen der Besitzer und nicht der übergeordnete Knoten.</span><span class="sxs-lookup"><span data-stu-id="553c7-111">However, in the DOM, the element node is the owner and not the parent.</span></span> <span data-ttu-id="553c7-112">In beiden Modellen werden Attribut- und Namespaceknoten nicht als untergeordnete Knoten des Elementknotens betrachtet.</span><span class="sxs-lookup"><span data-stu-id="553c7-112">In both models, attribute and namespace nodes are not considered child nodes of the element node.</span></span>  
  
 <span data-ttu-id="553c7-113">Der Namespaceknotentyp ist eine Erweiterung des XPath-Datenmodells, der nicht als DOM-Knotentyp erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="553c7-113">The namespace node type is an addition to the XPath data model and is not a recognized DOM node type.</span></span>  
  
 <span data-ttu-id="553c7-114">Weitere Informationen zum Navigieren durch Element-, Attribut-und Namespaceknoten finden Sie in den Themen [Navigieren in Knotengruppen mit XPathNavigator](node-set-navigation-using-xpathnavigator.md) und [Navigieren durch Attribut- und Namespaceknoten mit XPathNavigator](attribute-and-namespace-node-navigation-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="553c7-114">For more information about navigating element, attribute, and namespace nodes, see the [Node Set Navigation Using XPathNavigator](node-set-navigation-using-xpathnavigator.md) and [Attribute and Namespace Node Navigation Using XPathNavigator](attribute-and-namespace-node-navigation-using-xpathnavigator.md) topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="553c7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="553c7-115">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="553c7-116">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="553c7-116">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="553c7-117">Auswählen von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="553c7-117">Select XML Data Using XPathNavigator</span></span>](select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="553c7-118">Auswerten von XPath-Ausdrücken mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="553c7-118">Evaluate XPath Expressions using XPathNavigator</span></span>](evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="553c7-119">Vergleich von Knoten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="553c7-119">Matching Nodes using XPathNavigator</span></span>](matching-nodes-using-xpathnavigator.md)
- [<span data-ttu-id="553c7-120">XPath-Abfragen und Namespaces</span><span class="sxs-lookup"><span data-stu-id="553c7-120">XPath Queries and Namespaces</span></span>](xpath-queries-and-namespaces.md)
- [<span data-ttu-id="553c7-121">Kompilierte XPath-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="553c7-121">Compiled XPath Expressions</span></span>](compiled-xpath-expressions.md)
