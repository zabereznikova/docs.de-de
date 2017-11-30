---
title: Verarbeiten von XML-Daten mithilfe des DOM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56b6e9c7-ed82-4a65-a647-7be32c83bcc8
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 06c8b2e130dbecaca4c08684d030c8dcef1cd5a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="process-xml-data-using-the-dom-model"></a><span data-ttu-id="cd495-102">Verarbeiten von XML-Daten mithilfe des DOM</span><span class="sxs-lookup"><span data-stu-id="cd495-102">Process XML Data Using the DOM Model</span></span>
<span data-ttu-id="cd495-103">Das XML-DOM (Dokumentobjektmodell) behandelt XML-Daten wie eine Standardgruppe von Objekten und wird zur Verarbeitung von XML-Daten im Speicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd495-103">The XML Document Object Model (DOM) treats XML data as a standard set of objects and is used to process XML data in memory.</span></span> <span data-ttu-id="cd495-104">Der `System.Xml`-Namespace bietet eine programmgesteuerte Darstellung von XML-Dokumenten, XML-Fragmenten, XML-Knoten und XML-Knotengruppen.</span><span class="sxs-lookup"><span data-stu-id="cd495-104">The `System.Xml` namespace provides a programmatic representation of XML documents, fragments, nodes, or node-sets.</span></span> <span data-ttu-id="cd495-105">Diese basiert auf den W3C-Empfehlungen (World Wide Web Consortium) zu DOM Level 1 Core und DOM Level 2 Core.</span><span class="sxs-lookup"><span data-stu-id="cd495-105">It is based on the World Wide Web Consortium (W3C) DOM Level 1 Core and the DOM Level 2 Core recommendations.</span></span>  
  
 <span data-ttu-id="cd495-106">Die <xref:System.Xml.XmlDocument>-Klasse stellt ein XML-Dokument dar.</span><span class="sxs-lookup"><span data-stu-id="cd495-106">The <xref:System.Xml.XmlDocument> class represents an XML document.</span></span> <span data-ttu-id="cd495-107">Sie enthält Member zum Abrufen und Erstellen aller anderen XML-Objekte.</span><span class="sxs-lookup"><span data-stu-id="cd495-107">It includes members for retrieving and creating all other XML objects.</span></span> <span data-ttu-id="cd495-108">Mit dem <xref:System.Xml.XmlDocument> und seinen verwandten Klassen können Sie XML-Dokumente erstellen, Daten laden und auf diese zugreifen, Daten ändern und Änderungen speichern.</span><span class="sxs-lookup"><span data-stu-id="cd495-108">Using the <xref:System.Xml.XmlDocument>, and its related classes, you can construct XML documents, load and access data, modify data, and save changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cd495-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cd495-109">In This Section</span></span>  
  
-   [<span data-ttu-id="cd495-110">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="cd495-110">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)  
  
-   [<span data-ttu-id="cd495-111">XML-Knotentypen</span><span class="sxs-lookup"><span data-stu-id="cd495-111">Types of XML Nodes</span></span>](../../../../docs/standard/data/xml/types-of-xml-nodes.md)  
  
-   [<span data-ttu-id="cd495-112">XML-Dokument (DOM)-Objektmodellhierarchie</span><span class="sxs-lookup"><span data-stu-id="cd495-112">XML Document Object Model (DOM) Hierarchy</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md)  
  
-   [<span data-ttu-id="cd495-113">Zuordnen der Objekthierarchie zu XML-Daten</span><span class="sxs-lookup"><span data-stu-id="cd495-113">Mapping the Object Hierarchy to XML Data</span></span>](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md)  
  
-   [<span data-ttu-id="cd495-114">Erstellen eines XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="cd495-114">XML Document Creation</span></span>](../../../../docs/standard/data/xml/xml-document-creation.md)  
  
-   [<span data-ttu-id="cd495-115">Lesen eines XML-Dokuments in das DOM</span><span class="sxs-lookup"><span data-stu-id="cd495-115">Reading an XML Document into the DOM</span></span>](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md)  
  
