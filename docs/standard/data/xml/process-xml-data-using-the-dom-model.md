---
title: Verarbeiten von XML-Daten mithilfe des DOM
ms.date: 03/30/2017
ms.assetid: 56b6e9c7-ed82-4a65-a647-7be32c83bcc8
ms.openlocfilehash: 2608008f33eb8bc0dd0a9b5fe96e619df6138b51
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830908"
---
# <a name="process-xml-data-using-the-dom-model"></a><span data-ttu-id="e3aa0-102">Verarbeiten von XML-Daten mithilfe des DOM</span><span class="sxs-lookup"><span data-stu-id="e3aa0-102">Process XML Data Using the DOM Model</span></span>
<span data-ttu-id="e3aa0-103">Das XML-DOM (Dokumentobjektmodell) behandelt XML-Daten wie eine Standardgruppe von Objekten und wird zur Verarbeitung von XML-Daten im Speicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="e3aa0-103">The XML Document Object Model (DOM) treats XML data as a standard set of objects and is used to process XML data in memory.</span></span> <span data-ttu-id="e3aa0-104">Der `System.Xml`-Namespace bietet eine programmgesteuerte Darstellung von XML-Dokumenten, XML-Fragmenten, XML-Knoten und XML-Knotengruppen.</span><span class="sxs-lookup"><span data-stu-id="e3aa0-104">The `System.Xml` namespace provides a programmatic representation of XML documents, fragments, nodes, or node-sets.</span></span> <span data-ttu-id="e3aa0-105">Diese basiert auf den W3C-Empfehlungen (World Wide Web Consortium) zu DOM Level 1 Core und DOM Level 2 Core.</span><span class="sxs-lookup"><span data-stu-id="e3aa0-105">It is based on the World Wide Web Consortium (W3C) DOM Level 1 Core and the DOM Level 2 Core recommendations.</span></span>  
  
 <span data-ttu-id="e3aa0-106">Die <xref:System.Xml.XmlDocument>-Klasse stellt ein XML-Dokument dar.</span><span class="sxs-lookup"><span data-stu-id="e3aa0-106">The <xref:System.Xml.XmlDocument> class represents an XML document.</span></span> <span data-ttu-id="e3aa0-107">Sie enthält Member zum Abrufen und Erstellen aller anderen XML-Objekte.</span><span class="sxs-lookup"><span data-stu-id="e3aa0-107">It includes members for retrieving and creating all other XML objects.</span></span> <span data-ttu-id="e3aa0-108">Mit dem <xref:System.Xml.XmlDocument> und seinen verwandten Klassen können Sie XML-Dokumente erstellen, Daten laden und auf diese zugreifen, Daten ändern und Änderungen speichern.</span><span class="sxs-lookup"><span data-stu-id="e3aa0-108">Using the <xref:System.Xml.XmlDocument>, and its related classes, you can construct XML documents, load and access data, modify data, and save changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e3aa0-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e3aa0-109">In This Section</span></span>  
  
- [<span data-ttu-id="e3aa0-110">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="e3aa0-110">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)  
  
- [<span data-ttu-id="e3aa0-111">XML-Knotentypen</span><span class="sxs-lookup"><span data-stu-id="e3aa0-111">Types of XML Nodes</span></span>](types-of-xml-nodes.md)  
  
- [<span data-ttu-id="e3aa0-112">Hierarchie im XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="e3aa0-112">XML Document Object Model (DOM) Hierarchy</span></span>](xml-document-object-model-dom-hierarchy.md)  
  
- [<span data-ttu-id="e3aa0-113">Zuordnen der Objekthierarchie zu XML-Daten</span><span class="sxs-lookup"><span data-stu-id="e3aa0-113">Mapping the Object Hierarchy to XML Data</span></span>](mapping-the-object-hierarchy-to-xml-data.md)  
  
- [<span data-ttu-id="e3aa0-114">Erstellen eines XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="e3aa0-114">XML Document Creation</span></span>](xml-document-creation.md)  
  
- [<span data-ttu-id="e3aa0-115">Einlesen eines XML-Dokuments in das DOM</span><span class="sxs-lookup"><span data-stu-id="e3aa0-115">Reading an XML Document into the DOM</span></span>](reading-an-xml-document-into-the-dom.md)  
  
