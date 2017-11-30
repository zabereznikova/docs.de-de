---
title: Hierarchie im XML-Dokumentobjektmodell (DOM)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6dec61860fba5815b1dae802d280e8df6628ab91
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-object-model-dom-hierarchy"></a><span data-ttu-id="48bd0-102">Hierarchie im XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="48bd0-102">XML Document Object Model (DOM) Hierarchy</span></span>
<span data-ttu-id="48bd0-103">In der folgenden Abbildung wird die Klassenhierarchie für das XML-Document Object Model (DOM – Dokumentobjektmodell) veranschaulicht; dabei ist der W3C-Name (World Wide Web Consortium) an den relevanten Stellen zusammen mit dem Klassennamen angegeben.</span><span class="sxs-lookup"><span data-stu-id="48bd0-103">The following illustration shows the class hierarchy for the XML Document Object Model (DOM), with the World Wide Web Consortium (W3C) name in parenthesis along with the class name where it is relevant.</span></span>  
  
 <span data-ttu-id="48bd0-104">![XML-Dokumentobjektmodell &#40; DOM &#41; Hierarchie](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="48bd0-104">![XML Document Object Model &#40;DOM&#41; hierarchy](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span></span>  
<span data-ttu-id="48bd0-105">Hierarchie im XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="48bd0-105">XML Document Object Model (DOM) hierarchy</span></span>  
  
 <span data-ttu-id="48bd0-106">Die folgenden Klassen erben nicht von der **XmlNode**:</span><span class="sxs-lookup"><span data-stu-id="48bd0-106">The following classes do not inherit from the **XmlNode**:</span></span>  
  
-   <span data-ttu-id="48bd0-107">**XmlImplementation**</span><span class="sxs-lookup"><span data-stu-id="48bd0-107">**XmlImplementation**</span></span>  
  
-   <span data-ttu-id="48bd0-108">**XmlNamedNodeMap**</span><span class="sxs-lookup"><span data-stu-id="48bd0-108">**XmlNamedNodeMap**</span></span>  
  
-   <span data-ttu-id="48bd0-109">**XmlNodeList**</span><span class="sxs-lookup"><span data-stu-id="48bd0-109">**XmlNodeList**</span></span>  
  
-   <span data-ttu-id="48bd0-110">**"XmlNodeChangedEventArgs"**</span><span class="sxs-lookup"><span data-stu-id="48bd0-110">**XmlNodeChangedEventArgs**</span></span>  
  
 <span data-ttu-id="48bd0-111">Die **XmlImplementation** Klasse wird verwendet, um ein XML-Dokument zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="48bd0-111">The **XmlImplementation** class is used to create an XML document.</span></span> <span data-ttu-id="48bd0-112">Weitere Informationen finden Sie unter [Erstellen eines XML-Dokuments](../../../../docs/standard/data/xml/xml-document-creation.md).</span><span class="sxs-lookup"><span data-stu-id="48bd0-112">For more information, see [XML Document Creation](../../../../docs/standard/data/xml/xml-document-creation.md).</span></span>  
  
 <span data-ttu-id="48bd0-113">Die **XmlNamedNodeMap** -Klasse behandelt eine ungeordnete Gruppe von Knoten.</span><span class="sxs-lookup"><span data-stu-id="48bd0-113">The **XmlNamedNodeMap** class handles an unordered set of nodes.</span></span> <span data-ttu-id="48bd0-114">Weitere Informationen finden Sie unter [Abrufen von ungeordneten Knoten anhand des Namens oder Indexes](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span><span class="sxs-lookup"><span data-stu-id="48bd0-114">For more information, see [Unordered Node Retrieval by Name or Index](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span></span>  
  
 <span data-ttu-id="48bd0-115">Die **XmlNodeList** -Klasse behandelt eine geordnete Liste von Knoten.</span><span class="sxs-lookup"><span data-stu-id="48bd0-115">The **XmlNodeList** class handles an ordered list of nodes.</span></span> <span data-ttu-id="48bd0-116">Weitere Informationen finden Sie unter [Abrufen von geordneten Knoten über einen Index](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span><span class="sxs-lookup"><span data-stu-id="48bd0-116">For more information, see [Ordered Node Retrieval by Index](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span></span>  
  
 <span data-ttu-id="48bd0-117">Die **"XmlNodeChangedEventArgs"** -Klasse behandelt Ereignishandler registriert, auf die **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="48bd0-117">The **XmlNodeChangedEventArgs** class handles event handlers registered on the **XmlDocument**.</span></span> <span data-ttu-id="48bd0-118">Weitere Informationen finden Sie unter [Ereignisbehandlung in einem XML-Dokument mit "XmlNodeChangedEventArgs"](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span><span class="sxs-lookup"><span data-stu-id="48bd0-118">For more information, see [Event Handling in an XML Document using the XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span></span>  
  
 <span data-ttu-id="48bd0-119">Die **XmlLinkedNode** Klasse erbt von **XmlNode**.</span><span class="sxs-lookup"><span data-stu-id="48bd0-119">The **XmlLinkedNode** class inherits from **XmlNode**.</span></span> <span data-ttu-id="48bd0-120">Ihr Zweck besteht im Überschreiben zweier Methoden von **XmlNode**: die **PreviousSibling** und **NextSibling** Methoden.</span><span class="sxs-lookup"><span data-stu-id="48bd0-120">Its purpose is to override two methods from **XmlNode**: the **PreviousSibling** and **NextSibling** methods.</span></span> <span data-ttu-id="48bd0-121">Diese überschriebenen Methoden werden dann geerbt und von verwendet **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, und **XmlProcessingInstruction**, wobei es sich um Klassen, die vorherige und nächste gleichgeordnete.</span><span class="sxs-lookup"><span data-stu-id="48bd0-121">These overridden methods are then inherited and used by **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, and **XmlProcessingInstruction**, which are classes that have previous and next siblings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48bd0-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48bd0-122">See Also</span></span>  
 [<span data-ttu-id="48bd0-123">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="48bd0-123">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
