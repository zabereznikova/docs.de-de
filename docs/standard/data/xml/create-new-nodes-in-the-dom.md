---
title: Erstellen von neuen Knoten im Dokumentobjektmodell
ms.date: 03/30/2017
ms.assetid: 6c2b9789-b61a-49f9-b33f-db01a945edf2
ms.openlocfilehash: dea7add100fbdbb9e761fe39d0d824d27975757f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704746"
---
# <a name="create-new-nodes-in-the-dom"></a><span data-ttu-id="545f4-102">Erstellen von neuen Knoten im Dokumentobjektmodell</span><span class="sxs-lookup"><span data-stu-id="545f4-102">Create New Nodes in the DOM</span></span>

<span data-ttu-id="545f4-103">Das <xref:System.Xml.XmlDocument> verfügt über eine create-Methode für alle Knotentypen.</span><span class="sxs-lookup"><span data-stu-id="545f4-103">The <xref:System.Xml.XmlDocument> has a create method for all of the node types.</span></span> <span data-ttu-id="545f4-104">Stellen Sie der Methode, falls erforderlich, einen Namen und Inhalt oder andere Parameter für die Knoten bereit, die Inhalt aufweisen (z. B. ein Textknoten), und der Knoten wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="545f4-104">Supply the method with a name when required, and content or other parameters for those nodes that have content (for example, a text node), and the node is created.</span></span> <span data-ttu-id="545f4-105">Für die folgenden Methoden muss ein Name angegeben sein und es müssen einige andere Parameter ausgefüllt sein, damit ein entsprechender Knoten erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="545f4-105">The following methods are ones that need a name and a few other parameters filled to create an appropriate node.</span></span>  
  
- <xref:System.Xml.XmlDocument.CreateCDataSection%2A>  
  
- <xref:System.Xml.XmlDocument.CreateComment%2A>  
  
- <xref:System.Xml.XmlDocument.CreateDocumentFragment%2A>  
  
- <xref:System.Xml.XmlDocument.CreateDocumentType%2A>  
  
- <xref:System.Xml.XmlDocument.CreateElement%2A>  
  
- <xref:System.Xml.XmlDocument.CreateNode%2A>  
  
- <xref:System.Xml.XmlDocument.CreateProcessingInstruction%2A>  
  
- <xref:System.Xml.XmlDocument.CreateSignificantWhitespace%2A>  
  
- <xref:System.Xml.XmlDocument.CreateTextNode%2A>  
  
- <xref:System.Xml.XmlDocument.CreateWhitespace%2A>  
  
