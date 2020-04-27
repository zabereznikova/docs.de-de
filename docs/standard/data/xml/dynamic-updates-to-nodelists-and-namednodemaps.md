---
title: Dynamische Updates von "NodeLists" und "NamedNodeMaps"
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
ms.openlocfilehash: 58dfde94c2f37b0a09ee795b9df20296c9f86da6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710972"
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a>Dynamische Updates von "NodeLists" und "NamedNodeMaps"
Da **XmlNodeList** und **XmlNamedNodeMap** eine Knotengruppe enthalten, aber das XML-Dokument in den Speicher geladen und verändert wird, müssen die vom World Wide Web Consortium (W3C) definierten Statusangaben, die diese Objekte mit den Knotengruppen haben können, dynamisch sein. Anders ausgedrückt: Wenn das zugrunde liegende Dokument geändert wird, sollten sich auch die Daten in diesen beiden Objekten ändern. Dies ist der Fall bei einer **XmlNodeList**, die alle untergeordneten Elemente eines bestimmten Elements enthält (z.B. Element X). In diesem Fall fügen Sie dem Dokument ein weiteres Element Q unterhalb des Elements X hinzu. Dieses neue Element Q sollte nun ebenfalls in der **XmlNodeList** enthalten sein. Dies gilt auch umgekehrt. Wenn der **XmlNodeList** ein Knoten hinzugefügt wird, wird auch das zugrunde liegende Dokument aktualisiert.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
