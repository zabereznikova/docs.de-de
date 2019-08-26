---
title: Entitätsverweise werden beibehalten
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e512f2077c2e6b9feba5024c4eabc2568357ecab
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965916"
---
# <a name="entity-references-are-preserved"></a>Entitätsverweise werden beibehalten
Wenn der Entitätsverweis nicht erweitert, sondern beibehalten wird, erstellt das XML-Dokumentobjektmodell (DOM) beim Auffinden eines Entitätsverweises einen **XmlEntityReference**-Knoten.  
  
 Bei dem folgenden XML-Code  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 erstellt das DOM einen **XmlEntityReference**-Knoten, wenn der `&publisher;`-Verweis gefunden wird. Der **XmlEntityReference**-Knoten enthält untergeordnete Knoten, die aus dem Inhalt der Entitätsdeklaration kopiert werden. Im vorherigen Codebeispiel befindet sich Text in der Entitätsdeklaration. Daher wird ein **XmlText**-Knoten als untergeordneter Knoten des Entitätsverweisknotens erstellt.  
  
 ![Baumstruktur für beibehaltene Entitätsverweise](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")  
Struktur für Entitätsverweise, die erhalten bleiben  
  
 Die untergeordneten Knoten von **XmlEntityReference** sind Kopien sämtlicher untergeordneter Knoten, die aus dem **XmlEntity**-Knoten erstellt wurden, als die Entitätsdeklaration gefunden wurde.  
  
> [!NOTE]
> Die aus **XmlEntity** kopierten Knoten stellen nicht immer exakte Kopien dar, nachdem sie unter dem Entitätsverweisknoten angeordnet wurden. Es können sich Namespaces im Gültigkeitsbereich des Entitätsverweisknotens befinden, die die endgültige Konfiguration der untergeordneten Knoten beeinflussen.  
  
 Standardmäßig werden allgemeine Entitäten wie `&abc;` beibehalten, und es werden immer **XmlEntityReference**-Knoten erstellt.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
