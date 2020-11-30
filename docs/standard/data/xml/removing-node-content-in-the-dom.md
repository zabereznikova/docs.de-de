---
title: Entfernen von Knoteninhalt im Dokumentobjektmodell
ms.date: 03/30/2017
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
ms.openlocfilehash: d624e3eff3d61c2b8d312f370a4a11e3aede37e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721490"
---
# <a name="removing-node-content-in-the-dom"></a>Entfernen von Knoteninhalt im Dokumentobjektmodell

Bei Knotentypen, die von <xref:System.Xml.XmlCharacterData> erben (die Knotentypen <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace> und <xref:System.Xml.XmlSignificantWhitespace>), können Sie Zeichen mithilfe der <xref:System.Xml.XmlCharacterData.DeleteData%2A>-Methode entfernen. Diese löscht einen Bereich von Zeichen aus dem Knoten. Wenn Sie Inhalte vollständig löschen möchten, entfernen Sie den Knoten, in dem der betreffende Inhalt vorliegt. Wenn der Knoten erhalten bleiben soll, der Inhalt jedoch falsch ist, dann ändern Sie den Inhalt. Weitere Informationen zum Ändern des Inhalts eines Knotens finden Sie unter [Ändern von Knoten, Inhalten und Werten in einem XML-Dokument](modifying-nodes-content-and-values-in-an-xml-document.md).  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
