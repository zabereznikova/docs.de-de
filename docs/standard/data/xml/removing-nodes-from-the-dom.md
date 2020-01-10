---
title: Entfernen von Knoten aus dem DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 0a98e0ca-0555-45c1-ab69-0d8d20ca1abd
ms.openlocfilehash: a34b92abc59215c3cb2b94afd88e2e30405b4e9a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710309"
---
# <a name="removing-nodes-from-the-dom"></a>Entfernen von Knoten aus dem DOM
Verwenden Sie zum Entfernen eines bestimmten Knotens aus dem XML-DOM (Document Object Model) die <xref:System.Xml.XmlNode.RemoveChild%2A>-Methode. Beim Entfernen eines Knotens entfernt die Methode auch die zu diesem Knoten gehörende Teilstruktur, wenn es sich nicht um einen Endknoten handelt.  
  
 Wenn mehrere Knoten aus dem DOM entfernt werden sollen, entfernen Sie mit der <xref:System.Xml.XmlNode.RemoveAll%2A>-Methode alle untergeordneten Knoten und Attribute des aktuellen Knotens, falls vorhanden.  
  
 Wenn Sie mit einer <xref:System.Xml.XmlNamedNodeMap> arbeiten, können Sie einen Knoten mit der <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A>-Methode entfernen.  
  
 Weitere Informationen zum Entfernen von Attributen finden Sie unter [Entfernen von Attributen aus einem Elementknoten im DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