- <xref:System.Xml.XmlDocument.CreateXmlDeclaration%2A>  
  
 <span data-ttu-id="545f4-106">Für andere Knoten müssen über das Bereitstellen von Daten für Parameter hinausgehende Anforderungen erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="545f4-106">Other node types have more requirements than just providing data to parameters.</span></span>  
  
 <span data-ttu-id="545f4-107">Informationen zu Attributen finden Sie unter [Erstellen von neuen Attributen für Elemente im Dokumentobjektmodell](creating-new-attributes-for-elements-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="545f4-107">For information on attributes, see [Creating New Attributes for Elements in the DOM](creating-new-attributes-for-elements-in-the-dom.md).</span></span> <span data-ttu-id="545f4-108">Informationen zur Validierung von Element- und Attributnamen finden Sie unter [Überprüfen von XML-Element- und -Attributnamen beim Erstellen neuer Knoten](xml-element-and-attribute-name-verification-when-creating-new-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="545f4-108">For information on element and attribute name validation, see [XML Element and Attribute Name Verification when Creating New Nodes](xml-element-and-attribute-name-verification-when-creating-new-nodes.md).</span></span> <span data-ttu-id="545f4-109">Informationen zum Erstellen von Entitätsverweisen finden Sie unter [Erstellen von neuen Entitätsverweisen](creating-new-entity-references.md).</span><span class="sxs-lookup"><span data-stu-id="545f4-109">For creating entity references, see [Creating New Entity References](creating-new-entity-references.md).</span></span> <span data-ttu-id="545f4-110">Informationen dazu, welche Auswirkungen Namespaces auf die Erweiterung von Entitätsverweisen haben, finden Sie unter [Auswirkungen von Namespaces auf die Entitätsverweiserweiterung für neue Knoten mit Elementen und Attributen](namespace-affect-on-entity-ref-expansion-for-new-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="545f4-110">For information on how namespaces affect the expansion of entity references, see [Namespace Affect on Entity Reference Expansion for New Nodes Containing Elements and Attributes](namespace-affect-on-entity-ref-expansion-for-new-nodes.md).</span></span>  
  
 <span data-ttu-id="545f4-111">Nach dem Erstellen von neuen Knoten stehen verschiedene Methoden zum Einfügen der Knoten in die Struktur zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="545f4-111">Once new nodes are created, there are several methods available to insert them into the tree.</span></span> <span data-ttu-id="545f4-112">In der Tabelle sind die Methoden und eine Beschreibung der Position des neuen Knotens im XML-DOM (Dokumentobjektmodell) aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="545f4-112">The table lists the methods with a description of where the new node appears in the XML Document Object Model (DOM).</span></span>  
  
|<span data-ttu-id="545f4-113">Methode</span><span class="sxs-lookup"><span data-stu-id="545f4-113">Method</span></span>|<span data-ttu-id="545f4-114">Knotenposition</span><span class="sxs-lookup"><span data-stu-id="545f4-114">Node placement</span></span>|  
|------------|--------------------|  
|<xref:System.Xml.XmlNode.InsertBefore%2A>|<span data-ttu-id="545f4-115">Vor dem Referenzknoten eingefügt.</span><span class="sxs-lookup"><span data-stu-id="545f4-115">Inserted before the reference node.</span></span> <span data-ttu-id="545f4-116">So fügen Sie beispielsweise den neuen Knoten an Position 5 ein:</span><span class="sxs-lookup"><span data-stu-id="545f4-116">For example, to insert the new node in position 5:</span></span><br /><br /> `Dim refChild As XmlNode = node.ChildNodes(4) 'The reference is zero-based.node.InsertBefore(newChild, refChild);`<br /><br /> `XmlNode refChild = node.ChildNodes[4]; //The reference is zero-based. node.InsertBefore(newChild, refChild);`<br /><br /> <span data-ttu-id="545f4-117">Weitere Informationen finden Sie unter der Methode <xref:System.Xml.XmlNode.InsertBefore%2A>.</span><span class="sxs-lookup"><span data-stu-id="545f4-117">For more information, see the <xref:System.Xml.XmlNode.InsertBefore%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.InsertAfter%2A>|<span data-ttu-id="545f4-118">Nach dem Referenzknoten eingefügt.</span><span class="sxs-lookup"><span data-stu-id="545f4-118">Inserted after the reference node.</span></span> <span data-ttu-id="545f4-119">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="545f4-119">For example:</span></span><br /><br /> `node.InsertAfter(newChild, refChild)`<br /><br /> `node.InsertAfter(newChild, refChild);`<br /><br /> <span data-ttu-id="545f4-120">Weitere Informationen finden Sie unter der Methode <xref:System.Xml.XmlNode.InsertAfter%2A>.</span><span class="sxs-lookup"><span data-stu-id="545f4-120">For more information, see the <xref:System.Xml.XmlNode.InsertAfter%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.AppendChild%2A>|<span data-ttu-id="545f4-121">Fügt den Knoten am Ende der Liste der untergeordneten Knoten für den angegebenen Knoten an.</span><span class="sxs-lookup"><span data-stu-id="545f4-121">Adds the node to the end of the list of child nodes for the given node.</span></span> <span data-ttu-id="545f4-122">Wenn der Knoten, der hinzugefügt wird, ein <xref:System.Xml.XmlDocumentFragment> ist, wird der gesamte Inhalt des Dokumentfragments in die Liste der untergeordneten Elemente dieses Knotens verschoben.</span><span class="sxs-lookup"><span data-stu-id="545f4-122">If the node being added is an <xref:System.Xml.XmlDocumentFragment>, the entire contents of the document fragment are moved into the child list of this node.</span></span> <span data-ttu-id="545f4-123">Weitere Informationen finden Sie unter der Methode <xref:System.Xml.XmlNode.AppendChild%2A>.</span><span class="sxs-lookup"><span data-stu-id="545f4-123">For more information, see the <xref:System.Xml.XmlNode.AppendChild%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.PrependChild%2A>|<span data-ttu-id="545f4-124">Fügt den Knoten am Anfang der Liste der untergeordneten Knoten für den angegebenen Knoten an.</span><span class="sxs-lookup"><span data-stu-id="545f4-124">Adds the node to the beginning of the list of child nodes of the given node.</span></span> <span data-ttu-id="545f4-125">Wenn der Knoten, der hinzugefügt wird, ein <xref:System.Xml.XmlDocumentFragment> ist, wird der gesamte Inhalt des Dokumentfragments in die Liste der untergeordneten Elemente dieses Knotens verschoben.</span><span class="sxs-lookup"><span data-stu-id="545f4-125">If the node being added is an <xref:System.Xml.XmlDocumentFragment>, the entire contents of the document fragment are moved into the child list of this node.</span></span> <span data-ttu-id="545f4-126">Weitere Informationen finden Sie unter der Methode <xref:System.Xml.XmlNode.PrependChild%2A>.</span><span class="sxs-lookup"><span data-stu-id="545f4-126">For more information, see the <xref:System.Xml.XmlNode.PrependChild%2A> method.</span></span>|  
|<xref:System.Xml.XmlAttributeCollection.Append%2A>|<span data-ttu-id="545f4-127">Fügt am Ende der einem Element zugeordneten Attributauflistung einen <xref:System.Xml.XmlAttribute>-Knoten an.</span><span class="sxs-lookup"><span data-stu-id="545f4-127">Appends an <xref:System.Xml.XmlAttribute> node to the end of the attribute collection associated with an element.</span></span> <span data-ttu-id="545f4-128">Weitere Informationen finden Sie unter der Methode <xref:System.Xml.XmlAttributeCollection.Append%2A>.</span><span class="sxs-lookup"><span data-stu-id="545f4-128">For more information, see the <xref:System.Xml.XmlAttributeCollection.Append%2A> method.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="545f4-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="545f4-129">See also</span></span>

- [<span data-ttu-id="545f4-130">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="545f4-130">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
