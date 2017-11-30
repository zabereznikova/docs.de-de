---
title: "Entitätsverweise werden beibehalten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 770c714e8f5942ea733c417ae9b06f69e4acf1a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="entity-references-are-preserved"></a><span data-ttu-id="1d486-102">Entitätsverweise werden beibehalten</span><span class="sxs-lookup"><span data-stu-id="1d486-102">Entity References are Preserved</span></span>
<span data-ttu-id="1d486-103">Wenn der Entitätsverweis nicht erweitert, sondern beibehalten wird, erstellt das XML-Dokument (DOKUMENTOBJEKTMODELL) ein **XmlEntityReference** Knoten, wenn es ein Entitätsverweis gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="1d486-103">When the entity reference is not expanded, but preserved, the XML Document Object Model (DOM) builds an **XmlEntityReference** node when it encounters an entity reference.</span></span>  
  
 <span data-ttu-id="1d486-104">Bei dem folgenden XML-Code</span><span class="sxs-lookup"><span data-stu-id="1d486-104">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="1d486-105">erstellt das DOM ein **XmlEntityReference** Knoten, wenn er erkennt die `&publisher;` Verweis.</span><span class="sxs-lookup"><span data-stu-id="1d486-105">the DOM builds an **XmlEntityReference** node when it encounters the `&publisher;` reference.</span></span> <span data-ttu-id="1d486-106">Die **XmlEntityReference** enthält untergeordnete Knoten, die aus dem Inhalt der Entitätsdeklaration kopiert.</span><span class="sxs-lookup"><span data-stu-id="1d486-106">The **XmlEntityReference** contains child nodes copied from the content in the entity declaration.</span></span> <span data-ttu-id="1d486-107">Im vorangehenden Codebeispiel enthält Text in der Entitätsdeklaration, daher ein **XmlText** -Knoten als untergeordneter Knoten des Entitätsverweisknotens erstellt.</span><span class="sxs-lookup"><span data-stu-id="1d486-107">The preceding code example contains text in the entity declaration, so an **XmlText** node is created as the child node of the entity reference node.</span></span>  
  
 <span data-ttu-id="1d486-108">![Struktur für beibehaltene Entitätsverweise](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "Xmlentityref_notexpanded_nodes")</span><span class="sxs-lookup"><span data-stu-id="1d486-108">![Tree structure for preserved entity references](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span></span>  
<span data-ttu-id="1d486-109">Struktur für Entitätsverweise, die erhalten bleiben</span><span class="sxs-lookup"><span data-stu-id="1d486-109">Tree structure for entity references that are preserved</span></span>  
  
 <span data-ttu-id="1d486-110">Die untergeordneten Knoten des der **XmlEntityReference** sind Kopien aller untergeordneten Knoten, erstellt aus den **XmlEntity** Knoten, wenn die Entitätsdeklaration gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="1d486-110">The child nodes of the **XmlEntityReference** are copies of all the child nodes created from the **XmlEntity** node when the entity declaration was encountered.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d486-111">Die Knoten kopiert, aus der **XmlEntity** sind nicht immer exakte Kopien, die einmal unter dem Entitätsverweisknoten platziert.</span><span class="sxs-lookup"><span data-stu-id="1d486-111">The nodes copied from the **XmlEntity** are not always exact copies once placed under the entity reference node.</span></span> <span data-ttu-id="1d486-112">Es können sich Namespaces im Gültigkeitsbereich des Entitätsverweisknotens befinden, die die endgültige Konfiguration der untergeordneten Knoten beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="1d486-112">There can be namespaces that are in scope at the entity reference node, and that affects the final configuration of the child nodes.</span></span>  
  
 <span data-ttu-id="1d486-113">Standardmäßig werden allgemeine Entitäten wie `&abc;` werden beibehalten und **XmlEntityReference** Knoten immer erstellt.</span><span class="sxs-lookup"><span data-stu-id="1d486-113">By default, general entities like `&abc;` are preserved and **XmlEntityReference** nodes always created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d486-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d486-114">See Also</span></span>  
 [<span data-ttu-id="1d486-115">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="1d486-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
