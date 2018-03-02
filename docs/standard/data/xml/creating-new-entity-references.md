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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 76093fbe7095c2aae7caa69147f6181c292ca734
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="creating-new-entity-references"></a><span data-ttu-id="c6398-102">Erstellen von neuen Entitätsverweisen</span><span class="sxs-lookup"><span data-stu-id="c6398-102">Creating New Entity References</span></span>
<span data-ttu-id="c6398-103">Mit der **CreateEntityReference**-Methode wird ein neuer **XmlEntityReference**-Knoten erstellt.</span><span class="sxs-lookup"><span data-stu-id="c6398-103">The **CreateEntityReference** method creates a new **XmlEntityReference** node.</span></span> <span data-ttu-id="c6398-104">Das Dokumentobjektmodell (DOM) überprüft, ob der Entitätsname, auf den verwiesen wird, bereits deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="c6398-104">The XML Document Object Model (DOM) looks to see if the entity name being referenced has already been declared.</span></span> <span data-ttu-id="c6398-105">Wenn dies der Fall ist, wird eine Kopie der untergeordneten Knoten des **XmlEntityReference**-Knotens aus dem Entitätsdeklarationsknoten erstellt.</span><span class="sxs-lookup"><span data-stu-id="c6398-105">If it has, the child nodes of **XmlEntityReference** node are copied from the entity declaration node.</span></span> <span data-ttu-id="c6398-106">Wenn keine übereinstimmende Entitätsdeklaration vorhanden ist, wird eine leerer Textknoten als einziger untergeordneter Knoten des Entitätsdeklarationsknotens angefügt.</span><span class="sxs-lookup"><span data-stu-id="c6398-106">If there is no entity declaration that matches, an empty text node is attached as the only child of the entity reference node.</span></span> <span data-ttu-id="c6398-107">Da es sich bei den untergeordneten Knoten des **XmlEntityReference**-Knotens um Kopien anderer Knoten handelt, sind diese Knoten schreibgeschützt und können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c6398-107">Because the child nodes of the **XmlEntityReference** node are copies of other nodes, these child nodes are read-only and cannot be modified.</span></span>  
  
 <span data-ttu-id="c6398-108">Wenn die Knoten kopiert werden, kann ein Namespace im Gültigkeitsbereich an der Position des Entitätsverweises vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="c6398-108">When the nodes are copied, there may be a namespace in scope at the point of the entity reference.</span></span> <span data-ttu-id="c6398-109">Dieser Namespace wirkt sich auf die Konfiguration der generierten Element- oder Attributknoten aus.</span><span class="sxs-lookup"><span data-stu-id="c6398-109">This namespace affects the configuration of any element or attribute nodes generated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6398-110">Das DOM fügt **EntityReference** nur dann untergeordnete Knoten hinzu, wenn Sie den **EntityReference**-Knoten in das Dokument einfügen.</span><span class="sxs-lookup"><span data-stu-id="c6398-110">The DOM adds child nodes to the **EntityReference** only when you insert the **EntityReference** node to the document.</span></span> <span data-ttu-id="c6398-111">Neu erstellte **EntityReference**-Knoten weisen keine untergeordneten Knoten auf.</span><span class="sxs-lookup"><span data-stu-id="c6398-111">Newly created **EntityReference** nodes have no child nodes.</span></span>  
  
 <span data-ttu-id="c6398-112">Obwohl es sich bei **XmlDataDocument** um eine von **XmlDocument** abgeleitete Klasse handelt, wird das Erstellen von Entitätsverweisen von **XmlDataDocument** nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c6398-112">Even though the **XmlDataDocument** is a derived class of the **XmlDocument**, the **XmlDataDocument** does not support the creation of entity references.</span></span> <span data-ttu-id="c6398-113">Dies liegt daran, dass untergeordnete Elemente von **EntityReference** schreibgeschützt sind.</span><span class="sxs-lookup"><span data-stu-id="c6398-113">This is because **EntityReference** children are read-only.</span></span> <span data-ttu-id="c6398-114">Die untergeordneten Knoten eines **EntityReference**-Knotens können mehr als eine Region umfassen.</span><span class="sxs-lookup"><span data-stu-id="c6398-114">The children of an **EntityReference** node can span more than one region.</span></span> <span data-ttu-id="c6398-115">In diesem Fall ist der Teil einer Zeile schreibgeschützt, der mit der Region mit einem Teil einer **EntityReference** verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="c6398-115">In this case, part of a row associated with the region that contains a part of an **EntityReference** will be read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6398-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6398-116">See Also</span></span>  
 [<span data-ttu-id="c6398-117">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="c6398-117">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
