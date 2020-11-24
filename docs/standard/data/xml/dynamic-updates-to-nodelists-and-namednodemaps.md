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
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a>Dynamische Updates von "NodeLists" und "NamedNodeMaps"
Da **XmlNodeList** und **XmlNamedNodeMap** eine Knotengruppe enthalten, aber das XML-Dokument in den Speicher geladen und verändert wird, müssen die vom World Wide Web Consortium (W3C) definierten Statusangaben, die diese Objekte mit den Knotengruppen haben können, dynamisch sein. Anders ausgedrückt: Wenn das zugrunde liegende Dokument geändert wird, sollten sich auch die Daten in diesen beiden Objekten ändern. Dies ist der Fall bei einer **XmlNodeList**, die alle untergeordneten Elemente eines bestimmten Elements enthält (z.B. Element X). In diesem Fall fügen Sie dem Dokument ein weiteres Element Q unterhalb des Elements X hinzu. Dieses neue Element Q sollte nun ebenfalls in der **XmlNodeList** enthalten sein. Dies gilt auch umgekehrt. Wenn der **XmlNodeList** ein Knoten hinzugefügt wird, wird auch das zugrunde liegende Dokument aktualisiert.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
