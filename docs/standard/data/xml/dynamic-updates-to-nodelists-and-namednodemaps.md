---
title: Dynamische Updates von "NodeLists" und "NamedNodeMaps"
ms.date: 03/30/2017
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
ms.openlocfilehash: 2e23507000a780246c129d470b525f19b8b3b9c9
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827658"
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a><span data-ttu-id="54e75-102">Dynamische Updates von "NodeLists" und "NamedNodeMaps"</span><span class="sxs-lookup"><span data-stu-id="54e75-102">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>
<span data-ttu-id="54e75-103">Da **XmlNodeList** und **XmlNamedNodeMap** eine Knotengruppe enthalten, aber das XML-Dokument in den Speicher geladen und verändert wird, müssen die vom World Wide Web Consortium (W3C) definierten Statusangaben, die diese Objekte mit den Knotengruppen haben können, dynamisch sein.</span><span class="sxs-lookup"><span data-stu-id="54e75-103">Because the **XmlNodeList** and the **XmlNamedNodeMap** contain a set of nodes, yet the XML document is loaded into memory and is being modified, the World Wide Web Consortium (W3C) states that these objects that contain sets of nodes need to be dynamic.</span></span> <span data-ttu-id="54e75-104">Anders ausgedrückt: Wenn das zugrunde liegende Dokument geändert wird, sollten sich auch die Daten in diesen beiden Objekten ändern.</span><span class="sxs-lookup"><span data-stu-id="54e75-104">That is, if the underlying document changes, then the data in these two objects should change also.</span></span> <span data-ttu-id="54e75-105">Dies ist der Fall bei einer **XmlNodeList**, die alle untergeordneten Elemente eines bestimmten Elements enthält (z.B. Element X). In diesem Fall fügen Sie dem Dokument ein weiteres Element Q unterhalb des Elements X hinzu. Dieses neue Element Q sollte nun ebenfalls in der **XmlNodeList** enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="54e75-105">Therefore, if you have an **XmlNodeList** that contains all the child elements of a particular element (for example, element X), then you add an additional element, element Q, to the document under element X. The **XmlNodeList** should also have that new element Q added to its collection.</span></span> <span data-ttu-id="54e75-106">Dies gilt auch umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="54e75-106">The same is true in reverse.</span></span> <span data-ttu-id="54e75-107">Wenn der **XmlNodeList** ein Knoten hinzugefügt wird, wird auch das zugrunde liegende Dokument aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="54e75-107">If a node is added to the **XmlNodeList**, the underlying document is updated as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e75-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54e75-108">See also</span></span>

- [<span data-ttu-id="54e75-109">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="54e75-109">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