- [<span data-ttu-id="e3aa0-116">Einfügen von Knoten in ein XML-Dokument</span><span class="sxs-lookup"><span data-stu-id="e3aa0-116">Inserting Nodes into an XML Document</span></span>](inserting-nodes-into-an-xml-document.md)  
  
- [<span data-ttu-id="e3aa0-117">Entfernen von Knoten, Inhalten und Werten aus einem XML-Dokument</span><span class="sxs-lookup"><span data-stu-id="e3aa0-117">Removing Nodes, Content, and Values from an XML Document</span></span>](removing-nodes-content-and-values-from-an-xml-document.md)  
  
- [<span data-ttu-id="e3aa0-118">Ändern von Knoten, Inhalten und Werten in einem XML-Dokument</span><span class="sxs-lookup"><span data-stu-id="e3aa0-118">Modifying Nodes, Content, and Values in an XML Document</span></span>](modifying-nodes-content-and-values-in-an-xml-document.md)  
  
- [<span data-ttu-id="e3aa0-119">Validieren eines XML-Dokuments im DOM</span><span class="sxs-lookup"><span data-stu-id="e3aa0-119">Validating an XML Document in the DOM</span></span>](validating-an-xml-document-in-the-dom.md)  
  
- [<span data-ttu-id="e3aa0-120">Speichern und Ausgeben eines Dokuments</span><span class="sxs-lookup"><span data-stu-id="e3aa0-120">Saving and Writing a Document</span></span>](saving-and-writing-a-document.md)  
  
- [<span data-ttu-id="e3aa0-121">Auswählen von Knoten mithilfe der XPath-Navigation</span><span class="sxs-lookup"><span data-stu-id="e3aa0-121">Select Nodes Using XPath Navigation</span></span>](select-nodes-using-xpath-navigation.md)  
  
- [<span data-ttu-id="e3aa0-122">Auflösen von externen Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e3aa0-122">Resolving External Resources</span></span>](resolving-external-resources.md)  
  
- [<span data-ttu-id="e3aa0-123">Objektvergleich mit „XmlNameTable“</span><span class="sxs-lookup"><span data-stu-id="e3aa0-123">Object Comparison Using XmlNameTable</span></span>](object-comparison-using-xmlnametable.md)  
  
- [<span data-ttu-id="e3aa0-124">Knotensammlungen in „NamedNodeMaps“ und „NodeLists“</span><span class="sxs-lookup"><span data-stu-id="e3aa0-124">Node Collections in NamedNodeMaps and NodeLists</span></span>](node-collections-in-namednodemaps-and-nodelists.md)  
  
- [<span data-ttu-id="e3aa0-125">Dynamische Updates von „NodeLists“ und „NamedNodeMaps“</span><span class="sxs-lookup"><span data-stu-id="e3aa0-125">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>](dynamic-updates-to-nodelists-and-namednodemaps.md)  
  
- [<span data-ttu-id="e3aa0-126">Namespaceunterstützung im DOM</span><span class="sxs-lookup"><span data-stu-id="e3aa0-126">Namespace Support in the DOM</span></span>](namespace-support-in-the-dom.md)  
  
- [<span data-ttu-id="e3aa0-127">Ereignisbehandlung in einem XML-Dokument mit „XmlNodeChangedEventArgs“</span><span class="sxs-lookup"><span data-stu-id="e3aa0-127">Event Handling in an XML Document Using the XmlNodeChangedEventArgs</span></span>](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md)  
  
- [<span data-ttu-id="e3aa0-128">Erweitern des DOM</span><span class="sxs-lookup"><span data-stu-id="e3aa0-128">Extending the DOM</span></span>](extending-the-dom.md)  
  
## <a name="related-sections"></a><span data-ttu-id="e3aa0-129">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="e3aa0-129">Related Sections</span></span>  
 [<span data-ttu-id="e3aa0-130">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="e3aa0-130">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)  
 <span data-ttu-id="e3aa0-131">Erläutert die XML-Verarbeitung mithilfe der <xref:System.Xml.XPath.XPathNavigator>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="e3aa0-131">Discusses XML processing using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>
