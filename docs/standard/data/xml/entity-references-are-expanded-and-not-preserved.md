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
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 069d3b94a0269917400e75fdbe975ec39dcfdb71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="entity-references-are-expanded-and-not-preserved"></a>Entitätsverweise werden erweitert und nicht beibehalten
Wenn der Entitätsverweis erweitert und durch den Text, der er steht, ersetzt die **XmlEntityReference** -Knoten nicht erstellt. Stattdessen wird die Entitätsdeklaration analysiert, und Knoten aus dem Inhalt der Deklaration erstellt werden an die Stelle von kopiert die **XmlEntityReference**. Aus diesem Grund in die `&publisher;` beispielsweise die `&publisher;` nicht gespeichert, sondern stattdessen ein **XmlText** Knoten erstellt.  
  
 ![Struktur der Aufrufstruktur erweitert](../../../../docs/standard/data/xml/media/xmlentityref-expanded-nodes.gif "Xmlentityref_expanded_nodes")  
Struktur für Entitätsverweise, die erweitert werden  
  
 Zeichenentitäten, z. B. `B` oder `<`, werden nicht beibehalten. Stattdessen werden sie stets erweitert und als Textknoten dargestellt.  
  
 Beibehalten **XmlEntityReference** Knoten und die untergeordneten Knoten des Entitätsverweises angefügt ist, legen Sie die **EntityHandling** flag **ExpandCharEntities**. Lassen Sie andernfalls die **EntityHandling** Flag den Standardwert, also **ExpandEntities**. In diesem Fall werden im DOM keine Entitätsverweisknoten angezeigt. Die Knoten werden durch die Knoten ersetzt, die Kopien der untergeordneten Knoten der Entitätsdeklaration sind.  
  
 Wenn Entitätsverweise nicht beibehalten werden, hat dies u. U. den Nebeneffekt, dass der Zielanwendung beim Speichern und Übergeben des Dokuments an eine andere Anwendung nicht bekannt ist, dass die Knoten durch einen Entitätsverweis erstellt wurden. Wenn die Entitätsverweise dagegen beibehalten werden, erkennt die Zielanwendung den Entitätsverweis und liest die untergeordneten Knoten. Es ist offensichtlich, dass die untergeordneten Knoten die Informationen darstellen, die sich in der Entitätsdeklaration befanden. Wenn Entitätsverweise beibehalten werden, hat das DOM theoretisch die folgende Struktur:  
  
 XmlElement: Verleger  
  
 XmlEntityReference: `&publisher;`  
  
 XmlText: Microsoft Press  
  
 Wenn Entitätsverweise im DOM erweitert werden (dies ist die Standardvorgehensweise), ergibt sich folgende Struktur:  
  
 XmlElement: Verleger  
  
 XmlText: Microsoft Press  
  
 Beachten Sie, dass der Entitätsverweisknoten nicht mehr vorhanden ist und nicht von die empfangende Anwendung, dass mitzuteilen kann die **XmlText** Knoten mit "Microsoft Press" aus einer Entitätsdeklaration erstellt wurde.  
  
 Wenn Sie einen Reader verwenden, die keine Entitäten auflösen kann die **laden** Methode löst eine Ausnahme aus, wenn einen Entitätsverweis gefunden wird.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
