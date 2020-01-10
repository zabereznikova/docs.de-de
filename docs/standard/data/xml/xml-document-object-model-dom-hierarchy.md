---
title: Hierarchie im XML-Dokumentobjektmodell (DOM)
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
ms.openlocfilehash: 1193d7631816fe9fbf7aa1984d79ef8e61d5da80
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709971"
---
# <a name="xml-document-object-model-dom-hierarchy"></a><span data-ttu-id="c1e03-102">Hierarchie im XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="c1e03-102">XML Document Object Model (DOM) Hierarchy</span></span>
<span data-ttu-id="c1e03-103">In der folgenden Abbildung wird die Klassenhierarchie für das XML-Document Object Model (DOM – Dokumentobjektmodell) veranschaulicht; dabei ist der W3C-Name (World Wide Web Consortium) an den relevanten Stellen zusammen mit dem Klassennamen angegeben.</span><span class="sxs-lookup"><span data-stu-id="c1e03-103">The following illustration shows the class hierarchy for the XML Document Object Model (DOM), with the World Wide Web Consortium (W3C) name in parenthesis along with the class name where it is relevant.</span></span>  
  
 <span data-ttu-id="c1e03-104">![XML- &#40;Dokumentobjektmodell&#41; Dom-Hierarchie](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="c1e03-104">![XML Document Object Model &#40;DOM&#41; hierarchy](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span></span>  
<span data-ttu-id="c1e03-105">Hierarchie im XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="c1e03-105">XML Document Object Model (DOM) hierarchy</span></span>  
  
 <span data-ttu-id="c1e03-106">Die folgenden Klassen erben nicht vom **XmlNode**:</span><span class="sxs-lookup"><span data-stu-id="c1e03-106">The following classes do not inherit from the **XmlNode**:</span></span>  
  
- <span data-ttu-id="c1e03-107">**XmlImplementation**</span><span class="sxs-lookup"><span data-stu-id="c1e03-107">**XmlImplementation**</span></span>  
  
- <span data-ttu-id="c1e03-108">**XmlNamedNodeMap**</span><span class="sxs-lookup"><span data-stu-id="c1e03-108">**XmlNamedNodeMap**</span></span>  
  
- <span data-ttu-id="c1e03-109">**XmlNodeList**</span><span class="sxs-lookup"><span data-stu-id="c1e03-109">**XmlNodeList**</span></span>  
  
- <span data-ttu-id="c1e03-110">**XmlNodeChangedEventArgs**</span><span class="sxs-lookup"><span data-stu-id="c1e03-110">**XmlNodeChangedEventArgs**</span></span>  
  
 <span data-ttu-id="c1e03-111">Die **XmlImplementation**-Klasse wird zum Erstellen eines XML-Dokuments verwendet.</span><span class="sxs-lookup"><span data-stu-id="c1e03-111">The **XmlImplementation** class is used to create an XML document.</span></span> <span data-ttu-id="c1e03-112">Weitere Informationen finden Sie unter [Erstellen eines XML-Dokuments](../../../../docs/standard/data/xml/xml-document-creation.md).</span><span class="sxs-lookup"><span data-stu-id="c1e03-112">For more information, see [XML Document Creation](../../../../docs/standard/data/xml/xml-document-creation.md).</span></span>  
  
 <span data-ttu-id="c1e03-113">Die **XmlNamedNodeMap**-Klasse behandelt eine ungeordnete Knotengruppe.</span><span class="sxs-lookup"><span data-stu-id="c1e03-113">The **XmlNamedNodeMap** class handles an unordered set of nodes.</span></span> <span data-ttu-id="c1e03-114">Weitere Informationen finden Sie unter [Abrufen von ungeordneten Knoten anhand des Namens oder Indexes](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span><span class="sxs-lookup"><span data-stu-id="c1e03-114">For more information, see [Unordered Node Retrieval by Name or Index](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span></span>  
  
 <span data-ttu-id="c1e03-115">Die **XmlNodeList**-Klasse behandelt eine geordnete Knotenliste.</span><span class="sxs-lookup"><span data-stu-id="c1e03-115">The **XmlNodeList** class handles an ordered list of nodes.</span></span> <span data-ttu-id="c1e03-116">Weitere Informationen finden Sie unter [Abrufen von geordneten Knoten anhand des Indexes](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span><span class="sxs-lookup"><span data-stu-id="c1e03-116">For more information, see [Ordered Node Retrieval by Index](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span></span>  
  
 <span data-ttu-id="c1e03-117">Die **XmlNodeChangedEventArgs**-Klasse behandelt Ereignishandler, die im **XmlDocument** registriert sind.</span><span class="sxs-lookup"><span data-stu-id="c1e03-117">The **XmlNodeChangedEventArgs** class handles event handlers registered on the **XmlDocument**.</span></span> <span data-ttu-id="c1e03-118">Weitere Informationen finden Sie unter [Ereignisbehandlung in einem XML-Dokument mit „XmlNodeChangedEventArgs“](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span><span class="sxs-lookup"><span data-stu-id="c1e03-118">For more information, see [Event Handling in an XML Document using the XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span></span>  
  
 <span data-ttu-id="c1e03-119">Die **XmlLinkedNode**-Klasse erbt vom **XmlNode**.</span><span class="sxs-lookup"><span data-stu-id="c1e03-119">The **XmlLinkedNode** class inherits from **XmlNode**.</span></span> <span data-ttu-id="c1e03-120">Der Zweck besteht im Überschreiben zweier Methoden von **XmlNode**: die **PreviousSibling**-Methode und die **NextSibling**-Methode.</span><span class="sxs-lookup"><span data-stu-id="c1e03-120">Its purpose is to override two methods from **XmlNode**: the **PreviousSibling** and **NextSibling** methods.</span></span> <span data-ttu-id="c1e03-121">Diese überschriebenen Methoden werden dann geerbt und von **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** und **XmlProcessingInstruction** verwendet. Dabei handelt es sich um Klassen, die vorherige und nächste gleichgeordnete Elemente aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c1e03-121">These overridden methods are then inherited and used by **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, and **XmlProcessingInstruction**, which are classes that have previous and next siblings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1e03-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1e03-122">See also</span></span>

- [<span data-ttu-id="c1e03-123">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="c1e03-123">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
