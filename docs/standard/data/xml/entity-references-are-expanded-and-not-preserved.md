---
title: "Entitätsverweise werden erweitert und nicht beibehalten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ffd97806-ab43-4538-8de2-5828bfbbde57
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 00b997865c614756ea5fd9567ded3baa469f4c62
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="entity-references-are-expanded-and-not-preserved"></a>Entitätsverweise werden erweitert und nicht beibehalten
Wenn der Entitätsverweis erweitert und durch den Text ersetzt wird, für den er steht, wird der **XmlEntityReference**-Knoten nicht erstellt. Stattdessen wird die Entitätsdeklaration analysiert, und die Knoten, die aus dem Inhalt der Deklaration erstellt werden, werden an die Stelle von **XmlEntityReference** kopiert. Daher wird im `&publisher;`-Beispiel `&publisher;` nicht gespeichert. Stattdessen wird ein **XmlText**-Knoten erstellt.  
  
 ![Erweiterte Baumstruktur](../../../../docs/standard/data/xml/media/xmlentityref-expanded-nodes.gif "xmlentityref_expanded_nodes")  
Struktur für Entitätsverweise, die erweitert werden  
  
 Zeichenentitäten, z. B. `B` oder `<`, werden nicht beibehalten. Stattdessen werden sie stets erweitert und als Textknoten dargestellt.  
  
 Damit **XmlEntityReference**-Knoten und die untergeordneten Knoten des damit verknüpften Entitätsverweises beibehalten werden, legen Sie das **EntityHandling**-Flag auf **ExpandCharEntities** fest. Andernfalls behalten Sie den Standardwert des **EntityHandling**-Flags (**ExpandEntities**) bei. In diesem Fall werden im DOM keine Entitätsverweisknoten angezeigt. Die Knoten werden durch die Knoten ersetzt, die Kopien der untergeordneten Knoten der Entitätsdeklaration sind.  
  
 Wenn Entitätsverweise nicht beibehalten werden, hat dies u. U. den Nebeneffekt, dass der Zielanwendung beim Speichern und Übergeben des Dokuments an eine andere Anwendung nicht bekannt ist, dass die Knoten durch einen Entitätsverweis erstellt wurden. Wenn die Entitätsverweise dagegen beibehalten werden, erkennt die Zielanwendung den Entitätsverweis und liest die untergeordneten Knoten. Es ist offensichtlich, dass die untergeordneten Knoten die Informationen darstellen, die sich in der Entitätsdeklaration befanden. Wenn Entitätsverweise beibehalten werden, hat das DOM theoretisch die folgende Struktur:  
  
 XmlElement: Verleger  
  
 XmlEntityReference: `&publisher;`  
  
 XmlText: Microsoft Press  
  
 Wenn Entitätsverweise im DOM erweitert werden (dies ist die Standardvorgehensweise), ergibt sich folgende Struktur:  
  
 XmlElement: Verleger  
  
 XmlText: Microsoft Press  
  
 Beachten Sie, dass der Entitätsverweisknoten nun nicht mehr vorhanden ist, und die Zielanwendung nicht erkennen kann, dass der **XmlText**-Knoten mit „Microsoft Press“ aus einer Entitätsdeklaration erstellt wurde.  
  
 Wenn Sie einen Reader verwenden, der keine Entitäten auflösen kann, löst die **Load**-Methode beim Auffinden eines Entitätsverweises eine Ausnahme aus.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
