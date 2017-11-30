---
title: "Entitätsverweise werden beibehalten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 770c714e8f5942ea733c417ae9b06f69e4acf1a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="entity-references-are-preserved"></a>Entitätsverweise werden beibehalten
Wenn der Entitätsverweis nicht erweitert, sondern beibehalten wird, erstellt das XML-Dokument (DOKUMENTOBJEKTMODELL) ein **XmlEntityReference** Knoten, wenn es ein Entitätsverweis gefunden wird.  
  
 Bei dem folgenden XML-Code  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 erstellt das DOM ein **XmlEntityReference** Knoten, wenn er erkennt die `&publisher;` Verweis. Die **XmlEntityReference** enthält untergeordnete Knoten, die aus dem Inhalt der Entitätsdeklaration kopiert. Im vorangehenden Codebeispiel enthält Text in der Entitätsdeklaration, daher ein **XmlText** -Knoten als untergeordneter Knoten des Entitätsverweisknotens erstellt.  
  
 ![Struktur für beibehaltene Entitätsverweise](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "Xmlentityref_notexpanded_nodes")  
Struktur für Entitätsverweise, die erhalten bleiben  
  
 Die untergeordneten Knoten des der **XmlEntityReference** sind Kopien aller untergeordneten Knoten, erstellt aus den **XmlEntity** Knoten, wenn die Entitätsdeklaration gefunden wurde.  
  
> [!NOTE]
>  Die Knoten kopiert, aus der **XmlEntity** sind nicht immer exakte Kopien, die einmal unter dem Entitätsverweisknoten platziert. Es können sich Namespaces im Gültigkeitsbereich des Entitätsverweisknotens befinden, die die endgültige Konfiguration der untergeordneten Knoten beeinflussen.  
  
 Standardmäßig werden allgemeine Entitäten wie `&abc;` werden beibehalten und **XmlEntityReference** Knoten immer erstellt.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
