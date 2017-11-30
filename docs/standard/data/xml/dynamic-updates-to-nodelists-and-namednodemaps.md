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
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a>Dynamische Updates von "NodeLists" und "NamedNodeMaps"
Da die **XmlNodeList** und **XmlNamedNodeMap** enthalten einen Satz von Knoten, noch das XML-Dokument in den Arbeitsspeicher geladen wird und verändert wird, das World Wide Web Consortium (W3C) gibt an, dass diese Objekte enthalten die Sätze von Knoten müssen dynamisch sein. Anders ausgedrückt: Wenn das zugrunde liegende Dokument geändert wird, sollten sich auch die Daten in diesen beiden Objekten ändern. Aus diesem Grund haben eine **XmlNodeList** , enthält die untergeordneten Elemente eines bestimmten Elements (z. B. Element ist X), und fügen Sie Sie ein weiteres Element Q, um das Dokument unterhalb des Elements X hinzu. Die **XmlNodeList** sollten auch das neue Element Q der Teamprojektsammlung hinzugefügt haben. Dies gilt auch umgekehrt. Wenn ein Knoten, um hinzugefügt wird die **XmlNodeList**, wird auch das zugrunde liegende Dokument aktualisiert.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
