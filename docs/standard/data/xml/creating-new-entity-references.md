---
title: "Erstellen von neuen Entitätsverweisen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a42f81b3-0403-4e34-b346-7d2129804e54
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 22e9b66f58275141cf9da154573ca43a0b90affc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-entity-references"></a><span data-ttu-id="58e56-102">Erstellen von neuen Entitätsverweisen</span><span class="sxs-lookup"><span data-stu-id="58e56-102">Creating New Entity References</span></span>
<span data-ttu-id="58e56-103">Die **CreateEntityReference** Methode erstellt ein neues **XmlEntityReference** Knoten.</span><span class="sxs-lookup"><span data-stu-id="58e56-103">The **CreateEntityReference** method creates a new **XmlEntityReference** node.</span></span> <span data-ttu-id="58e56-104">Das Dokumentobjektmodell (DOM) überprüft, ob der Entitätsname, auf den verwiesen wird, bereits deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="58e56-104">The XML Document Object Model (DOM) looks to see if the entity name being referenced has already been declared.</span></span> <span data-ttu-id="58e56-105">Wenn die Tabelle enthält, die untergeordneten Knoten des **XmlEntityReference** Knoten aus dem Entitätsdeklarationsknoten kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="58e56-105">If it has, the child nodes of **XmlEntityReference** node are copied from the entity declaration node.</span></span> <span data-ttu-id="58e56-106">Wenn keine übereinstimmende Entitätsdeklaration vorhanden ist, wird eine leerer Textknoten als einziger untergeordneter Knoten des Entitätsdeklarationsknotens angefügt.</span><span class="sxs-lookup"><span data-stu-id="58e56-106">If there is no entity declaration that matches, an empty text node is attached as the only child of the entity reference node.</span></span> <span data-ttu-id="58e56-107">Da die untergeordneten Knoten von der **XmlEntityReference** -Knotens Kopien anderer Knoten handelt, dieser untergeordneten Knoten sind schreibgeschützt und können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="58e56-107">Because the child nodes of the **XmlEntityReference** node are copies of other nodes, these child nodes are read-only and cannot be modified.</span></span>  
  
 <span data-ttu-id="58e56-108">Wenn die Knoten kopiert werden, kann ein Namespace im Gültigkeitsbereich an der Position des Entitätsverweises vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="58e56-108">When the nodes are copied, there may be a namespace in scope at the point of the entity reference.</span></span> <span data-ttu-id="58e56-109">Dieser Namespace wirkt sich auf die Konfiguration der generierten Element- oder Attributknoten aus.</span><span class="sxs-lookup"><span data-stu-id="58e56-109">This namespace affects the configuration of any element or attribute nodes generated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58e56-110">Das DOM fügt seinen untergeordneten Knoten der **EntityReference** nur beim Einfügen der **EntityReference** -Knoten in das Dokument.</span><span class="sxs-lookup"><span data-stu-id="58e56-110">The DOM adds child nodes to the **EntityReference** only when you insert the **EntityReference** node to the document.</span></span> <span data-ttu-id="58e56-111">Neu erstellte **EntityReference** Knoten haben keine untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="58e56-111">Newly created **EntityReference** nodes have no child nodes.</span></span>  
  
 <span data-ttu-id="58e56-112">Obwohl die **XmlDataDocument** ist eine abgeleitete Klasse von der **XmlDocument**, die **XmlDataDocument** unterstützt nicht das Erstellen von Entitätsverweisen.</span><span class="sxs-lookup"><span data-stu-id="58e56-112">Even though the **XmlDataDocument** is a derived class of the **XmlDocument**, the **XmlDataDocument** does not support the creation of entity references.</span></span> <span data-ttu-id="58e56-113">Grund hierfür ist, **EntityReference** untergeordneten Elemente sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="58e56-113">This is because **EntityReference** children are read-only.</span></span> <span data-ttu-id="58e56-114">Die untergeordneten Elemente ein **EntityReference** Knoten kann mehr als eine Region umfassen.</span><span class="sxs-lookup"><span data-stu-id="58e56-114">The children of an **EntityReference** node can span more than one region.</span></span> <span data-ttu-id="58e56-115">In diesem Fall ein Teil einer Zeile verknüpft sind, mit der Region, die einen Teil einer **EntityReference** wird schreibgeschützt sein.</span><span class="sxs-lookup"><span data-stu-id="58e56-115">In this case, part of a row associated with the region that contains a part of an **EntityReference** will be read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58e56-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58e56-116">See Also</span></span>  
 [<span data-ttu-id="58e56-117">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="58e56-117">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
