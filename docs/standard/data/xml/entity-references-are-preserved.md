---
title: Entitätsverweise werden beibehalten
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
ms.openlocfilehash: e4c902df1b0cd2bd9e97b49c0ec1d10df91ef1c7
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290343"
---
# <a name="entity-references-are-preserved"></a>Entitätsverweise werden beibehalten
Wenn der Entitätsverweis nicht erweitert, sondern beibehalten wird, erstellt das XML-Dokumentobjektmodell (DOM) beim Auffinden eines Entitätsverweises einen **XmlEntityReference**-Knoten.  
  
 Bei dem folgenden XML-Code  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 erstellt das DOM einen **XmlEntityReference**-Knoten, wenn der `&publisher;`-Verweis gefunden wird. Der **XmlEntityReference**-Knoten enthält untergeordnete Knoten, die aus dem Inhalt der Entitätsdeklaration kopiert werden. Im vorherigen Codebeispiel befindet sich Text in der Entitätsdeklaration. Daher wird ein **XmlText**-Knoten als untergeordneter Knoten des Entitätsverweisknotens erstellt.  
  
 ![Struktur für beibehaltene Entitätsverweise](media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")  
Struktur für Entitätsverweise, die erhalten bleiben  
  
 Die untergeordneten Knoten von **XmlEntityReference** sind Kopien sämtlicher untergeordneter Knoten, die aus dem **XmlEntity**-Knoten erstellt wurden, als die Entitätsdeklaration gefunden wurde.  
  
> [!NOTE]
> Die aus **XmlEntity** kopierten Knoten stellen nicht immer exakte Kopien dar, nachdem sie unter dem Entitätsverweisknoten angeordnet wurden. Es können sich Namespaces im Gültigkeitsbereich des Entitätsverweisknotens befinden, die die endgültige Konfiguration der untergeordneten Knoten beeinflussen.  
  
 Standardmäßig werden allgemeine Entitäten wie `&abc;` beibehalten, und es werden immer **XmlEntityReference**-Knoten erstellt.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
