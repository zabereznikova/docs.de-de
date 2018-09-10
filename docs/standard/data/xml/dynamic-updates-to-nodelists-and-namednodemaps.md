---
title: Dynamische Updates von "NodeLists" und "NamedNodeMaps"
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9f56ba8711988f2f7d743dc4ff7b69272e2642a2
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44207407"
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a><span data-ttu-id="c95cf-102">Dynamische Updates von "NodeLists" und "NamedNodeMaps"</span><span class="sxs-lookup"><span data-stu-id="c95cf-102">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>
<span data-ttu-id="c95cf-103">Da **XmlNodeList** und **XmlNamedNodeMap** eine Knotengruppe enthalten, aber das XML-Dokument in den Speicher geladen und verändert wird, müssen die vom World Wide Web Consortium (W3C) definierten Statusangaben, die diese Objekte mit den Knotengruppen haben können, dynamisch sein.</span><span class="sxs-lookup"><span data-stu-id="c95cf-103">Because the **XmlNodeList** and the **XmlNamedNodeMap** contain a set of nodes, yet the XML document is loaded into memory and is being modified, the World Wide Web Consortium (W3C) states that these objects that contain sets of nodes need to be dynamic.</span></span> <span data-ttu-id="c95cf-104">Anders ausgedrückt: Wenn das zugrunde liegende Dokument geändert wird, sollten sich auch die Daten in diesen beiden Objekten ändern.</span><span class="sxs-lookup"><span data-stu-id="c95cf-104">That is, if the underlying document changes, then the data in these two objects should change also.</span></span> <span data-ttu-id="c95cf-105">Dies ist der Fall bei einer **XmlNodeList**, die alle untergeordneten Elemente eines bestimmten Elements enthält (z.B. Element X). In diesem Fall fügen Sie dem Dokument ein weiteres Element Q unterhalb des Elements X hinzu. Dieses neue Element Q sollte nun ebenfalls in der **XmlNodeList** enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="c95cf-105">Therefore, if you have an **XmlNodeList** that contains all the child elements of a particular element (for example, element X), then you add an additional element, element Q, to the document under element X. The **XmlNodeList** should also have that new element Q added to its collection.</span></span> <span data-ttu-id="c95cf-106">Dies gilt auch umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="c95cf-106">The same is true in reverse.</span></span> <span data-ttu-id="c95cf-107">Wenn der **XmlNodeList** ein Knoten hinzugefügt wird, wird auch das zugrunde liegende Dokument aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c95cf-107">If a node is added to the **XmlNodeList**, the underlying document is updated as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c95cf-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c95cf-108">See also</span></span>

- [<span data-ttu-id="c95cf-109">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="c95cf-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