-   [<span data-ttu-id="cd495-116">Einfügen von Knoten in einem XML-Dokument</span><span class="sxs-lookup"><span data-stu-id="cd495-116">Inserting Nodes into an XML Document</span></span>](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md)  
  
-   [<span data-ttu-id="cd495-117">Entfernen von Knoten, Inhalten und Werten aus einem XML-Dokument</span><span class="sxs-lookup"><span data-stu-id="cd495-117">Removing Nodes, Content, and Values from an XML Document</span></span>](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md)  
  
-   [<span data-ttu-id="cd495-118">Ändern von Knoten, Inhalten und Werten in einem XML-Dokument</span><span class="sxs-lookup"><span data-stu-id="cd495-118">Modifying Nodes, Content, and Values in an XML Document</span></span>](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md)  
  
-   [<span data-ttu-id="cd495-119">Validieren eines XML-Dokuments im DOKUMENTOBJEKTMODELL</span><span class="sxs-lookup"><span data-stu-id="cd495-119">Validating an XML Document in the DOM</span></span>](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)  
  
-   [<span data-ttu-id="cd495-120">Speichern und Ausgeben eines Dokuments</span><span class="sxs-lookup"><span data-stu-id="cd495-120">Saving and Writing a Document</span></span>](../../../../docs/standard/data/xml/saving-and-writing-a-document.md)  
  
-   [<span data-ttu-id="cd495-121">Auswählen von Knoten mithilfe von XPath-Navigation</span><span class="sxs-lookup"><span data-stu-id="cd495-121">Select Nodes Using XPath Navigation</span></span>](../../../../docs/standard/data/xml/select-nodes-using-xpath-navigation.md)  
  
-   [<span data-ttu-id="cd495-122">Auflösen von externen Ressourcen</span><span class="sxs-lookup"><span data-stu-id="cd495-122">Resolving External Resources</span></span>](../../../../docs/standard/data/xml/resolving-external-resources.md)  
  
-   [<span data-ttu-id="cd495-123">Vergleich von Objekt mit "XmlNameTable"</span><span class="sxs-lookup"><span data-stu-id="cd495-123">Object Comparison Using XmlNameTable</span></span>](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md)  
  
-   [<span data-ttu-id="cd495-124">Knotenauflistungen in "NamedNodeMaps" und "NodeLists"</span><span class="sxs-lookup"><span data-stu-id="cd495-124">Node Collections in NamedNodeMaps and NodeLists</span></span>](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md)  
  
-   [<span data-ttu-id="cd495-125">Dynamische Updates von "NodeLists" und "NamedNodeMaps"</span><span class="sxs-lookup"><span data-stu-id="cd495-125">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>](../../../../docs/standard/data/xml/dynamic-updates-to-nodelists-and-namednodemaps.md)  
  
-   [<span data-ttu-id="cd495-126">Namespace-Unterstützung in das DOM</span><span class="sxs-lookup"><span data-stu-id="cd495-126">Namespace Support in the DOM</span></span>](../../../../docs/standard/data/xml/namespace-support-in-the-dom.md)  
  
-   [<span data-ttu-id="cd495-127">Ereignisbehandlung in einem XML-Dokument mit "XmlNodeChangedEventArgs"</span><span class="sxs-lookup"><span data-stu-id="cd495-127">Event Handling in an XML Document Using the XmlNodeChangedEventArgs</span></span>](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md)  
  
-   [<span data-ttu-id="cd495-128">Erweitern des DOM</span><span class="sxs-lookup"><span data-stu-id="cd495-128">Extending the DOM</span></span>](../../../../docs/standard/data/xml/extending-the-dom.md)  
  
## <a name="related-sections"></a><span data-ttu-id="cd495-129">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="cd495-129">Related Sections</span></span>  
 [<span data-ttu-id="cd495-130">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="cd495-130">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 <span data-ttu-id="cd495-131">Erläutert die XML-Verarbeitung mithilfe der <xref:System.Xml.XPath.XPathNavigator>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="cd495-131">Discusses XML processing using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>
