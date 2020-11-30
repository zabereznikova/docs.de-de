---
title: Entitätsverweise werden beibehalten
ms.date: 03/30/2017
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
ms.openlocfilehash: 484eb5c874c6de05acae7dcd87a477c186b81482
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687267"
---
# <a name="entity-references-are-preserved"></a><span data-ttu-id="46d30-102">Entitätsverweise werden beibehalten</span><span class="sxs-lookup"><span data-stu-id="46d30-102">Entity References are Preserved</span></span>

<span data-ttu-id="46d30-103">Wenn der Entitätsverweis nicht erweitert, sondern beibehalten wird, erstellt das XML-Dokumentobjektmodell (DOM) beim Auffinden eines Entitätsverweises einen **XmlEntityReference**-Knoten.</span><span class="sxs-lookup"><span data-stu-id="46d30-103">When the entity reference is not expanded, but preserved, the XML Document Object Model (DOM) builds an **XmlEntityReference** node when it encounters an entity reference.</span></span>  
  
 <span data-ttu-id="46d30-104">Bei dem folgenden XML-Code</span><span class="sxs-lookup"><span data-stu-id="46d30-104">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="46d30-105">erstellt das DOM einen **XmlEntityReference**-Knoten, wenn der `&publisher;`-Verweis gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="46d30-105">the DOM builds an **XmlEntityReference** node when it encounters the `&publisher;` reference.</span></span> <span data-ttu-id="46d30-106">Der **XmlEntityReference**-Knoten enthält untergeordnete Knoten, die aus dem Inhalt der Entitätsdeklaration kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="46d30-106">The **XmlEntityReference** contains child nodes copied from the content in the entity declaration.</span></span> <span data-ttu-id="46d30-107">Im vorherigen Codebeispiel befindet sich Text in der Entitätsdeklaration. Daher wird ein **XmlText**-Knoten als untergeordneter Knoten des Entitätsverweisknotens erstellt.</span><span class="sxs-lookup"><span data-stu-id="46d30-107">The preceding code example contains text in the entity declaration, so an **XmlText** node is created as the child node of the entity reference node.</span></span>  
  
 <span data-ttu-id="46d30-108">![Struktur für beibehaltene Entitätsverweise](media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span><span class="sxs-lookup"><span data-stu-id="46d30-108">![Tree structure for preserved entity references](media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span></span>  
<span data-ttu-id="46d30-109">Struktur für Entitätsverweise, die erhalten bleiben</span><span class="sxs-lookup"><span data-stu-id="46d30-109">Tree structure for entity references that are preserved</span></span>  
  
 <span data-ttu-id="46d30-110">Die untergeordneten Knoten von **XmlEntityReference** sind Kopien sämtlicher untergeordneter Knoten, die aus dem **XmlEntity**-Knoten erstellt wurden, als die Entitätsdeklaration gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="46d30-110">The child nodes of the **XmlEntityReference** are copies of all the child nodes created from the **XmlEntity** node when the entity declaration was encountered.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="46d30-111">Die aus **XmlEntity** kopierten Knoten stellen nicht immer exakte Kopien dar, nachdem sie unter dem Entitätsverweisknoten angeordnet wurden.</span><span class="sxs-lookup"><span data-stu-id="46d30-111">The nodes copied from the **XmlEntity** are not always exact copies once placed under the entity reference node.</span></span> <span data-ttu-id="46d30-112">Es können sich Namespaces im Gültigkeitsbereich des Entitätsverweisknotens befinden, die die endgültige Konfiguration der untergeordneten Knoten beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="46d30-112">There can be namespaces that are in scope at the entity reference node, and that affects the final configuration of the child nodes.</span></span>  
  
 <span data-ttu-id="46d30-113">Standardmäßig werden allgemeine Entitäten wie `&abc;` beibehalten, und es werden immer **XmlEntityReference**-Knoten erstellt.</span><span class="sxs-lookup"><span data-stu-id="46d30-113">By default, general entities like `&abc;` are preserved and **XmlEntityReference** nodes always created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46d30-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46d30-114">See also</span></span>

- [<span data-ttu-id="46d30-115">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="46d30-115">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
