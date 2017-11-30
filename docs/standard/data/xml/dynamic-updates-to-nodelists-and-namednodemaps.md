---
title: Dynamische Updates von "NodeLists" und "NamedNodeMaps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 459d746ff278ac4affa0318c1fad0aeb6a73e560
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a><span data-ttu-id="23261-102">Dynamische Updates von "NodeLists" und "NamedNodeMaps"</span><span class="sxs-lookup"><span data-stu-id="23261-102">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>
<span data-ttu-id="23261-103">Da die **XmlNodeList** und **XmlNamedNodeMap** enthalten einen Satz von Knoten, noch das XML-Dokument in den Arbeitsspeicher geladen wird und verändert wird, das World Wide Web Consortium (W3C) gibt an, dass diese Objekte enthalten die Sätze von Knoten müssen dynamisch sein.</span><span class="sxs-lookup"><span data-stu-id="23261-103">Because the **XmlNodeList** and the **XmlNamedNodeMap** contain a set of nodes, yet the XML document is loaded into memory and is being modified, the World Wide Web Consortium (W3C) states that these objects that contain sets of nodes need to be dynamic.</span></span> <span data-ttu-id="23261-104">Anders ausgedrückt: Wenn das zugrunde liegende Dokument geändert wird, sollten sich auch die Daten in diesen beiden Objekten ändern.</span><span class="sxs-lookup"><span data-stu-id="23261-104">That is, if the underlying document changes, then the data in these two objects should change also.</span></span> <span data-ttu-id="23261-105">Aus diesem Grund haben eine **XmlNodeList** , enthält die untergeordneten Elemente eines bestimmten Elements (z. B. Element ist X), und fügen Sie Sie ein weiteres Element Q, um das Dokument unterhalb des Elements X hinzu. Die **XmlNodeList** sollten auch das neue Element Q der Teamprojektsammlung hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="23261-105">Therefore, if you have an **XmlNodeList** that contains all the child elements of a particular element (for example, element X), then you add an additional element, element Q, to the document under element X. The **XmlNodeList** should also have that new element Q added to its collection.</span></span> <span data-ttu-id="23261-106">Dies gilt auch umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="23261-106">The same is true in reverse.</span></span> <span data-ttu-id="23261-107">Wenn ein Knoten, um hinzugefügt wird die **XmlNodeList**, wird auch das zugrunde liegende Dokument aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="23261-107">If a node is added to the **XmlNodeList**, the underlying document is updated as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23261-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23261-108">See Also</span></span>  
 [<span data-ttu-id="23261-109">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="23261-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
