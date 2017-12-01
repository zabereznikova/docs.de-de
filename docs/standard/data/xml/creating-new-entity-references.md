---
title: "Erstellen von neuen Entitätsverweisen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a42f81b3-0403-4e34-b346-7d2129804e54
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 22e9b66f58275141cf9da154573ca43a0b90affc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-entity-references"></a>Erstellen von neuen Entitätsverweisen
Die **CreateEntityReference** Methode erstellt ein neues **XmlEntityReference** Knoten. Das Dokumentobjektmodell (DOM) überprüft, ob der Entitätsname, auf den verwiesen wird, bereits deklariert ist. Wenn die Tabelle enthält, die untergeordneten Knoten des **XmlEntityReference** Knoten aus dem Entitätsdeklarationsknoten kopiert werden. Wenn keine übereinstimmende Entitätsdeklaration vorhanden ist, wird eine leerer Textknoten als einziger untergeordneter Knoten des Entitätsdeklarationsknotens angefügt. Da die untergeordneten Knoten von der **XmlEntityReference** -Knotens Kopien anderer Knoten handelt, dieser untergeordneten Knoten sind schreibgeschützt und können nicht geändert werden.  
  
 Wenn die Knoten kopiert werden, kann ein Namespace im Gültigkeitsbereich an der Position des Entitätsverweises vorhanden sein. Dieser Namespace wirkt sich auf die Konfiguration der generierten Element- oder Attributknoten aus.  
  
> [!NOTE]
>  Das DOM fügt seinen untergeordneten Knoten der **EntityReference** nur beim Einfügen der **EntityReference** -Knoten in das Dokument. Neu erstellte **EntityReference** Knoten haben keine untergeordneten Knoten.  
  
 Obwohl die **XmlDataDocument** ist eine abgeleitete Klasse von der **XmlDocument**, die **XmlDataDocument** unterstützt nicht das Erstellen von Entitätsverweisen. Grund hierfür ist, **EntityReference** untergeordneten Elemente sind schreibgeschützt. Die untergeordneten Elemente ein **EntityReference** Knoten kann mehr als eine Region umfassen. In diesem Fall ein Teil einer Zeile verknüpft sind, mit der Region, die einen Teil einer **EntityReference** wird schreibgeschützt sein.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
