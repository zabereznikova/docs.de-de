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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8a7abbb7344530ca993b8d07b774da17e6d0349b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a>Dynamische Updates von "NodeLists" und "NamedNodeMaps"
Da **XmlNodeList** und **XmlNamedNodeMap** eine Knotengruppe enthalten, aber das XML-Dokument in den Speicher geladen und verändert wird, müssen die vom World Wide Web Consortium (W3C) definierten Statusangaben, die diese Objekte mit den Knotengruppen haben können, dynamisch sein. Anders ausgedrückt: Wenn das zugrunde liegende Dokument geändert wird, sollten sich auch die Daten in diesen beiden Objekten ändern. Dies ist der Fall bei einer **XmlNodeList**, die alle untergeordneten Elemente eines bestimmten Elements enthält (z.B. Element X). In diesem Fall fügen Sie dem Dokument ein weiteres Element Q unterhalb des Elements X hinzu. Dieses neue Element Q sollte nun ebenfalls in der **XmlNodeList** enthalten sein. Dies gilt auch umgekehrt. Wenn der **XmlNodeList** ein Knoten hinzugefügt wird, wird auch das zugrunde liegende Dokument aktualisiert.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
